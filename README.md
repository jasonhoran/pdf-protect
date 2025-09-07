# PDF Protect
Linux script to add and remove password protection to .pdf files via Nautilus or other file managers.
# Installation
This is a collection of 2 bash scripts, which you should copy to the ~/.local/share/nautilus/scripts/ folder.

For Caja (the file manager used in Ubuntu Mate, etc.) the script directory is the ~/.config/caja/scripts/ folder.  Check your distros documentation for the appropriate script folder for your file manager, if different.

You need to set appropriate execution rights (via Properties > Permissions > Allow executing file as program or `chmod +x`). 

You must also ensure that you have Zenity and PDF Toolkit installed. In order to consistently remove .pdf passwords it is also required that you install qPDF so that you can handle AES256-encrypted files.
`sudo apt install zenity pdftk qpdf`
# Usage
Once installed, right clicking on a PDF file will show a "Scripts" menu, with a both a "Password Protect PDF to Done" and a "Remove PDF Password to Done" submenu entries. A dialog box will ask for a password.  If it does not already exist, the script will create a /Done folder.  Using the password supplied, the .pdf file will either be password-protected or the password will be removed and the new file will be saved in the /Done folder.  The original file will be preserved.
# Alternative
I also found that some files could not be decrypted using pdftk.  These are often encrypted using the AES256 algorithm.  However qPDF might work, so this has been included in the "Remove PDF Password to Done" script.  The qPDF tool will be automatically tried if password removal using pdftk fails before giving an error message.
# Credits
Thanks to Ricardo Ferreira (https://launchpad.net/compress-pdf/) for the original work on Compress PDF which was the inspiration for this project.

Thanks to my work colleagues for their work on translating this project.  Ania Lala, Dr Maury Guerrero, Hariraj Ji, Dr Georgios Diakidis, Dr Paul Ayadoe, Dr Khalid Siddig, Dr Asim Nayeem.
