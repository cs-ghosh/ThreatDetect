# Task: Apache Hosting & DDOS Simulation

## Objective
Demonnstrate availability threats by simulating SYN flood attack on the Apache web server

## Setup

### Installed and started Apache Web Server:
```bash 
suodo apt install apache2 -y
sudo systemctl start apache2
sudo systemctl enable apache2
```
### Veriied via:

```bash 
curl http://localhost
```
Apache2 default page is displayed


### Created a sample static web page
```bash 
echo "<h1>SecureMe Test Page</h1><p>Testing Availability</p>" | sudo tee /var/www/html/index.html
```
On browser refresh, Apache default page loaded your custom message.

## Attack Simulation

### Used `hping3` SYN flood:
```bash 
sudo hping3 -S --flood -p 80 localhost
```

## Observation:
Expected: logs should flood with connection attempts and Apache should go down <br>
Actual: since it was lightweight web page, apache server was still runing with SYN flood, however system performance slowed down.