# elf info #
This is a very minimal elf parser to display the sections and symbols in an ELF file.

## How it works ##
This is a very simple ELF parser. It doesn't use libelf . This first checks the Elf Header,
And depending on the Information available it process the elf file and displays the info.

It may not work on sstriped ELFs, because this is dependent on SHDR(section headers).
One might modify it to use PHDRs.

**Need your Code contribution**