# GIT_SSH

A cartridge to make it easier to build from GitHub or BitBucket with the OpenShift Jenkins.

In short, cartridges may never write to ~/.ssh, so connecting to GitHub or BitBucket will fail with an error about the host key.

This cartridge provides an executable called `git-ssh` and the `GIT_SSH` environmental variable to point at that executable. 

The script will cause all git operations to SSH command with the `StrictHostKeyChecking` option set to no.

## Keys and Credentials

You can put an SSH key into `$OPENSHIFT\_DATA\_DIR/git-ssh/id_rsa` and the `git-ssh` binary will use it.

Finally, for good measure, it will unlock ~/.netrc, in case your Jenkins builds need to store credentials there.
