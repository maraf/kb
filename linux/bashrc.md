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
`kubectl` is so long, let's make it shorter `k`.

```
alias k=kubectl
source <(kubectl completion bash)
complete -F __start_kubectl k
```

**kubens**
For switching current namespace

```
_kube_namespaces()
{
  local curr_arg;
  curr_arg=${COMP_WORDS[COMP_CWORD]}
  COMPREPLY=( $(compgen -W "- $(kubectl get namespaces -o=jsonpath='{range .items[*].metadata.name}{@}{"\n"}{end}')" -- $curr_arg ) );
}
alias kns=kubens
complete -F _kube_namespaces kubens kns
```

**kubectx**
For switching kube cluster contexts

```
_kube_contexts()
{
  local curr_arg;
  curr_arg=${COMP_WORDS[COMP_CWORD]}
  COMPREPLY=( $(compgen -W "- $(kubectl config get-contexts --output='name')" -- $curr_arg ) );
}
alias kctx=kubectx
complete -F _kube_contexts kubectx kctx
```
