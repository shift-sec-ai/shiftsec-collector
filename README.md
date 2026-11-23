# ShiftSec Collector

ShiftSec Collector is a planned Go agent for Ubuntu and Debian servers running Docker. It will open outbound connections to the ShiftSec platform to send heartbeats and report inventory for the host and its running containers. It will use Syft to identify packages in the container images.

## Source and releases

This public repository will contain the source code, installation instructions, and descriptions of the fields the collector sends. Each release will include its supported message schema and example messages so you can build the collector from source and verify the protocol for that version.

GitHub Releases will provide a `.deb` package and its SHA-256 checksum. You choose when to install or update the collector on your servers.
