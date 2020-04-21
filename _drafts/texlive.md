
The texlive path: pathtotexlive/texlive/ include two subdirectories: 2019 and texmf-local.

Run the script pathtotexlive/texlive/2020/tlpkg/installer/uninst.bat to uninstall the old texlive(version 2019).

Run the script install-tl-windows.bat to install the new texlive. 

Choose the basic scheme and the xetex.

Then install the needed packages.

The package list:
- ctex: for Chinese
- unicode-math
- stix2-otf: for using the stix 2 fonts
- datetime: for the date format
- elsarticle: for the articles to elsevier journals