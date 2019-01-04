# ossec-base

## Instructions
- Install the atomic repo. Only needed if you don't have /etc/yum.repos.d/atomic.repo yet
```
rpm -ivh https://updates.atomicorp.com/channels/atomic/centos/7/x86_64/RPMS/atomic-release-1.0-21.el7.art.noarch.rpm
```
- Download OSSEC
```
yum install --enablerepo=atomic ossec-hids-server
```
- Clone the repo
```
git clone https://github.com/VoyagerInnovations/ossec-base.git /tmp/ossec-base
```
- Copy the configs
```
cp -ran /tmp/ossec-base/etc/* /var/ossec/etc/ && cp -ran /tmp/ossec-base/rules/* /var/ossec/rules/ && rm -rf /tmp/ossec-base
chmod 644 /var/ossec/etc/internal_options.conf && chmod 650 /var/ossec/etc/
```
- Start OSSEC
```
service ossec-hids start
```
