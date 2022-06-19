# /status/read

## Reads the status of the servers
Returns a JSON object of each server, with a status array of max length 30 where each element in the array represents whether a server failed for that day - 1 if a ping failed, and 0 otherwise.
<br><br>

## Request

    import requests
    resp = requests.get("http://127.0.0.1:5000/status/read)
    print(resp.text)

## Response

    {
        "Magenta": {
            "description": "Production server for KT API",
            "status": [
                1
            ]
        },
        "Violet": {
            "description": "Development server for KT API",
            "status": [
                1
            ]
        }
    }