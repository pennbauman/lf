NAME = lf
GCC_FLAGS = -Wl,--build-id

prefix = /usr/local
bindir = $(prefix)/bin
mandir = $(prefix)/share/man
docdir = $(prefix)/share/doc/$(NAME)

$(NAME): *.go
	go build -gccgoflags $(GCC_FLAGS) -o $@

clean:
	rm -rf lf debian/lf

install: lf
	install -m 0755 -d $(DESTDIR)$(bindir)
	install -m 0755 $(NAME) $(DESTDIR)$(bindir)/$(NAME)
	install -m 0755 -d $(DESTDIR)$(mandir)/man1
	install -m 0755 -d $(DESTDIR)$(docdir)
	install -m 0644 $(NAME).1 $(DESTDIR)$(mandir)/man1/$(NAME).1
	install -m 0644 etc/lfrc.example $(DESTDIR)$(docdir)/lfrc.example
	install -m 0644 etc/colors.example $(DESTDIR)$(docdir)/colors.example
	install -m 0644 etc/icons.example $(DESTDIR)$(docdir)/jicons.example
