AR=ar
CXX=g++
RM=rm -f
override CXXFLAGS:=-std=c++11 -fPIC -Wall -Wextra -O3 $(CFLAGS)
override LIB:=-lm $(LIB)

.PHONY: all clean tests

all: libjksn++.a libjksn++.so

clean:
	$(RM) libjksn++.so libjksn++.a jksn.o

tests: libjksn++.a
	$(MAKE) -C tests

libjksn++.a: jksn.o
	$(AR) crs $@ $^

libjksn++.so: jksn.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -shared -o $@ $^ $(LIB)
