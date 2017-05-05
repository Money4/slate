# Get or create session

> `POST http://domain.com/im_chat/api/get_or_create_session`

```
Example response
```

```python
{
    "jsonrpc": "2.0",
    "id": null,
    "result": {
        "create_date": "2017-02-02 07:56:00",
        "uuid": "91e03d34-1929-4a02-9486-4c3e708686b3",
        "with_documents:": true,
        "status": "active",
        "state": "open",
        "is_group": false,
        "is_read": true,
        "groups": [],
        "docs:":
        [
            {
                "doc_model": "res.partner",
                "doc_id": 25,
                "id": 9
            }
        ],
        "users":
        [
            {
                "im_status": "away",
                "id": 5,
                "name": "Lucid Lynx",
                "partner_id":
                (
                    6,
                    "Lucid Lynx"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "222", 
                    "create_date": "2017-04-10 07:46:21", 
                    "id": 191
                }
            },
            {
                "im_status": "away",
                "id": 6,
                "name": "Oneiric Ocelot",
                "partner_id":
                (
                    7,
                    "Oneiric Ocelot"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "444", 
                    "create_date": "2017-04-10 07:50:40", 
                    "id": 201
                }
            }
        ]
    }
}
```

### HTTP Request

`POST http://domain.com/im_chat/api/get_or_create_session`

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
user_to | number | Required | ID of user
doc_id | string | Optional | ID of document
doc_model | string | Optional | document's model

### Returns
Dictionary with data about session.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
uuid | session uuid | *
create_date | date of session creating | *
users | list of users | *
state | state of session | 'open', 'folded' or 'closed'


# Get or create session with group

> `POST http://domain.com/im_chat/api/get_or_create_session_group`

```
Example response
```

```python
{
    "jsonrpc": "2.0",
    "id": null,
    "result":
    {
        "create_date": "2017-02-02 07:56:00",
        "uuid": "91e03d34-1929-4a02-9486-4c3e708686b3",
        "with_documents": true,
        "status": "active",
        "state": "open",
        "is_group": true,
        "is_read": true,
        "groups":
        [
            {
                "id": 3,
                "name": "News"
            }
        ],
        "docs:":
        [
            {
                "doc_model": "res.partner",
                "doc_id": 25,
                "id": 9
            }
        ],
        "users":
        [
            {
                "im_status": "away",
                "id": 5,
                "name": "Lucid Lynx",
                "partner_id":
                (
                    6,
                    "Lucid Lynx"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "222", 
                    "create_date": "2017-04-10 07:46:21", 
                    "id": 191
                }
            },
            {
                "im_status": "away",
                "id": 6,
                "name": "Oneiric Ocelot",
                "partner_id":
                (
                    7,
                    "Oneiric Ocelot"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "444", 
                    "create_date": "2017-04-10 07:50:40", 
                    "id": 201
                }
            }
        ]
    }
}
```

### HTTP Request

`POST http://domain.com/im_chat/api/get_or_create_session_group`

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
group | number | Required | ID of group
doc_id | string | Optional | ID of document
doc_model | string | Optional | document's model

### Returns
Dictionary with data about session.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
uuid | session uuid | *
create_date | date of session creating | *
users | list of users | *
state | state of session | 'open', 'folded' or 'closed'

# Get sessions

> `POST http://domain.com/im_chat/api/get_sessions`

```
Example response
```

```python
[
    {
        "create_date": "2017-02-02 07:56:00",
        "uuid": "91e03d34-1929-4a02-9486-4c3e708686b3",
        "with_documents": true,
        "status": "active",
        "state": "open",
        "is_group": false,
        "is_read": true,
        "groups": [],
        "docs:":
        [
            {
                "doc_model": "res.partner",
                "doc_id": 25,
                "id": 9
            }
        ],
        "users":
        [
            {
                "im_status": "away",
                "id": 5,
                "name": "Lucid Lynx",
                "partner_id":
                (
                    6,
                    "Lucid Lynx"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "222", 
                    "create_date": "2017-04-10 07:46:21", 
                    "id": 191
                }
            },
            {
                "im_status": "away",
                "id": 6,
                "name": "Oneiric Ocelot",
                "partner_id":
                (
                    7,
                    "Oneiric Ocelot"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "444", 
                    "create_date": "2017-04-10 07:50:40", 
                    "id": 201
                }
            }
        ]
    }
]
```

### HTTP Request

`POST http://domain.com/im_chat/api/get_sessions`

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
user_to | number | Optional | ID of user
doc_id | string | Optional | ID of document
doc_model | string | Optional | document's model
state | string | Optional | state of session

