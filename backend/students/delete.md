# /students/delete

## Deletes an entry in the students database
From its _id value, deletes that entry in the database.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "_id" : 0
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/students/delete, data=data)
    print(resp.text)

### Request Data Parameters

**_id** (*str*) <br>
    The ID of the entry in the students database.

<hr> <br>

## Response

    SUCCESSFUL deletion: record with id 0

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.