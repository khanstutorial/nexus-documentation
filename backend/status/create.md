# /status/create

## Creates an entry in the status database
Adds a timestamp and 0/1 key-value pair to the status field in all entries in the status database, which repesents whether or not each server is responsive or not.
<br><br>

## Request

    import requests, json

    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/status/create)
    print(resp.text)

<hr> <br>

## Response
    
    SUCCESSFUL creation of system status: server Magenta (www.apiv2.ktlearning.com) now has status 1 for date 2022-08-27
    SUCCESSFUL creation of system status: server Violet (www.devapi.ktlearning.com) now has status 0 for date 2022-08-27

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.