# GIT_SSH

A cartridge to make it easier to build from GitHub or BitBucket with the OpenShift Jenkins.

In short, cartridges may never write to ~/.ssh, so connecting to GitHub or BitBucket will fail with an error about the host key.

This environmental variable and script will have git use a custom SSH command that sets the `StrictHostKeyChecking` option to no.

Finally, for good measure, it will unlock ~/.netrc, in case your Jenkins builds need to store credentials there.
