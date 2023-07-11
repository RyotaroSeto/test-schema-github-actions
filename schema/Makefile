
.PHONY: up

ENV := "local"
CONFIG_FILE := dbconfig.yml

up:
	sql-migrate up -env=$(ENV) -config=$(CONFIG_FILE)

