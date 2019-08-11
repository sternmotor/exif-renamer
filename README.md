# exif-renamer
Rename photo files based on exif date - combine multiple photographers work

## Description
After holidays with friends or other situations where photos are taken from different cameras, it is hard to sort those photos by filename. Creation date may be mangled due to copy actions. 

This script helps sorting this files by renaming them so file name starts with date info found in exif data. Just call this script from command line while in the directory where all photos are kept. All sub-directories are handled recursively. 

Make sure all cameras have their date and time set up properly prior to shooting.

## Details

The original file name is kept as-is and is just appended to the time stamp. Thus, file names look like

```
<YYYYmmdd-HHMMSS> <old file name>.<old extension>
```

For example
```
20050313-0401 CIMG0352.JPG
```

In case there is no exif information, the script tries to retrieve date info from file name or file creation date in case everything else failes.

## TODO
* Implement argparse for selecting working dir and verbosity
* Implement reading files from stdin so drag 'n drop is working on desktop:
  * script called from command line with no arguments: walk current directory
  * (multiple) path(es) given: walk direktories, handle single files given
