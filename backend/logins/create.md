# /logins/create

## Creates an entry in the logins database
Adds an entry into the logins MongoDB database, where entries represents information about a student's login activity.
<br><br>

## Request

    import requests, json

    data = json.dumps({
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
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/logins/create, data=data)
    print(resp.text)

### Request Data Parameters

**name** (*str*) <br>
    The name of the student.

**classes** (*list*) <br>
    The list of classes the student accessed.

**num_accesses** (*int*) <br>
    The number of times the student accessed a class.

**times** (*list*) <br>
    A list of strings in "MM/DD/YYYY HH:MM:SS" format, representing the dates and times the student accessed a class.

**ip** (*str*) <br>
    The IP address of the student.

<hr> <br>

## Response
    
    SUCCESSFUL creation: Record {      
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
    } has been inserted into the logins collection in the shadow database.

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.