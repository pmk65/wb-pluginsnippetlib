# wb-pluginsnippetlib
Plugin Snippet Library for Blumentals WeBuilder/RapidPHP/RapidCSS/HTMLPad editors

This is a Snippet Library for the following editors:

Webuilder: http://www.webuilderapp.com/<br/>
RapidPHP: http://www.rapidphpeditor.com/<br/>
RapidCSS: https://www.rapidcsseditor.com/<br/>
HTMLPad: https://www.htmlpad.net/

#### Function:
FastScript snippet library with various functions to help creating WeBuilder plugins.


### Filehandling functions:

<table>

  <tr>
    <td valign="top">GetFilesList(folder)</td>
    <td valign="top">Get list of files in a given path<br>
@param  string   folder  the root folder<br>
@return string   comma separated list of filenames</td>
  </tr>

  <tr>
    <td valign="top">GetFoldersList(folder)</td>
    <td valign="top">Get list of folders in a given path<br>
@param  string   folder  the root folder<br>
@return string   comma separated list of foldernames</td>
  </tr>

  <tr>
    <td valign="top">GetFilesFoldersList(folder)</td>
    <td valign="top">@param  string   folder  the root folder<br>
@param  int      mode    0=files, 1=folders<br>
@return string   comma separated list of file or folder names
 </td>
  </tr>

  <tr>
    <td valign="top">CopyFile(source, destination, overwrite)</td>
    <td valign="top">Copy one or more files from one location (the source) to another (destination).<br>

If source contains wildcard characters or destination ends with a path separator (\), it is assumed that destination is an existing folder in which to copy matching files.<br>
Otherwise, destination is assumed to be the name of a file to create. In either case, three things can happen when an individual file is copied.<br>
If destination does not exist, source gets copied. This is the usual case.<br>
If destination is an existing file, an error occurs if overwrite is false. Otherwise, an attempt is made to copy source over the existing file.<br>
If destination is a directory, an error occurs.<br>
<br>
@param  string   source location of one or more files to be copied<br>
@param  string   destination location to where one or more files in source will be copied<br>
@param  bool     overwrite True allows the overwriting of existing files in the destination<br>
@return void</td>
  </tr>
 
  <tr>
    <td valign="top">MoveFile(source, destination)</td>
    <td valign="top">Move one or more files from one location (the source) to another (destination).<br>

If source contains wildcards or destination ends with a path separator (\), it is assumed that destination specifies an existing folder in which to move the matching files. Otherwise, destination is assumed to be the name of a destination file to create. In either case, three things can happen when an individual file is moved:
If destination does not exist, the file gets moved. This is the usual case.<br>
If destination is an existing file, an error occurs.<br>
If destination is a directory, an error occurs.<br>

@param  string   source location of one or more files to be moved<br>
@param  string   destination location to where one or more files in source will be moved<br>
@return void</td>
  </tr>
  
  <tr>
    <td valign="top"></td>
    <td valign="top"></td>
  </tr>
  
</table>



W.I.P.
