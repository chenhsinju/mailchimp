# mailchimp

curl -d '{"name":"newlist"}' -H "Content-Type: application/json" -X POST https://flask-mailchimp.herokuapp.com/lists

curl -d '{"email_address":"chenhsinju@gmail.com", "status":"subscribed"}' -H "Content-Type: application/json" -X POST https://flask-mailchimp.herokuapp.com/lists/5fc653fc87/members
