# /gazette/update

## Updates an existing gazette entry
Updates an existing gazette entry with new information. Note that the "valid" and "created_at" fields of the entry cannot be modified.
<br><br>

## Request

    import requests, json

    data = json.dumps({
        "_id" : 0,
        "title" : "Sample title",
        "author" : "Timothy Louie",
        "content" : "Lorem ipsum dolor sit amet"
    })
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/gazette/update, data=data)
    print(resp.text)

NOTE: Only "_id" needs to be in data. All of the fields above DO NOT NEED TO BE INCLUDED for the request to succeed! Only include the fields you want to change.

### Request Data Parameters

**_id** (*int*) - REQUIRED FIELD <br>
    The ID of the entry in the gazette database. The reason for the beginning underscore is because that is MongoDB's default ID field.

**title** (*str*) <br>
    The new title of the article.

**author** (*str*) <br>
    The new author of the article.

**content** (*str*) <br>
    The new content of the article.

<hr> <br>

## Response
    
    SUCCESSFUL update: record with id 0 now has new values : {
        "title" : "Sample title",
        "author" : "Timothy Louie",
        "content" : "Lorem ipsum dolor sit amet"
        "created_datetime" : 123456789
    }

If a failure has occured, this message will not be shown. Instead a 500 error will be returned displaying the reason for the failure.