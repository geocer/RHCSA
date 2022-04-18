find / - name "passwd"
which passwd
whereis passwd

=====

ln /etc/hosts computers
ls -il /etc/hosts computers
ln -s computers newcomputers
ls -il /etc/hosts computers newcomputers

======
du -Sh | sort -rh | head -5
find -type f -exec du -Sh {} + | sort -rh | head -n 5
find /dir/to/search/ -type f -name "FILES-TO-FIND" -depth -delete

======

tar cvf /root/etc.tar /etc
tar czvf /root/etc2.tgz /etc
tar tvf /root/etc2.tgz
tar xvf /root/etc.tar -C /tmp
tar xvf /root/etc.tar -C / etc/wgetrc
