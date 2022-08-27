# /logins/update

## Updates an existing logins entry
Updates an existing logins entry with new information.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "_id" : 0,
        "name" : "Timothy Louie",
        "classes" : [
            "Class 1",
            "Class 2"
        ],
        "num_accesses" : 1,
        "times" : [
            "08/27/2022 12:00:00"
        ],
        "ip" : "123.45.67.890"
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/logins/update, data=data)
    print(resp.text)

NOTE: Only "_id" needs to be in data. All of the fields above DO NOT NEED TO BE INCLUDED for the request to succeed! Only include the fields you want to change.

### Request Data Parameters

**_id** (*int*) - REQUIRED FIELD <br>
    The ID of the entry in the logins database. The reason for the beginning underscore is because that is MongoDB's default ID field.

**name** (*str*) <br>
    The new name of the student.

**classes** (*list*) <br>
    The new list of classes the student accessed.

**num_accesses** (*int*) <br>
    The new number of times the student accessed a class.

**times** (*list*) <br>
    A list of strings in "MM/DD/YYYY HH:MM:SS" format, representing the dates and times the student accessed a class.

**ip** (*str*) <br>
    The new IP address of the student.

<hr> <br>

## Response
    
    SUCCESSFUL update: record with id 0 now has new values : {
        "name" : "Timothy Louie",
        "classes" : [
            "Class 1",
            "Class 2"
        ],
        "num_accesses" : 1,
        "times" : [
            "08/27/2022 12:00:00"
        ],
        "ip" : "123.45.67.890"
    }

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.