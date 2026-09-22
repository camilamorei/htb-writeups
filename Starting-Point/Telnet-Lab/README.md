# Hack The Box — Telnet Lab

## Objetivo

Identificar os serviços disponíveis no alvo, conectar ao serviço **Telnet** e localizar a flag no diretório inicial do usuário `root`.

## 1. Conexão VPN

A conexão com a rede do Hack The Box foi estabelecida utilizando **OpenVPN**.

## 2. Teste de conectividade

Foi utilizado o comando `ping` para verificar a conectividade com o alvo:

```bash
ping <IP_DO_ALVO>
```

O `ping` utiliza **ICMP Echo Requests** para verificar se o host está acessível.

## 3. Enumeração de portas

Foi utilizado o **Nmap** para identificar portas abertas:

```bash
nmap <IP_DO_ALVO>
```

Durante a enumeração, foi identificada a seguinte porta:

```text
23/tcp
```

A porta **23/TCP** está associada ao serviço **Telnet**.

## 4. Conexão via Telnet

Foi realizada uma conexão com o serviço:

```bash
telnet <IP_DO_ALVO> 23
```

O acesso foi realizado utilizando o usuário identificado no exercício e uma senha em branco.

Após o login, foi possível confirmar o usuário atual com:

```bash
whoami
```

Resultado:

```text
root
```

## 5. Localização da flag

Após obter acesso como `root`, foi acessado o diretório inicial do usuário:

```bash
cd
pwd
ls -la
```

O arquivo contendo a flag foi identificado e seu conteúdo foi exibido utilizando:

```bash
cat <nome_do_arquivo>
```

> A flag não está incluída neste write-up.

### Ferramentas utilizadas

* OpenVPN — conexão com a rede do laboratório
* Nmap — enumeração de portas
* Ping — teste de conectividade
* Telnet — acesso remoto
* Linux CLI — navegação e interação com o sistema

## Conceitos aprendidos

* Conexão VPN com ambientes de laboratório
* ICMP e teste de conectividade
* Enumeração básica de portas
* Identificação de serviços através de portas
* Utilização do Telnet
* Navegação pelo sistema de arquivos Linux
* Leitura de arquivos pela linha de comando

## Resumo do processo

```text
OpenVPN
   ↓
Ping
   ↓
Nmap
   ↓
23/tcp — Telnet
   ↓
Telnet
   ↓
Login como root
   ↓
Localização da flag
```

---

Lab concluído com sucesso.
