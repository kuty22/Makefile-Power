MSG = "Hello I'm a message."
NAME_ERROR_MSG = "You must specify NAME (eg. $ make msg_args NAME=kuty)."
NAME_MSG_1 = "Hello "
NAME_MSG_2 = ", I'm a message."

all: message

msg:
		@echo $(MSG)

msg_args:
ifndef NAME
	@echo $(NAME_ERROR_MSG)
	@exit 1
endif
	@echo  $(NAME_MSG_1)$(NAME)$(NAME_MSG_2)

clean:
	$(RM) .user-config.yml
