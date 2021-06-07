ATTENTION!!! Before use, it is recommended to remove all comments in the code, lines start with ##

1) After installation, turn on the uniper, you can connect using an adapter COM port - RJ-45
   (connect to the port labeled CONSOLE, this connector has nothing to do with the ethernet port and is used
   only for device configuration) via PuTTY program

2) Wait for full download and root @ srx%
3) Enter cli
4) Enter edit
5) Enter set system host-name RouterName (device name)
6) Enter set system root-authentication plain-text-password
7) Enter the new root password twice
8) Enter set system services web-management http interface [fe-0/0 / 2.0 vlan.20]
9) Enter set system services ssh (SSH activation)
10) Select the interfaces that will look on the Internet in our case, fe0 / 0/0, and fe0 / 0/1 in the LAN network
12) set interface fe-0/0/2 unit 0 family ethernet-switching port-mode trunk
13) set interface fe-0/0/2 unit 0 family ethernet-switching vlan members [v-10 v-20 v-30 v-40 v-50 v-60 v-70 v-80 v-90 v-100 v-101]
14) set interface vlan unit 10 family inet address 192.168.10.1/24
15) Then you can connect your computer to the device via the fe-0/0/2 port
16) Go to the browser and enter the ip address of the gateway 192.168.10.1 and go to the uniper page
17) Enter the login password as root
18) Click on the CLI button and select CLI Edit
19) Copy the required code from Config-juniper.txt and paste into the field
20) Edit before everything is as it should be (respecting spaces and brackets, and;)
21) When finished, click the "Commit" button (in the upper right corner)
22) Repeat 19 and / or 20 and 21 until everything is as it should be)