### Returns
List with dictionaries with data about sessions.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
uuid | session uuid | *
create_date | date of session creating | *
users | list of users | *
groups | list of groups | *
docs | list of documents | *
state | state of session | 'open', 'folded' or 'closed'
status | status of chat | 'active', 'favorite' or 'archive'
with_documents | attribute of chat with document | true or false
is_group | attribute of group session | true or false
is_read | attribute of read chat | true or false

# Get sessions with group

> `POST http://domain.com/im_chat/api/get_sessions_group`

```
Example response
```

```python
[
    {
        "create_date": "2017-02-02 07:56:00",
        "uuid": "91e03d34-1929-4a02-9486-4c3e708686b3",
        "with_documents": true,
        "status": "active",
        "state": "open",
        "is_group": true,
        "is_read": true,
        "groups":
        [
            {
                "id": 3,
                "name": "News"
            }
        ],
        "docs:":
        [
            {
                "doc_model": "res.partner",
                "doc_id": 25,
                "id": 9
            }
        ],
        "users":
        [
            {
                "im_status": "away",
                "id": 5,
                "name": "Lucid Lynx",
                "partner_id":
                (
                    6,
                    "Lucid Lynx"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "222", 
                    "create_date": "2017-04-10 07:46:21", 
                    "id": 191
                }
            },
            {
                "im_status": "away",
                "id": 6,
                "name": "Oneiric Ocelot",
                "partner_id":
                (
                    7,
                    "Oneiric Ocelot"
                ),
                "last_message": 
                {
                    "type": "message",
                    "message": "444", 
                    "create_date": "2017-04-10 07:50:40", 
                    "id": 201
                }
            }
        ]
    }
]
```

### HTTP Request

`POST http://domain.com/im_chat/api/get_sessions_group`

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
group | number | Optional | ID of group
doc_id | string | Optional | ID of document
doc_model | string | Optional | document's model
state | string | Optional | state of session

### Returns
List with dictionaries with data about sessions.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
uuid | session uuid | *
create_date | date of session creating | *
users | list of users | *
groups | list of groups | *
docs | list of documents | *
state | state of session | 'open', 'folded' or 'closed'
status | status of chat | 'active', 'favorite' or 'archive'
with_documents | attribute of chat with document | true or false
is_group | attribute of group session | true or false
is_read | attribute of read chat | true or false

# Get all users

> `POST http://domain.com/im_chat/api/user_chat_ab/get_all_users`

```
Example response
```

```json
[
    {
        "im_status": "offline", 
        "id": 5, 
        "name": "odoo"
    },
    {
        "im_status": "offline", 
        "id": 239, 
        "name": "Ivan"
    },
    {
        "im_status": "offline", 
        "id": 330, 
        "name": "Test1"
    }
]
```

### HTTP Request

`POST http://domain.com/im_chat/api/user_chat_ab/get_all_users`

Get all users without users from address book of current user

### Returns
List with dictionaries with data about users.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
im_status | chat status | 'online', 'offline' or 'away'
id | user id | *
name | user name | *

# Get users from book

> `POST http://domain.com/im_chat/api/user_chat_ab/get_users_from_book`

```
Example response
```

```json
[
    {
        "im_status": "offline", 
        "id": 5, 
        "name": "odoo"
    }
]
```

### HTTP Request

`POST http://domain.com/im_chat/api/user_chat_ab/get_users_from_book`

Get all users from address book of current user

### Returns
List with dictionaries with data about users.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
im_status | chat status | 'online', 'offline' or 'away'
id | user id | *
name | user name | *

# Add users in book

> `POST http://domain.com/im_chat/api/user_chat_ab/add_users`

```
Successful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "success"
    }
}
```

```
Unsuccessful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "error",
        "message": "user_ids is not list"
    }
}
```

### HTTP Request

`POST http://domain.com/im_chat/api/user_chat_ab/add_users`

Add user in address book of current user

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
user_ids | list of user ids | Required | User IDs

### Returns
Dictionary with status of operation.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
status | status of operation | 'success' or 'error'
message | error message | *

# Remove users from book

> `POST http://domain.com/im_chat/api/user_chat_ab/remove_users`

```
Successful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "success"
    }
}
```

```
Unsuccessful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "error",
        "message": "user_ids is not list"
    }
}
```

### HTTP Request

`POST http://domain.com/im_chat/api/user_chat_ab/remove_users`

Remove user from address book of current user

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
user_ids | list of user ids | Required | User IDs

### Returns
Dictionary with status of operation.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
status | status of operation | 'success' or 'error'
message | error message | *

# Add partner in book

> `POST http://domain.com/im_chat/api/user_chat_ab/add_partner`

```
Successful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "success"
    }
}
```

```
Unsuccessful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "error",
        "message": "input parameters are not valid"
    }
}
```

### HTTP Request

`POST http://domain.com/im_chat/api/user_chat_ab/add_partner`

Add partner in address book of current partner

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
parent_partner_id | number | Required | ID of owner of address book 
child_partner_id | number | Required | Added partner ID in book

