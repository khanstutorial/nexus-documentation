# /maintenance/update

## Updates an existing maintenance entry
Updates an existing maintenance entry with new information. Note that the "valid" and "created_at" fields of the entry cannot be modified.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "_id" : 0,
        "start_datetime" : "06/12/2022 11:46:51 AM",
        "stop_datetime" : "06/14/2022 07:39:58 PM",
        "author" : "Rashed Rifat",
        "affected_servers" : ["Shadow", "Nexus", "Ark"],
        "description" : "Routine maintenance and performance tuning"
    }
    resp = requests.post("http://127.0.0.1:5000/maintenance/update, data=data)
    print(resp.text)

NOTE: All of the fields above DO NOT NEED TO BE INCLUDED for the request to succeed! Only include the fields you want to change.

### Request Data Parameters

**_id** (*int*) <br>
    The ID of the entry in the maintenance database. The reason for the beginning underscore is because that is MongoDB's default ID field.

**start_datetime** (*str*) <br>
    The date and time the maintenance period should start, in zero-padded "MM/DD/YYYY HH:MM:SS AM/PM" format.

**stop_datetime** (*str*) <br>
    The date and time the maintenance period should stop, in zero-padded "MM/DD/YYYY HH:MM:SS AM/PM" format.

**author** (*str*) <br>
    The person making the create request.

**affected_servers** (*list*) <br>
    A list of the servers affected by the maintenance.

**description** (*str*) <br>
    The reason for the maintenance and any other important information regarding the maintenance.

<hr> <br>

## Response
    
    SUCCESSFUL update: record with id 0 now has new values : {
        "_id": 0,
        "start_datetime": 1655740011.0,
        "stop_datetime": 1655897998.0,
        "author": "Rashed Rifat",
        "affected_servers": [
            "Shadow",
            "Nexus",
            "Ark"
        ],
        "description": "Routine maintenance and performance tuning"
    }

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.