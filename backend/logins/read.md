# /logins/read

## Returns all logins
Returns a list of JSONs sorted by name, where each JSON is data about a student's login activity.
<br><br>

## Request

    import requests

    resp = requests.get("https://whale-app-5ml2e.ondigitalocean.app/logins/read)
    print(resp.text)

<hr> <br>

## Response
    [
        {      
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
    ]