# BDS-Hub-Detect-Instructions

Black Duck Software Hub Detect Examples

Full Documentation here: https://blackducksoftware.atlassian.net/wiki/spaces/INTDOCS/pages/49131875/Hub+Detect

## Table of Contents

1. [Running your first scan](#firstscan)
2. [Windows](#windows)
3. [Linux/Unix](#linux)
4. [Examples](#examples)

## Running your first scan

<a name="firstscan"></a>

**Prerequisites**

* Java 8 (JRE 1.8)
* 8GB RAM
* Run any commands used to gather open source dependencies prior to conducting a scan (if applicable).
* Choose OS you will be running this scan on.

    * [Windows](#windows)
    * [Linux/Unix](#linux)




## Windows

<a name="windows"></a>

**Powershell**

These are meant to be run inside powershell. See the hub-detect.ps1 file for complete list of environment variables that can be utilized to modify the execution script.

Send results to the Hub:

```
[Net.ServicePointManager]::SecurityProtocol = 'tls12'; irm https://blackducksoftware.github.io/hub-detect/hub-detect.ps1?$(Get-Random) | iex; detect --blackduck.hub.url=http://myhub.url --blackduck.hub.username=myusername --blackduck.hub.password=mypassword
```


Offline scan to create JSON:

```
[Net.ServicePointManager]::SecurityProtocol = 'tls12'; irm https://blackducksoftware.github.io/hub-detect/hub-detect.ps1?$(Get-Random) | iex; detect --detect.hub.signature.scanner.host.url=https://saleshub.blackducksoftware.com --detect.hub.signature.scanner.dry.run=true --blackduck.hub.offline.mode=true
```

## Linux/Unix

<a name="linux"></a>

**Shell**

Send results to the Hub:

```
#!/bin/bash
bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --blackduck.hub.url=http://myhub.url --blackduck.hub.username=myusername --blackduck.hub.password=mypassword
```

Offline scan to create JSON:

```
#!/bin/bash
bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --detect.hub.signature.scanner.host.url=https://saleshub.blackducksoftware.com --detect.hub.signature.scanner.dry.run=true --blackduck.hub.offline.mode=true
```

## Examples

<a name="examples"></a>


