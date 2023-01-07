# /auth/check

## Checks if an encrypted JWT is valid
This endpoint checks if an encrypted JWT is valid or not. If it is, it sends back an encrypted JSON with the true secret specified in the JWT. If it is not, it sends back either 401 or the false secret with the JSON.

## Request

    import requests, json

    data = json.dumps({
        "msg" : "+hSSYYF/WFTwvzUd4U587dR1zT9G2HPv/6bFn6OqqL6ODeMCe+MPZwtCAW7tNjO1IDjzhFbAUN17MsW4LdPNI5jDNqQJCrjjBRZ5HotQXu6ggZguBXF5UFEUCV0aa8U22NUpBw47avX7GPZPJpAmNyE0XuhnLS+EMBB1AIdJoJ7MeOmCVRKCDMms5bJ7/Mv+xCN2P5g0f35a3cMtadCd/CtBmAe99L3JUeTKmvbAdlmXUjn+lu/Hj0Ab/LoUa7YN"
        "true_secret" : "true",
        "false_secret" : "false"
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/auth/check, data=data)
    print(resp.text)

### Request Data Parameters

**msg** (*str*) <br>
    The encoded JWT.

**true_secret** (*str*) <br>
    A secret to be sent back when the authentication succeeds.

**false_secret** (*str*) <br>
    A secret to be sent back when the authentication fails.

<hr> <br>

## Response

    {
        "auth_status" : "true",
        "exp" : 2023-01-07 15:09:45
    }


NOTE: This is the *decoded* JSON! You must decrypt the response data to get this.