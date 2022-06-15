# mailchimp

# [mailchimp] lists相關的restful api
1-1. 可獲得list_id <br>
@app.route('/lists', methods=['GET']) <br>
https://flask-mailchimp.herokuapp.com/lists <br>

1-2. 可刪除指定的list (請自行置換<list_id>--如何得知list_id？請見第1-1.點) <br>
@app.route('/lists/<list_id>', methods=['DELETE']) <br>
curl -X DELETE https://flask-mailchimp.herokuapp.com/lists/<list_id> <br>

1-3. 可增加一個新的list （由於我的mailchimp是免費版，所以至多只能建立一個list） <br>
@app.route('/lists', methods=['POST']) <br>
curl -d '{"name":"newlist"}' -H "Content-Type: application/json" -X POST https://flask-mailchimp.herokuapp.com/lists <br>

# [mailchimp] members相關的restful api
2. 可在指定的list中 (請自行置換<list_id>--如何得知list_id？請見第1-1.點)   ，新增一個「訂閱戶的email」 （請自行置換<email>，如下下行中的「chenhsinju@gmail.com」） <br>
@app.route('/lists/<list_id>/members', methods=['POST']) <br>
curl -d '{"email_address":"chenhsinju@gmail.com", "status":"subscribed"}' -H "Content-Type: application/json" -X POST https://flask-mailchimp.herokuapp.com/lists/<list_id>/members <br>



# 參考資料
Mailchimp API Docs: https://developer.mailchimp.com/documentation/mailchimp/reference/overview/ <br>
Mailchimp Marketing API Quick Start： https://mailchimp.com/developer/marketing/guides/quick-start/ <br>
Mailchimp Website: http://mailchimp.com/ <br>
