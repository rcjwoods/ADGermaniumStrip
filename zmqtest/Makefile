# the compiler: gcc for C program, define as g++ for C++
CC = g++

ZMQ = /home/beams0/TMADDEN/swWork/ZMQ


# compiler flags:
#  -g    adds debugging information to the executable file
#  -Wall turns on most, but not all, compiler warnings


CFLAGS  = -g -Wall -pthread -I$(ZMQ)/include

LFLAGS  = -L$(ZMQ)/lib -lzmq


# the build target executable:
SRV = helloworldsrv
CLT = helloworldclt
MAIASIM=maia_simserver
MAIACLT=maia_client

all: $(SRV) $(CLT) $(MAIASIM) $(MAIACLT)

$(SRV): $(SRV).cpp
	$(CC) $(CFLAGS) -o $(SRV) $(SRV).cpp $(LFLAGS)


$(CLT): $(CLT).cpp
	$(CC) $(CFLAGS) -o $(CLT) $(CLT).cpp $(LFLAGS)

  
$(MAIASIM): $(MAIASIM).cpp erfmath.cpp stopWatch.cpp
	$(CC) $(CFLAGS) -o $(MAIASIM) erfmath.cpp stopWatch.cpp $(MAIASIM).cpp $(LFLAGS)
  
$(MAIACLT): $(MAIACLT).cpp 
	$(CC) $(CFLAGS) -DMAIA_TEST_MAIN -o $(MAIACLT) $(MAIACLT).cpp stopWatch.cpp  $(LFLAGS)

clean:
	$(RM) $(SRV) $(CLT) $(MAIASIM) $(MAIACLT)
