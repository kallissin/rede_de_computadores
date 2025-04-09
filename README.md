# 📘 Roteiro de Estudo: Redes de Computadores e TCP

## Livros Utilizados
- **Redes de Computadores** – Andrew S. Tanenbaum & David Wetherall
- **Redes de Computadores e a Internet** – James F. Kurose & Keith Ross

### Sugestão de Leitura Paralela:
| Semana | Tema                                      | Kurose                          | Tanenbaum                        |
|--------|-------------------------------------------|----------------------------------|----------------------------------|
| 1      | Fundamentos e Modelo OSI                 | Capítulo 1                      | Capítulos 1 e 2                  |
| 2      | IP, Roteamento e Sub-redes               | Capítulo 4                      | Capítulo 5 (Camada de Rede)      |
| 3      | Transporte: TCP e UDP                    | Capítulo 3                      | Capítulo 6 (Camada de Transporte) |
| 4      | TCP: Máquina de Estados e Sockets        | Capítulo 3 (seções TCP)         | Capítulo 6 + Apêndice TCP (RFC)  |

---

## Semana 1 – Fundamentos de Redes e Modelo OSI

### 🎯 Objetivo
Compreender como os dados são transmitidos em camadas e o papel de cada camada.

### 📘 Teoria
- Leitura:
  - Tanenbaum: Capítulos 1 e 2
  - Kurose: Capítulo 1
- Tópicos:
  - O que é uma rede de computadores
  - Modelo OSI vs Modelo TCP/IP
  - Camadas: Aplicação, Transporte, Rede, Enlace, Física

### 🎥 Vídeos
- [Computer Networking Explained (Computerphile)](https://www.youtube.com/watch?v=3QhU9jd03a0)
- [OSI vs TCP/IP Models (Practical Networking)](https://www.youtube.com/watch?v=Zt3wCrUoT4o)

### 🛠️ Prática
- Explorar [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer)
- Criar um diagrama OSI com exemplos de protocolos por camada

### ✅ Desafio prático
- Monte um mapa mental ou esquema visual com as 7 camadas OSI e os principais protocolos associados.
- Explique com suas palavras o que acontece em cada camada quando você acessa "google.com" pelo navegador.

---

## Semana 2 – IP, Roteamento e Sub-redes

### 🎯 Objetivo
Entender como pacotes trafegam na rede e como dispositivos se comunicam.

### 📘 Teoria
- Leitura:
  - Tanenbaum: Capítulo sobre Camada de Rede
  - Kurose: Capítulo 4
- Tópicos:
  - Endereçamento IP (IPv4), máscaras, sub-redes
  - Roteadores, tabelas de roteamento, gateway
  - DNS, NAT, DHCP

### 🎥 Vídeos
- [How IP addresses work (Computerphile)](https://www.youtube.com/watch?v=8aGhZQkoFbQ)
- [Subnetting made easy (Practical Networking)](https://www.youtube.com/watch?v=2n0gXGK4bQE)

### 🛠️ Prática
- Calcular sub-redes manualmente
- Usar `ipconfig` / `ifconfig` / `ip a` para inspecionar a rede local

### ✅ Desafio prático
- Dado um IP e uma máscara (ex: 192.168.1.0/24), liste:
  - Número total de hosts válidos
  - Endereço de rede
  - Primeiro e último IP utilizável
  - Endereço de broadcast
- Faça ping em um domínio e acompanhe os IPs no `traceroute` até o destino final.

---

## Semana 3 – TCP e UDP: Entendendo Transporte

### 🎯 Objetivo
Compreender como o TCP garante entrega de dados e suas diferenças com o UDP.

### 📘 Teoria
- Leitura:
  - Tanenbaum: Capítulo da Camada de Transporte
  - RFC 793 (introdução e máquina de estados)
  - Kurose: Capítulo 3
- Tópicos:
  - Handshake TCP (3-way)
  - ACK, retransmissões, janela deslizante
  - Controle de fluxo e congestionamento
  - Diferenças com UDP

### 🎥 Vídeos
- [TCP vs UDP (Practical Networking)](https://www.youtube.com/watch?v=Vdc8TCESIg8)
- [TCP Handshake (Computerphile)](https://www.youtube.com/watch?v=x2TuK2X39Bc)

### 🛠️ Prática
- Capturar handshakes TCP com Wireshark
- Ferramentas: `telnet`, `nc`, `ping`, `traceroute`

### ✅ Desafio prático
- Use o Wireshark para capturar a abertura de uma conexão TCP com um site.
  - Identifique os pacotes SYN, SYN-ACK, e ACK.
  - Faça anotações dos números de sequência e confirmação.
- Simule perda de pacotes com `tc` (Linux) ou em rede virtual, e veja se o TCP tenta retransmitir.

---

## Semana 4 – Máquina de Estados TCP + Sockets

### 🎯 Objetivo
Visualizar e entender os estados de uma conexão TCP e como os sockets funcionam.

### 📘 Teoria
- Leitura:
  - RFC 793 – Máquina de estados TCP
  - Tanenbaum – Estados da conexão TCP
  - Kurose: Capítulo 3 (seções sobre TCP)
- Tópicos:
  - Estados TCP: `LISTEN`, `SYN_SENT`, `ESTABLISHED`, `FIN_WAIT`, `TIME_WAIT`, etc.

### 🎥 Vídeo
- [TCP State Machine (Jon G.)](https://www.youtube.com/watch?v=WGJrLqtXz-I)

### 🛠️ Prática
- Criar cliente/servidor com Python `socket`
- Usar `netstat -an` ou `ss` para ver estados das conexões
- Acompanhar estados TCP durante conexão real

### ✅ Desafio prático
- Crie um pequeno servidor HTTP com `socket` em Python que responde com "Hello, world!".
- Acompanhe com `ss` ou `netstat` os estados da conexão do momento em que você conecta até fechar.
- Desenhe o caminho da máquina de estados TCP do início ao fim da sua conexão.
