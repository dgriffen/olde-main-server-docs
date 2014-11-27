Configuration Files
====================
The following are any configuration files that were generated during setup either by a tool or manually edited. They will be listed in the following format:
* /path/to/file/filename
    ```
    contents
    setting=example
    #comments
    ```
---
* /etc/network/interfaces
    ```
    # This file describes the network interfaces available on your system
    # and how to activate them. For more information, see interfaces(5).
    
    # The loopback network interface
    auto lo
    iface lo inet loopback
    
    # The primary network interface
    auto em1
    iface em1 inet static
        address 192.168.16.16
        netmask 255.255.255.0
        gateway 192.168.16.1
        dns-nameserver 192.168.16.16
    ```
* /etc/samba/smb.conf
    ```
    # Global parameters
    [global]
        workgroup = OLDEMAINBREWERY
        realm = OLDEMAINBREWERY.LOCAL
        netbios name = UBUNTUSAMBA
        interfaces = lo, em1
        bind interfaces only = Yes
        server role = active directory domain controller
        dns forwarder = 8.8.8.8
        idmap_ldb:use rfc2307 = yes
        
    [netlogon]
        path = /var/lib/samba/sysvol/oldemainbrewery.local/scripts
        read only = No
        
    [sysvol]
        path = /var/lib/samba/sysvol
        read only = No
    ```