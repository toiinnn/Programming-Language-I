RM = rm -rf

CC=g++

INC_DIR=./include
SRC_DIR=./src
OBJ_DIR=./build
BIN_DIR=./bin
DOC_DIR=./doc

CFLAGS = -Wall -pedantic -ansi -std=c++11 -I. -I$(INC_DIR)

.PHONY: all clean distclean doxy

all: store agency inherit_agency

debug: CFLAGS += -g -O0
debug: store agency

init:
	@mkdir -p $(BIN_DIR)/
	@mkdir -p $(OBJ_DIR)/
	@mkdir -p $(INC_DIR)/
	@mkdir -p $(SRC_DIR)/
	@mkdir -p $(DOC_DIR)/

store: $(OBJ_DIR)/product.o $(OBJ_DIR)/fruit.o $(OBJ_DIR)/beverage.o $(OBJ_DIR)/store.o $(OBJ_DIR)/clothing.o $(OBJ_DIR)/main.o
	@echo "============="
	@echo "Connecting the target $@"
	@echo "============="
	$(CC) $(CFLAGS) -o $(BIN_DIR)/$@ $^
	@echo "+++ [Executable store created in $(BIN_DIR)] +++"
	@echo "============="

$(OBJ_DIR)/product.o: $(SRC_DIR)/task_one/product.cpp $(INC_DIR)/task_one/product.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/fruit.o: $(SRC_DIR)/task_one/fruit.cpp $(INC_DIR)/task_one/fruit.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/beverage.o: $(SRC_DIR)/task_one/beverage.cpp $(INC_DIR)/task_one/beverage.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/clothing.o: $(SRC_DIR)/task_one/clothing.cpp $(INC_DIR)/task_one/clothing.h
	$(CC) -c $(CFLAGS) -o $@ $<	

$(OBJ_DIR)/store.o: $(SRC_DIR)/task_one/store.cpp $(INC_DIR)/task_one/store.h
	$(CC) -c $(CFLAGS) -o $@ $<		

$(OBJ_DIR)/main.o: $(SRC_DIR)/task_one/store_main.cpp
	$(CC) -c $(CFLAGS) -o $@ $<

agency: $(OBJ_DIR)/checking_account.o $(OBJ_DIR)/agency.o $(OBJ_DIR)/transaction.o $(OBJ_DIR)/interface.o $(OBJ_DIR)/main2.o
	@echo "============="
	@echo "Connecting the target $@"
	@echo "============="
	$(CC) $(CFLAGS) -o $(BIN_DIR)/$@ $^
	@echo "+++ [Executable agency created in $(BIN_DIR)] +++"
	@echo "============="

$(OBJ_DIR)/checking_account.o: $(SRC_DIR)/task_two/checking_account.cpp $(INC_DIR)/task_two/checking_account.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/agency.o: $(SRC_DIR)/task_two/agency.cpp $(INC_DIR)/task_two/agency.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/transaction.o: $(SRC_DIR)/task_two/transaction.cpp $(INC_DIR)/task_two/transaction.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/interface.o : $(SRC_DIR)/task_two/interface.cpp $(INC_DIR)/task_two/interface.h
	$(CC) -c $(CFLAGS) -o $@ $<	

$(OBJ_DIR)/main2.o: $(SRC_DIR)/task_two/main.cpp
	$(CC) -c $(CFLAGS) -o $@ $<	

inherit_agency: $(OBJ_DIR)/transaction2.o $(OBJ_DIR)/account.o $(OBJ_DIR)/checking_account2.o $(OBJ_DIR)/saving_account.o $(OBJ_DIR)/agency2.o $(OBJ_DIR)/interface2.o $(OBJ_DIR)/main3.o
	@echo "============="
	@echo "Connecting the target $@"
	@echo "============="
	$(CC) $(CFLAGS) -o $(BIN_DIR)/$@ $^
	@echo "+++ [Executable inherit_agency created in $(BIN_DIR)] +++"
	@echo "============="

$(OBJ_DIR)/transaction2.o: $(SRC_DIR)/task_three/in_transaction.cpp $(INC_DIR)/task_three/in_transaction.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/account.o: $(SRC_DIR)/task_three/in_account.cpp $(INC_DIR)/task_three/in_account.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/checking_account2.o: $(SRC_DIR)/task_three/in_checking_account.cpp $(INC_DIR)/task_three/in_checking_account.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/saving_account.o: $(SRC_DIR)/task_three/in_saving_account.cpp $(INC_DIR)/task_three/in_saving_account.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/agency2.o: $(SRC_DIR)/task_three/in_agency.cpp $(INC_DIR)/task_three/in_agency.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/interface2.o: $(SRC_DIR)/task_three/in_interface.cpp $(INC_DIR)/task_three/in_interface.h
	$(CC) -c $(CFLAGS) -o $@ $<

$(OBJ_DIR)/main3.o: $(SRC_DIR)/task_three/in_main.cpp
	$(CC) -c $(CFLAGS) -o $@ $<	

doxy:
	$(RM) $(DOC_DIR)/*
	doxygen Doxyfile

clean:
	$(RM) $(BIN_DIR)/*
	$(RM) $(OBJ_DIR)/*
	$(RM) $(DOC_DIR)/*