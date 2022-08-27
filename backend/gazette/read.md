# /gazette/read

## Returns all future gazette entries
Returns the latest gazette entry.
<br><br>

## Request

    import requests

    resp = requests.get("https://whale-app-5ml2e.ondigitalocean.app/gazette/read)
    print(resp.text)

<hr> <br>

## Response
    
    {      
        "title" : "Sample title",
        "author" : "Timothy Louie",
        "content" : "Lorem ipsum dolor sit amet"
        "created_datetime" : 123456789
    }