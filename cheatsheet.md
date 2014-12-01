# Cheatsheet Enterprise Linux

# Vagrant box opzetten

- Vagrant box add [name]/[version] : invoegen van de vagrant box (matyunin/centos7)
- Vagrant up : launchen van de VM : daarna kan je deze launchen in VBox
- Vagrant halt : afzetten
- Vagrant reload : rebooten
- Vagrant provision : van minimaal OS naar volledig functionerend systeem.
- Vagrant destroy : verwijderen van de VM(s)
- Vagrant box list : lijst van alle VMs in de box.

# Vagrant firewall

- firewalld: service=https permanent=true state=enabled : unblocked de https service
- firewalld: port=8081/tcp permanent=true state=disabled : blocked de TCP poort 8081

# Windows CMD

- Cd .. : één niveau hoger (Lnx cd - )

# CentOS – Firewall controls

- Firewall-cmd --status : status van de firewall
- Firewall-cmd –list-all-zones : overzicht van alle services en poorten die worden gefilterd.

# CentOS – Services controls

- sudo systemctl [start/stop/restart] [naam-service].service : de genoemde service starten/stoppen/herstarten.
- sudo systemctl status [naam-service].service : de status van de service opvragen.
- sudo systemctl [enable/disable] [naam-service].service : de servers wel/niet opstarten bij het booten.

# Utilities

- Bash-completion: vult automatisch opties van commando's aan.

# Bind-Utils

- dig @[ip-of-dnsServer] [FQDN] [NS/A] : vraagt het IP-adres op van de server die geregistreerd staat met deze FQDN. De laatste parameter is optioneel en vraagt de specifieke records op.
- dig @[ip-of-dnsServer] –x [ip-adres]: vraagt de FQDN op van de server met het gegeven ip adres.

# CentOS – Configuratie testen

- named-checkconf [locatie conf]: configuratie testen named.conf
- named-checkzone [naam-zone-file] [locatie-zone-file]: configuratie van zone-file testen.
- testparm: controleert configuratie van Samba config file.

# CentOS – Locaties

| Locatie | Uitleg |
| --- | --- |
| /etc/named.conf | Bind config file |
| /var/named/[zone name] | Bind zone file |
| /etc/dhcp/dhcpd.conf | DHCP config file |
| /etc/vsftpd/vsftpd.conf | VSFTP config file |
| /etc/samba/smb.conf | SMB config file |
| /etc/pki/tls/certs | SSL certificaat locatie |
| /etc/pki/tls/private/ca.key  
/etc/pki/tls/private/ca.csr | SSL locatie private key |
| /etc/httpd/conf.d/ssl.conf | SSL config file |
| /etc/httpd/conf/httpd.conf | http config file |
| /etc/httpd/conf.d/wordpress.conf | Secundaire configs (vn wordpress bv) |
| /etc/sysconfig/network-scripts | In deze map staan de config files voor alle netwerkinterfaces |
| - /var/log/messages (hoofd-log)– /var/log/audit/audit.log (SELinux)– /var/log/httpd/\*– /var/log/samba/\*– /var/log/vsftpd/\* | Oude logfile locaties |

# SELinux

- getsebool –a: toont alle booleans die SELinux bevat en hun status.
- setsebool -P [naamBoolean] [0/1]
- setenforce [0/1]: uit of aanschakelen van SELinux