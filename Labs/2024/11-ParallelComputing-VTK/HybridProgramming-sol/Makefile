CXX       = mpic++
CXXFLAGS ?= -std=c++17
CPPFLAGS ?= -fopenmp -O3 -Wall -pedantic

LDFLAGS ?=
LIBS    ?=

EXEC = 01-hello-world 02-Matrix 03-pi 

.PHONY = all $(EXEC) clean distclean $(DEPEND)

all: $(EXEC)

$(EXEC): %: %.cpp
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) $(LDFLAGS) $< $(LIBS) -o $@

clean:
	$(RM) *.o

distclean: clean
	$(RM) $(EXEC)
	$(RM) *.csv *.out *.bak *~
