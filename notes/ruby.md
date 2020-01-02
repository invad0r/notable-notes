---
tags: [ruby]
title: ruby
created: '2019-07-30T06:19:49.226Z'
modified: '2020-01-02T13:02:51.594Z'
---

# ruby 

## usage
```sh
ruby -h       # Prints a summary of the options

ruby -e 'puts "Hello, world."; puts "It is now #{Time.now}."'

ruby -e 'puts "Hello, world."' -e 'puts "It is now #{Time.now}."'

ruby -e 'puts STDIN.readlines[58]' < ulysses.txt      # prints the 59th line

ruby -e 'puts ARGF.readlines.first(5)' ulysses.txt    # first 5 lines

ruby -e 'puts ARGF.readlines.last(5)' ulysses.txt     # last 5 lines

ruby -n -a -e 'puts $F[2]' ulysses.txt


ruby -n -e 'p eval($_)'         # starts repl; see also irb

ruby -n -e 'puts $_ if $_ =~ /\bold\b/i' ulysses.txt

#   -n   wraps loop around script: `while gets; SCRIPT; end.`
#   $_   magic global set to the last line returned from gets



ruby -rjson -ryaml -e "puts YAML.load_file('my_file.yml').to_json"                          # yaml to json

ruby -rjson -ryaml -e "puts JSON.pretty_generate(YAML.load_file('my_file.yml'))"            # yaml to json and pretty print

ruby -e "require 'json'; puts JSON.pretty_generate(JSON.parse(ARGF.read))" file.json        # pretty print json

ruby -ryaml -rjson -e 'puts YAML.dump(JSON.load(ARGF))' < file.json                         # json to yml

ruby -ryaml -rjson -e 'puts YAML.dump(JSON.load(ARGF))' < file.json > file.yml              # json to yml

ruby -ryaml -rjson -e 'puts YAML.dump(JSON.load(ARGF))' < file.yml                          # yml to json

ruby -ryaml -rjson -e 'puts YAML.dump(JSON.load(ARGF))' < file.yml > file.json              # yml to json

```


 ## see also
 - [[irb]]
 - https://hashrocket.com/blog/posts/ruby-on-the-command-line
 - [[python]]
 - [[yaml]]

