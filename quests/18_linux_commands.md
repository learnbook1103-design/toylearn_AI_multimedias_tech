```
~ $ cd Commands && pwd
/home/node/Commands
~/Commands $ mkdir test && ls -l
total 4
-rw-r--r--    1 node     node             0 Nov  7 03:05 temp_01.txt
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 test
~/Commands $ mkdir notes && cd notes && pwd
/home/node/Commands/notes
~/Commands/notes $ cd ../
~/Commands $ mkdir images videos docs && ls -l
total 20
drwxr-sr-x    2 node     node          4096 Nov  7 03:44 docs
drwxr-sr-x    2 node     node          4096 Nov  7 03:44 images
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 notes
-rw-r--r--    1 node     node             0 Nov  7 03:05 temp_01.txt
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 test
drwxr-sr-x    2 node     node          4096 Nov  7 03:44 videos
~/Commands $ cd docs && cd ../ && ls -l
total 20
drwxr-sr-x    2 node     node          4096 Nov  7 03:44 docs
drwxr-sr-x    2 node     node          4096 Nov  7 03:44 images
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 notes
-rw-r--r--    1 node     node             0 Nov  7 03:05 temp_01.txt
drwxr-sr-x    2 node     node          4096 Nov  7 03:42 test
drwxr-sr-x    2 node     node          4096 Nov  7 03:44 videos
~/Commands $ 
```