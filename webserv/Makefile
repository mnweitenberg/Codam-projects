# VARIABLES
NAME			:=	webserv
CFLAGS			:=	-Isrc -std=c++98 -Wall -Wextra -Werror  -pedantic
SANIT			:=  #-g -fsanitize=address
CC				:=	c++

# STATIC
RM				:=	rm
MKDIR_P			:=	@mkdir -p
SRC_DIR			:=	./src
OBJ_DIR			:=	./obj
SRC				:=	$(shell find $(SRC_DIR) -name '*.cpp')
OBJ				:=	$(SRC:$(SRC_DIR)/%.c=$(OBJ_DIR)/%.o)

all				:	$(NAME)

$(NAME)			: 	$(OBJ)
					$(CC) $(CFLAGS) $(OBJ) -o $@ $(SANIT)

$(OBJ_DIR)/%.o	:	$(SRC_DIR)/%.cpp $(SRC_DIR)/%.hpp
					$(MKDIR_P) $(dir $@)
					$(CC) $(CFLAGS) -c $< -o $@

bonus			:	$(NAME)
clean			:
					$(RM) -rf $(OBJ_DIR) 
fclean			:	clean
					$(RM) -f $(NAME)
re				: 	fclean all
.PHONY			:	all bonus clean fclean re
