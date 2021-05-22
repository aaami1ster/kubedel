# kubedel
bash script that enables you to delete pod  or list of pods with one commands. this is same as kubectl delete -l app=xx but for multiple pods. this script is inspired by kubedel 

# Installation
Just download the kubedel file and you're good to go.

## ZSH plugin
If you're using a ZSH plugin manager, you can install kubedel as a plugin.

### Antigen
If you're using Antigen:

Add antigen bundle johanhaleby/kubedel to your .zshrc where you've listed your other plugins.
Close and reopen your Terminal/iTerm window to refresh context and use the plugin. Alternatively, you can run antigen bundle johanhaleby/kubedel in a running shell to have antigen load the new plugin.
### oh-my-zsh
If you're using oh-my-zsh:

In the command line, change to oh-my-zsh's custom plugin directory :
```
cd ~/.oh-my-zsh/custom/plugins/
```
Clone the repository into a new kubedel directory:
```
git clone git@github.com:aaami1ster/kubedel.git kubedel
```
Edit your ~/.zshrc and add kubedel – same as clone directory – to the list of plugins to enable:
```
plugins=( ... kubedel )
```
Then, restart your terminal application to refresh context and use the plugin. Alternatively, you can source your current shell configuration:
```
source ~/.zshrc
```

# Usage

First find the names of all your pods:
```
$ kubectl get pods
```
This will return a list looking something like this:
```
NAME                   READY     STATUS    RESTARTS   AGE
app1-v1-aba8y          1/1       Running   0          1d
app1-v1-gc4st          1/1       Running   0          1d
app1-v1-m8acl  	       1/1       Running   0          6d
app1-v1-s20d0  	       1/1       Running   0          1d
app2-v31-9pbpn         1/1       Running   0          1d
app2-v31-q74wg         1/1       Running   0          1d
my-demo-v5-0fa8o       1/1       Running   0          3h
my-demo-v5-yhren       1/1       Running   0          2h
```

To tail the logs of the two "app2" pods in one go simply do:

$ kubedel app2

To tail multiple applications at the same time seperate them by comma:

$ kubedel app1,app2
