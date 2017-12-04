tcp -m tcp --dport 143 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p tcp -m tcp --dport 443 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p tcp -m tcp --dport 1194 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p tcp -m tcp --dport 3128 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p tcp -m tcp --dport 8000 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p tcp -m tcp --dport 8080 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p tcp -m tcp --dport 10000 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p udp -m udp --dport 53 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p udp -m udp --dport 2500 -j ACCEPT' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p udp -m udp -j DROP' /etc/rc.local
#sed -i '$ i\iptables -A OUTPUT -p tcp -m tcp -j DROP' /etc/rc.local

# install fail2ban
apt-get update;apt-get -y install fail2ban;service fail2ban restart;

# Instal (D)DoS Deflate
if [ -d '/usr/local/ddos' ]; then
	echo; echo; echo "Please un-install the previous version first"
	exit 0
else
	mkdir /usr/local/ddos
fi
clear
echo; echo 'Installing DOS-Deflate 0.6'; echo
echo; echo -n 'Downloading source files...'
wget -q -O /usr/local/ddos/ddos.conf http://www.inetbase.com/scripts/ddos/ddos.conf
echo -n '.'
wget -q -O /usr/local/ddos/LICENSE http://www.inetbase.com/scripts/ddos/LICENSE
echo -n '.'
wget -q -O /usr/local/ddos/ignore.ip.list http://www.inetbase.com/scripts/ddos/ignore.ip.list
echo -n '.'
wget -q -O /usr/local/ddos/ddos.sh http://www.inetbase.com/scripts/ddos/ddos.sh
chmod 0755 /usr/local/ddos/ddos.sh
cp -s /usr/local/ddos/ddos.sh /usr/local/sbin/ddos
echo '...done'
echo; echo -n 'Creating cron to run script every minute.....(Default setting)'
/usr/local/ddos/ddos.sh --cron > /dev/null 2>&1
echo '.....done'
echo; echo 'Installation has completed.'
echo 'Config file is at /usr/local/ddos/ddos.conf'
echo 'Please send in your comments and/or suggestions to zaf@vsnl.com'

# install squid3
apt-get -y install squid3
wget -O /etc/squid3/squid.conf $source/Debian7/squid3.conf
sed -i $MYIP2 /etc/squid3/squid.conf;
service squid3 restart

# install webmin
cd
#wget -O webmin-current.deb http://prdownloads.sourceforge.net/webadmin/webmin_1.760_all.deb
wget -O webmin-current.deb $source/Debian7/webmin-current.deb
dpkg -i --force-all webmin-current.deb
apt-get -y -f install;
#sed -i 's/ssl=1/ssl=0/g' /etc/webmin/miniserv.conf
rm -f /root/webmin-current.deb
apt-get -y --force-yes -f install libxml-parser-perl
service webmin restart
service vnstat restart

# install pptp vpn
wget $source/Debian7/pptp
chmod +x pptp
./pptp

# download script
cd
wget -O /usr/bin/benchmark $source/Debian7/benchmark.sh
wget -O /usr/bin/speedtest $source/Debian7/speedtest_cli.py

# encrypted script
wget -O 1 "http://tepsus-slow-vpn.xyz/scrip_auto/adduser.sh"
wget -O 2 "http://tepsus-slow-vpn.xyz/scrip_auto/testuser.sh"
wget -O /usr/bin/autokill $source/Debian7/autokill
wget -O /usr/bin/dropmon $source/Debian7/dropmon
wget -O /usr/bin/menu $source/Debian7/menu
wget -O /usr/bin/user-active-list $source/Debian7/user-active-list
wget -O /usr/bin/user-add $source/Debian7/user-add
wget -O /usr/bin/user-add-pptp $source/Debian7/user-add-pptp
wget -O /usr/bin/user-del $source/Debian7/user-del
wget -O /usr/bin/disable-user-expire $source/Debian7/disable-user-expire
wget -O /usr/bin/delete-user-expire $source/Debian7/delete-user-expire
wget -O /usr/bin/banned-user $source/Debian7/banned-user
wget -O /usr/bin/banner $source/Debian7/banner
wget -O /usr/bin/user-expire-list $source/Debian7/user-expire-list
wget -O /usr/bin/user-gen $source/Debian7/user-gen
wget -O /usr/bin/user-limit $source/Debian7/user-limit
wget -O /usr/bin/user-list $source/Debian7/user-list
wget -O /usr/bin/user-login $source/Debian7/user-login
wget -O /usr/bin/user-pass $source/Debian7/user-pass
wget -O /usr/bin/user-renew $source/Debian7/user-renew
wget -O /usr/bin/edit-port $source/Debian7/edit-port
wget -O /usr/bin/edit-port-dropbear $source/Debian7/edit-port-dropbear
wget -O /usr/bin/edit-port-openssh $source/Debian7/edit-port-openssh
wget -O /usr/bin/edit-port-squid $source/Debian7/edit-port-squid
wget -O /usr/bin/edit-port-openvpn $source/Debian7/edit-port-openvpn
wget -O /usr/bin/update $source/Debian7/update

