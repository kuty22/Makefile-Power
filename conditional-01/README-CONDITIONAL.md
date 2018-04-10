# Conditional statement with Makefile

## Description:

  This is an example of how ask a variable set in a Makefile.

  in the rule `msg_args` you can found the statement for the `NAME` variable:

  ```yaml
  msg_args:
  ifndef NAME
    @echo $(NAME_ERROR_MSG)
    @exit 1
  endif
    @echo  $(NAME_MSG_1)$(NAME)$(NAME_MSG_2)
  ```

![ttygif example](https://media.giphy.com/media/27IQOJWtPOkVezd5Rv/giphy.gif)

```bash
➜  conditional-01 git:(master) ✗ make msg
Hello I'm a message.
➜  conditional-01 git:(master) ✗ make msg_args
You must specify NAME (eg. make msg_args NAME=kuty).
make: *** [msg_args] Error 1
➜  conditional-01 git:(master) ✗ make msg_args NAME=toto
Hello toto, I'm a message.
➜  conditional-01 git:(master) ✗ exit
➜  conditional-01 git:(master) ✗ ttygif conditional-01
➜  conditional-01 git:(master) ✗ make
make: *** No rule to make target `message', needed by `all'.  Stop.
➜  conditional-01 git:(master) ✗ make msg
Hello I'm a message.
➜  conditional-01 git:(master) ✗ make msg_args
You must specify NAME (eg. make msg_args NAME=kuty).
make: *** [msg_args] Error 1
➜  conditional-01 git:(master) ✗ make msg_args NAME=toto
Hello toto, I'm a message.
```
