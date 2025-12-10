# Targets

Mitjançant els targets farem funcional un keylogger que s'iniciï automàticament amb la màquina, i que envie al correu totes les tecles que l'usuari a premut.

Creem un directori ocult que emmagatzemi el keylogger

<img width="589" height="25" alt="image" src="https://github.com/user-attachments/assets/599ca31a-7a19-487c-ab6e-e397d03c4c38" />

Creem el keylogger

<img width="683" height="23" alt="image" src="https://github.com/user-attachments/assets/0b3b4d92-01cf-4c4f-9ff5-827853a58080" />

Aqui podem observar el script 

<img width="719" height="814" alt="image" src="https://github.com/user-attachments/assets/de08a275-0271-49f1-8e5d-4f62588fd71b" />

Li donem permisos d'execució

<img width="788" height="49" alt="image" src="https://github.com/user-attachments/assets/8c9c80e1-7f3b-4765-bb11-63e92c2838e3" />

Creem un servei anomenat keylogger

<img width="645" height="23" alt="image" src="https://github.com/user-attachments/assets/f95f86d5-9a6f-46cd-92b1-553be7f00fb5" />

Fem que el servei executi el python que hem creat anteriorment.

<img width="723" height="271" alt="image" src="https://github.com/user-attachments/assets/09b7b92c-f075-49ef-953f-e1598332c5bc" />

Recarreguem el systemd, l'habilitem i l'iniciem, i després comprovem que funcioni.

<img width="841" height="240" alt="image" src="https://github.com/user-attachments/assets/12ecdea7-4d65-475e-8f09-74809d696b84" />

I com podem observar en el nostre correu, s'esta fent un registre del keylogger.

<img width="464" height="540" alt="image" src="https://github.com/user-attachments/assets/bbbc69f8-2719-449c-a969-8cb5568ac104" />

# Serveis Windows

Ara faré el mateix però amb windows, mitjançant l'eina nssm. Primer descarreguem l'eina, i desrpés obrim el powershell i anem al directori del nssm. De moment el deixem així. Ara, crearem un fitxer on posarem el nostre keylogger, un python per a que llençi el keylogger com a servei, i un últim arxiu per a que en iniciar no s'obri una finestra de python. 

<img width="610" height="75" alt="image" src="https://github.com/user-attachments/assets/3c590eee-b6eb-4fb4-9104-fea00ac32921" />

Instal·lem el servei, relacionant-lo amb python i després el configurarem

<img width="1006" height="43" alt="image" src="https://github.com/user-attachments/assets/92dbc72b-6992-45e1-9a1c-12cc6bffea28" />

Li donem el nom al servei i també la ruta del nostre servei de keylogger que llença el keylogger.

<img width="958" height="85" alt="image" src="https://github.com/user-attachments/assets/d53290ce-82c9-44eb-80c4-8a86f419d7d0" />

Establim que es faci un auto start

<img width="775" height="30" alt="image" src="https://github.com/user-attachments/assets/a279aaa4-3a52-4ad7-8939-acaa4ab5282a" />

Com podem veure el nostre servei està RUNNING.

<img width="647" height="118" alt="image" src="https://github.com/user-attachments/assets/c16886dd-ef96-44fe-a549-dd3c7bbb7e76" />

Reiniciem l'ordinador i podem observar com ja comença a enviar correus. 

<img width="1391" height="111" alt="image" src="https://github.com/user-attachments/assets/af8fa413-9734-4025-afea-73dc1335c8db" />



# Kernel

Mitjançant uname -r podem comprovar la versió del nostre kernel.

<img width="350" height="47" alt="image" src="https://github.com/user-attachments/assets/cbd24190-1840-4190-a733-88728a4b7919" />

Descarguem el kernel

<img width="729" height="238" alt="image" src="https://github.com/user-attachments/assets/ae8f40bf-eb69-44e5-b246-656e19aa833a" />

Aquí isntal·lem les dependències que necessitem per a realitzar la compilació de kernel. 

<img width="729" height="75" alt="image" src="https://github.com/user-attachments/assets/1d9e5551-2583-4dff-b67d-d1eb1f361ac3" />

Amb la comanda make menuconfig podem modificar característiques del kernel el cual volem compilar.

<img width="771" height="551" alt="image" src="https://github.com/user-attachments/assets/4473180b-0bfb-4366-ac4a-d1ba4dcfa4ed" />

Jo personalment desactivaré la funció de xarxa per a que es pugui comprovar que realment funciona. 
<img width="633" height="724" alt="image" src="https://github.com/user-attachments/assets/28262398-2757-4fdf-8aff-8afee79d2faf" />

Al .config toquem dues línies les cuals fan que revisi uns certificats que no tenim.

<img width="482" height="134" alt="image" src="https://github.com/user-attachments/assets/ef7e48ac-0d3e-4fa8-a02e-b8b53dc472e2" />

Amb la comanda make ja podem començar la compilació del kernel. 

<img width="621" height="598" alt="image" src="https://github.com/user-attachments/assets/bb69ed15-5419-4a01-9bf4-4fb865c7421f" />

Realitzem un make install  quan acabi

<img width="659" height="436" alt="image" src="https://github.com/user-attachments/assets/719af529-5a89-41a2-a770-eac8b443cfe6" />

Actualitzem el grub

<img width="614" height="110" alt="image" src="https://github.com/user-attachments/assets/bb81367c-db97-48c8-adfa-80e5e72ee890" />
