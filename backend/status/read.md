# /status/read

## Returns all status entries
Returns a JSON of all the servers and their statuses, with keys in human-readable dates and values are 0 (if active) and 1 (if not)
<br><br>

## Request

    import requests

    resp = requests.get("https://whale-app-5ml2e.ondigitalocean.app/status/read)
    print(resp.text)

<hr> <br>

## Response
    
    {
        "Magenta": {
            "description": "Production server for KT API",
            "status": {
                "08/27/22 05:00:00": 1
            }
        },
        "Violet": {
            "description": "Development server for KT API",
            "status": {
                "08/27/22 05:00:00": 0
            }
        }
    }