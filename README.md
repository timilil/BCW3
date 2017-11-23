# File Upload

## Start
1. Load and extract this repo as a ZIP https://github.com/ilkkamtk/BCW3

## 1. It's 90's again

* Modify task_a.html
  * Complete the form to upload an image to your Java server
  * Study [attributes of input element](https://www.w3schools.com/tags/tag_input.asp) and find a suitable attribute to select only images 


## 2. Modern version

* Use fetch API to upload the file
* Example:
```javascript
    // select input element where type is file
    const input = document.querySelector('input[type="file"]');
    // make FormData -object
    const data = new FormData();
    // add file to FormData -object.
    // Note that 'files' is an FileList object. This means that you can upload multiple files. 
    data.append('fileToUpload', input.files[0]);
    // make an object for settings
    const settings = {
            method: 'POST',
            body: data
        };
    // initiate fetch. In this example the server responds with text.
    // Response could also be json. Then you would use response.json()
    fetch('upload.php', settings).then((response) => {
        return response.text();
    }).then((text) => {
        console.log(text);
    });
```
* [FormData](https://developer.mozilla.org/en-US/docs/Web/API/FormData)
* Modify task_b.html and main_b.js
* More help in the comments of main_b.js
