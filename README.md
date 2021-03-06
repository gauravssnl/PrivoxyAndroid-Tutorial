# PrivoxyAndroid-Tutorial
Tutorial for using Privoxy on Android

## Steps

1. Install Privoxy in Termux by using the following command:

```console
apt install privoxy
```

2. Check Privoxy version by using the following command:

```console
privoxy --version
```

3. Download Privoxy Android config file for the same version  from Privoxy website : 
http://www.privoxy.org/sf-download-mirror/Android/

4.Open the downloaded ZIP file and extract etc folder to /sdcard .

5. To enable debugging (logging), edit the /sdcard/etc/privoxy/config file and add these lines to the beginning of the file:

```console


debug 1

debug 2

debug 4

debug 128

debug 512

debug 1024

debug 4096

debug 8192

```

6. Now start Privoxy by using this command :

```console
privoxy --no-daemon /sdcard/etc/privoxy/config
```

7.If everything is alright, you would see Privoxy running successfully on port 8118.
You need to use proxy as 127.0.0.1 & port as 8118 in Access Point Name ( APN)  settings of your Network .

8.If you do not want to type this command each time, save the above command as privoxy.sh in HOME directory of Termux, then you can use this command:

```console
sh privoxy.sh
```

9.(optional) You can also  forward requests to HTTP / SOCKS proxy.Read Privoxy config files for more details. In case you need to forward requests to HTTP proxy ( say http-proxy.com:80)  , you can add anyone of this line to /sdcard/etc/privoxy/config file:

```console
forward   /      http-proxy.com:8080
```
10.(optional) In case you need to forward requests to SOCKS5 proxy ( say socks5-proxy.com:9050)  , you can add anyone of this line to /sdcard/etc/privoxy/config file:

```console
forward-socks5 /  socks5-proxy.com:9050 .
```


