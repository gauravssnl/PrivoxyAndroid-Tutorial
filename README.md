# PrivoxyAndroid-Tutorial
Tutorial for using Privoxy on Android

## Steps

1. Install Privoxy in Termux by using the following command:

`code
apt install privoxy
`

2. Check Privoxy version by using the following command:

`code
privoxy --version
`

3. Download Privoxy Android config file for the same version  from Privoxy website : 
http://www.privoxy.org/sf-download-mirror/Android/

4.Open the downloaded ZIP file and extract etc folder to /sdcard .

5. To enable debugging (logging), edit the /sdcard/etc/privoxy/config file and add these lines to the beginning of the file:

`code
debug 1

debug 2

debug 4

debug 128

debug 512

debug 1024

debug 4096

debug 8192
`
6. Now start Privoxy by using this command :

`code
privoxy --no-daemon /sdcard/etc/privoxy/config
`

7.If everything is alright, you would see Privoxy running successfully on port 8118.
You need to use proxy as 127.0.0.1 & port as 8118 in Access Point Name ( APN)  settings of your Network .

8.You can forward requests to HTTP / SOCKS proxy.Read Privoxy config files for example. In case you need to forward request to SOCKS5 proxy (say example.com:9050) , you can add these lines to /sdcard/etc/privoxy/config file:

`code
forward-socks5forward-socks5forward-sockforward-socks5forward-socks5forward-sockforward-socks5forward-socks5forward-socks5forward-socks5 / example.com:9050
`


