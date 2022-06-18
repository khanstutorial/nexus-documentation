# /maintenance/read

## Returns all future maintenance entries
Returns a string of all maintenance entries in the database that have not yet occured. If there are no future maintenance periods, the API will return an empty string.
<br><br>

## Request

    import requests

    resp = requests.get("http://127.0.0.1:5000/maintenance/read)
    print(resp.text)

<hr> <br>

## Response
    
    {      
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
    }