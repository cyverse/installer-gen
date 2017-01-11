# installer-gen

A generator for self-extracting installers.

It generates a posix shell script that has a GNU compressed tarball attached to the end of it. The generated shell script will let the user choose the place where the tarball is expanded. Optionally, the shell script can be generated so that it executes shell commands to set up the environment once the tarball ball has been expanded.

## Usage

    gen-installer INSTALLER_NAME TGZ [SETUP_SCRIPT]

INSTALLER_NAME is the name of the installer to be created. 

TGZ is gnu compressed tar file encapsulating the contents of the software to be 
installed. 

If provided, SETUP_SCRIPT is a POSIX shell script that sets up the software once
TGZ has been expanded.

The created installer will accept an optional command line argument allowing the
user to specify where the contents of TGZ will be expanded. If the user doesn't
specify the location on the command line, the user will be asked.

If SETUP_SCRIPT is provided, the absolute path to the contents of TGZ will be 
exported in the variable INSTALL_BASE.

## Dependencies

gen-installer requires bash and tar to be installed.
