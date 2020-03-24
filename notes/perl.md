---
tags: [perl]
title: perl
created: '2019-07-30T06:19:49.150Z'
modified: '2020-03-18T15:00:37.374Z'
---

# perl

> perl language interpreter

## usage
```sh
perl -de 42         # starts debugger in repl-mode, 42 has no meaning it's just valid

# options:
#   -v                print version, patchlevel and license
```

```perl
#!/usr/bin/perl
=head1 DESCRIPTION
printenv — a CGI program that just prints its environment
source: https://en.wikipedia.org/wiki/Common_Gateway_Interface
=cut
print "Content-type: text/plain\r\n\r\n";

for my $var ( sort keys %ENV ) {
 printf "%s = \"%s\"\r\n", $var, $ENV{$var};
}
```

## see also
- [[cpan]]
- [[php]]
- [[python]]
