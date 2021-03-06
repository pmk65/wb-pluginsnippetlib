# wbl-pluginsnippetlib
Plugin Snippet Library for Blumentals WeBuilder/RapidPHP/RapidCSS/HTMLPad editors

This is a Snippet Library for the following editors:

Webuilder: http://www.webuilderapp.com/<br/>
RapidPHP: http://www.rapidphpeditor.com/<br/>
RapidCSS: https://www.rapidcsseditor.com/<br/>
HTMLPad: https://www.htmlpad.net/

### Function:
FastScript snippet library with various functions to help your create WeBuilder plugins.

For more information on the FastScript syntax and how to create WeBuilder plugins, see the <a href="http://help.blumentals.net/webuilder/plugins/develop/structure.htm" target="_blank">WeBuilder Documentation</a> or the original <a href="https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwiE1t3ZjubeAhVnCcAKHcWZAMAQFjAAegQICRAC&url=https%3A%2F%2Fwww.fast-report.com%2Fpublic_download%2Ffs_en.pdf&usg=AOvVaw2bRZqajsrSV8zTMp6aby66" target="_blank">FastScript Manual.</a>


### Filehandling functions:

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
Otherwise, destination is assumed to be the name of a file to create. In either case, three things can happen when an individual file is copied.
  <ul>
    <li>If destination does not exist, source gets copied. This is the usual case.</li>
    <li>If destination is an existing file, an error occurs if overwrite is false. Otherwise, an attempt is made to copy source over the existing file.</li>
    <li>If destination is a directory, an error occurs.</li>
  </ul>
@param  string   source location of one or more files to be copied<br>
@param  string   destination location to where one or more files in source will be copied<br>
@param  bool     overwrite True allows the overwriting of existing files in the destination<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>MoveFile(source, destination)</strong></td>
    <td valign="top"><strong>Move one or more files from one location (the source) to another (destination)</strong><br>

If source contains wildcards or destination ends with a path separator (\), it is assumed that destination specifies an existing folder in which to move the matching files. Otherwise, destination is assumed to be the name of a destination file to create. In either case, three things can happen when an individual file is moved:
  <ul>
    <li>If destination does not exist, the file gets moved. This is the usual case.</li>
    <li>If destination is an existing file, an error occurs.</li>
    <li>If destination is a directory, an error occurs.</li>
  </ul>
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
If source contains wildcard characters or destination ends with a path separator (\), it is assumed that destination is an existing folder in which to copy matching folders and subfolders. Otherwise, destination is assumed to be the name of a folder to create. In either case, four things can happen when an individual folder is copied.
  <ul>
    <li>If destination does not exist, the source folder and all its contents gets copied. This is the usual case.</li>
    <li>If destination is an existing file, an error occurs.</li>
    <li>If destination is a directory, an attempt is made to copy the folder and all its contents. If a file contained in source already exists in destination, an error occurs if overwrite is false. Otherwise, it will attempt to copy the file over the existing file.</li>
    <li>If destination is a read-only directory, an error occurs if an attempt is made to copy an existing read-only file into that directory and overwrite is false.</li>
  </ul>
@param  string   source location of one or more folders to be copied<br>
@param  string   destination location to where one or more folders in source will be copied<br>
@param  bool     overwrite True allows the overwriting of existing folders in the destination<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>MoveFolder(source, destination)</strong></td>
    <td valign="top"><strong>Move one or more folders from one location (the source) to another (destination)</strong><br>
If source contains wildcards or destination ends with a path separator (\), it is assumed that destination specifies an existing folder in which to move the matching files. Otherwise, destination is assumed to be the name of a destination folder to create. In either case, three things can happen when an individual folder is moved:
  <ul>
    <li>If destination does not exist, the folder gets moved. This is the usual case.</li>
    <li>If destination is an existing file, an error occurs.</li>
    <li>If destination is a directory, an error occurs.</li>
  </ul>
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
    <td valign="top"><strong>SelectFile(defaultPath, title)</strong></td>
    <td valign="top"><strong>Bring up dialog to select file</strong><br>
@param  string   defaultPath initial path<br>
@param  string   title displayed in dialogbox<br>
@return string   path/filename name of file selected</td>
  </tr>

  <tr>
    <td valign="top"><strong>SelectFolder(defaultPath, text, createnew)</strong></td>
    <td valign="top"><strong>Bring up dialog to select folder</strong><br>
