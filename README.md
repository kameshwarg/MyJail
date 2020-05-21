# MyJail

Steps to create a simple jail on ubuntu /debian systems.
Once created can be copied/modified on to other systems and run

```
mkdir d
debootstrap stretch d
mount -B /dev d/dev
mount -B /dev/pts d/dev/pts
mount -B /proc d/proc
mount -B /sys d/sys
chroot d /bin/bash
```

Note: might have to use sudo if restricted

once the chroot to the jail (the folder 'd' that was created) you would be in a fully functioning debian setup
[insert image]

Now you may install your packages of choosing
example
`apt update`
you may want to update your package manager, probably `yum upgrade -y` in redhat
`apt-get install docker`
[insert image]
you can run docker within the confines of folder 'd'
`apt-get install postgresql`

Note: you may have to jump through some hoops to get the services started as it is chroot and requests might be ignored
https://superuser.com/questions/688733/start-a-systemd-service-inside-chroot

