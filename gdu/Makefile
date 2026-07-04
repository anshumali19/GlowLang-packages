# Build gdu (Glow Dependency Utility)
#
# Requires: libsqlite3-dev libssl-dev
#   Debian/Ubuntu: sudo apt-get install -y libsqlite3-dev libssl-dev
#
#   -lsqlite3 : local package cache / registry
#   -lcrypto  : OpenSSL SHA-256 for package integrity (gdu verify / Glow.lock)

CC      ?= gcc
CFLAGS  ?= -O2
LDLIBS  := -lsqlite3 -lcrypto

gdu: gdu.c
	$(CC) $(CFLAGS) gdu.c -o gdu $(LDLIBS)

clean:
	rm -f gdu

.PHONY: clean