@param  string   defaultPath  initial folder<br>
@param  string   text         title displayed in dialogbox<br>
@param  bool     createnew    enable creating of new folder in the dialog
@return string   path</td>
  </tr>

  <tr>
    <td valign="top"><strong>FileGetContents(filename)</strong></td>
    <td valign="top"><strong>Load external file and return the contents</strong><br>
@param  string   filename the name of the file to load<br>
 @return string  the contents of the file</td>
  </tr>

  <tr>
    <td valign="top"><strong>FilePutContents(filename, contents)</strong></td>
    <td valign="top"><strong>Save contents to external file</strong><br>
@param  string   filename the name of the file to save<br>
@param  string   contents the contents of the file<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>GetTempFileName(ext)</strong></td>
    <td valign="top"><strong>Creates a random tempfile name, located in the system TEMP folder</strong><br>
@param  string   ext  file extension in format ".xxx". Default is ".tmp"<br>
@return string   path/name to tempfile</td>
  </tr>

  <tr>
    <td valign="top"><strong>GetSystemFolder(type)</strong></td>
    <td valign="top"><strong>Obtain the full path to any of the special Windows folders</strong><br>
@param  string  type One of the following special folders: AllUsersDesktop, AllUsersStartMenu, AllUsersPrograms, AllUsersStartup, Desktop, Favorites, Fonts, MyDocuments, NetHood, PrintHood, Programs, Recent, SendTo, StartMenu, Startup, Templates<br>
@return string</td>
  </tr>

  <tr>
    <td valign="top"><strong>GetRelPath(abspath, root, slash)</strong></td>
    <td valign="top"><strong>Convert absolute path to relative path</strong><br>
Works with both slash and backslash as dividers<br>
@param  string   path   The absolute path to convert<br>
@param  string   root   The root path from which the relative path is calculated<br>
@param  bool     slash  Use slash as divider. default is backslash<br>
@return string   the relative path</td>
  </tr>

  <tr>
    <td valign="top"><strong>GetRecursiveFileList(folder)</strong></td>
    <td valign="top"><strong>Get recursive list of files in a given path</strong><br>
@param  string   folder  the root folder<br>
@return string   comma separated list of file or folder names
</td>
  </tr>

  <tr>
    <td valign="top"><strong>ToShortName(longName)</strong></td>
    <td valign="top"><strong>Convert Windows long name to short name</strong><br>
Path/file must exist on system, otherwise longname is returned<br>
@param  string   longName<br>
@return string</td>
  </tr>

  <tr>
    <td valign="top"><strong>TrimPath(path, segments)</strong></td>
    <td valign="top"><strong>Removes last segment of path/url</strong><br>
@param  string   path the path/url to trim<br>
@param  int      segments number of segments to trim<br>
@return string</td>
  </tr>

</table>

### AJAX functions:

<table>

  <tr>
    <td valign="top"><strong>ParseJson(jsonStr)</strong></td>
    <td valign="top"><strong>JSON parser using "htmlfile" OLE object</strong><br>
The JSON result object is extended with two custom methods, making data fully accessible from FastScript. Custom methods:
  <ul>
    <li><strong>getProp(key/index)</strong> to access properties by index or name</li>
    <li><strong>getKeys(dummy)</strong> to get list of keys</li>
  </ul>
@param  string   jsonStr The JSON string to parse<br>
@return mixed    variant or empty string if failure</td>
  </tr>

  <tr>
    <td valign="top"><strong>XhrRequest(uri)</strong></td>
    <td valign="top"><strong>Make XHR request and return result</strong><br>
@param  string   uri<br>
@return string</td>
  </tr>

</table>

### Variables functions:

<table>

  <tr>
    <td valign="top"><strong>GetVarType(val)</strong></td>
    <td valign="top"><strong>Get the type of a variable</strong><br>
@param  mixed    val The variable to test<br>
@return integer  The variable type</td>
  </tr>

  <tr>
    <td valign="top"><strong>VarTypeAsText(type)</strong></td>
    <td valign="top"><strong>Convert variable type (integer) to text value (constants name)</strong><br>
@param  integer   type The variable type<br>
@return string    The textual name of the variable type</td>
  </tr>

  <tr>
    <td valign="top"><strong>IsArray(val)</strong></td>
    <td valign="top"><strong>Test if variable is an array</strong><br>
@param  mixed   val<br>
@return bool    True is val is a array</td>
  </tr>

  <tr>
    <td valign="top"><strong>IsBool(val)</strong></td>
    <td valign="top"><strong>Test if variable is a boolean</strong><br>
