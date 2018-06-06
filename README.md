# PS4 Server

This is a project designed for the <a href=https://wiki.wemos.cc/products:d1:d1_mini>esp8266 D1 Mini</a> to be installed inside the console much like a modchip but to provide a wifi http server and dns server.

the D1 Mini is perfect for this project because it is only 34mm x 25mm in size and can operate off 5v using the 5v pin onboard so the usb connection is not needed and the ps4 has 5v solder points.

the firmware is updatable via http and the exploit files can be managed via http so the esp8266 board once installed never needs to be accessed again.

this is designed to use the 5.05 exploit and payloads in a single html file format like <b>ApptoUsb.html</b>

i would not call this a modchip but its the closest thing we have right now to having a totally self contained method for the ps4 to launch mirafw and the payloads.



implemented internal pages:

http://SERVERIP/index.html - if no index.html is found the server will generate a simple index page and list the payloads automatically.

http://SERVERIP/info.html - provides information about the esp board.

http://SERVERIP/format.html - used to format the internal storage(<b>SPIFFS</b>) of the esp board.

http://SERVERIP/upload.html - used to upload files(<b>html</b>) to the esp board for the webserver.

http://SERVERIP/update.html - used to update the firmware on the esp board (<b>fwupdate.bin</b>).

http://SERVERIP/fileman.html - used to <b>view</b> / <b>download</b> / <b>delete</b> files on the internal storage of the esp board.


there is a storage limitation of <b>2.8mb</b> using the D1 Mini board

the <b>User's Guide</b> in the ps4 settings menu will be redirected to the main index.html