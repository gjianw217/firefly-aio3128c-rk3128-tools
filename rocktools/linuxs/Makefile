CC      ?= gcc
CFLAGS  ?= -O2 -Wall -Wextra
LDFLAGS ?= -lcrypto
PREFIX  ?= usr/local

TARGETS = mkkrnlimg resource_tool
SCRIPTS = mkkrnlimg resource_tool
DEPS    = Makefile

all: $(TARGETS)

%: %.c $(COMMON) $(DEPS)
	$(CC) $(CFLAGS) -o $@ $< $(LDFLAGS)

install: $(TARGETS)
	install -d -m 0755 $(DESTDIR)/$(PREFIX)/bin
	install -m 0755 $(TARGETS) $(DESTDIR)/$(PREFIX)/bin
	install -m 0755 $(SCRIPTS) $(DESTDIR)/$(PREFIX)/bin

.PHONY: clean uninstall

clean:
	rm -f $(TARGETS)

uninstall:
	cd $(DESTDIR)/$(PREFIX)/bin && rm -f $(TARGETS)
	cd $(DESTDIR)/$(PREFIX)/bin && rm -f $(SCRIPTS)