@param  mixed   val<br>
@return bool    True is val is a boolean</td>
  </tr>

  <tr>
    <td valign="top"><strong>IsFloat(val)</strong></td>
    <td valign="top"><strong>Test if variable is a floating point</strong><br>
@param  mixed   val<br>
@return bool    True is val is a floating point</td>
  </tr>

  <tr>
    <td valign="top"><strong>IsInt(val)</strong></td>
    <td valign="top"><strong>Test if variable is an integer</strong><br>
@param  mixed   val<br>
@return bool    True is val is an integer</td>
  </tr>

  <tr>
    <td valign="top"><strong>IsString(val)</strong></td>
    <td valign="top"><strong>Test if variable is a string </strong><br>
@param  mixed   val<br>
@return bool    True is val is a string</td>
  </tr>

</table>

### RegularExpression functions:

<table>

  <tr>
    <td valign="top"><strong>WildcardsToRegex(str)</strong></td>
    <td valign="top"><strong>Convert wildcard characters * and ? to regular expression equivalents</strong><br>
@param  string   str The string to convert<br>
@return string</td>
  </tr>

  <tr>
    <td valign="top"><strong>EscapeRegExp(str)</strong></td>
    <td valign="top"><strong>Escape characters which have special meaning in regular expressions</strong><br>
@param  string   str The string to escape<br>
@return string</td>
  </tr>

</table>

### GUI functions:

<table>

  <tr>
    <td colspan="2"><strong>TEdit Helpers</strong></td>
  </tr>

  <tr>
    <td valign="top"><strong>NumbersOnly(Sender, key)</strong></td>
    <td valign="top"><strong>OnKeyPress event handler - Prevent entry of chars other than numbers</strong><br>
@param     object  Sender: The parent object<br>
@param     string  key: The character key pressed<br>
@return    void</td>
  </tr>

  <tr>
    <td valign="top"><strong>NumbersAndPeriodOnly(Sender, key)</strong></td>
    <td valign="top"><strong>OnKeyPress event handler - Prevent entry of chars other than numbers and a single period</strong><br>
@param     object  Sender: The parent object<br>
@param     string  key: The character key pressed<br>
@return    void</td>
  </tr>

  <tr>
    <td valign="top"><strong>HideCaret(Sender)</strong></td>
    <td valign="top"><strong>OnEnter callback for use in TRichEdit/TEdit - Hide caret in TRichEdit/TEdit when in ReadOnly Mode</strong><br>
@param  object   Sender<br>
@return void</td>
  </tr>

  <tr>
    <td colspan="2"><strong>TListBox Helpers</strong></td>
  </tr>

  <tr>
    <td valign="top"><strong>SetSelection(Sender, selected)</strong></td>
    <td valign="top"><strong>Set selection in TListBox</strong><br>
@param  object   Sender  the TListBox object<br>
@param  string   selected  comma separated list of selected item values<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>GetSelection(Sender)</strong></td>
    <td valign="top"><strong>Get selection from TListBox</strong><br>
@param  object  Sender  the TListBox object<br>
@return string   res   comma separated list of selected items
</td>
  </tr>

  <tr>
    <td colspan="2"><strong>Mics GUI functions/examples</strong></td>
  </tr>

  <tr>
    <td valign="top"><strong>ShowAnalogClock()</strong></td>
    <td valign="top"><strong>Displays a woking Analog Clock</strong><br>
Example of how to draw directly on the TForm Canvas using FastScript.<br>
@return void
    </td>
  </tr>

  <tr>
    <td valign="top"><strong>ShowDialog(title, message, buttonRightCaption, buttonLeftCaption, buttonCenterCaption, defaultButtonCaption, timeout, imageFile)</strong></td>
    <td valign="top"><strong>Messagebox with 1 to 3 buttons and optional button timeout</strong><br>
Also incl. support for displaying image. (Both static and animated sprite sequences)<br>
Note: You will need to include the AnimSprite() function if you want to use animations<br>
You can turn regular animated GIF into sprite frames, using <a href="http://www.piskelapp.com" target="_blank">Piskel</a><br>
@param  string         title                 Dialogbox title<br>
@param  string         message               Dialogbox Message<br>
@param  string         buttonRightCaption	Caption of Right button (Empty string if not used)<br>
@param  string         buttonLeftCaption     Caption of Left button (Empty string if not used)<br>
@param  string         buttonCenterCaption   Caption of Center button (Empty string if not used)<br>
@param  string         defaultButtonCaption  Caption of default button (Empty string if not used)<br>
@param  integer        timeout               Timeout value for timed dialogbox. 0 for no timeout<br>
@param  string/array   imageFile             Single Image: path/name  (Empty string if not used), Animated Image: [path/name, [duration frame1, duration frame2, ...]]<br>
@return string                               Caption of clicked button or empty string if dialog was cancled.
</td>
  </tr>

  <tr>
    <td valign="top"><strong>AnimateSprite(imgObj, durations)</strong></td>
    <td valign="top"><strong>Animate Sprite image loaded into TImage object</strong><br>
