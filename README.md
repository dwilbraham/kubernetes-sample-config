Some simple sample config to run test sshd containers.

Log into them as root:root

Quick launch:

```shell
kubecfg -p 31001:22 run rastasheep/ubuntu-sshd 1 sshd-test-controller
```
