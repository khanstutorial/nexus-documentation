# /classes/update

## Updates an existing classes entry
Updates an existing classes entry with new information.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "name" : "Grade 3 Common-Core Class 1",
        "new_vals" : {
            "name' : "Grade 3 Common-Core Class 2
            "group" : "Grade 3 Common-Core",
            "zoom_url" : "https://khanstutorial.zoom.us/j/86050581704?pwd=dmYzUWZ4dmx6b3crWDB4NnduR0M2UT09",
            "department" : "Common-Core",
            "num_students" : 10
        }
    }
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/classes/update, data=data)
    print(resp.text)

NOTE: All of the fields in "new_vals" above DO NOT NEED TO BE INCLUDED for the request to succeed! Only include the fields you want to change.

### Request Data Parameters

**name** (*str*) <br>
    The name of the class whose data you want to change.

**new_vals** (*json*) <br>
    A JSON of data you want to change in the class. The keys should be a subset of {"name", "group", "zoom_url", "department", "num_students}.

<hr> <br>

## Response
    
    SUCCESSFUL update: record with name Grade 3 Common-Core Class 1 in classes collection now has new values : {
        "name" : "Grade 3 Common-Core Class 2",
        "group": "Grade 3 Common-Core",
        "zoom_url": "https://khanstutorial.zoom.us/j/86050581704?pwd=dmYzUWZ4dmx6b3crWDB4NnduR0M2UT09",
        "department": "Common-Core",
        "num_students": 10
    }
If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.