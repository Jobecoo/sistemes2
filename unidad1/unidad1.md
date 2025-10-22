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

1. Crear un nou servei:
    - Opció 1: nssm.exe
    - Opció 2: Powershell
2. Executar un script a l'inici de sessio d'un usuari determinat
3. Services.msc automàtic
