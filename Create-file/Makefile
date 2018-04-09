
VIEW= -e .user-config.yml
RM= rm -rf

all: .user-config.yml

display:
		@cat $(VIEW)
clean:
	$(RM) .user-config.yml

.user-config.yml:
	echo "root:" 								> $@
	echo "	id:"$(shell id -g) 	>> $@
	echo "	roles:" 						>> $@
	echo "	- admin:" 					>> $@
	echo "user:"  							>> $@
	echo "	id:"$(shell id -u) 	>> $@
	echo "	roles:" 						>> $@
	echo "	- guest:" 					>> $@
