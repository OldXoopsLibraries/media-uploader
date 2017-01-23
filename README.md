[![License](https://img.shields.io/github/license/OldXoopsLibraries/media-uploader.svg?maxAge=2592000)](License.txt) [![GitHub release](https://img.shields.io/github/release/OldXoopsLibraries/media-uploader.svg?maxAge=2592000)](https://github.com/OldXoopsLibraries/media-uploader/releases) [![Build Status](https://travis-ci.org/OldXoopsLibraries/media-uploader.svg?branch=master)](https://travis-ci.org/OldXoopsLibraries/media-uploader)

# Media uploader

Extracted XoopsMediaUploader class from [Xoops](http://xoops.org) for handling file uploads.

##Installation

`composer require old-xoops-libraries/media-uploader`

## Example of usage

```php5
  $allowed_mimetypes = array('image/gif', 'image/jpeg', 'image/pjpeg', 'image/x-png');
  $maxfilesize = 50000;
  $maxfilewidth = 120;
  $maxfileheight = 120;
  $uploader = new XoopsMediaUploader('/home/xoops/uploads', $allowed_mimetypes, $maxfilesize, $maxfilewidth, $maxfileheight);
  if ($uploader->fetchMedia($_POST['uploade_file_name'])) {
             if (!$uploader->upload()) {
                echo $uploader->getErrors();
             } else {
                echo '<h4>File uploaded successfully!</h4>'
                echo 'Saved as: ' . $uploader->getSavedFileName() . '<br>';
                echo 'Full path: ' . $uploader->getSavedDestination();
             }
  } else {
             echo $uploader->getErrors();
  }
```