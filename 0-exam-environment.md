# Exam Environment

## Time management
- 19 problems in 2 hours, skip a question if you get stuck

## Trinity of tooling
1. Edit YAML files
2. vim
3. bash commands

## Relevant Materials
- kubectl cheat sheet
- k8s API resource reference
- You can reference kubernetes.io/docs during the exam

## Getting Help on a Commnad
```sh
$ kubectl <command> --help

# Drill into object details with the explain command
$ kubectl explain pods.spec
```

## Increase productivity
```sh
# Create kubectl alias for speed
$ alias k k=kubectl

# Setting a context and namespace
$ kubectl config set-context <context-of-question> --namespace=<namespace-of-question>

# Internalize resource short names
$ kubectl get ns
$ kubectl describe pvc

# Deleting k8s objects
# Don't wait for graceful deletio of objects
$ kubectl delete pod nginx --grace-period=0 --force
```

## Understand and practice bash
- Practice relevant syntax and language constrcuts
```sh
$ if [! -d ~/tmp]; then mkdir -p ~/tmp; fi; while true;
do echo $(date) >> ~/tmp/date.txt; sleep 5; done;
```

## Finding object information
- Filter configuration with context from a set of objects
```sh
# grep is your friend
$ kubectl describe pods | grep -C 10 "author=John Doe"
```

## Key to exam
- be proficient with kubectl
