# Samba-dfree

Based on http://stanislavs.org/reporting-correct-space-usage-for-samba-shared-zfs-volumes/ but tweaked for my personal liking. 

Basically, it fixes the volume sizes shown on network drives mounted in Windows and residing on a ZFS volume.

![Example 1](/images/example1.png)

You'll want to place the dfree file somewhere like `/usr/local/bin/dfree`, and reference it in `/etc/samba/smb.conf` by adding under `[Global]` the line `dfree command = /usr/local/bin/dfree`.

A side effect of this is that in the share properties, the used size isn't 100% accurate. For example, I have a photos dataset on my main ZFS volume, but that dataset isn't actually using 10TB, the whole volume is. 

![Side Effect 1](/images/sideeffect1.png)
