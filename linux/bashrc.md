# .bashrc

This file in `~/.bashrc` acts as a user specific setup of bash.

### My preferences

Here are things I can't live without.

**Abbrevitation for ls**

```
alias ll='ls -ls'
```

> For raspbian it's almost there, but commented out and without -s option.

**Kubectl with completion**

```
alias k=kubectl
source <(kubectl completion bash)
complete -F __start_kubectl k
```
