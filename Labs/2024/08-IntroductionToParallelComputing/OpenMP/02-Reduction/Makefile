CXX      ?= g++
CXXFLAGS ?= -std=c++17
CPPFLAGS ?= -fopenmp -Wall

LDFLAGS ?=
LIBS    ?=

EXEC = simpleReduction pi_reduction

.PHONY = all $(EXEC) clean distclean

all: $(EXEC)

$(EXEC): %: %.cpp
	$(CXX) $(CPPFLAGS) $(CXXFLAGS) $(LDFLAGS) $< $(LIBS) -o $@

clean:
	$(RM) *.o

distclean: clean
	$(RM) $(EXEC)
	$(RM) *.csv *.out *.bak *~
