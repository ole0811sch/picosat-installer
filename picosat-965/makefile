CC=gcc
CFLAGS= -DTRACE -Wall -Wextra -DNDEBUG -O3 -fPIC

all: libpicosat-trace.so

picosat.o: picosat.c picosat.h makefile
	$(CC) $(CFLAGS) -c $<

version.o: version.c config.h makefile
	$(CC) $(CFLAGS) -c $<

config.h: makefile VERSION mkconfig.sh
	rm -f $@; ./mkconfig.sh > $@

SONAME=-Xlinker -soname -Xlinker libpicosat-trace.so.0
libpicosat-trace.so: picosat.o version.o
	$(CC) $(CFLAGS) -shared -o $@ picosat.o version.o $(SONAME)

install: libpicosat-trace.so
	install -m 0755 -p libpicosat-trace.so /usr/local/lib/libpicosat-trace.so.0.0.965
	ln -s libpicosat-trace.so.0.0.965 /usr/local/lib/libpicosat-trace.so.0
	ln -s libpicosat-trace.so.0 /usr/local/lib/libpicosat-trace.so
	ldconfig

remove:
	rm -f /usr/local/lib/libpicosat-trace.so.0.0.965
	rm -f libpicosat-trace.so.0.0.965
	rm -f libpicosat-trace.so.0

.PHONY: all install remove
