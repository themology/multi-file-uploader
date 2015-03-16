Responsive, liteweight, flexible and High performance multi-file uploader. Highly configurable with a contemporary design and native animation effects using CSS3 and HTML5.

Its designed for those who want an upload solution that can be implemented out of the box in minutes without writing infrastructure or custom code. It also has an intelligent template that will tailor the view of the uploaded item according to the file type.

This script could be integrated into a form without a conflict, as it does only use pure javascript/jQuery to upload binary files.


###Setup###

* Download "Multi File Uploader" and save it to your local computer.
* Extract the ZIP archive in a folder.
* Now you need to access root, fonts, css, images and js folders to extract the following files:
    * <strong>processMultipleUploads.php file:</strong> Which is responsible of processing all of the uploaded files and store them in a specific configurable folder, and if no configuration was made, the files will initially be stored in root path inside folder named 'uploads'. To change "upload" path, you can easily access the PHP file and modify the upload path in the header section according to your need.
   * <strong>icomoon.eot, icomoon.svg, icomoon.ttf and icomoon.woff:</strong> These files do have the vectorized font icons that is been used by the script, and it is up to you whether you want to reuse them, or replace them with your own font based icons.
   * <strong>style.css file:</strong> Where it contains all of neccessary CSS styles for this plugin. You can copy the internal content and append it into your own style sheet if you need to have a one centralized style sheet.
Finally you need jquery + arfaly-min.js as they are the only javascript dependencies needed.

Here is how to import the libraries in your website:
```
<link rel="stylesheet" type="text/css" href="css/style.css">
<script language="javascript" type="text/javascript" src="js/jquery-1.11.1.min.js" ></script>
<script language="javascript" type="text/javascript" src="js/multi-uploader-min.js" ></script>
```
And here is how you can define your Multi uploader DIV in a single line:

```<div id="company-files"></div>```


###Apply your settings for the Script###

This is how you activate the Multi Uploader, using jQuery:

```
$(document).ready(function(){
     
    // ==> Option one
    // Apply Multi Uploader to a div with default options
    // Note that all of the default options value are listed below
    $("#company-files").arfaly();
                     
    --------------------
     
    // ==> Option two
    // Apply Multi Uploader to a div with custom options
    $("#company-files").arfaly(
        {
            limitNumberofFiles:10,              // Limit the number of total uploaded file per session
            debug:false,                        // Enable/Disable debug for tracking error
            targetOutput:'.output',             // Print the output of the debug into a specific target HTML element
            allowedFileSize: 1024 * 1024 * 10, 
            disableRemovingItems:true,          // Disable removing upload items from the list
            delay:5000,                         // Define a hide delay of each upload element if it is set to be hidden
            multi:true,                         // Enable multi-file select/upload
            dragDrop:true,
            url: "processMultipleUploads.php",  // URL on where the files should be submitted
            dataType: "json",                   // Define AJAX dataType
            type: "post",                       // Define post type "GET/POST" (POST Recommended)
            label:'Allowed file types are gif, jpg, png, avi, mp3, wav, mp4, doc, docx, pdf, txt, zip and rar',
            labelColor:'rgb(90, 90, 90)',
            logoColor:'rgb(150, 155, 255)',     // Change the color of logo
            textColor:'#DADADA',                // Change the color of border line and text
            disablePostProgressAnimation: false,
            progressBarColor: 'red',            // Change the color of the progress-bar {red, orange, and green}
            action:'itech_themo_submission',   // Pass a custom JSON object to the server side along the files
            successfulUpload: themo.successfulUpload,  // Event handler for successful file upload
            failedUpload: themo.failedUpload,          // Event for unsuccessful file upload
            fileDeleted: themo.fileDeleted             // File deleted even
        });
    }
);
```

And as you can see in the above script, you can either apply Multi Uploader into a DIV with default options as for the first option, or overriding the options as shown for the second option.

###Script options###

![Image of options](https://)
					
All of the options listed above could be overridden as shown in the previous code snippet.

###Server side script configuration###

From the server side there will be only one PHP file that should process the uploaded files from the client side, and this single processing file is represented by the "processMultipleUploads.php" file.

Here is the code segments where you can add/permit your own file types to the filtering array called "allowedExts":

```
############ Global settings ##############
 
$localFileDestination       = 'uploads/'; // From server side, define the uploads folder url
$maxFileSize            = 1024 * 1024 * 10; // Max 10MB
$allowedExts            = array( // Change this list to allow more files to be uploaded :)
    "gif",
    "jPeg",
    "jpg",
    "png",
    "avi",
    "mp3",
    "wav",
    "mp4",
    "dOc",
    "docX",
    "pdf",
    "txt",
    "zip",
    "rar"
);
```

Last but not least it is open for you, to extend this script and intefrate into whatever custom application you have. You can add extra codes to tag files with extra information and store their file path into your database correspondingly.

###Client side script configuration###

For security reasons, this script validates MIME file types in both server and client side. Because there are hundreds of MIME types for files, we couldn't include all of the MIME types by default inside of our client and server script, but we have rather included only the most common file types shown on the the following list: 

Default file allowed in both server and client side:

* Images:
    * PNG
    * GIF
    * JPG

* Audio:
    * mp3
    * wave
    * mp4

* Videos:
    * avi
    * mp4
    * mkv

* Archives:
    * zip
    * rar
    * Documents:
    * text

So according to the above default allowed file extensions, you can disallow some types and allow others. To disallow file type from being uploaded just remove its extension from server side correspondingly.

Last but not least it is open for you, to extend this script and integrate it into whatever custom application you have. You can add extra codes to tag files with extra information and store their file path into your database correspondingly.

###Sources and Credits###

We've used the following images, icons or other files as listed.

* jQuery - <a href="http://jquery.com/">http://jquery.com/</a>
* Iconmoon - <a href="http://icomoon.io/">Icon-Moon</a>



###Contributer:###

- **Author:** Themology
- **Email:** info@themology.net
- **Web:** http://themology.net
