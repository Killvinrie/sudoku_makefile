vpath %.a ../lib
CXXFLAGS += -I../include
#LDFLAGS += -L../lib
#LDLIBS += -lsudoku

../bin/sudoku:main.o  sudokulib.a
	g++ -o $@ $^ 

.PHONY: clean
clean:
	-rm *.o ../bin/*