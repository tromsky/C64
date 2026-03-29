# C64
Collection of C64 programs and documentation for learning


## Documentation and Resources
- Pickled Light [C64 User's Guide and Programmer's Reference Guide](https://pickledlightprojects.com/documents/c64-guides/)
- [Kick Assembler Guide](https://theweb.dk/KickAssembler/KickAssembler.pdf)


## Requirements

### [Java Development Kit](https://formulae.brew.sh/formula/openjdk)
`brew install openjdk`

### [Kick Assember](https://theweb.dk/KickAssembler/Main.html#frontpage)
[Download link](https://theweb.dk/KickAssembler/KickAssembler.zip)
- Unzip the package and note the location of the `KickAss.jar` file

### [vice Commodore Emulator](https://formulae.brew.sh/formula/vice)
`brew install vice`

### [KickAss (C64)](https://marketplace.visualstudio.com/items?itemName=CaptainJiNX.kickass-c64)
- VS Code extension


## Configuration

### vice
- Launch with command `x64sc`
- Preferences > Settings... > Machine > Model > Model > C64 NTSC
- Preferences > Settings... > Display > VIC-II > Render filter > Unfiltered
- Preferences > Save settings

### VS Code & KickAss (C64) Extension
- Extensions > KickAss (C64) > Cog Icon > Settings > Workspace
- Kick Ass Jar
    - Add path to Kick Ass Jar file
- Vice Bin
    - Add the path to Vice (C64)
        - `which x64sc`
- Alternatively, add this to `.vscode/settings.json` after confirming the paths

```
{
    "kickass-c64.kickAssJar": "/Users/<user>>/projects/kickass/KickAssembler/KickAss.jar",
    "kickass-c64.viceBin": "/opt/homebrew/bin/x64sc"
}
```


## Usage

- Starting in VS Code in a `.asm` file, hit `fn-F5`
- This will launch vice with the program
- In the assembly file, `* = $c000` indicates that the program will begin at hex location `$c000`
- Use a hex to dec tool to find the decimal value
    - e.g. hex `$c000` is dec `49152`
- In vice, enter `SYS <dec value>`
    - e.g. `SYS 49152`