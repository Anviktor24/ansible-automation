# Lab 1: Ansible automatiseerimislahendus

See repositoorium sisaldab Tartu Rakendusliku Kolledži (VOCO) oppeaine **SKPVA** labor 1 materjale ja seadistusi. Projekti eesmärk on paigaldada Ansible juhtserver ning seadistada SSH-põhine haldus kahe kliendiserveri üle.

---

## 📐 Võrgulahendus ja arhitektuur

* **Ansible juhtserver (Control Node):** Debian 12 (`root@viktor`)
* **Klient 1 (Managed Node 1):** Debian (`serverklient1`)
* **Klient 2 (Managed Node 2):** CentOS Stream (`serverklient2` – `192.168.37.138`)

Kõik seadistused ja hallatavad ühendused sooritatakse `root`-kasutaja õigustes läbi turvalise SSH-võtmepaari.

---

## 📁 Repositooriumi struktuur

* `hosts` – Ansible inventarifail (Inventory), kus on kirjeldatud hallatavad serverid ja nende parameetrid.
* `ansible.cfg` – Ansible peakonfiguratsioonifail (vaike-inventar, ühenduse viited jm).
* `README.md` – Projekti dokumentatsioon.

---

## ⚙️ Seadistamine ja paigaldus

### 1. Juhtserveri ettevalmistus
1. Paigalda Ansible:
   ```bash
   apt update && apt install -y ansible git
