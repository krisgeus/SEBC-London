1. Check vm.swappiness  
```
sysctl vm.swappiness
```

	Setting it with `sysctl vm.swappiness=1` doesn't survive a reboot so  need to set it in a more permanant way.  
```  
sudo sh -c 'echo "vm.swappiness = 1" >> /etc/sysctl.d/00_swappiness.conf'
```
2. Show mount attributes.  
``` 
mount
```  
3. Show the reserve space of ext based volumes    
4. Disable transparent hugepages  
```
sudo sh -c 'echo never > /sys/kernel/mm/transparent_hugepage/enabled'
sudo sh -c 'echo never > /sys/kernel/mm/transparent_hugepage/defrag'
```

5. List network interface configuration  
```
ifconfig -a
```
6. List forward and reverse lookups using getent or nslookup  
```
getent hosts $(hostname -i)
getent hosts $(hostname -f)  
```  
to make sure we get back an ipv4 address use:  
```
getent ahostsv4 $(hostname -f)
```
7. Show nscd is running  
```
systemctl status nscd
```
8. Show ntpd is running  
```
systemctl status ntpd
```