# ShiftSec Collector

ShiftSec Collector is a planned Go agent for Ubuntu and Debian servers running Docker. ShiftSec will use its inventory to identify which running services a vulnerability affects.

## What the collector will report

The collector will send a heartbeat every 10 minutes over an outbound connection to ShiftSec. It will send an inventory snapshot every hour and whenever the set of running containers changes.

An inventory snapshot will include the following data.

- **Host** — operating system version and installed packages.
- **Containers** — exact image versions, published ports, and Docker networks for each running container.
- **Images** — packages that Syft identifies in each image.
- **Configuration** — selected settings that ShiftSec uses to assess vulnerabilities.

The inventory will exclude environment variables, secrets, application and database contents, logs, source code, and user files.

## Docker access

The collector will need access to the Docker daemon. When the daemon runs as root, that access grants root-equivalent privileges on the host. The collector's code will limit its use of Docker to read operations.

## Source and releases

You will be able to build the collector from this public repository and follow the installation instructions for your release. Each release will document the fields the collector sends and include the matching message schema, a sample heartbeat, and examples of complete and partial inventory snapshots. You can compare the schemas before upgrading to see which fields have changed.

GitHub Releases will provide the `.deb` package, its SHA-256 checksum, and release notes. You choose the version, verify the package against its checksum, and decide when to install it on your servers.
