# Extract tar.gz command
`tar -xvf archive.tar.gz -C /where/to/extract`

Where:
* `-x` extract
* `-v` print the names of the files being extracted on the terminal
* `-f` the file to extract
* `-C` where to extract

# Remove
## file
`rm path/to/file`
## directory
`rm -r path/to/directory`

Where:
* `-r` recursive
* `-f` no prompt before delete

# Edit PATH
1. `[code/nano] ~/.profile`
2. Add the new path `export PATH=/path/to/location:$PATH`
3. Reload PATH 
    1. `cd ~`
    2. `. .bashrc`