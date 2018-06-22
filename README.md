# PS4 Server

This is a project designed for the <a href=https://wiki.wemos.cc/products:d1:d1_mini>esp8266 D1 Mini</a> or <a href=https://wiki.wemos.cc/products:retired:d1_mini_pro_v1.0.0>esp8266 D1 Mini PRO V1</a> to be installed inside the console much like a modchip but to provide a wifi http server and dns server.

the D1 Mini is perfect for this project because it is only 34mm x 25mm in size and can operate off 5v using the 5v pin onboard so the usb connection is not needed and the ps4 has 5v solder points.

the <a href=https://wiki.wemos.cc/products:retired:d1_mini_pro_v1.0.0>D1 MINI PRO V1</a> is 34mm x 25mm in size and the <a href=https://wiki.wemos.cc/products:d1:d1_mini_pro>D1 MINI PRO V2</a> is 48mm x 25mm in size, v1 of the board was used in this project because of its smaller size.


the firmware is updatable via http and the exploit files can be managed via http so the esp8266 board once installed never needs to be accessed again.

this is designed to use the 5.05 exploit and payloads in a single html file format like <b>ApptoUsb.html</b>

i would not call this a modchip but its the closest thing we have right now to having a totally self contained method for the ps4 to launch mirafw and the payloads.


<br>
<br>


<b>implemented internal pages</b>

admin.html - the main landing page for administration.

index.html - if no index.html is found the server will generate a simple index page and list the payloads automatically.

info.html - provides information about the esp board.

format.html - used to format the internal storage(<b>SPIFFS</b>) of the esp board.

upload.html - used to upload files(<b>html</b>) to the esp board for the webserver.

update.html - used to update the firmware on the esp board (<b>fwupdate.bin</b>).

fileman.html - used to <b>view</b> / <b>download</b> / <b>delete</b> files on the internal storage of the esp board.

config.html - used to configure wifi ap and ip settings.


there is a storage limitation of <b>2.8mb</b> using the <b>D1 Mini</b> board and <b>14.2mb</b> for the <b>D1 Mini PRO</b> board.

the <b>User's Guide</b> in the ps4 settings menu will be redirected to the main index.html


<br><br>


installation is simple you just use the arduino ide to flash the sketch/firmware to the esp8266 board.<br>
<br>
make sure you set the flash size to match the D1 board you are using.<br>
<b>4M (3M SPIFFS)</b> for the D1 Mini<br>
<img src=https://github.com/stooged/PS4-Server/blob/master/Images/4m3m_spiffs.jpg><br><br>

<b>16M (15M SPIFFS)</b> for the D1 Mini PRO<br>
<img src=https://github.com/stooged/PS4-Server/blob/master/Images/16m15m_spiffs.jpg><br><br>



next you connect to the wifi access point with a pc/laptop, <b>PS4_WEB_AP</b> is the default SSID and <b>password</b> is the default password.<br>
then use a webbrowser and goto http://10.1.1.1/admin.html <b>10.1.1.1</b> is the defult webserver ip.<br>
on the side menu of the admin page select <b>File Uploader</b> and then click <b>Select Files</b> and locate the <b>esp_html</b> folder from this repo and select all the files inside the <b>esp_html</b> folder and click <b>Upload Files</b>
you can then goto <b>Config Editor</b> and change the password for the wifi ap.

once that is all setup you can then install the <a href=https://wiki.wemos.cc/products:d1>D1 Board</a> inside the ps4 console, there are lots of youtube videos to show you how to open the ps4 console and there are some pictures of the points on the ps4 mainboards i use to install the <a href=https://wiki.wemos.cc/products:d1>esp8266 D1</a> inside the images folder of this repo.


<br><br>

updating the html is simple you just power on the ps4 and connect to the wifi ap with a pc/laptop like you did for the initial install and goto upload files again and upload new html.<br>
you can also go into <b>File Manager</b> and delete or download files.

to update the firmware you goto <b>Firmware Update</b> and upload the new firmware file (<b>fwupdate.bin</b>)



<br><br>


the phat, slim and pro consoles all have a location to fit the <a href=https://wiki.wemos.cc/products:d1:d1_mini>esp8266 D1 Mini</a> and <a href=https://wiki.wemos.cc/products:retired:d1_mini_pro_v1.0.0>esp8266 D1 Mini PRO V1</a>

<b>PHAT</b>
<img src=https://github.com/stooged/PS4-Server/blob/master/Images/PHAT_CUH-1102/2.jpg>

<b>SLIM</b>
<img src=https://github.com/stooged/PS4-Server/blob/master/Images/SLIM_CUH-2002/3.jpg>

<b>PRO</b>
<img src=https://github.com/stooged/PS4-Server/blob/master/Images/PRO_CUH-7102/4.jpg>











