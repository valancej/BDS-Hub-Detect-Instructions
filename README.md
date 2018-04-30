# BDS-Hub-Detect-Instructions

Black Duck Software Hub Detect Examples

## Table of Contents

1. [Windows](#windows)
2. [Linux/Unix](#linux)

## Windows

<a name="windows"></a>
**Powershell**


## Linux/Unix

<a name="linux"></a>

**Shell**

Send results to the Hub:

`bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --blackduck.hub.url=http://myhub.url --blackduck.hub.username=myusername --blackduck.hub.password=mypassword`

Offline scan to create JSON:

`bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --detect.hub.signature.scanner.host.url=https://saleshub.blackducksoftware.com --detect.hub.signature.scanner.dry.run=true --blackduck.hub.offline.mode=true`
