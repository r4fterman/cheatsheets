# BASH

## Search in all files like <trace.log*> containing "mySearchString"
```
    grep "mySearchString" trace.log*
```

## List of files containing "lorem ipsum" (ignore case sensitve)
```
    grep -li "lorem ipsum" *
```

## Search in all files like <trace.log*> containing "mySearchString" recursively
```
    grep -R "mySearchString" <trace.log*> .
```

## Search in all files like <pom.xml> containing "<scope>runtime</scope>", print the line itself and print 1 line after and 3 lines before
h - print file name
n - line number
```
    grep --include="pom.xml" -nRHi "<scope>runtime</scope>" -A1 -B3 *
```

## Find all files ending with <.java> containing "class? " recursively
```
    egrep -r "class.*?{\s+}" --include=*.java .
```

## Find all files recursively ending with <*Test.java> and containing "org.mockito" or "org.easymock"
```
    grep -lR "org.mockito" --include=*Test.java * | xargs grep "org.easymock"
```

## Find all files recursively ending with <*Test.java> and containing "EasyMockSupport" but not "replayAll"
```
    grep -lR "EasyMockSupport" --include=*Test.java * | xargs grep -L "replayAll"
``` 

## Print lines in a file
```
    wc -l
```

## Count duplicate lines in a file
```
    sort <file> | uniq -c
```

## Find all files with a size of 2 bytes
```
    find . -type f -size 2c -exec ls {} \;
```

## Count all files in a folder
```
    ls -1 ./ | wc -l
```

## Print last lines of file and color lines containing "ERROR" red
tail -f /opt/tomcat-instances/logs/catalina.out | perl -pe 's/.*ERROR.*/\e[1;31m$&\e[0m/g'

## Print the nth column of a file
```
    awk -v x=2 '{print $x}' <file>
```

## Print all but the first 2 columns
```
    awk '{$1=$2=""; print $0}' <file>
```

## Execute command and print on console AND into a file
```
    ls 2>&1 | tee /tmp/ls.txt
```

## Copy all pom.xml and there folder content into a new destination folder
```
    find . -name pom.xml | pax -0 -rw /targetFolder
```

## Build checkSum on all WAR files and validate (later on)
```
    find . -regex ".*war$" -print0 | xargs -0 shasum -b > shasum.original
    shasum -c shasum.original
```

## Show all PIDs and the used ports
```
    sudo netstat -pltun
```