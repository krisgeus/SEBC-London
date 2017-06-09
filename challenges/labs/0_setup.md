### Cloud provider

AWS

### Linux release
```
cat /etc/redhat-release 
Red Hat Enterprise Linux Server release 7.3 (Maipo)
```

### Diskspace on each node
```
df -h
```

automated that with the following ansible commandline
```
ansible -u ec2-user -m command -a "df -h" all
```

output:

```
52.209.129.57 | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1.2G   99G   2% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000

52.19.57.45 | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1.2G   99G   2% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000

52.211.62.211 | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1.2G   99G   2% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000

54.77.46.69 | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1.2G   99G   2% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000

34.248.13.233 | SUCCESS | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2      100G  1.2G   99G   2% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/0
tmpfs           1.5G     0  1.5G   0% /run/user/1000
```

### yum repolist command
```
sudo yum repolist enabled
```

with ansible that is
```
ansible -u ec2-user -b -m command -a "yum repolist enabled" all
```

output:

```
54.77.46.69 | SUCCESS | rc=0 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                           repo name               status
!rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastr      6
!rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linu 14,447
!rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linu    228
repolist: 14,681

52.19.57.45 | SUCCESS | rc=0 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                           repo name               status
!rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastr      6
!rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linu 14,447
!rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linu    228
repolist: 14,681

34.248.13.233 | SUCCESS | rc=0 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                           repo name               status
!rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastr      6
!rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linu 14,447
!rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linu    228
repolist: 14,681

52.209.129.57 | SUCCESS | rc=0 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                           repo name               status
!rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastr      6
!rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linu 14,447
!rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linu    228
repolist: 14,681

52.211.62.211 | SUCCESS | rc=0 >>
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                           repo name               status
!rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastr      6
!rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linu 14,447
!rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linu    228
repolist: 14,681
```

### Add users
```
sudo useradd -u 2000 theresa
sudo useradd -u 3000 jeremy
```

### add groups
```
sudo groupadd conservative
sudo groupadd labour
```

### add users to groups
```
sudo usermod -a -G conservative theresa
sudo usermod -a -G labour jeremy
```

### Combined in ansible to do this on all hosts this is
```
- hosts: all
  user: ec2-user
  become: yes
  become_method: sudo
  tasks:

  - name: "add groups"
    user: name={{ item }} state=present
    with_items:
    - conservative
    - labour

  - name: "add user theresa"
    user: name=theresa uid=2000 groups=conservative state=present

  - name: "add user jeremy"
    user: name=jeremy uid=3000 groups=labour state=present
```

### List passwd entries
```
sudo sh -c "cat /etc/passwd | grep -e theresa -e jeremy"
```

In ansible that is
```
ansible -u ec2-user -b -m shell -a "cat /etc/passwd | grep -e theresa -e jeremy" all
```

output

```
52.209.129.57 | SUCCESS | rc=0 >>
theresa:x:2000:2000::/home/theresa:/bin/bash
jeremy:x:3000:3000::/home/jeremy:/bin/bash

52.211.62.211 | SUCCESS | rc=0 >>
theresa:x:2000:2000::/home/theresa:/bin/bash
jeremy:x:3000:3000::/home/jeremy:/bin/bash

34.248.13.233 | SUCCESS | rc=0 >>
theresa:x:2000:2000::/home/theresa:/bin/bash
jeremy:x:3000:3000::/home/jeremy:/bin/bash

54.77.46.69 | SUCCESS | rc=0 >>
theresa:x:2000:2000::/home/theresa:/bin/bash
jeremy:x:3000:3000::/home/jeremy:/bin/bash

52.19.57.45 | SUCCESS | rc=0 >>
theresa:x:2000:2000::/home/theresa:/bin/bash
jeremy:x:3000:3000::/home/jeremy:/bin/bash

```

### List group entries
```
sudo sh -c "cat /etc/group | grep -e conservative -e labour"
```

in ansible that is
```
 ansible -u ec2-user -b -m shell -a "cat /etc/group | grep -e conservative -e labour" all
```

output

```
34.248.13.233 | SUCCESS | rc=0 >>
conservative:x:1001:theresa
labour:x:1002:jeremy

52.19.57.45 | SUCCESS | rc=0 >>
conservative:x:1001:theresa
labour:x:1002:jeremy

52.209.129.57 | SUCCESS | rc=0 >>
conservative:x:1001:theresa
labour:x:1002:jeremy

52.211.62.211 | SUCCESS | rc=0 >>
conservative:x:1001:theresa
labour:x:1002:jeremy

54.77.46.69 | SUCCESS | rc=0 >>
conservative:x:1001:theresa
labour:x:1002:jeremy
```