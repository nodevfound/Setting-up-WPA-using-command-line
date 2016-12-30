# Setting-up-WPA-using-command-line

1) Install wpasupplicant <br>
2) Use the WPA passphrase to calculate the correct WPA PSK hash for your SSID by altering the following example:<br>
 $ wpa_passphrase myssid my_very_secret_passphrase<br>

  network={<br>
          ssid="myssid"<br>
          #psk="my_very_secret_passphrase"<br>
          psk=ccb290fd4fe6b22935cbae31449e050edd02ad44627b16ce0151668f5f53c01b<br>
  }<br>

3) Open /etc/network/interfaces in a text editor <br>

  auto wlan0<br>
  iface wlan0 inet dhcp<br>
          wpa-ssid myssid<br>
          wpa-psk ccb290fd4fe6b22935cbae31449e050edd02ad44627b16ce0151668f5f53c01b<br>
          
 4) Restart interface<br>
    $ ifdown wlan0<br>
    $ ifup wlan0<br>
