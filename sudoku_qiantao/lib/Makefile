cpps = $(wildcard *.cpp)
#include $(cpps:%.cpp=%.d)

#objs = $(cpps:%.cpp=%.o)
objs = $(patsubst %.cpp,%.o,$(cpps))


vpath %.h ../include

CXXFLAGS += -I../include 
default: sudokulib.a cleantemp
sudokulib.a:$(objs)
	@echo $(cpps)
	@echo $(objs)
	ar rcs $@ $^

$(objs):%.o:%.cpp %.h
	g++  -c -o $@ $< $(CXXFLAGS) 

#%.d:%.cpp
#	@-rm $@
#	$(CXX) -MM  $< > $@.temp
#	@sed 's,\($*\)\.o[ :]*,\1.o $@ : ,g' < $@.temp > $@
#	@-rm $@.temp

.PHONY:clean cleantemp
clean:
	-rm $(objs) *.a
	
cleantemp:
	-rm $(objs)
	

	