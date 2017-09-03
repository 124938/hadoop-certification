#### Help on hadoop command

```
hadoop help
Usage: hadoop [--config confdir] COMMAND
       where COMMAND is one of:
  fs                   run a generic filesystem user client
  version              print the version
  jar <jar>            run a jar file
  checknative [-a|-h]  check native hadoop and compression libraries availability
  distcp <srcurl> <desturl> copy file or directories recursively
  archive -archiveName NAME -p <parent path> <src>* <dest> create a hadoop archive
  classpath            prints the class path needed to get the
  credential           interact with credential providers
                       Hadoop jar and the required libraries
  daemonlog            get/set the log level for each daemon
  trace                view and modify Hadoop tracing settings
 or
  CLASSNAME            run the class named CLASSNAME
```

#### Help on filesystem specific option

```
hadoop fs -help
Usage: hadoop fs [generic options]
	[-appendToFile <localsrc> ... <dst>]
	[-cat [-ignoreCrc] <src> ...]
	[-checksum <src> ...]
	[-chgrp [-R] GROUP PATH...]
	[-chmod [-R] <MODE[,MODE]... | OCTALMODE> PATH...]
	[-chown [-R] [OWNER][:[GROUP]] PATH...]
	[-copyFromLocal [-f] [-p] [-l] <localsrc> ... <dst>]
	[-copyToLocal [-p] [-ignoreCrc] [-crc] <src> ... <localdst>]
	[-count [-q] [-h] [-v] <path> ...]
	[-cp [-f] [-p | -p[topax]] <src> ... <dst>]
	[-createSnapshot <snapshotDir> [<snapshotName>]]
	[-deleteSnapshot <snapshotDir> <snapshotName>]
	[-df [-h] [<path> ...]]
	[-du [-s] [-h] <path> ...]
	[-expunge]
	[-find <path> ... <expression> ...]
	[-get [-p] [-ignoreCrc] [-crc] <src> ... <localdst>]
	[-getfacl [-R] <path>]
	[-getfattr [-R] {-n name | -d} [-e en] <path>]
	[-getmerge [-nl] <src> <localdst>]
	[-help [cmd ...]]
	[-ls [-d] [-h] [-R] [<path> ...]]
	[-mkdir [-p] <path> ...]
	[-moveFromLocal <localsrc> ... <dst>]
	[-moveToLocal <src> <localdst>]
	[-mv <src> ... <dst>]
	[-put [-f] [-p] [-l] <localsrc> ... <dst>]
	[-renameSnapshot <snapshotDir> <oldName> <newName>]
	[-rm [-f] [-r|-R] [-skipTrash] <src> ...]
	[-rmdir [--ignore-fail-on-non-empty] <dir> ...]
	[-setfacl [-R] [{-b|-k} {-m|-x <acl_spec>} <path>]|[--set <acl_spec> <path>]]
	[-setfattr {-n name [-v value] | -x name} <path>]
	[-setrep [-R] [-w] <rep> <path> ...]
	[-stat [format] <path> ...]
	[-tail [-f] <file>]
	[-test -[defsz] <path>]
	[-text [-ignoreCrc] <src> ...]
	[-touchz <path> ...]
	[-usage [cmd ...]]
```

#### Help on du command of filesystem

```
hadoop fs -help du
-du [-s] [-h] <path> ... :
  Show the amount of space, in bytes, used by the files that match the specified
  file pattern. The following flags are optional:
                                                                                 
  -s  Rather than showing the size of each individual file that matches the
      pattern, shows the total (summary) size.
  -h  Formats the sizes of files in a human-readable fashion rather than a number
      of bytes.
  
  Note that, even without the -s option, this only shows size summaries one level
  deep into a directory.
  
  The output is in the form 
  	size	disk space consumed	name(full path)
```

#### Help on mkdir command of filesystem

```
hadoop fs -help mkdir
-mkdir [-p] <path> ... :
  Create a directory in specified location.
                                                  
  -p  Do not fail if the directory already exists
```

#### Help on ls command of filesystem

```
hadoop fs -help ls
-ls [-d] [-h] [-R] [<path> ...] :
  List the contents that match the specified file pattern. If path is not
  specified, the contents of /user/<currentUser> will be listed. Directory entries
  are of the form:
  	permissions - userId groupId sizeOfDirectory(in bytes)
  modificationDate(yyyy-MM-dd HH:mm) directoryName
  
  and file entries are of the form:
  	permissions numberOfReplicas userId groupId sizeOfFile(in bytes)
  modificationDate(yyyy-MM-dd HH:mm) fileName
                                                                                 
  -d  Directories are listed as plain files.
  -h  Formats the sizes of files in a human-readable fashion rather than a number
      of bytes.
  -R  Recursively list the contents of directories.
```

#### Help on cat command of filesystem

```
hadoop fs -help cat
-cat [-ignoreCrc] <src> ... :
  Fetch all files that match the file pattern <src> and display their content on
  stdout.
```

#### Help on copyFromLocal command of filesystem

```
hadoop fs -help copyFromLocal
-copyFromLocal [-f] [-p] [-l] <localsrc> ... <dst> :
  Identical to the -put command.
```

#### Help on copyToLocal command of filesystem

```
hadoop fs -help copyToLocal
-copyToLocal [-p] [-ignoreCrc] [-crc] <src> ... <localdst> :
  Identical to the -get command.
```

#### Help on get command of filesystem

```
hadoop fs -help get
-get [-p] [-ignoreCrc] [-crc] <src> ... <localdst> :
  Copy files that match the file pattern <src> to the local name.  <src> is kept. 
  When copying multiple files, the destination must be a directory. Passing -p
  preserves access and modification times, ownership and the mode.
```

#### Help on put command of filesystem

```
hadoop fs -help put
-put [-f] [-p] [-l] <localsrc> ... <dst> :
  Copy files from the local file system into fs. Copying fails if the file already
  exists, unless the -f flag is given.
  Flags:
                                                                       
  -p  Preserves access and modification times, ownership and the mode. 
  -f  Overwrites the destination if it already exists.
  -l  Allow DataNode to lazily persist the file to disk. Forces
         replication factor of 1. This flag will result in reduced
         durability. Use with care.
```

#### Help on moveFromLocal command of filesystem

```
hadoop fs -help moveFromLocal
-moveFromLocal <localsrc> ... <dst> :
  Same as -put, except that the source is deleted after it's copied.
```

#### Help on moveToLocal command of filesystem

```
hadoop fs -help moveToLocal
-moveToLocal <src> <localdst> :
  Not implemented yet
```

#### Help on mv command of filesystem

```
hadoop fs -help mv
-mv <src> ... <dst> :
  Move files that match the specified file pattern <src> to a destination <dst>. 
  When moving multiple files, the destination must be a directory.
```

#### Help on rm command of filesystem

```
hadoop fs -help rm
-rm [-f] [-r|-R] [-skipTrash] <src> ... :
  Delete all files that match the specified file pattern. Equivalent to the Unix
  command "rm <src>"
                                                                                 
  -skipTrash  option bypasses trash, if enabled, and immediately deletes <src> 
  -f          If the file does not exist, do not display a diagnostic message or 
              modify the exit status to reflect an error.                        
  -[rR]       Recursively deletes directories 
```

#### Help on rmdir command of filesystem

```
hadoop fs -help rmdir
-rmdir [--ignore-fail-on-non-empty] <dir> ... :
  Removes the directory entry specified by each directory argument, provided it is
  empty. 
```


