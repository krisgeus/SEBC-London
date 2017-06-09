## yum repo cm
```
ll /etc/yum.repos.d
```

output

```
total 40
-rw-r--r--. 1 root root  294 Jun  9 06:08 cloudera-manager.repo
-rw-r--r--. 1 root root 1209 Jun  9 05:18 mysql-community.repo
-rw-r--r--. 1 root root 1209 Jun  9 05:15 mysql-community.repo.rpmsave
-rw-r--r--. 1 root root 1060 Jan 29  2014 mysql-community-source.repo
-rw-r--r--. 1 root root  358 Oct 20  2016 redhat.repo
-rw-r--r--. 1 root root  607 Jun  9 03:40 redhat-rhui-client-config.repo
-rw-r--r--. 1 root root 8679 Jun  9 03:40 redhat-rhui.repo
-rw-r--r--. 1 root root   80 Jun  9 03:40 rhui-load-balancers.conf
```

## scm prepare db
```
sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-2-76.eu-west-1.compute.internal --scm-host $(hostname -f) scm scm scm123
```