# BDS Hub Detect Instructions

Black Duck Software Hub Detect Documentation

Full Documentation here: https://blackducksoftware.atlassian.net/wiki/spaces/INTDOCS/pages/49131875/Hub+Detect

## Table of Contents

1. [Running your first scan](#firstscan)
2. [Windows](#windows)
3. [Linux/Unix](#linux)
4. [Examples](#examples)
5. [Docker](#docker)



## Running your first scan

<a name="firstscan"></a>

**Prerequisites**

* Run any commands used to gather open source dependencies prior to conducting a scan (if applicable).
* Choose OS you will be running this scan on.
* Typically, scans are run in the root directory of an application/project you would like scanned.

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

## Common Hub Detect properties

<a name="examples"></a>

**Display full list of Hub Detect properties**

```
#!/bin/bash
bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) -hv
```

**Automatically import certificates**

You can automatically import certificates from your instance of the Hub. This is a convenience feature, and your certificates should be imported by your administrator. However, if the certificate is not imported, Hub Detect imports the certificate for you using the following property set to true.

```
#!/bin/bash
bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --blackduck.hub.url=http://myhub.url --blackduck.hub.username=myusername --blackduck.hub.trust.cert=true
```