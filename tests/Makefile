##
## EPITECH PROJECT, 2023
## Makefile
## File description:
## to make a file
##

CC		=	gcc
CFLAGS		=	-Wall -Wextra -Werror -g
INCLUDES	=	-I./includes
LIBS		=

NAME		=	NAME_PROJECT
SRC_DIR		=	srcs
INC_DIR		=	includes
BUILD_DIR	=	objs

SRC_FILES	=	main.c			\
				mini_printf.c	\
				my_put_nbr.c 	\
				my_putchar.c	\
				my_putstr.c

SRC		=	$(addprefix $(SRC_DIR)/,$(SRC_FILES))
OBJ		=	$(addprefix $(BUILD_DIR)/,$(SRC_FILES:.c=.o))

GREENBOLD	=	"\033[1;32m"
REDBOLD		=	"\033[1;31m"
NORMAL		=	"\033[0m"

.PHONY: all clean fclean re

all: $(NAME)

$(NAME): $(OBJ)
	@$(CC) $(OBJ) $(LIBS) -o $(NAME)
	@echo $(GREENBOLD) "[Done] [BIN] Compilation successful" $(NORMAL)

$(BUILD_DIR)/%.o: $(SRC_DIR)/%.c | $(BUILD_DIR)
	@$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@
	@echo $(GREENBOLD) "[Done] [CC] $<" $(NORMAL)

$(BUILD_DIR):
	@mkdir -p $@

tests_run:
	make -C tests/

clean:
	@$(RM) -rf $(BUILD_DIR)
	@rm -rf *.a
	@rm -rf *~
	@rm -rf *.log
	@rm -rf srcs/*.a
	@rm -rf srcs/*~
	@rm -rf includes/*~
	@echo $(GREENBOLD) "[Done] [CLEAN]  Clean successful" $(NORMAL)

fclean: clean
	@$(RM) -f $(NAME)
	@echo $(GREENBOLD) "[Done] [FCLEAN] Clean successful" $(NORMAL)

re: fclean all