### Returns
Dictionary with status of operation.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
status | status of operation | 'success' or 'error'
message | error message | *

# Post message

> `POST http://domain.com/im_chat/post`

### HTTP Request

`POST http://domain.com/im_chat/post`

Post message in chat

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
uuid | string | Required | Session UUID 
message_type | string | Required | Type of message
message_content | string | Required | Content of message

### Returns
ID of message.

Parameter | Description | Possible values 
--------- | ----------- | -----------
message_id | ID of posted message | *

# Chat initialization

> `POST http://domain.com/im_chat/api/init`

```
Example response
```

```json
[
    {
        "last_message":
        {
            "type": "message",
            "create_date": "2017-03-30 09:15:07",
            "id": 118
        },
        "im_status": "away",
        "id": 8,
        "name": "Russian Support",
        "email": "russian@support.ru",
        "partner_id": 9
    }
]
```

### HTTP Request

`POST http://domain.com/im_chat/api/init`

Initialize chat for current user and returns his contact list. Method supports filtration 
of contact list by name and quantity of output names.

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
name | string | Required | search name of user field
limit | number | Optional | quantity of output names in contact list

### Returns
List with dictionaries with data about users in contact list.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
last_message | last message data | *
im_status | status of chat member | 'online', 'offline' or 'away'
id | user's ID | *
name | name of user | *
email | user's email | *
partner_id | partner's ID | *

# Get history of messages

> `POST http://domain.com/im_chat/api/history`

```
Example response
```

```python
[
    {
        "create_date": "2017-03-30 09:15:07", 
        "to_id": 
        (
          15, 
          "37474642-60c7-4315-8575-0497ad23ac12"
        ), 
        "message": "888", 
        "type": "message", 
        "id": 118, 
        "from_id": 
        (
            8, 
            "Russian Support"
        ),
        "from_partner_id": 
        (
            9, 
            "Russian Support"
        )
    }, 
    {
        "create_date": "2017-03-30 09:14:47", 
        "to_id": 
        (
            15, 
            "37474642-60c7-4315-8575-0497ad23ac12"
        ), 
        "message": "999", 
        "type": "message", 
        "id": 113, 
        "from_id": 
        (
            5, 
            "Lucid Lynx"
        ),
        "from_partner_id": 
        (
            6, 
            "Lucid Lynx"
        )
    },  
    {
        "create_date": "2017-03-30 09:14:45", 
        "to_id": 
        (
            15, 
            "37474642-60c7-4315-8575-0497ad23ac12"
        ), 
        "message": "555", 
        "type": "message", 
        "id": 108, 
        "from_id": 
        (
            5, 
            "Lucid Lynx"
        ),
        "from_partner_id": 
        (
            6, 
            "Lucid Lynx"
        )
    }, 
    {
        "create_date": "2017-03-29 10:50:10", 
        "to_id": 
        (
            15, 
            "37474642-60c7-4315-8575-0497ad23ac12"
        ), 
        "message": "111", 
        "type": "message", 
        "id": 98, 
        "from_id": 
        (
            5, 
            "Lucid Lynx"
        ),
        "from_partner_id": 
        (
            6, 
            "Lucid Lynx"
        )
    }
]
```

### HTTP Request

`POST http://domain.com/im_chat/api/history`

Method that is used for getting history of messages in current session. 
Method supports filtration of messages in output list by ID of last message 
and quantity of messages in output list. Method also changes is_read parameter 
of current session for current user in True value.

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
uuid | string | Required | session UUID
last_ID | number | Optional | ID of last message
limit | number | Optional | quantity of messages in output list

### Returns
List with dictionaries with data about messages.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
create_date | date of message creating | *
to_id | data about session | *
message | text of message | *
type | type of message | 'message', 'money4_chat_attach_msg' or 'typing'
id | message ID | *
from_id | data about sender (user data) | *
from_partner_id | data about sender (partner data) | *


# Change session status

> `POST http://domain.com/im_chat/api/change_session_status`

```
Successful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "success"
    }
}
```

```
Unsuccessful response
```

```json
{
    "jsonrpc": "2.0", 
    "id": null, 
    "result": 
    {
        "status": "error",
        "field": "uuid",
        "message": "Session does not exist"
    }
}
```

### HTTP Request

`POST http://domain.com/im_chat/api/change_session_status`

Method that is used for changing status of current user's session.

### Arguments

Parameter | Type | Required | Description
--------- | ----------- | ----------- | -----------
uuid | string | Optional | session UUID
new_status | string | Optional | new status of session

### Returns
Dictionary with status of operation and optional error message.

Contains fields:

Parameter | Description | Possible values 
--------- | ----------- | -----------
status | status of operation | 'success' or 'error'
field | field, which contains error | *
message | error message | *

