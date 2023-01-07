# /students/read

## Returns all students
Returns a list of JSONs sorted by name, where each JSON is data about a student's login activity.
<br><br>

## Request

    import requests

    resp = requests.get("https://whale-app-5ml2e.ondigitalocean.app/students/read)
    print(resp.text)

<hr> <br>

## Response
    [
        "_id" : 0    
        "name" : "Timothy Louie",
        "password" : hashed and salted password string here,
        "roles": [
            "Tech Team Member"
        ]
    ]