# Problem
An Indian website seemed in-accesssible from the USA. The website in question is GHMC(https://www.ghmc.gov.in/). This is Greater Hyderabad Municipal Corporation

# Solution
While there might be easier solutions to access Indian websites from USA. This is the solution that I tried and that worked for me. I did try installing some VPN's but none of them worked under the free plan to connect with an Indian server.

- Create a DigitalOcean Account
- Create a Droplet
  - with 2vCPU and 2Gb memory.(Default with 1Gb and 1vCPU wont work).
  - Choose region as Banglore(Very Important)
- Access the Console and run the following commands
-  `sudo apt update && sudo apt upgrade -y`
-  Install LightWeight Desktop `sudo apt install xfce4 xfce4-goodies -y`
-  Install VNC Server `sudo apt install tightvncserver -y`
-  Install Chrome
   - `wget -q -O - https://dl.google.com/linux/linux_signing_key.pub | sudo apt-key add -`
   - `echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" | sudo tee /etc/apt/sources.list.d/google-chrome.list`
   - `sudo apt update`
   - `sudo apt install google-chrome-stable -y`
 - Configure VNC
   - `vncserver :1`
   -  Set password when prompted
   - `vncserver -kill :1`
   - `echo "startxfce4 &" > ~/.vnc/xstartup`
   - `chmod +x ~/.vnc/xstartup`
   - `vncserver :1`
 - Connect to VNC Server from Ubuntu
   - Install VNC viewer on your Ubuntu laptop
   - `sudo apt install tigervnc-viewer -y`
   - `# Connect to your droplet`
   - `vncviewer your-droplet-ip:5901`
 - Start Chrome as follows
   - Open a terminal
   - `google-chrome --no-sandbox`
   - access the ghmc website and it works
