CC = gcc
CFLAGS = -O2 -fPIC -Wall
IFLAGS = $(shell pkg-config lua --cflags)
LFLAGS = $(shell pkg-config lua --libs)
TARGET = protobuf.so

.PHONY : all clean

all : $(TARGET)

$(TARGET) : pbc-lua.c
	$(CC) $(CFLAGS) -shared -o $@ -I../.. $(IFLAGS) $(LFLAGS) -L../../build $^ -lpbc

clean :
	rm -f $(TARGET)
