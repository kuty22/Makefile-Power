BUILD=build
DC=docker-compose
DOWN=down
UP=up

# down build and start
all: down_build_up

### basic make ###
down_build_up: down build up

buid_up: build up

build:
	$(DC) $(BUILD)

up_update:
	$(DC) $(UP) --no-deps service_2

up:
	$(DC) $(UP) --no-deps service_1

down:
	$(DC) $(DOWN)

### utils ###
ps:
	$(DC) ps

logs:
	$(DC) logs -f
