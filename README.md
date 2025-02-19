# Conllu Editor install

## Requirements

Java 11:
 - [Mac (apple silicon)](https://www.dropbox.com/scl/fi/xe42zdgp83i5zj9v0tvgd/jdk-11.0.24_macos-aarch64_bin.dmg?rlkey=ole9lxa6v2lynuy6ehu9lc757&dl=1)
 - [Mac (x86)](https://www.dropbox.com/scl/fi/5azycwb7elynbyaj09pfs/jdk-11.0.24_macos-x64_bin.dmg?rlkey=vyqlckklvxwcgn7ff15h3puqd&dl=1)
 - [Windows](https://www.dropbox.com/scl/fi/megwt9ytu6bs71hc4skva/jdk-11.0.24_windows-x64_bin.exe?rlkey=52p5qmn2gcodeerpewpn39cky&dl=1) 

Git
 - [Git (Windows)](https://git-scm.com/downloads/win)

Python
 - [Python 3](https://www.python.org/downloads/)

in windows setup env variables and run ```pip install regex```  

## Install

Download conllu editor
 - [Releases](https://github.com/Orange-OpenSource/conllueditor/releases) 

or

 - [ConlluEditor 2.28](https://github.com/Orange-OpenSource/conllueditor/releases/download/V2.28.0/conllueditor-2.28.0.zip)

Unzip conllueditor

go in the conllueditor folder 
``` 
cd conllueditor-2.28.0
```
clone ud tools
```
git clone https://github.com/UniversalDependencies/tools.git
```

copy ```conf``` folder into the conllu editor folder


create a working directory into conllu editor folder i.e. ```works```
```
mkdir works
```

copy the conllu files into working directory.

and

initialize git in working directory 

```
cd works
git init
git add .
```

 
 

Run from your conllu editor folder with:

```
java -jar ./target/ConlluEditor-2.28.0-jar-with-dependencies.jar --validator conf/validator.conf --UPOS conf/cpos.ud --deprels conf/deprels.json --features conf/feats.json --language la  --rootdir  ./gui ./works/trainingTreebank_set1_practice 8888
```

windows 
``` 
java -jar ./target/ConlluEditor-2.28.0-jar-with-dependencies.jar --validator conf/validatorWin.conf --UPOS conf/cpos.ud --deprels conf/deprels.json --features conf/feats.json --language la  --rootdir  ./gui ./works/trainingTreebank_set1_practice 8888
```

## Create an sh launcher files
with your text editor create a file with this content:
```
!#/bin/bash

java -jar ./target/ConlluEditor-2.28.0-jar-with-dependencies.jar --validator conf/validator.conf --UPOS conf/cpos.ud --deprels conf/deprels.json --features conf/feats.json --language la  --rootdir  ./gui $1 8888
```
save it in the conllueditor folder as ```run.sh```

in the terminal give the exec permission to the script with
```
chmod a+x run.sh
```
run the script with:
```
./run.sh works/<file_to_be_annotate>
```
or
```
sudo ./run.sh works/<file_to_be_annotate>
```

> $${\color{red}Note:}$$ All the examples are basesd on the conllueditor 2.28.0 version. if you use a different version please change $${\color{red}2.28.0}$$ in all the commands above with the correct verison the you use.



