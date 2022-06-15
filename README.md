# mailchimp

# [mailchimp] lists相關的restful api
1-1. 可獲得list_id<br>
@app.route('/lists', methods=['GET'])
https://flask-mailchimp.herokuapp.com/lists

1-2. 可刪除指定的list (請自行置換<list_id>--如何得知list_id？請見第1-1.點)
@app.route('/lists/<list_id>', methods=['DELETE'])
curl -X DELETE https://flask-mailchimp.herokuapp.com/lists/<list_id>

1-3. 可增加一個新的list （由於我的mailchimp是免費版，所以至多只能建立一個list）
@app.route('/lists', methods=['POST'])
curl -d '{"name":"newlist"}' -H "Content-Type: application/json" -X POST https://flask-mailchimp.herokuapp.com/lists

# [mailchimp] members相關的restful api
2. 可在指定的list中 (請自行置換<list_id>--如何得知list_id？請見第1-1.點)   ，新增一個「訂閱戶的email」 （請自行置換<email>，如下下行中的「chenhsinju@gmail.com」）
@app.route('/lists/<list_id>/members', methods=['POST'])
curl -d '{"email_address":"chenhsinju@gmail.com", "status":"subscribed"}' -H "Content-Type: application/json" -X POST https://flask-mailchimp.herokuapp.com/lists/<list_id>/members



# 參考資料
Mailchimp API Docs: https://developer.mailchimp.com/documentation/mailchimp/reference/overview/
Mailchimp Marketing API Quick Start： https://mailchimp.com/developer/marketing/guides/quick-start/
Mailchimp Website: http://mailchimp.com/
