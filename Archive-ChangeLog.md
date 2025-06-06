# Archived ChangeLog for PSScriptTools

This file contains older change history. It is maintained for reference purposes.

## v2.42.0

- Updated module manifest to load required .NET assembly for `Convert-HTMLtoAnsi`. [Issue #124](https://github.com/jdhitsolutions/PSScriptTools/issues/124)
- Updated `Show-AnsiSequence` to fix a display bug that was dropping values. [Issue #125](https://github.com/jdhitsolutions/PSScriptTools/issues/125)
- Updated missing online help links.
- Added new sample script `today.ps1`.
- Help updates.
- Updated `README.md`.

## v2.41.0

- Added function `Copy-CommandHistory` with an alias of `ch`.
- Updated `Out-Copy` to ignore ANSI unless specified. [Issue #118](https://github.com/jdhitsolutions/PSScriptTools/issues/118)
- Added an alias of `oc` for `Out-Copy`.
- Updated `New-PSFormatXML` to fix ReadOnly property error. [Issue #121](https://github.com/jdhitsolutions/PSScriptTools/issues/121)
- Updated `Get-ModuleCommand` to include version information and to accept pipeline input.
- Updated `modulecommand.format.ps1xml` with a new table view called `version`.
- Updated missing online help links.
- Updated `README.md`.

## v2.40.0

- Updated parameter validation for IP address in `Get-WhoIs` to allow addresses with 255 in an octet. [Issue #117](https://github.com/jdhitsolutions/PSScriptTools/issues/117).
- Updated help files with missing online links.
- Added command `Convert-HtmlToAnsi` with an alias of `cha`.
- Modified `Convertto-Markdown` to add a `AsList` parameter. [Issue #114](https://github.com/jdhitsolutions/PSScriptTools/issues/114)
- Updated `README.md`.

## v2.39.0

- Updated `Test-WithCulture` to include additional Verbose output.
- Added command [Get-FileExtensionInfo](docs/Get-FileExtensionInfo.md) with format file `FileExtensionInfo.format.ps1xml'. This command will require PowerShell 7.
- Added `New-PSDynamicParameter` and `New-PSDynamicParameterForm`.
- Incorporated pull request [#116](https://github.com/jdhitsolutions/PSScriptTools/pull/116) to fix bug with `Get-ParameterInfo` when the command has a `count` parameter. Thanks @ninmonkey.
- Added command [Get-LastModifiedFile](docs/Get-LastModifiedFile.md) and its alias *glm*.
- Help updates.
- Updated `README.md`.

## v2.38.0

- Added `Get-PSUnique` function with an alias of `gpsu`. ([Issue #109](https://github.com/jdhitsolutions/PSScriptTools/issues/109)).
- Modified `Show-AnsiSequence` to default to `Foreground` when using `-Type` ([Issue #110](https://github.com/jdhitsolutions/PSScriptTools/issues/110)).
- Cleaned up module manifest.
- Updated `New-PSFormatXML` to __not__ create the ps1xml file if a bad property is detected ([Issue #111](https://github.com/jdhitsolutions/PSScriptTools/issues/111)).
- Modified `New-PSFormatXML` to __not__ add an explicit declaration. This means the files will now be saved in the correct UTF-8 format and not UTF-8 with BOM.
- Modified TODO VSCode command to put date at the end. Otherwise, it breaks the `Better Comments` extension.
- Added `Set-LocationToFile` which is only loaded when importing the module in VS Code or the PowerShell ISE.
- Re-saved all `.ps1xml` files as `UTF-8`.
- Added custom type extension files `fileinfo.types.ps1xml` and `system.diagnostics.process.types.ps1xml`.
- Updated `README.md`.

## v2.37.0

- Updated `Convertto-WPFGrid` to better handle non-standard property names. ([Issue #108](https://github.com/jdhitsolutions/PSScriptTools/issues/108)).
- Modified custom format files that use ANSI to test if host name matches 'console' or 'code' to support VSCode.
- Modified `Summary` view in `psparameterinfo.format.ps1xml` to not use autosizing.
- Added `<AutoSize/>` back to `serviceansi.format.ps1xml` so that ANSI output displays properly.
- Modified `Show-ANSI` and `Get-PSAnsiFileMap` to use `[char]27` instead of `[char]0x1b` for Windows PowerShell sessions.
- Modified ANSI sequences in format files to use `[char]27`. ([Issue #107](https://github.com/jdhitsolutions/PSScriptTools/issues/107)).
- Modified ANSI sequences in format files recognize a remote PSSession. ([Issue #106](https://github.com/jdhitsolutions/PSScriptTools/issues/106)).
- Update `Get-PSLocation` to work in a PowerShell remoting session where there is no profile.  ([Issue #104](https://github.com/jdhitsolutions/PSScriptTools/issues/104)).
- Updated help.
- Updated `README.md`.


## v2.36.0

- Update `Get-MyVariable` to make it more compatible with PowerShell 7 ([Issue #103](https://github.com/jdhitsolutions/PSScriptTools/issues/103)). This also makes the command now compatible with the PowerShell ISE.
- Added table view called `Simple` to format file for Aliases.
- Modified `Options` table view in `alias.format.ps1xml` to highlight read-only aliases in Red using ANSI if running in a PowerShell console host.
- Updated `Get-PSLocation` to include `$PSHome`.
- Modified module to only dot source `Get-MyCounter.ps1` if running Windows. The file contains a class definition that uses a Windows-only reference and PowerShell "scans" the file before it dot sources it, which throws an exception on non-Windows platforms.
- Added command `Get-PSSessionInfo` and an alias of `gsin`. The command uses a new format file, `pssessioninfo.format.ps1xml`.
- Added command `Test-IsElevated`.
- Updated `Get-PSWho` to included elevated information for non-Windows platforms.
- Added format file `pswho.format.ps1xml`.
- Help updates
- Updated `README.md`.

## v2.35.0

- Added `ConvertTo-TitleCase` command with aliases of `totc` and `title`.
- Added `New-FunctionItem` command with an alias of `nfi` to create functions on-the-fly.
- Added `Show-FunctionItem` command with an alias of `sfi` to display a function.
- Modified format files to test the console when using ANSI formatting. ([Issue #102](https://github.com/jdhitsolutions/PSScriptTools/issues/102))
- Modified ANSI functions to display a warning when run in the PowerShell ISE and exit.
- Updated `Get-PSScriptTools` to not use ANSI in the header when running in a non-console host.
- Updated `Get-CommandSyntax` to not use ANSI formatting when running in a non-console host.
- Updated `README.md`.

## v2.34.1

- Updated `license.txt` with the new year.
- Added missing online help links.
- Fixed bug in `Get-ParameterInfo` that failed to display dynamic parameters when using a command alias. ([Issue #101](https://github.com/jdhitsolutions/PSScriptTools/issues/101))
- Modified format file for `PSParameterInfo` to display `Mandatory` and `IsDynamic` values in color when the value is `$True`.

## v2.34.0

- Fixed typo bug in `Get-PSScriptTools` that was failing to get command aliases. ([Issue #99](https://github.com/jdhitsolutions/PSScriptTools/issues/99))
- Modified `Get-PSScriptTools` to improve performance. Assuming that all exported functions are using standard verbs.
- Added `Get-PSAnsiFileMap`.
- Added `Set-PSAnsiFileMapEntry`.
- Added `Remove-PSAnsiFileMapEntry`.
- Added `Export-PSAnsiFileMap`.
- Added `Show-ANSISequence`.
- Updated `filesystem.ansi.format.ps1xml` to use last matching pattern.
- Modified `Show-Tree` to better handle piped-in file and directory objects.
- Added an alias `ab` for `Add-Border`.
- Added an alias of `nab` for `New-AnsiBar`.
- Updated `README.md`.
- Updated module description.
- Help updates.

## v2.33.1

- Fixed bug in `ConvertTo-WPFGrid` with refresh and timeout values. (Issue #98)
- Added missing online help links.
- Added a few related module links in `README.md`.

## v2.33.0

- Added `Select-Before`,`Select-After`,`Select-Newest` and `Select-Oldest` and their respective aliases of *before*,*after*,*newest*, and *oldest*.
- Added `Get-MyCounter` and a custom format file `mycounter.format.ps1xml`.
- Added `Trace-Message` and its alias *trace*.
- Added more Verbose messages to `Get-PSScriptTools`.
- Code cleanup in `SelectFunctions.ps1`.
- Modified `Get-PSScriptTools` to let you specify a verb. Updated command help.
- Modified `ConvertTo-Markdown` to handle properties with line returns when formatting as a table. (I[Issue #97](https://github.com/jdhitsolutions/PSScriptTools/issues/97))
- Code cleanup in sample script files.
- Added sample file `CounterMarkdown.ps1`.
- Updated `README.md`.

## v2.32.0

- Added `ConvertTo-ASCIIArt` and its alias *cart*.
- Added `Get-DirectoryInfo`, its alias *dw*, and a custom formatting file, `directorystat.format.ps1xml`.
- Modified `Open-PSScriptToolsHelp` to use `Invoke-Item` to launch the PDF file. This should work better on non-Windows platforms.
- Modified `Get-FormatView` to accept pipeline input for the `Typename` parameter. (Issue #95)
- Modified `New-PSFormatXML` to use a static value width when using scriptblocks. (Issue #94)
- Added `Out-Copy` and its alias *oc*.
- Added `Get-CommandSyntax` and its alias *gsyn*.
- Updated missing online help links.
- Added a splash header to `Get-PSScriptTools`. The header writes to the host so it isn't part of the command output.
- Updated `README.md`.

## v2.31.0

- Merged PR from @corbob to fix an issue detecting profiles scripts when the user's Documents location has changed. (Issue #93)
- Modified `Convert-HasthtableToCode` to explicitly use `@()` for array elements. This is a continuation of a fix for Issue #91.
- Updated `New-PSFormatXML` to process a custom hashtable as a property name and convert the XML property to a scriptblock.
- Updated `New-PSFormatXML` so that Wide views are auto-sized by default.
- Modified the metadata comment generated by `New-PSFormatXML`.
- Modified `New-PSFormatXML` to only display the warning message once when detecting additional objects.
- Added `Get-FormatView` with an alias of `gfv` to show defined format views. This command uses a format file, `formatview.format.ps1xml`.
- Added `Changelog.md` to `PSScriptToolsManual.pdf`.
- Moved older change log information to `Archive-Changelog.md`.
- Help and documentation updates.

## v2.30.0

- Fixed a bug in `Convert-HashtableToCode` when converting hashtables with nested hashtables. (Issue #91)
- Modified `Convert-HashtableToCode` to honor `-Inline` when processing nested hashtables.
- Updated help documentation for `Convert-HashtableToCode` to clarify the use of array values in a hashtable.

## v2.29.0

- Modified `Get-WindowsVersion` to not use remoting when connecting to the local computer. (Issue #90)
- Updated help documentation for `Get-WindowsVersion` and `Get-WindowsVersionString`.
- Added command `Copy-PSFunction` with an alias of `cpfun`.

## v2.28.0

- Added `Compare-Script` thanks to @cohdjn.
- Added `Get-PSProfile` and a related formatting file, `psprofilepath.format.ps1xml`.
- Updated `README.md`.

## v2.27.0

- Added a new command called `Get-MyAlias` with an alias of `gma`.
- Added a custom formatting file for alias objects with new views of `Options` and `Source`.
- Revised the help PDF to include command help.
- Help documentation cleanup.
- Updated `README.md`
- Fixed bug in `Test-Expression` that was importing the wrong module.
- Modified `New-PSDriveHere` to not write the new PSDrive object to the pipeline. Added a `-PassThru` parameter. This is a BREAKING change to the command.
- Modified `Get-ParameterInfo` to write a custom `PSParameterInfo` object to the pipeline and added a default list formatted view.
- Modified `psscripttool.format.ps1xml` to display Verb in color using ANSI.

## v2.26.2

- Cleaned up bad links and code fence re-formatting in `README.md`.
- Created new base version of `PSScriptToolsHelp.md`.
- Generated a new help manual with a table of contents and nicer formatting. (Issue #87)
- Renamed help pdf to `PSScriptToolsManual.pdf`.

## v2.26.1

- Replaced links in `PSScriptToolsHelp` (Issue #86)
- Updated PDF style when exporting `PSScriptToolsHelp`
- Removed Table of Contents from `PSScriptToolsHelp.md`. There is a bug when rendering to PDF that doesn't follow the relative links in the document. Hopefully I can add this back in the future.
- Minor changes to `README.md`.

## v2.26.0

- Added a Documents type to `PSAnsiFileMap.json`.
- Added a parameter to `Convert-HashtableToCode` to output an inline string. (Issue #85)
- Added an alias `chc` for `Convert-HashtableToCode`.
- Added `Copy-HelpExample` command with an alias of `che`.
- Added `Open-PSScriptToolsHelp` to open a PDF version of `README.md` as a help manual.
- Fixed duplicate entry in `PSAnsiFileMap.json`.
- Revised regex patterns in `PSAnsiFileMap.json`. (Issue #83)
- Cleaned up code in `filesystem-ansi.format.ps1xml`.
- Modified `Convert-HashtableToCode` to (hopefully) better handle scriptblocks. (Issue #84)
- Updated `README.md`

## v2.25.1

- Fixed incorrect sequence for BlackRectangle in `$PSSpecialChar`. (Issue #82)
- Fixed incorrect ANSI for System files in `PSAnsiFileMap.json`.

## v2.25.0

- Added a set of ANSI mappings for temporary files and system files in `psansifilemap.json`.
- Added additional file extensions to `psansifilemap.json`.
- Added pointers, section sign, and black rectangle to PSSpecialChars hashtable.
- Modified `Show-Tree` to make the `InColor` parameter always available. (Issue #80)
- Modified `Add-Border` to use ANSI escape codes that will work in both Windows PowerShell and PowerShell 7.
- Updated `New-PSFormatXML` to better handle empty or null property values. (Issue #81)
- Help Updates

## v2.24.0

- Added parameter alias of `tb` for `-TextBlock` in `Add-Border`.
- Added parameter alias of `border` for `-Character` in `Add-Border`.
- Added `New-ANSIBar` command.
- Added `New-RedGreenGradient` command.
- Added `Write-ANSIProgress` command with an alias of `wap`.
- Defined a global variable called `$PSSpecialChar` which is a hash table select special characters you might want to use with `Add-Border` or `New-AnsiBar`.
- Added a table view to `modulecommand.format.ps1xml` and made it the default.
- Added a new table view called `verb` to `modulecommand.format.ps1xml`.
- Added `Get-PathVariable` with its own custom format file. (Issue #74)
- Added sample script `Get-Status.ps1`.
- Added global variable `$PSSamplePath` to point to the sample script location
- Modified `Add-Border` to adjust line length when ANSI escapes are part of the text. (Issue #79)
- Modified `Get-PSWho` to trim when using `-AsString`.
- Fixed bug in `New-PSFormatXML` what was writing an XML element to the pipeline when using `-Wrap`.
- Updated `Get-ModuleCommand` output to include the module name.
- Updated `serviceansi.format.ps1xml` and `filesystem-ansi.format.ps1xml` to use an escape sequence available to both Windows PowerShell and PowerShell 7.
- Fixed wrong type name in `serviceansi.format.ps1xml`.
- Help updates.
- Updated sample scripts.
- Updated `README.md`.
- Removed duplicate line of code in `New-PSFormatXML`.

## v2.23.0

- Updated `New-PSFormatXML` to include an option to wrap tables. (Issue #78)
- Updated `Add-Border` to include parameters to specify an ANSI sequence for the border and one for the text.
- Revised `Add-Border` to better support inserting blank lines.
- Updated `README.md`.

## v2.22.0

- Modified `Set-ConsoleTitle` to move parameter validation into the `Process` script block. (Issue #75)
- Modified `Get-FolderSizeInfo` to fix an enumeration bug when used in Windows PowerShell. (Issue #77)
- Added online help links for `Get-GitSize`, `Get-ModuleCommand` and `Remove-MergedBranch`.
- Updated `foldersizeinfo.format.ps1xml` to include a view called `TB` to display values in TB.

## v2.21.0

- Updated `Set-ConsoleTitle` and `Set-ConsoleColor` to display a warning if not in a console session. (Issue #75)
- Added `Get-GitSize` and format file `gitsize.format.ps1xml`
- Added a default ANSI color map file `psansimap.json`.
- Modified module to use a copy of `psansimap.json` in $HOME if detected. Otherwise, use the module's version.
- Create a global variable called `PSAnsiFileMap` from importing the `psansimap.json` file.
- Updated `Show-Tree` to use an ANSI color map. (Issue #69)
- Added `FileSystem-ansi.format.ps1xml` which adds a custom view called `ansi`. This colorizes files based on `$PSAnsiMap`.
- Updated `Show-Tree` to resolve child paths using `-LiteralPath`.
- Updated `README.md`

## v2.20.0

- Restructured `Get-FileSizeInfo` to better handle Windows PowerShell. (Issue #70)
- Added `Remove-MergedBranch` with an alias of `rmb`. (Issue #71)
- Added `Get-ModuleCommand` with an alias of `gmc`.
- Added `modulecommand.format.ps1xml` to format `Get-ModuleCommand` results.
- Added an alias of `shtree` for `Show-Tree` because `pstree` is a Linux command.
- Added parameter alias `files` for `-ShowItem` in `Show-Tree`.
- Added parameter alias `properties` for `-ShowProperties` in `Show-Tree`.
- Added parameter alias `ansi` for dynamic parameter `InColor` in `Show-Tree`. (Issue #73)
- Set the default parameter value for `-Path` in `Show-Tree` to the current directory.
- Modified `Show-Tree` to allow the user to specify an array of properties. This is a __breaking change__ as the parameter has been changed from a `switch` to `string[]`. (Issue #72)
- Removed `PROPERTY` label in `Show-Tree` output when displaying properties.
- Corrected errors in the module manifest.
- Added auto completer for `Runspace` parameter in `Remove-Runspace`.
- Added alias `rfn` for `New-RandomFileName`.
- Added alias `cfn` for `New-CustomFileName`.
- Updated `README.md`.
- `ChangeLog.md` clean up.

## v2.19.0

- Modified `Get-FolderSizeInfo` to use [system.collections.arraylist]` to improve performance. (Issue #68)
- Fixed bug in `Get-FolderSizeInfo` running in PowerShell 7 that wasn't including System files.
- Updated help for `Get-FolderSizeInfo`.
- Added online help link for `Get-PSScriptTools`.
- Added better error handling to `Test-EmptyFolder`.
- Added `Computername` property to PassThru output from `Test-EmptyFolder`.
- Added alias `fcc` for `Find-CimClass`.
- Added alias `pstree` for `Show-Tree`.
- Revised `Show-Tree` to use splatting for internal commands.
- Added a dynamic parameter `InColor` for `Show-Tree` to display results in ANSI color if running PowerShell 7.
- Added format file `serviceansi.format.ps1xml` to display service status colored when using PowerShell 7.
- Updated `README.md`.

## v2.18.0

- Fixed missing `ReleaseID` property in `Get-WindowsVersion`. (Issue #67)
- Added `BuildBranch` property to `Get-WindowsVersion`.
- Updated `windowsversion.format.ps1xml` to include new properties and not use Autosize.
- Added `Name` property to output from `Get-FolderSizeInfo` (Issue #66)
- Added a new table view called `name` for `Get-FolderSizeInfo`.
- Added `Get-PSScriptTools` function to display summary information about commands in this module.
- Added `psscripttools.format.ps1xml` to define a default table view for `Get-PSScriptTools`.
- Help updates.
- Added online help link for `Test-EmptyFolder`.
- Updated `README.md`.

## v2.17.0

- Updated `Get-FolderSizeInfo` to handle directory names like `[data]`. (Issue #65)
- Updated `Get-FolderSizeInfo` to show a TotalSize of 0 for empty directories. (Issue #64)
- Cleaned up code in `Get-FolderSizeInfo` script file now that it is part of this module.
- Added `Test-EmptyFolder`.
- Updated `README.md`.

## v2.16.0

- Fixed bug in `New-CustomFileName` when using a 24-hour value. (Issue #62)
- Updated `Test-ExpressionForm` to clear the text results. (Issue #61)
- Updated `Convertto-WPFGrid` to display a refresh message. (Issue #43)
- Updated `foldersizeinfo.format.ps1xml` to include a KB formatted view.

## v2.15.1

- Fixed bug in `Get-FolderSizeInfo` that was returning incorrect data. (Issue #60)
- Updated newer help with online links.
- Updated `README.md`.

## v2.15.0

- Added `Get-FolderSizeInfo` and its alias `gsi` along with a corresponding format.ps1xml file.
- Fixed IsWindows bug in `New-WPFMessageBox`. (Issue #59)
- Fixed IsWindows bug in `Convertto-WPFGrid`, `Find-CimClass`, `Test-ExpressionForm`, `Get-WindowsVersion`,`Get-WindowsVersionString` and `Invoke-InputBox` by using a new function `Test-IsPSWindows`.
- Updated `Get-PSWho` to better work cross-platform.
- Help updates.
- Updated `README.md`.

## v2.14.1

- Fixed bug in `Save-GitSetup` that relies on `$IsWindows` (Issue #58). Now this command should work on Windows PowerShell 5.1 as well.
- Updated help for `Save-GitSetup`.
- Updated help files with missing online links.

## v2.14.0

- Updated `New-PSFormatXML` to support Wide table formats. (Issue #55)
- Updated `Test-ExpressionForm` to better handle non-Windows platforms.
- Added `Save-GitSetup` to download the latest x64 version of `git`.
- Modified `New-CustomFileName` to support a new template element, `%hour24`. (Issue #57)
- Added `tv` alias to `Out-VerboseTee`.
- Added `ConvertTo-LexicalTimespan`.
- Added `ConvertFrom-LexicalTimespan`.
- Updated manifest description.
- Updated help for `Get-PowerShellEngine`.
- Updated `README.md`.

## v2.13.0

- Added `New-RunspaceCleanupJob` command to be used with WPF commands running in a new runspace.
- Modified `ConvertTo-WPFGrid` to clean up runspace when closed. (Issue #25)
- Modified `ConvertTo-WPFGrid` to attempt to run on all platforms and gracefully fail where it won't work. (Issue #56)
- Added 'Convert-EventLogRecord' function and its alias `clr`.
- Added `Rename-Hashtable` function and its alias `rht`.
- Updated `Convertto-Markdown` to include options to format as a table.
- Updated module manifest to export `ConvertTo-WPFGrid` to all hosts. The code in the command will determine compatibility.
- Updated `Find-FileItem` to work better cross-platform.
- Updated `New-WPFMessagebox` to work on PowerShell 7 on Windows platforms.
- Help Updates.
- Modified module and manifest to export all functions regardless of edition. Any OS limitations will be handled on a per-command basis.
- Updated `README.md`.

## v2.12.0

- Help updates.
- Replaced GitHub online help links with bit.ly short links.
- Minor updates to `README.md`.
- Updated `Out-More` to work better with output from `Get-Help`.

## v2.11.0

- Added a grouping feature to `New-PSFormatXML`. (Issue #54)
- Modified `New-PSFormatXML` to open the XML file if the command is run in VS Code as part of `-PassThru`.
- Help updates.

## v2.10.0

- Added `Test-WithCulture`.
- Fixed typo in `Copy-Command` help.
- Created YAML formatted help files.
- Updated `README.md`.
- Updated help documentation with online links.
- Updated `PSScriptTools.md`.

## v2.9.0

- Added `ConvertFrom-Text` and its alias `cft`. (Issue #53)
- Updated `ConvertTo-UTC` to include an option to format the result as a sortable string. (Issue #52)
- Added `Get-WhoIs` and `whoisresult.format.ps1xml`.
- help documentation clean up.
- Updated and reorganized `README.md`.

## v2.8.0

- Added `Get-FileItem` with an alias of `pswhere`.
- Renamed `timezonedata.format.ps1xml` to all lower case.
- Replaced using `Out-Null` to use `[void]` in `Convertto-WPFGrid`,
 `New-PSFormatXML`, `Copy-Command`,`New-WPFMessageBox`, `Write-Detail`,
 `Test-Expression`,`Invoke-Inputbox`. (Issue #47)
- Revised warning message in `New-PSFormatXML`. (Issue #50)
- Fixed icon path error in `New-WPFMessageBox`.

## v2.7.0

- Modified `ConvertTo-LocalTime` to allow for locations supporting Daylight Saving Time. (Issue #44)
- Fixed bug in `New-PSFormatXML` that wasn't using auto detected property names. (Issue #45)
- Added `Get-TZList` and `Get-TZData` commands.
- Added format file `timeZoneData.format.ps1xml`.
- Modified `ConvertTo-WPFGrid` to allow the user to control which gridlines are displayed
- Modified `New-CustomFilename` to improve parameter help.
- Modified `New-CustomFilename` to add %seconds.
- Modified `New-CustomFilename` so that %month, %day and %minute will use a leading zero if necessary.
- Added new help examples for `New-CustomFilename`.
- Help updates.
- File re-organization.
- Updated `README.md`.

## v2.6.0

- Modified `Convertto-WPFGrid` to set maximum size equal to the total available working area. (Issue #36)
- Modified `Convertto-WPFGrid` to change the cursor on refresh and display a refresh message in the title bar
- Added InitializationScript option for `ConvertTo-WPFGrid`. (Issue #42)
- Added `ConvertTo-LocalTime` with an alias of `clt`.
- Updated `README.md`.
- Help updates.

## v2.5.0

- Fixed bug which was hiding the horizontal scroll bar in `ConvertTo-WPFGrid`. (Issue #40)
- Fixed bug which prevented the status bar from updating when manually refreshing in `ConvertTo-WPFGrid`. (Issue #34)
- Changed time display in `ConvertTo-WPFGrid` as a timespan instead of raw seconds. (Issue #41)
- Markdown help cleanup.
- Added `Set-ConsoleTitle`.
- Added `Set-ConsoleColor`.
- Updated `README.md`.

## v2.4.0

- Made datagrid in `ConvertTo-WPFGrid` read-only. (Issue #38)
- Modified the datagrid in `ConvertTo-WPFGrid` to better handle resizing. (Issue #36)
- Modified the statusbar in `ConvertTo-WPFGrid` to better handle resizing. (Issue #37)
- Modified form in `ConvertTo-WPFGrid` to better fit in the screen and not exceed the screen area. (Issue #39)
- Added parameter to allow usage of local variables in `ConvertTo-WPFGrid`. (Issue #35)
- Help updates.
- Reorganized `README.md`.

## v2.3.0

- Fixed bug in `ConvertTo-WPFGrid` that wasn't updating last update time. (Issue #30)
- Modified `ConvertTo-WPFGrid` to allow the user to load their profile scripts into the runspace. (Issue #29)
- Modified auto-sizing code in `ConvertTo-WPFGrid`.
- Modified `ConvertTo-WPFGrid` to automatically display scroll bars when necessary.
- Modified `New-PSFormatXML` to display a warning on invalid property names. (Issue #33)
- Added `Get-myTimeInfo`, `ConvertTo-UTCTime` and `ConvertFrom-UTCTime` (Issue #31)
- help updates.
- Updated `README.md`.

## v2.2.0

- Code revisions in `ConvertTo-WPFGrid` (Issue #27)
- Updated `Get-ParameterInfo` to reflect dynamic parameters. (Issue #28)
- Updated `Get-PSLocation` to better reflect locations and use a custom format file.
- Updated `Get-WindowsVersion` with custom type for format file. Also better handling of non-Windows platforms.
- Updated `Get-WindowsVersionString` to include the computername.
- Updated `New-WPFMessageBox` to gracefully exit if running on PowerShell Core.
- Updated `Test-ExpressionForm` to gracefully exit if running on PowerShell Core.
- Updated `New-RandomFilename` to better reflect locations using `[environment]`.
- Modified manifest to be more aware of PSEdition and only load compatible commands.
- Help updates.
- Updated `README.md`.

## v2.1.0

- Added parameter to allow the user to specify a type name with `New-PSFormatXML`. (Issue #26)
- Added `Get-ParameterInfo` command with an alias of `gpi`.
- Updated help for `Optimize-Text`.
- Help updates.
- Updated `README.md`.

## v2.0.0

- Added `New-PSFormatXml` and its alias `nfx`.
- Raised minimum PowerShell version to 5.1.
- Modified manifest to support both `Desktop` and `Core`.
- Added `Remove-Runspace`.
- Modified `ConvertTo-WPFGrid` to AutoSize the display and support an automatic refresh.
- Modified `ConvertTo-WPFGrid` to use a runspace. (Issue #22)
- Updated `README.md`.
- Updated help documentation.
- Raised version number to reflect a number of potentially breaking changes.

## v1.8.1

- minor corrections to `Compare-Module`. (Issue #21)

## v1.8.0

- Fixed typo in `Write-Detail`. (Thanks @AndrewPla)
- Added `Compare-Module` function. (Issue #19)
- Added `Get-WindowsVersion` function. (Issue #20)
- Added `Get-WindowsVersionString` function.
- Updated `README.md`.
- Updated module manifest.
- reorganized module.
- Updated Pester test for `Test-Expression`.
- Updated external help file.

## v1.7.0

- Added `New-WPFMessagebox` function. (Issue #11)
- Added alias `nmb` for `New-WPFMessageBox`.
- Added icon files for the WPF Message box.
- Updated `README.md`.

## v1.6.0

- Added `Optimize-Text` and its alias `ot`.
- Added `Show-Tree`.
- Help and documentation updates.

## v1.5.1

- code cleanup for the published module in the PowerShell Gallery.

## v1.5.0

- Added `Select-First` and its alias `first`.
- Added `Select-Last` and its alias `last`.
- Added `Get-MyVariable` and its alias `gmv`.
- Added `New-PSDriveHere` and its alias `npsd`.
- Updated `README.md`.

## v1.4.0

- Added hashtable tools.
- Updated `README.md`.
- minor code cleanup.

## v1.3.0

- Fixed documentation errors for `Out-ConditionalColor`. (Issue #13)
- Added alias definitions to functions.
- Added my `Test-Expression` commands. (Issue #14)
- Added my `Find-CimClass` function. (Issue #16)
- Added my `ConvertTo-Markdown` function. (Issue #17)
- Added `ConvertTo-WPFGrid`. (Issue #15)
- help cleanup and updates.
- Code cleanup and formatting.

## v1.2.0

- Updated `Write-Detail`.
- Updated `README.md`.

## v1.1.0

- Cleaned up ToDo code. (Issue #12)
- Updated `README.md`.
- Help cleanup.

## v1.0.1

- fixed version number mistake.
- updated `README.md`.

## v1.0.0

- initial release to the PowerShell Gallery.

## v0.5.0

- Added `Get-PSLocation` function. (Issue #4)
- Added `Get-PowerShellEngine` function. (Issue #5)
- Added `Out-More` and alias `om`. (Issue #10)
- Added icon to manifest.
- Added `Invoke-InputBox` and alias `ibx`.
- Added code to insert ToDo comments for the ISE and VSCode. (Issue #7)
- Updated `README.md`.
- Updated documentation.

## v0.4.0

- Added `Copy-Command`. (Issue #2)
- Updated `Copy-Command` to open a new file in the ISE or VSCode.
- Added Format functions. (Issue #3)
- Updated help.
- Added new sample files.

## v0.3.0

- Added help documentation.
- Updated `README.md`.
- Added samples.
- Reverted `Get-PSWho` to not trim when using -AsString.
- Added code to `New-CustomFileName` to preserve case for non-placeholders.
- Modified `Out-VerboseTee` to turn on VerboseTee.

## v0.2.0

- Modified verbose output to use `Write-Detail`.
- Expanded aliases to full cmdlet names.
- Modified `Get-PSWho` to trim when using -AsString.
- Added `Out-ConditionalColor`.
- Added `Get-RandomFileName`.
- Added `New-CustomFileName`.

## v0.1.0

- initial module files
