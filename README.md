# Ansible-Advanced keuzedeel.

## De contributors zijn: Joshua, Andy, Maid, Sebastiaan en Michel.

## Ansible Galaxy
Deze Ansible Galaxy collections hebben wij gebruikt: <br>
```shell
ansible-galaxy collection install ansible.windows
ansible-galaxy collection install community.windows
ansible-galaxy collection install microsoft.ad
```

## Ansible-Vault
Ansible vault maak je aan met het volgende commando: <br>
`ansible-vault create "naam".yml` <br>
Je kan ook een bestaande file encrypten met het volgende commando: <br>
`ansible-vault encrypt "naam".yml` <br>
Om een bestaande file te decrypten gebruik je het volgende commando: <br>
`ansible-vault decrypt "naam".yml` <br>
Al wil je een playbook runnen met een encrypte vault gebruik dan de volgende parameter: <br>
`--ask-vault-pass` <br>

## Win-RM opzetten voor connectie met je Ansible VM:

```powershell
winrm quickconfig
Set-Item -Path WSMan:\localhost\Service\Auth\Basic -Value $true
winrm set winrm/config/service '@{AllowUnencrypted="true"}'
```

> Handige tips: <br>
Public firewall uitzetten als je NIC op public staat, of verander je NIC naar Private als je firewall hebt aan staan. <br>
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