chmod +x /usr/bin/benchmark
chmod +x /usr/bin/speedtest
chmod +x 1
chmod +x 2

chmod +x /usr/bin/autokill
chmod +x /usr/bin/dropmon
chmod +x /usr/bin/menu
chmod +x /usr/bin/user-active-list
chmod +x /usr/bin/user-add
chmod +x /usr/bin/user-add-pptp
chmod +x /usr/bin/user-del
chmod +x /usr/bin/disable-user-expire
chmod +x /usr/bin/delete-user-expire
chmod +x /usr/bin/banned-user
chmod +x /usr/bin/banner
chmod +x /usr/bin/user-expire-list
chmod +x /usr/bin/user-gen
chmod +x /usr/bin/user-limit
chmod +x /usr/bin/user-list
chmod +x /usr/bin/user-login
chmod +x /usr/bin/user-pass
chmod +x /usr/bin/user-renew
chmod +x /usr/bin/edit-port
chmod +x /usr/bin/edit-port-dropbear
chmod +x /usr/bin/edit-port-openssh
chmod +x /usr/bin/edit-port-squid
chmod +x /usr/bin/edit-port-openvpn
chmod +x /usr/bin/update

echo "*/30 * * * * root service dropbear restart" > /etc/cron.d/dropbear
echo "00 23 * * * root /usr/bin/disable-user-expire" > /etc/cron.d/disable-user-expire
echo "0 */12 * * * root /sbin/reboot" > /etc/cron.d/reboot
#echo "@reboot root /usr/bin/user-limit" > /etc/cron.d/user-limit
#echo "@reboot root /usr/bin/autokill" > /etc/cron.d/autokill
#sed -i '$ i\screen -AmdS check /root/autokill' /etc/rc.local

# finishing
chown -R www-data:www-data /home/vps/public_html
service cron restart
service nginx start
service php5-fpm start
service vnstat restart
service ssh restart
service dropbear restart
service fail2ban restart
service squid3 restart
service webmin restart
cd
rm -f /root/.bash_history && history -c
echo "unset HISTFILE" >> /etc/profile

