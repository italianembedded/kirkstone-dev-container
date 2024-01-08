Come inizio un nuovo progetto basato su Yocto Project? Quanto ci metto a mettere in piedi l'ambiente?

Per questo specifico caso devo fare delle assunzioni: ipotizzo infatti di mettere in piedi un ambiente "base". Il che vuol dire che non mi appoggio su nessun hardware in particolare (cioè niente BSP). Se è vero che il procedimento rimane un po' teorico, per il momento voglio concentrarmi sull'ambiente di sviluppo e sugli strumenti che mi aiutano a velocizzare il processo stesso di sviluppo.

In particolare faccio leva sull' IDE VSCode e del suo plugin Dev Container. Grazie a questi due strumenti, link nei commenti, e con l'aggiunta di docker/podman, posso infatti mettere in piedi una build machine Yocto in pochi minuti. Ci vorrà poi qualche ora/giorno per aggiungere i meta-layer necessari e tutte le varie customizzazioni. 

La cosa positiva è che questo approccio velocizza moltissimo i primissimi passi durante l'inizio di un nuovo progetto Embedded Linux basato su Yocto. Il valore aggiunto inoltre è che lo stesso repo può essere usato come base per la continuous integration e continuous delivery, infatti avremo già pronta la macchina container e gli script per automatizzare la build e lanciare i test.

In un ambiente utilizzabile a livello professionale ci sono diverse ottimizzazioni che vanno fatte, per esempio montare la cartella downloads in un volume dati per velocizzare il tutto. Ma per il momento lascio stare queste migliorie e confido che abbiate abbastanza spazio disco per provarlo.

Una volta che la macchina è attiva ti basterà lanciare da dentro la tua home:

/home/dev$ source poky/oe-init-build-env
/home/dev/build$ bitbake core-image-minimal
/home/dev/build$ runqemu slirp

Lo hai già provato? Quanto ci hai messo a riprodurre il tutto? 
Facci sapere qui sotto nei commenti come è andata.

https://code.visualstudio.com/
https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
https://www.docker.com/ oppure https://podman.io/
