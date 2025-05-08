[![Build and Test](https://github.com/milliewalky/setup-7-zip/actions/workflows/sample.yml/badge.svg)](https://github.com/milliewalky/setup-7-zip/actions/workflows/sample.yml)

# Setup 7-Zip

This action downloads, unpacks, and configures 7-Zip for use in GitHub Actions workflows. 7-Zip is a free and open-source file archiver. 7-Zip is unpacked under the temporary directory of a runner.

# Usage

<!-- start usage -->
```yaml
- uses: drajabr/actions-7-zip-win
  with:
    tag: ""                 # Optional > default: latest > 7-Zip release tag from its GitHub Releases page e.g. 24.07.
    execute: true           # Optional > default: false  > Excute command 7z <options> <in> <out>
    in: ./dist              # Required > yes, if execute is enabled, else it just downloads 7z and adds 7z command to PATH
    out: ./build/dist.zip   # Optional > default: same as input but with .7z extension
    options: a -tzip        # Optional > default: add input to .zip archive
```
<!-- end usage -->

This action appends 7-Zip to a temporary PATH file, so doing this:

```
7z a -t7z {dst}.7z {src}
```

Should do just fine.

Optionally, for **WINDOWS RUNNER ONLY** enable `excute: true` and add the rest of options to excute 7zip command with your in/options/out combinations.

Refer to [documentation](https://documentation.help/7-Zip/), or use [@axelstudios/7-Zip Command Line Reference Wizard](https://axelstudios.github.io/7z/#!/) to build your options.


# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)

# Credits

[@milliewalky](https://github.com/milliewalky) Original code author.
