CXX      ?= g++
CXXFLAGS ?= -std=c++20
CPPFLAGS ?= -O3 -Wall -pedantic -I. -isystem../../../../Examples/include \
            -isystem$(mkBoostInc) -isystem$(mkTbbInc) -I../../../../../pacs-examples/Examples/include
LDLIBS   ?= -L$(mkBoostLib) -L$(mkTbbLib) \
            -lboost_iostreams -lboost_system -lboost_filesystem -ltbb
LINK.o := $(LINK.cc) # Use C++ linker.

DEPEND = make.dep

EXEC = main
SRCS = $(wildcard *.cpp)
OBJS = $(SRCS:.cpp=.o)

.PHONY = all $(EXEC) $(OBJS) clean distclean $(DEPEND)

all: $(DEPEND) $(EXEC)

$(EXEC): $(OBJS)

$(OBJS): %.o: %.cpp

clean:
	$(RM) $(DEPEND)
	$(RM) *.o

distclean: clean
	$(RM) $(EXEC)
	$(RM) *.csv *.out *.bak *~

cleanSnapshots:
	$(RM) snapshot* output* sir.gif sir.png


$(DEPEND): $(SRCS)
	@$(RM) $(DEPEND)
	@for file in $(SRCS); \
	do \
	  $(CXX) $(CPPFLAGS) $(CXXFLAGS) -MM $${file} >> $(DEPEND); \
	done

-include $(DEPEND)
