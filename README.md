# BDS-Hub-Detect-Instructions

Black Duck Software Hub Detect Examples

## Table of Contents

1. [Windows](#windows)
2. [Linux/Unix](#linux)

## Windows

<a name="windows"></a>

**Powershell**

These are meant to be run inside powershell.

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
