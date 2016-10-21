
# API

## POST /sales/sms
|DESCRIPTION      | Send *Text*  *From* (user)  *To* (source)           |
|-----------------|------------------------------------------------------------|
|QUERY            | none|
|BODY             | "From=917417361066&To=917417361067&Text=What is your name?"|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | none|



## GET /sales/sms
|DESCRIPTION      | Get messages between *source* and  *user*            |
|-----------------|------------------------------------------------------------|
|QUERY            | "?source=917417361067&user=917417361066"|
|BODY             | none|
|RESPONSE STATUS  | 200|
|RESPONSE BODY    | [{source:917417361066,user:917417361066,text:'name',flow:'RX',createdAt:'2016-10-21T11:58:43.151Z'}]|
