
PROGRAM = elfinfo
VERSION = 1.1
SOURCE = $(PROGRAM).c
CFLAGS = -Wall -c -g
LFLAGS = -Wall
#LAUNCHER = $(HOME)/Desktop/$(PROGRAM).desktop

# use $PREFIX if defined, else assume /usr/local

ifeq "$(PREFIX)" ""
	PREFIX = /usr/local
endif

BINDIR = $(PREFIX)/bin
DATADIR = $(PREFIX)/share/$(PROGRAM)
DOCDIR = $(PREFIX)/share/doc/$(PROGRAM)


$(PROGRAM): $(PROGRAM).o
	@gcc -o $(PROGRAM) $(PROGRAM).o

$(PROGRAM).o: $(SOURCE)
	@gcc $(CFLAGS) -o $(PROGRAM).o $(SOURCE)		\
	 -D "DOCDIR=\"$(DOCDIR)\""


install: $(PROGRAM)
	mkdir -p $(DESTDIR)$(DOCDIR) 
	mkdir -p $(DESTDIR)$(BINDIR)
	cp -p README AUTHORS ChangeLog  COPYING  $(DESTDIR)$(DOCDIR)
	cp -p  $(PROGRAM)  $(DESTDIR)$(BINDIR)


uninstall:
	rm -f $(DESTDIR)$(BINDIR)/$(PROGRAM)
	rm -f $(DESTDIR)$(DOCDIR)/*
	rmdir $(DESTDIR)$(DOCDIR)
clean:
	rm -f *.o $(PROGRAM)

dist:
	tar -cz * -f $(PROGRAM)-$(VERSION).tar.gz
