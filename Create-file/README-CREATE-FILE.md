# Create file with Makefile

## Description:

  This example use the Makefile to generate a yaml configuration file.

  The more interesting thing in this example are these lines :
  ```Makefile
  all: .user-config.yml
  ...
  .user-config.yml:
  	echo "root:" 								> $@
  	echo "	id:"$(shell id -g) 	>> $@
  ...
  ```
  When you `make`, the Makefile call the rule `.user-config.yml` only if the file
   does not exist, that mean you can exec multiple `make` and that not create the file again.

  ![ttygif example](https://media.giphy.com/media/8UGoKUvkDQDmFB6GeA/giphy.gif)


  run example:
  ```shell
  ➜  Create-file git:(master) ✗ make
  echo "root:" 								> .user-config.yml
  echo "	id:"20 	>> .user-config.yml
  echo "	roles:" 						>> .user-config.yml
  echo "	- admin:" 					>> .user-config.yml
  echo "user:"  							>> .user-config.yml
  echo "	id:"501 	>> .user-config.yml
  echo "	roles:" 						>> .user-config.yml
  echo "	- guest:" 					>> .user-config.yml
  ➜  Create-file git:(master) ✗ make
  make: Nothing to be done for `all'.
  ➜  Create-file git:(master) ✗ make display
  root:$
  	id:20$
  	roles:$
  	- admin:$
  user:$
  	id:501$
  	roles:$
  	- guest:$
  ➜  Create-file git:(master) ✗ ls -la
  total 32
  drwxr-xr-x  6 kuty  staff   192 Apr  9 18:42 .
  drwxr-xr-x  5 kuty  staff   160 Apr  9 18:00 ..
  -rw-r--r--  1 kuty  staff    63 Apr  9 18:42 .user-config.yml
  -rw-r--r--  1 kuty  staff   373 Apr  9 18:17 Makefile
  -rw-r--r--  1 kuty  staff   325 Apr  9 18:29 READNE-CREATE-FILE.md
  -rw-r--r--  1 kuty  staff  3343 Apr  9 18:42 create-file-example-Makefile
  ➜  Create-file git:(master) ✗ make clean
  rm -rf .user-config.yml
  ➜  Create-file git:(master) ✗ ls -la
  total 32
  drwxr-xr-x  5 kuty  staff   160 Apr  9 18:42 .
  drwxr-xr-x  5 kuty  staff   160 Apr  9 18:00 ..
  -rw-r--r--  1 kuty  staff   373 Apr  9 18:17 Makefile
  -rw-r--r--  1 kuty  staff   325 Apr  9 18:29 READNE-CREATE-FILE.md
  -rw-r--r--  1 kuty  staff  5239 Apr  9 18:42 create-file-example-Makefile
  ```
