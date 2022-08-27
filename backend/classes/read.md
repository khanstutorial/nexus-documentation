# /classes/read

## Returns all classes
Returns a list of JSONs, where each JSON is data about a class.
<br><br>

## Request

    import requests

    resp = requests.get("https://whale-app-5ml2e.ondigitalocean.app/classes/read)
    print(resp.text)

<hr> <br>

## Response
    [
        {      
            "name" : "Grade 3 Common-Core Class 1",
            "group" : "Grade 3 Common-Core",
            "zoom_url" : "https://khanstutorial.zoom.us/j/86050581704?pwd=dmYzUWZ4dmx6b3crWDB4NnduR0M2UT09",
            "department" : "Common-Core",
            "num_students" : 20
        }
    ]