---
tags: [macos]
title: system_profiler
created: '2023-06-02T06:21:37.392Z'
modified: '2023-06-02T06:25:29.379Z'
---

# system_profiler

> reports system hardware and software configuration

## option

```sh
-xml                # generates report in XML format.  If the XML report is redirected to a file with a ".spx" suffix that file can be opened with System Information.app
-json               # generates report in JSON format
-listDataTypes      # lists the available datatypes
-detailLevel level  # specifies level of detail for the report: mini, basic, full
-timeout            # specifies maximum time to wait in seconds for results
-usage              # prints usage info and examples
```

## usage

```sh
system_profiler SPSoftwareDataType SPHardwareDataType -json
system_profiler SPSoftwareDataType SPNetworkDataType       # generates text report containing only software and network data

system_profiler                           # Generates a text report with the standard detail level

system_profiler -detailLevel mini         # Generates a short report containing no personal information

system_profiler -listDataTypes            # Shows a list of the available data types

system_profiler -xml > MyReport.spx       # Creates a XML file which can be opened by System Profiler.app
```

## see also

- [[defaults]]
- [[mdfind]]
