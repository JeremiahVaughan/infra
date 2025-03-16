Install:
    - `git clone https://github.com/JeremiahVaughan/infra`
    - `sudo apt update && sudo apt install haproxy -y`
    - `sudo cp ./infra.service /etc/systemd/system/infra.service`
    - `sudo cp ./haproxy.cfg /etc/haproxy/haproxy.cfg`
    - `sudo systemctl enable haproxy`
    - `sudo systemctl start haproxy`
    - `sudo systemctl status haproxy`
