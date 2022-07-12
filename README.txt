# Readme
This file describes how to use this software

This project has a graded risk level (RL) of negligible and a practice level (PL) of 0 because the consequence and likelihood of an undesirable event are both negligible.  See [LPS QA001](https://lps.web.sandia.gov/policy/QA001?section=requirements&h1=quality-assurance-program-(qap)) for more guidance on Sandia's software quality assurance program.

This project adheres to [Semantic Versioning](http://semver.org/)

This file uses Markdown format from [Daring Fireball](http://daringfireball.net/projects/markdown/)

## Development

### Dependencies

- LabVIEW 2018 Version 18.0.1 (32-bit)

### Modifications

This software is developed under a LabVIEW project file as a single top-level VI.  To modify the software:

1. Open the "SuNLaMP.lvproj" LabVIEW project file.
2. Open the most recent "UI Main - SuNLaMP vX.Y.Z.vi"
3. Save this file as a "Copy" with the "Open additional copy" option and the "Add copy to SuNLaMP.lvproj" option checked to create a new version of the UI.  Refer to [Semantic Versioning](http://semver.org/) when incrementing the version number.
4. Instructions are included in the block diagram for adding new indicators and controls as these are the most common operations.

The "Scan Interface" programming mode is used for interfacing with the CompactRIO hardware.  To modify the channel layout or signal scaling:

1. Expand the "NI-cRIO..." listing
2. Right-click on the "Chassis" listing and select "Multiple Variable Editor"
3. Update the table as appropriate and press the "Done" button in the bottom-right corner
4. While connected to the CompactRIO hardware, right-click on the "Chassis" listing and select "Deploy All"
5. Update the string array UUIDs located in the "Read Network-published IO Shared Variables.vi" sub-VIs as necessary to match any changes to the channel listing

### Deployment

To deploy this software first you must first build the UI into an executable and then build the installation files.

1. Right-click the "SuNLaMP HMI" entry under the "Build Specifications" and select "Properties"
2. Under "Source Files" remove the old VI from the "Startup VIs" listing and add the new one into it and select the "Ok" button
3. Right-click the "SuNLaMP HMI" entry under the "Build Specifications" and select "Build"
4. Right-click on the "SuNLaMP" entry under the "Build Specifications" and select "Build"
5. The installation files will be located at .\builds\Volume

### Installation

Under the appropriate build folder select and run the "setup.exe" file.  This installation directory contains all the run-time libraries required to install and run the software on any Windows machine without needing to install any LabVIEW development environment version.

*NOTE* It may not be possible to install this software on a machine with an existing LabVIEW development environment installed with a version earlier than that used for development.  In this case the existing LabVIEW software should be updated or un-installed in order for this software to be installed.

## Contribute

Please review stay consistent with the README and CHANGELOG files before modifying any source code.

[readme]: .\README.txt
[changelog]: .\CHANGELOG.txt
[source]: .\