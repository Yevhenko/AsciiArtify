1. instal krew and add it yo PATH: https://krew.sigs.k8s.io/docs/user-guide/setup/install
2. give propper rights to file `chmod 755 scripts/kubeplugin`
3. copy plugin to the PATH directory `sudo cp scripts/kubeplugin /usr/local/bin/kubectl-kubeplugin`
4. use this command to run script `kubectl kubeplugin pod kube-system`