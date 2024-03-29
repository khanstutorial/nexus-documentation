# /students/create

## Creates an entry in the students database
Adds an entry into the students MongoDB database, where entries represents information about Shadow students.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "name" : "Timothy Louie",
        "password" : "password",
        "roles": [
            "Tech Team Member"
        ]
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/students/create, data=data)
    print(resp.text)

### Request Data Parameters

**name** (*str*) <br>
    The name of the user.

**password** (*str*) <br>
    The password of the user.

**roles** (*list*) <br>
    The roles the user has.

<hr> <br>

## Response
    
    SUCCESSFUL creation: Record {  
        "_id" : 0    
        "name" : "Timothy Louie",
        "password" : hashed and salted password string here,
        "roles": [
            "Tech Team Member"
        ]
    } has been inserted into the students collection in the shadow database.

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.