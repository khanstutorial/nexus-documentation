# /util/upload

## Uploads a file to the backend
<br><br>

## Request

    import requests, json

    files = [File('file1.txt'), File('file2.txt')]
    resp = requests.post("https://whale-app-5ml2e.ondigitalocean.app/students/delete, files=files)
    print(resp.text)

### Request Data Parameters

**files** (*list*) <br>
    List of File objects.

<hr> <br>

## Response

    Successfully uploaded file file1.txt!
    Successfully uploaded file file2.txt!

If an error has occured, this output will be produced instead:

    Could not upload file file1.txt due to error: ...