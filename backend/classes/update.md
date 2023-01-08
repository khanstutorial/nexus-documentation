# /classes/update

## Updates an existing classes entry
Updates an existing classes entry with new information.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "_id" : 0,
        "name" : "Grade 3 Common-Core Class 2
        "group" : "Grade 3 Common-Core",
        "zoom_url" : "https://khanstutorial.zoom.us/j/86050581704?pwd=dmYzUWZ4dmx6b3crWDB4NnduR0M2UT09",
        "department" : "Common-Core",
        "num_students" : 10
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/classes/update, data=data)
    print(resp.text)

NOTE: Only "_id" needs to be in data. All of the fields above DO NOT NEED TO BE INCLUDED for the request to succeed! Only include the fields you want to change.

### Request Data Parameters

**_id** (*int*) - REQUIRED FIELD <br>
    The ID of the entry in the classes database. The reason for the beginning underscore is because that is MongoDB's default ID field.

**name** (*str*) <br>
    The name of the class.

**group** (*str*) <br>
    The name of the Google Group the class belongs to.

**zoom_url** (*str*) <br>
    The Zoom URL of the class.

**department** (*str*) <br>
    The department the class belongs to (Common-Core, GPA, Pre-SHSAT, SAT, Grade 7/8 SHSAT)

**num_students** (*int*) <br>
    The current number of students in the class.

<hr> <br>

## Response
    
    SUCCESSFUL update: record with id 0 in classes collection now has new values : {
        "name" : "Grade 3 Common-Core Class 2",
        "group": "Grade 3 Common-Core",
        "zoom_url": "https://khanstutorial.zoom.us/j/86050581704?pwd=dmYzUWZ4dmx6b3crWDB4NnduR0M2UT09",
        "department": "Common-Core",
        "num_students": 10
    }
If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.