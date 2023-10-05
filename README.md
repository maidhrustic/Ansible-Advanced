# Ansible-Advanced keuzedeel.

## De contributors zijn: Joshua, Andy, Maid, Sebastiaan en Michel.

## Nadat je de repo hebt gecloned naar je eigen machine, run dan vervolgens het volgende commando:
`ansible-galaxy collection install -r requirements.yml && ansible-galaxy role install -r requirements.yml`

> **HIERVOOR MOET JE WEL IN DE JUISTE DIRECTORY ZITTEN!!!!!!!!!!!!!** <br>
**Requirements.yml** bevat alle collections/roles die wij hebben gebruikt om de modules in de playbooks te kunnen gebruiken. <br>

Dit zorgt ervoor dat de volgende collections/roles worden geinstalleerd: <br>
Collections:
- community.windows 
- ansible.windows 
- microsoft.ad 

Roles:
- geerlingguy/ansible-role-ntp <br>

Als je al de collections hebt geinstalleerd, dan hoef je dit commando niet uit te voeren. <br>

## Ansible-Vault
Ansible vault maak je aan met het volgende commando: <br>
`ansible-vault create "naam".yml` <br>
Je kan ook een bestaande file encrypten met het volgende commando: <br>
`ansible-vault encrypt "naam".yml` <br>
Om een bestaande file te decrypten gebruik je het volgende commando: <br>
`ansible-vault decrypt "naam".yml` <br>
Al wil je alleen een string encrypten gebruik dan het volgende commando: <br>
`ansible-vault encrypt_string "string"` <br>
Al wil een ad-hoc commando uitvoeren met een encrypted variabele gebruik dan het volgende commando: <br>
ansible -m "module" -i hosts.ini "host" --ask-vault-pass

Al wil je een playbook runnen met de run file, hoef je hier geen --ask-vault-pass bij te gebruiken. <br>

## Win-RM opzetten voor connectie met je Ansible VM:

```powershell
winrm quickconfig
Set-Item -Path WSMan:\localhost\Service\Auth\Basic -Value $true
winrm set winrm/config/service '@{AllowUnencrypted="true"}'
```

> Handige tips: <br>
als je NIC geconnect is met de Public network, moet je de firewall van public uitzetten. <br>
Als je NIC geconnect is met de Private network, dan hoef je geen firewall uit te zetten. <br>
en dan werkt de connectie tussen ansible en winrm. <br><br>
DNS van je NIC veranderen naar de IP van de server. <br>
Zorg ervoor dat de Windows Remote Manager service op "Automatic" staat. <br>
De juiste user gebruiken als ansible_user: <br>
Juiste IP-address gebruiken in de hosts.ini of host_vars. <br>
Juiste hostname gebruiken. <br>


### De opdracht bevat de volgende onderdelen:
![img](https://i.imgur.com/xsiaq7y.png) <br>
![img](https://i.imgur.com/1UbG5Ri.png) <br>
![img](https://i.imgur.com/RuOyz2o.png) <br>

## Topologie van de opdracht:
![img](https://i.imgur.com/EJe8cGb.png) <br>