When animation ends, delete the "imageAnimTimer" object to end animation.<br>
@param  object  imgObj The TImage object to animate<br>
@param  array   durations The duration of each sprite frame<br>
@return void
    </td>
  </tr>

</table>

### Misc functions:

<table>

  <tr>
    <td valign="top"><strong>Debug(label, val)</strong></td>
    <td valign="top"><strong>Debug helper - Shows output in WeBuilder message panel</strong><br>
@param  string    label: the label<br>
@param  mixed     val: the variable<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>CopyToClipboard(contents)</strong></td>
    <td valign="top"><strong>Copy contents to Clipboard</strong><br>
@param  string   contents the contents to place on clipboard<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>PasteFromClipboard()</strong></td>
    <td valign="top"><strong>Paste contents from Clipboard into editor</strong><br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>Max(x,y)</strong></td>
    <td valign="top"><strong>Returns the largest of two numbers</strong><br>
@param     number  x: The 1st value<br>
@param     number  y: The 2nd value<br>
@return    number</td>
  </tr>

  <tr>
    <td valign="top"><strong>Min(x,y)</strong></td>
    <td valign="top"><strong>Returns the smallest two numbers</strong><br>
@param     number  x: The 1st value<br>
@param     number  y: The 2nd value<br>
@return    number</td>
  </tr>

  <tr>
    <td valign="top"><strong>IntToHex(intNum)</strong></td>
    <td valign="top"><strong>Convert integer value to 2-byte Hexadecimal number</strong><br>
@param     int  intNum: The value<br>
@return    string</td>
  </tr>

  <tr>
    <td valign="top"><strong>UrlEncode(str)</strong></td>
    <td valign="top"><strong>UrlEncode string</strong><br>
@param  string   str  the string to urlencode<br>
@return string   res  the urlencoded string</td>
  </tr>

  <tr>
    <td valign="top"><strong>UrlDecode(str)</strong></td>
    <td valign="top"><strong>UrlDecode string</strong><br>
@param  string   str<br>
@return string</td>
  </tr>

  <tr>
    <td valign="top"><strong>OpenUrlInBrowser(url)</strong></td>
    <td valign="top"><strong>Open URL in default browser</strong><br>
@param  string   url the url to open<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>RemoveQuoted(str)</strong></td>
    <td valign="top"><strong>Get rid of quoues and anything between them</strong><br>
@param  string  str: the string to clean<br>
@return string</td>
  </tr>

  <tr>
    <td valign="top"><strong>ReturnToOriginalTab(fileName)</strong></td>
    <td valign="top"><strong>Return to original Editor Tab after opening new Document/Tab</strong><br>
@param  string   fileName path/name of file in original Tab<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>CreateJScriptObject(jsCode)</strong></td>
    <td valign="top"><strong>Allows you to run true JavaScript (MS variant) functions</strong><br>
Similar to Webkit/Chromium frame, except no frame/window needs to be opened first.<br>
@param  string   javaScript code<br>
@return object</td>
  </tr>

  <tr>
    <td valign="top"><strong>SendKeys(keys)</strong></td>
    <td valign="top"><strong>Sends one or more keystrokes to the active window (as if typed on the keyboard)</strong><br>
For more info, see: <a href="https://msdn.microsoft.com/en-us/library/8c6yea83.aspx" target="_blank">https://msdn.microsoft.com/en-us/library/8c6yea83.aspx</a><br>
Example (Activates Find dialog and enter "hello" in searchfield):<br>
<em>SendKeys("^fhello");</em><br>
@param  string   ksSeq<br>
@return void</td>
  </tr>

  <tr>
    <td valign="top"><strong>PlaySound(soundFile)</strong></td>
    <td valign="top"><strong>Play sound using Windows Media Player API</strong><br>
@param  string   soundFile The sound file to play<br>
@return void</td>
  </tr>

</table>

W.I.P.
