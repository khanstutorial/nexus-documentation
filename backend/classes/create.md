# /classes/create

## Creates an entry in the classes database
Adds an entry into the classes MongoDB database, where entries represents information about each class.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "name" : "Grade 3 Common-Core Class 1",
        "group" : "Grade 3 Common-Core",
        "zoom_url" : "https://khanstutorial.zoom.us/j/86050581704?pwd=dmYzUWZ4dmx6b3crWDB4NnduR0M2UT09",
        "department" : "Common-Core",
        "num_students" : 20
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/classes/create, data=data)
    print(resp.text)

### Request Data Parameters

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
    
    SUCCESSFUL creation: Record {      
        "name" : "Grade 3 Common-Core Class 1",
        "group" : "Grade 3 Common-Core",
        "zoom_url" : "https://khanstutorial.zoom.us/j/86050581704?pwd=dmYzUWZ4dmx6b3crWDB4NnduR0M2UT09",
        "department" : "Common-Core",
        "num_students" : 20
    } has been inserted into the classes collection in the shadow database.

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.