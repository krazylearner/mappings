
# API

## POST /sales/sms
|DESCRIPTION      | Send *Text*  *From* (user)  *To* (source)                  |
|-----------------|------------------------------------------------------------|
|QUERY            | none|
|BODY             | "From=917417361066&To=917417361067&Text=What is your name?"|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | none|



## GET /sales/sms
|DESCRIPTION      | Get messages between *source* and  *user*                  |
|-----------------|------------------------------------------------------------|
|QUERY            | "?source=917417361067&user=917417361066"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{source:917417361066,user:917417361066,text:'name',flow:'RX',createdAt:'2016-10-21T11:58:43.151Z'}]|


## GET /sales/rejectcall
|DESCRIPTION      | Rejects an incoming call                                   |
|-----------------|------------------------------------------------------------|
|QUERY            | none|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | \<Response>\<Hangup reason="rejected"/>\</Response> |


## GET /sales/sms/rx
|DESCRIPTION      | Get count of RX sms grouped by source number between a date range (unix timestamp)    |
|-----------------|------------------------------------------------------------|
|QUERY            | "?from=1477051856741&to=1477051956741"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{\_id:917417361067,count :4}] |


## GET /sales/sms/tx
|DESCRIPTION      | Get count of TX sms grouped by source number between a date range (unix timestamp)    |
|-----------------|------------------------------------------------------------|
|QUERY            | "?from=1477051856741&to=1477051956741"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{\_id:917417361067,count :3}] |


## GET /sales/sms/triggers
|DESCRIPTION      | Get count of triggers fired grouped by trigger name between a date range (unix timestamp)    |
|-----------------|------------------------------------------------------------|
|QUERY            | "?from=1477051856741&to=1477051956741"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{\_id:'AskBotEmail',count :1}] |


## GET /sales/sms/logs
|DESCRIPTION      | Get logs between a date range (unix timestamp)    |
|-----------------|------------------------------------------------------------|
|QUERY            | "?from=1477051856741&to=1477051956741"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{"source":"917417361067","user":"917417361066","flow":"RX","level":"info","message":"what is your name?","timestamp":"2016-10-21T11:36:56.191Z"}] |


## GET /sales/sms/search
|DESCRIPTION      | Search logs for a query  |
|-----------------|------------------------------------------------------------|
|QUERY            | "?q=hello"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{"source":"917417361067","user":"917417361066","flow":"RX","level":"info","message":"hello your name?","timestamp":"2016-10-21T11:36:56.191Z"}] |



## GET /sales/sms/messages
|DESCRIPTION      | Get all messages between two numbers                  |
|-----------------|------------------------------------------------------------|
|QUERY            | "?from=917417361067&to=917417361066"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{source:917417361066,user:917417361066,text:'what is your name ?',flow:'RX',createdAt:'2016-10-21T11:58:43.151Z'}]|
