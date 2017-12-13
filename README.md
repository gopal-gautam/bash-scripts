# Some commonly used bash scripts

## Remove country specific sources in ubuntu apt sources list
```bash
sudo sed -i -re 's/\w+\.archive\.ubuntu\.com/archive.ubuntu.com/g' /etc/apt/sources.list
```

## List files with null last character. Used to find invalid json files as in json files, the last character should be ']' or '}'
```bash
for f in $(ls); do { a=$(tail -c 1 $f); if [ "$a" == "" ]; then echo $f; fi;} done;
#Remove it
for f in $(ls); do { a=$(tail -c 1 $f); if [ "$a" == "" ]; then rm $f; fi;} done;
```

## Remove files newer than specific date and less than specific size (size specified in no. of characters)
```bash
find . -type f -newermt 2017-06-11 -and -size 13c -exec rm {} \;
```
