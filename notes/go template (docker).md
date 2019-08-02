---
tags: [container/docker, lang/go]
title: go template (docker)
created: '2019-07-30T06:19:49.074Z'
modified: '2019-07-30T08:15:16.461Z'
---

# go template (docker)

[Docker Inspect Template Magic - Container Solutions](http://container-solutions.com/docker-inspect-template-magic/)
[template - The Go Programming Language](https://golang.org/pkg/text/template/)
[Docker - How do I change the docker gwbridge address?](https://success.docker.com/article/how-do-i-change-the-docker-gwbridge-address)

```sh
directive:        "{{ }}"

current-context:  "."         e.g. .Container

root-context:     $
```
### control structures
```sh
  if

  with

  range
```
### functions
```sh
  join      # concatenates a list of strings to create a single string
            # '{{join .Args " , "}}'

  json      # encodes an element as a json string.
    
  lower     # transforms a string into its lowercase
    
  split     # lices a string into a list of strings separated by a separator
            # {{split .Image ":"}}

  title     # capitalizes the first character of a string 
    
  upper     # transforms a string into its uppercase 
    
  println   # prints each value on a new line
            # '{{range $k,$v := .Args}} {{println $v $k}} {{end}}'
            
  index     # function: can lookup arbitrary strings in the map
```

https://golang.org/pkg/text/template/#example_Template_share


```sh
docker network inspect 

  --format '{{ range $c, $n := .Containers }} => {{$c}} {{$n.Name}} {{end}}'

docker image inspect 

  --format '{{ range $k, $v := .ContainerConfig.Labels -}} {{ $k }}={{ $v }} {{ end -}}'
  
docker container inspect 
  
  --format '{{ .Config.Env}}'
  
  --format '{{ .HostConfig.LogConfig.Type}}'
  
  --format '{{ if eq 0.0 .State.ExitCode }} {{.Name }} {{.State.ExitCode}} {{end }}'

  --format '{{ range $p, $conf := .NetworkSettings.Ports}} {{$p}} -> {{(index $conf 0).HostPort}} {{end}}'

  --format '{{ range $conf := .Config.Env}}{{$conf}}{{end}}'

  --format '{{ range $i,$j:= .Spec.Labels}}{{$i}}: {{$j}} {{end}}'

  --format '{{ index .Config.Labels "com.wherever.foo" }}'

  --format '{{ if (.Parent) }}{{.Id}} {{.Parent}}{{end}}'    # if has parent e.g. docker image inspect $(docker image ls -q)

docker inspect monitoring_exporter_1
  
  --format '{{ range $k, $v := .Config.Labels}}{{if eq $k "SERVICE_9100_NAME"}} {{$v}} {{end}} {{end}}'

docker network inspect docker_gwbridge
  
  --format '{{.Containers}}'

  --format '{{ range $k, $v := index .IPAM.Config 0}}{{.| printf "%s: %s " $k}}{{end}}'
  
  --format '{{ range $key, $val := .Containers}} {{$key}} {{end}}'
  
  --format '{{ .Name}} 
            {{ range $k,$v:= .Containers }}
              {{ printf "%s\n" $k}}
              {{ range $x,$y := $v }}
                {{ printf "%s: %s\n" $x $y}}
              {{end}}
            {{end}}'
            


# extract laysers from container
docker inspect 
  --format '
    {{ range $e := .Config.Env}}              ENV {{$e}}    {{end}}

    {{ range $e,$v := .Config.ExposedPorts}}  EXPOSE {{$e}} {{end}}

    {{ range $e,$v := .Config.Volumes}}       VOLUME {{$e}} {{end}}

    {{ with .Config.User}}USER {{.}} {{end}}
    {{ with .Config.WorkingDir}}WORKDIR {{.}} {{end}}
    {{ with .Config.Entrypoint}}ENTRYPOINT {{json .}} {{end}}
    {{ with .Config.Cmd}}CMD {{json .}} {{end}}
    {{ with .Config.OnBuild}}ONBUILD {{json .}} {{end}}'
```
