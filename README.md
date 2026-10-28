# Ansible Infrastruktuuri Automatiseerimine (VOCO)

Käesolev repositoorium sisaldab Tartu Rakendusliku Kolledži (VOCO) raames loodud Ansible automatiseerimise skripte, inventarifaile ja playbook'e veebiserverite ning andmebaaside haldamiseks eriilmelises operatsioonisüsteemide keskkonnas (Debian 12 ja CentOS Stream 10).

## 🛠️ Taristu Arhitektuur

| Sõlm (Node) | Kasutaja / IP | Operatsioonisüsteem | Roll / Teenused |
| :--- | :--- | :--- | :--- |
| **Control Node** | `root@192.168.37.169` | Debian 12 | Ansible juhtserver, Git |
| **Managed Node 1** | `serverklient1` (`192.168.37.177`) | Debian 12 | Apache2, MySQL 8.0 |
| **Managed Node 2** | `serverklient2` (`192.168.37.138`) | CentOS Stream 10 | Apache2 (httpd), MariaDB 10.11 |

---

## 📁 Projekti Struktuur

```text
ansible-automation/
├── ansible.cfg              # Ansible globaalne konfigureerimisfail
├── hosts                    # Inventarifail (Debian ja CentOS kliendid)
├── playbooks/
│   ├── webserver.yml        # Lab 2: Veebiserverite paigaldus ja konfigureerimine
│   ├── mysql-server.yml     # Lab 4: MySQL/MariaDB teenuse paigaldus ja käivitus
│   └── mysql-user.yml       # Lab 4: Root kasutaja parooli ja .my.cnf seadistamine
└── README.md                # Projekti dokumentatsioon
