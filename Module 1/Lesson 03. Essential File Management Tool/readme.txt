find / - name "passwd"
which passwd
whereis passwd

=====

ln /etc/hosts computers
ls -il /etc/hosts computers
ln -s computers newcomputers
ls -il /etc/hosts computers newcomputers

======

tar cvf /root/etc.tar /etc
tar czvf /root/etc2.tgz /etc
tar tvf /root/etc2.tgz
tar xvf /root/etc.tar -C /tmp
tar xvf /root/etc.tar -C / etc/wgetrc