# Visual Studio IDE for Informix ESQL/C application development
Copyright (c) 2016 Sathyanesh Krishnan. All rights reserved.

## Using Visual Studio IDE for Informix ESQL/C development
This sample demo provide jump start for Informix ESQL/C application developer by providing a Visual Studio Project setup for their development work. With this project setup, an ESQLC application can be compile, debug and run from the IDE. The project uses custom build setup for preprocessing ESQL/C file (the file with.ec extension). The demo has project file for VS2005 and VS2015.  

In short these are the hardcoded settings for the time being.  
Assume that you have installed CSDK at
```
C:\informix
```

Then supplied the project property as shown below, you may generalize these setting based on your CSDK installation.

```
Project -> Properties:
Configuration Properties:
General:
Character Set = Use Multi-Byte Character Set

C/C++ -> General
Additional Include Directories = C:\informix\incl\esql

Linker -> General
Additional Options = isqlt09a.lib
Additional Library Directories=c:\informix\lib
```


Custom Build rules for processing EC files  
In short the build rules are  
```
Commands:
esql -dcmdl -p  %(FullPath) .\%(Filename).c

Outputs:
.\%(Filename).c

Description:
ESQLC Pre Processor
```

For more informatin about VS Custom Build option, please see.  
[https://msdn.microsoft.com/en-us/library/hefydhhy.aspx](https://msdn.microsoft.com/en-us/library/hefydhhy.aspx)






