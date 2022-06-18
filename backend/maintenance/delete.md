# /maintenance/delete

## Deletes an entry in the maintenance database
For an existing entry in the database, sets its "valid" field to false.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "_id" : 0
    }
    resp = requests.post("http://127.0.0.1:5000/maintenance/delete, data=data)
    print(resp.text)

### Request Data Parameters

**_id** (*str*) <br>
    The ID of the entry in the maintenance database.

<hr> <br>

## Response

    SUCCESSFUL deletion: record with id 0

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.