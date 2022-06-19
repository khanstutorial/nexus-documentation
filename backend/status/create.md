# /status/create

## Updates the status of the servers
Pings each server and puts a 0 for today's entry if the ping succeeded, otherwise puts a 1.
<br><br>

## Request

    import requests
    resp = requests.post("http://127.0.0.1:5000/status/create)
    print(resp.text)

## Response

    SUCCESSFUL non-update of system status: server Magenta has status 1 for date 2022-06-19 and does not need to be updated
    SUCCESSFUL non-update of system status: server Violet has status 1 for date 2022-06-19 and does not need to be updated