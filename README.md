# BDS-Hub-Detect-Instructions

## Hub Detect on Windows

### Powershell

## Hub Detect on Linux/Unix

### Send results to the Hub

`bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --blackduck.hub.url=http://myhub.url --blackduck.hub.username=myusername --blackduck.hub.password=mypassword`

### Offline scan to create JSON

`bash <(curl -s https://blackducksoftware.github.io/hub-detect/hub-detect.sh) --detect.hub.signature.scanner.host.url=https://saleshub.blackducksoftware.com --detect.hub.signature.scanner.dry.run=true --blackduck.hub.offline.mode=true`
