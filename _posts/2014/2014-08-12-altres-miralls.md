---

title: Miralls alternatius durant l'apagada del servidor de Caliu
layout: default

---

Seguim amb el servidor de Caliu aturat i la previsió és que aquesta situació pot durar encara un parell de setmanes més, fins que s'acabin els serveis mínims d'agost al Campus Nord de la UPC.

Els serveis afectats són els següents:

*   Els miralls dels paquets i imatges de diverses distribucions.
*   La web principal de Caliu i els blogs.
*   Els wikis de Caliu i KDE.
*   El planeta Caliu.

Els serveis '''no afectats'' són aquests altres:

*   Les [llistes](http://llistes.cpl.upc.edu/) de distribució.
*   El correu del domini caliu.cat.
*   El servei de XMPP/Jabber.
*   El [canal](https://webchat.freenode.net/?channels=caliu) d'IRC a Freenode.

Com que el servei de miralls és el que té més impacte us oferim un consell per triar el mirall més proper automàticament en les distribucions més populars: heu de canviar la URL del mirall al fitxer `/etc/apt/sources.list` segons el cas:

*   [Debian](http://http.debian.net/)

        deb http://http.debian.net/debian stable main

*   [Ubuntu](http://askubuntu.com/questions/37753/how-can-i-get-apt-to-use-a-mirror-close-to-me-or-choose-a-faster-mirror)

        deb mirror://mirrors.ubuntu.com/mirrors.txt trusty          main restricted universe multiverse
        deb mirror://mirrors.ubuntu.com/mirrors.txt trusty-updates  main restricted universe multiverse
        deb mirror://mirrors.ubuntu.com/mirrors.txt trusty-security main restricted universe multiverse

Si necessiteu posar-vos en contacte amb nosaltres, podeu fer-ho al correu dels ''masovers a caliu punt cat'' per a qüestions tècniques relacionades amb el servidor i a ''junta a caliu punt cat'' per a qualsevol altra cosa.

[@alexmuntada](https://twitter.com/alexmuntada)
