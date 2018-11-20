# wb-pluginsnippetlib
Plugin Snippet Library for Blumentals WeBuilder/RapidPHP/RapidCSS/HTMLPad editors

This is a Snippet Library for the following editors:

Webuilder: http://www.webuilderapp.com/<br/>
RapidPHP: http://www.rapidphpeditor.com/<br/>
RapidCSS: https://www.rapidcsseditor.com/<br/>
HTMLPad: https://www.htmlpad.net/

### Function:
FastScript snippet library with various functions to help creating WeBuilder plugins.


#### Filehandling functions:

<table>

  <tr>
  <td valign="top"><strong>GetFilesList(folder)</strong></td>
    <td valign="top"><strong>Get list of files in a given path</strong><br>
@param  string   folder  the root folder<br>
@return string   comma separated list of filenames</td>
  </tr>

  <tr>
    <td valign="top"><strong>GetFoldersList(folder)</strong></td>
    <td valign="top"><strong>Get list of folders in a given path</strong><br>
@param  string   folder  the root folder<br>
@return string   comma separated list of foldernames</td>
  </tr>

  <tr>
    <td valign="top"><strong>GetFilesFoldersList(folder)</strong></td>
    <td valign="top"><strong>Get list of files or folders of a given path</strong><br>
@param  string   folder  the root folder<br>
@param  int      mode    0=files, 1=folders<br>
@return string   comma separated list of file or folder names
 </td>
  </tr>

  <tr>
    <td valign="top"><strong>CopyFile(source, destination, overwrite)</strong></td>
    <td valign="top"><strong>Copy one or more files from one location (the source) to another (destination)</strong><br>

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
    <td valign="top"><strong>MoveFile(source, destination)</strong></td>
    <td valign="top"><strong>Move one or more files from one location (the source) to another (destination)</strong><br>

If source contains wildcards or destination ends with a path separator (\), it is assumed that destination specifies an existing folder in which to move the matching files. Otherwise, destination is assumed to be the name of a destination file to create. In either case, three things can happen when an individual file is moved:
If destination does not exist, the file gets moved. This is the usual case.<br>
If destination is an existing file, an error occurs.<br>
If destination is a directory, an error occurs.<br>

@param  string   source location of one or more files to be moved<br>
@param  string   destination location to where one or more files in source will be moved<br>
@return void</td>
  </tr>
  
  <tr>
    <td valign="top"><strong>DeleteFile(file, force)</strong></td>
    <td valign="top"><strong>Delete file or files (using wilcards) from system</strong><br>
@param  string  file   path/name of file to delete<br>
@param  bool    force  true if files with the read-only attribute set are to be deleted false if they are not.<br>
@return bool   true if file have been deleted sucessfully</td>
  </tr>

  <tr>
    <td valign="top"><strong>CopyFolder(source, destination, overwrite)</strong></td>
    <td valign="top"><strong>Copy one or more folders from one location (the source) to another (destination)</strong><br>
If source contains wildcard characters or destination ends with a path separator (\), it is assumed that destination is an existing folder in which to copy matching folders and subfolders. Otherwise, destination is assumed to be the name of a folder to create. In either case, four things can happen when an individual folder is copied.<br>
If destination does not exist, the source folder and all its contents gets copied. This is the usual case.<br>
If destination is an existing file, an error occurs.<br>
If destination is a directory, an attempt is made to copy the folder and all its contents. If a file contained in source already exists in destination, an error occurs if overwrite is false. Otherwise, it will attempt to copy the file over the existing file. <br>
If destination is a read-only directory, an error occurs if an attempt is made to copy an existing read-only file into that directory and overwrite is false.<br>
@param  string   source location of one or more folders to be copied<br>
@param  string   destination location to where one or more folders in source will be copied<br>
@param  bool     overwrite True allows the overwriting of existing folders in the destination<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>MoveFolder(source, destination)</strong></td>
    <td valign="top"><strong>Move one or more folders from one location (the source) to another (destination)</strong><br>
If source contains wildcards or destination ends with a path separator (\), it is assumed that destination specifies an existing folder in which to move the matching files. Otherwise, destination is assumed to be the name of a destination folder to create. In either case, three things can happen when an individual folder is moved:<br>
If destination does not exist, the folder gets moved. This is the usual case.<br>
If destination is an existing file, an error occurs.<br>
If destination is a directory, an error occurs.<br>
@param  string   source location of one or more folders to be moved<br>
@param  string   destination location to where one or more folders in source will be moved<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>DeleteFolder(folder, force)</strong></td>
    <td valign="top"><strong>Delete folder from system, including all files and subfolders</strong><br>
@param  string   folder  path/name of folder to delete<br>
@param  bool    force  true if folders with the read-only attribute set are to be deleted false if they are not<br>
@return bool   true if folder have been deleted sucessfully</td>
  </tr>

  <tr>
    <td valign="top"></td>
    <td valign="top"></td>
  </tr>

</table>



W.I.P.
