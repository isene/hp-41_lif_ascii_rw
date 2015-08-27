# hp-41_lif_ascii_rw
## HP-41: LIF to ASCII read/write

**lifasread** – a Ruby script to read an ascii file stored in a lif-formated file (used by the HP-41 as file format on mass storage mediums. Tested on Linux. Run the script with the -h (or –help) option to see how it is used.

**lifaswrite** – a Ruby script to write a text file to a lif-formated file (the reverse of “lifasread”. Run the script with the -h (or –help) option to see how it is used.

**NAME**<br>
    lifasread - LIF ascii file read

**SYNOPSIS**<br>
    lifasread [-hv] [--help, --version] [lif-file] [destination file]

**DESCRIPTION**<br>
    lifasread is used as a tool for HP-41 or HP-71 connected to a PC.
    lifasread reads an ascii file inside a lif formated file.
    It reads only the first ascii file and so the lif-file should
    be consisting of only one file. To create a lif file with only
    one file from an HP-41, have your calculator hooked to the PC
    and/or a lif-writing mass storage device and XEQ "NEWM 001". Then
    put the size of the ascii file in the X register and its name in
    the Alpha register. Then XEQ "CRFLAS". Fill it with content as needed,
    and XEQ "SAVEAS" to save the file to mass storage.
    Then from your PC execute lifasread to extract the content.
    The sister-script "lifaswrite" will reverse the process.

**OPTIONS**<br>
-h, --help<br>
    Show this help text
    
-v, --version<br>
    Show the version of imap_search

**EXAMPLE**<br>
`lifasread hdrive1.lif textfile.txt`

This would extract the ascii file from "hdrive1.lif" and write it to the file "textfile.txt".

**NAME**<br>
    lifaswrite - LIF ascii file write

**SYNOPSIS**<br>
    lifaswrite [-hv] [--help, --version] [text file] [destination lif-file]

**DESCRIPTION**<br>
    lifaswrite is used as a tool for HP-41 or HP-71 connected to a PC.
    lifaswrite takes text file and writes an ascii file inside a lif formated file.
    It creates a lif-file of 32KB with only one ascii file in it. 
    The name of that ascii file is the first line in the text file.
    To read the file into your HP-41, you make sure the lif-file resides
    on the a mass storage device accessible from the calculator and then
    XEQ "GETAS". The ascii file will then be loaded into Extended Memory.
    The sister-script "lifasread" will read an ascii file from within a lif-file.

**OPTIONS**<br>
-h, --help<br>
    Show this help text
    
-v, --version<br>
    Show the version of imap_search

**EXAMPLE**<br>
`lifasread textfile.txt hdrive1.lif`

This would create the lif-file "hdrive1.lif" with the content of "textfile.txt" as an ascii file within the lif-file.

