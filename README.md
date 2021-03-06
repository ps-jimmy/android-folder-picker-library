# android-folder-picker-library
[![Demo](https://img.shields.io/badge/Demo%20APK-2.2-blue.svg)](https://github.com/kashifo/android-folder-picker-library/releases/download/v2.2/FolderPickerDemo_v2.2.apk)
[![Bintray](https://img.shields.io/badge/Bintray-2.2-blue.svg)](https://bintray.com/kashifo/android-folder-picker-library/android-folder-picker-library/_latestVersion)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

A light-weight android library that can be quickly integrated into any app to let users choose folder, also files (but esp built for folders).

# Example Uses
- To let users choose folder for saving files
- To let users choose backup folder
- To let users pick files to upload
etc...

# Screenshots

|![Preview](https://github.com/kashifo/android-folder-picker-library/raw/master/screenshots/folderpicker-scr1.png) | ![Preview](https://github.com/kashifo/android-folder-picker-library/raw/master/screenshots/folderpicker-scr2.png) | ![Preview](https://github.com/kashifo/android-folder-picker-library/raw/master/screenshots/folderpicker-scr3.png) |
|:-------------------:|:------------------------:|:-----------------:|
| Can pick folders | Can create folder | Can also pick file |


# Installation

For your convenience, it is available on jCenter, So just add this in your app dependencies:
```gradle
    compile 'lib.kashif:folderpicker:2.2'
```
  
# Usage

**To pick folder**

```java
        Intent intent = new Intent(this, FolderPicker.class);
        startActivityForResult(intent, FILEPICKER_CODE);        
```

```java
        
        protected void onActivityResult(int requestCode, int resultCode, Intent intent) {
          if (requestCode == FILEPICKER_CODE && resultCode == Activity.RESULT_OK) {

              String folderLocation = intent.getExtras().getString("data");
              Log.i( "folderLocation", folderLocation );
            
          }
        }
        
 ```

**Options**


 ```java
 
        //To show a custom title
        intent.putExtra("title", "Select file to upload");
        
        //To begin from a selected folder instead of sd card's root folder. Example : Pictures directory
        intent.putExtra("location", Environment.getExternalStoragePublicDirectory(Environment.DIRECTORY_PICTURES).getAbsolutePath());
        
        //To pick files
        intent.putExtra("pickFiles", true);
        
  ```
  
[Click to see an example working code](https://github.com/kashifo/android-folder-picker-library/blob/master/app/src/main/java/lib/folderpicker/demo/MainActivity.java)
