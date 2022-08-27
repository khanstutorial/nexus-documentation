# /users/update

## Updates an existing users entry
Updates an existing users entry with new information.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "_id" : 0,   
        "name" : "Timothy Louie",
        "password" : hashed and salted password string here,
        "roles": [
            "Tech Team Member"
        ]
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/users/update, data=data)
    print(resp.text)

NOTE: Only "_id" needs to be in data. All of the fields above DO NOT NEED TO BE INCLUDED for the request to succeed! Only include the fields you want to change.

### Request Data Parameters

**_id** (*int*) - REQUIRED FIELD <br>
    The ID of the entry in the users database. The reason for the beginning underscore is because that is MongoDB's default ID field.

**name** (*str*) <br>
    The new name of the user.

**password** (*str*) <br>
    The new password of the user.

**roles** (*list*) <br>
    The new roles the user has.

<hr> <br>

## Response
    
    SUCCESSFUL update: record with id 0 now has new values : {  
        "name" : "Timothy Louie",
        "password" : hashed and salted password string here,
        "roles": [
            "Tech Team Member"
        ]
    }

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.