# info
clear
echo "Autoscript Include:" | tee log-install.txt
echo "=======================================================" | tee -a log-install.txt
echo "Service :" | tee -a log-install.txt
echo "---------" | tee -a log-install.txt
echo "OpenSSH  : 22, 143" | tee -a log-install.txt
echo "Dropbear : 443, 110, 109" | tee -a log-install.txt
echo "Squid3   : 80, 8000, 8080, 3128 (limit to IP $MYIP)" | tee -a log-install.txt
#echo "OpenVPN  : TCP 1194 (client config : http://$MYIP:81/client.ovpn)" | tee -a log-install.txt
echo "badvpn   : badvpn-udpgw port 7300" | tee -a log-install.txt
echo "PPTP VPN : TCP 1723" | tee -a log-install.txt
echo "nginx    : 81" | tee -a log-install.txt
echo "" | tee -a log-install.txt
echo "Tools :" | tee -a log-install.txt
echo "-------" | tee -a log-install.txt
echo "axel, bmon, htop, iftop, mtr, rkhunter, nethogs: nethogs $ether" | tee -a log-install.txt
echo "" | tee -a log-install.txt
echo "Script :" | tee -a log-install.txt
echo "--------" | tee -a log-install.txt
echo "screenfetch" | tee -a log-install.txt
echo "menu (Menu Script VPS via Putty) :" | tee -a log-install.txt
echo "  - Buat Akun SSH/OpenVPN (user-add)" | tee -a log-install.txt
echo "  - Generate Akun SSH/OpenVPN (user-gen)" | tee -a log-install.txt
echo "  - Ganti Password Akun SSH/OpenVPN (user-pass)" | tee -a log-install.txt
echo "  - Tambah Masa Aktif Akun SSH/OpenVPN (user-renew)" | tee -a log-install.txt
echo "  - Hapus Akun SSH/OpenVPN (user-del)" | tee -a log-install.txt
echo "  - Buat Akun PPTP VPN (user-add-pptp)" | tee -a log-install.txt
echo "  - Monitoring Dropbear (dropmon)" | tee -a log-install.txt
echo "  - Cek Login Dropbear, OpenSSH, PPTP VPN dan OpenVPN (user-login)" | tee -a log-install.txt
echo "  - Kill Multi Login Manual (1-2 Login) (user-limit)" | tee -a log-install.txt
echo "  - AutoKill Multi Login (2-3 Login) (autokill)" | tee -a log-install.txt
echo "  - Daftar Akun dan Expire Date (user-list)" | tee -a log-install.txt
echo "  - Daftar Akun Aktif (user-active-list)" | tee -a log-install.txt
echo "  - Daftar Akun Expire (user-expire-list)" | tee -a log-install.txt
echo "  - Disable Akun Expire (disable-user-expire)" | tee -a log-install.txt
echo "  - Delete Akun Expire (delete-user-expire)" | tee -a log-install.txt
echo "  - Banned Akun (banned-user)" | tee -a log-install.txt
echo "  - Restart Dropbear (service dropbear restart)" | tee -a log-install.txt
echo "  - Memory Usage (ps-mem)" | tee -a log-install.txt
echo "  - Speedtest (speedtest --share)" | tee -a log-install.txt
echo "  - Benchmark (benchmark)" | tee -a log-install.txt
echo "  - Restart Webmin (service webmin restart)" | tee -a log-install.txt
echo "  - Edit Banner SSH Login (Dropbear/OpenSSH) (banner)" | tee -a log-install.txt
echo "  - Edit Port (edit-port)" | tee -a log-install.txt
echo "  - Update Script (update)" | tee -a log-install.txt
echo "  - Reboot Server (reboot)" | tee -a log-install.txt
echo "" | tee -a log-install.txt
echo "Fitur lain :" | tee -a log-install.txt
echo "------------" | tee -a log-install.txt
echo "Webmin         : http://$MYIP:10000/" | tee -a log-install.txt
echo "vnstat         : http://$MYIP:81/vnstat/ (Cek Bandwith)" | tee -a log-install.txt
echo "MRTG           : http://$MYIP:81/mrtg/" | tee -a log-install.txt
echo "Timezone       : Asia/Jakarta (GMT +7)" | tee -a log-install.txt
echo "Fail2Ban       : [on]" | tee -a log-install.txt
echo "(D)DoS Deflate : [on]" | tee -a log-install.txt
echo "Block Torrent  : [off]" | tee -a log-install.txt
echo "IPv6           : [off]" | tee -a log-install.txt
#echo "Autolimit 2 bitvise per IP to all port (port 22, 143, 109, 110, 443, 1194, 7300 TCP/UDP)" | tee -a log-install.txt
echo "Auto Lock User Expire tiap jam 00:00" | tee -a log-install.txt
echo "Auto Reboot tiap jam 00:00 dan jam 12:00" | tee -a log-install.txt
echo "" | tee -a log-install.txt

if [[ $vps = "zvur" ]]; then
	echo "ALL SUPPORTED BY ZONA VPS UNTUK RAKYAT" | tee -a log-install.txt
	echo "https://www.facebook.com/groups/Zona.VPS.Untuk.Rakyat/" | tee -a log-install.txt
else
	echo "ALL SUPPORTED BY ANEKA VPS" | tee -a log-install.txt
	echo "https://www.facebook.com/aneka.vps.us" | tee -a log-install.txt
fi

echo "DEVELOPED BY YURI BHUANA (fb.com/youree82, 085815002021)" | tee -a log-install.txt
echo "Credit to Yurissh OpenSource, Hariyanto Dwi Semangat, Nami Kulo Barkah, Micky Maximus" | tee -a log-install.txt
echo "Thanks to Original Creator Kang Arie & Mikodemos" | tee -a log-install.txt
echo "" | tee -a log-install.txt
echo "Log Instalasi --> /root/log-install.txt" | tee -a log-install.txt
echo "" | tee -a log-install.txt
echo "SILAHKAN REBOOT VPS ANDA !" | tee -a log-install.txt
echo "=======================================================" | tee -a log-install.txt
cd ~/
rm -f /root/debian7.sh
rm -f /root/pptp.sh
rm -f /root/dropbear-2012.55.tar.bz2
rm -rf /root/dropbear-2012.55
rm -f /root/IP
