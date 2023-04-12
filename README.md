# suri
Train LLM models with vast.ai cloud GPU cheaply

## Install vast cli
Install vast cli following the documentation here:
[vast cli](https://cloud.vast.ai/cli/)

### Set API key
```bash
bin/vast set api-key your-api-key
```

## Basic idea
1. Get a return list with vast search command
2. Turn the list into a normal csv format file by replace the blanks between fields into comma.
```bash
sed 's/[ ][ ]*/,/g' list.txt > list.csv
```
3. Load the converted csv file into a python dictionary list.
4. Find proper instance from the list.
5. Create instance with following command:
```bash
bin/vast create instance 36842 --image vastai/tensorflow --disk 32
```
