# /gazette/create

## Creates an entry in the gazette database
Adds an entry into the gazette MongoDB database, where entries represents information about a gazette article.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "title" : "Sample title",
        "author" : "Timothy Louie",
        "content" : "Lorem ipsum dolor sit amet"
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/gazette/create, data=data)
    print(resp.text)

### Request Data Parameters

**title** (*str*) <br>
    The title of the article.

**author** (*str*) <br>
    The author of the article

**content** (*str*) <br>
    The content of the article.

<hr> <br>

## Response
    
    SUCCESSFUL creation: Record {      
        "title" : "Sample title",
        "author" : "Timothy Louie",
        "content" : "Lorem ipsum dolor sit amet"
        "created_datetime" : 123456789
    } has been inserted into the gazette collection in the shadow database.

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.