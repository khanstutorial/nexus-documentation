# /maintenance/create

## Creates an entry in the maintenance database
Adds an entry into the maintenance MongoDB database, where entries represents information about a maintenance period on any KT servers.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "start_datetime" : "06/12/2022 11:46:51 AM",
        "stop_datetime" : "06/14/2022 07:39:58 PM",
        "author" : "Rashed Rifat",
        "affected_servers" : ["Shadow", "Nexus", "Ark"],
        "description" : "Routine maintenance and performance tuning"
    }
    resp = requests.post("http://127.0.0.1:5000/maintenance/create, data=data)
    print(resp.text)

### Request Data Parameters

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
    
    SUCCESSFUL creation: Record {      
        "start_datetime": 1655048811.0,
        "stop_datetime": 1655206798.0, 
        "author": "Rashed Rifat",      
        "affected_servers": [
            "Shadow",
            "Nexus",
            "Ark"
        ],
        "description": "Routine maintenance and performance tuning",
        "_id": 2,
        "valid": true,
    "created_at": 1655580491.0
    } has been inserted into the maintenance collection in the shadow database.

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.