Configure:
    - allow firewall traffic only through:
        - 22
        - 443
        - 2222
    - set static ip:
       - My raspberry pi's appear to be using NetworkManager
       - List network connections: 
            - `sudo nmcli con show`
       - Modify connection:
            - `sudo nmcli con mod 'Wired connection 1' ipv4.addresses <ip_address>/30`
            - `sudo nmcli con mod 'Wired connection 1' ipv4.gateway <ip_address>`
            - `sudo nmcli con mod 'Wired connection 1' ipv4.dns "1.1.1.1 8.8.8.8"`
            - `sudo nmcli con mod 'Wired connection 1' ipv4.method manual`
            - `sudo nmcli con up 'Wired connection 1'`
        
Install:
    - `git clone https://github.com/JeremiahVaughan/infra`
    - `sudo apt update && sudo apt install haproxy -y`
    - `sudo cp ./haproxy.cfg /etc/haproxy/haproxy.cfg`
    - `sudo systemctl enable haproxy`
    - `sudo systemctl start haproxy`
    - `sudo systemctl status haproxy`
View logs with:
    - `journalctl -u haproxy`
