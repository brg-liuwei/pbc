CC = gcc
CFLAGS = -O2 -fPIC -Wall
LUAFLAG = $(shell pkg-config luajit --cflags)
LFLAG = $(shell pkg-config luajit --libs)
TARGET = protobuf.so

PREFIX = /usr/local/openresty

.PHONY : all install clean

all : $(TARGET)

$(TARGET) : pbc-lua.c
	$(CC) $(CFLAGS) -shared -o $@ -I../.. $(LUAFLAG) $(LFLAG) -L../../build $^ -lpbc

install:
	install protobuf.lua $(PREFIX)/lualib
	install protobuf.so $(PREFIX)/lualib

clean :
	rm -f $(TARGET)
