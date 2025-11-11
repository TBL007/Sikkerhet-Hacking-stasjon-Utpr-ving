# Dette er den vanskelige oppgaven
## I denne oppgaven skal du bruke Metasploit til å få tilgang til en maskin
* Maskinen du skal få tilgang til er åpen i VMWARE
* Programmet du skal bruke heter Metasploit og er et terminal basert program
* ![](/Bilder/metasploit.png)
* og nmap  
## step by step
* Første du må gøre er å finne ip addressen til maskinene du skal angripe.
* "Ipconfig" i cmd vil visse ip addresen(e) på maskinen din (ipv4). 
* ip-en til maskinen du skal angripe cfinner du ved å søke nettverket med nmap verktøyet. 
* start med å søke helle nettverket. 
* bruk de første 3 oktettene og legg til et * på slutten for eksempel (192.168.16.*). 
* Kjør kommandoen i cmd
 
* nmap -F (Din modifiserte ip)

* Nå får du opp en liste med alle maskinene på nettverket og info om de som ser ca sånn ut.
* ![](/Bilder/Nmap.png)
* Let etter navnet VMWARE dette er maskinen du skal angripe
* Vmware har mange porter åpne som du kan utnytte
* prøv vnc porten  (5900) 
* gå i metasploit vinduet og let etter kjente svakheter med:
* search vnc
* her er det veldig mange muligheter prøv:
* search vnc_login
* det skal være en mulighet for å bruke den skriv:
* use (tallet til venstre)
* du har nå funnet en brukbar exploit i metasploit 
* nå må du konfigurere den før du kjører den
* skriv:
* options
* nå får du muligheter for hva du kan konfigurere med denne exploiten
* "RHOSTS" er mottaker ipv4 addressen set denne til ip addressen til maskinene du skal angripe*
* set rhosts (ip)
* skjekk at ip-en er satt i options og kjør programmet:
* run
* du skal nå ha fått opp passordet på linjen "Login successful:  :(passordet)"
* koble maskinen i vnc viewer ned ip og passord og du har nå full tilgang til en veldig kjedelig maskin :)


