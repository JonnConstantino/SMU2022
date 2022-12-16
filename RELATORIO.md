# Relatório - Jhonatan Constatino

Foi analisado a troca de mensagens que ocorre num jogo web desenvolvido em aula por alunos do IFSC. Analisando principalmente os protocolos RTC e SDP.

## Aplicação

Um jogo web disponível no link abaixo.
https://boidacarapreta.github.io/adcipt20221/

## Sinalização

- Requisições
    - Envia requisições do tipo candidate e offer via websocket.

- Respostas
    - Ao receber uma requisição offer, responde com uma answer. Essas respostas são do tipo websocket.

- Mensagens

<a id="entrar-na-sala"></a>
**entrar-na-sala**
```json
42[
    "entrar-na-sala",
    "0"
]
```

Após a mensagem entrar na sala é possível identificar o jogador pela mensagem abaixo com o seu ID.

```json
42[
    "jogadores",
    {
        "primeiro": "OvWO4CTtQPZvjmdXAAAx"
    }
]
```

<a id="offer"></a>
**offer**
```json
42[
    "offer",
    "VkckMc1phvy9BPS5AAAz",
    {
        "type": "offer",
        "sdp": "v=0
                o=- 3062628635648565754 2 IN IP4 127.0.0.1
                s=-
                t=0 0
                a=group:BUNDLE 0
                a=extmap-allow-mixed
                a=msid-semantic: WMS w45J5Tw5F3Z4Am1TBONlht1YJQUq5YLkdc8x
                m=audio 9 UDP/TLS/RTP/SAVPF 111 63 103 104 9 0 8 106 105 13 110 112 113 126
                c=IN IP4 0.0.0.0
                a=rtcp:9 IN IP4 0.0.0.0
                a=ice-ufrag:wiLi
                a=ice-pwd:A/AavxvjHLj/QjJFa38R4lV7
                a=ice-options:trickle
                a=fingerprint:sha-256 58:F5:50:85:E9:13:30:A6:5B:C1:98:DE:3D:04:38:A2:59:16:81:75:00:03:52:8B:52:95:A4:32:1E:DB:EC:77
                a=setup:actpass
                a=mid:0
                a=extmap:1 urn:ietf:params:rtp-hdrext:ssrc-audio-level
                a=extmap:2 http://www.webrtc.org/experiments/rtp-hdrext/abs-send-time
                a=extmap:3 http://www.ietf.org/id/draft-holmer-rmcat-transport-wide-cc-extensions-01
                a=extmap:4 urn:ietf:params:rtp-hdrext:sdes:mid
                a=sendrecv
                a=msid:w45J5Tw5F3Z4Am1TBONlht1YJQUq5YLkdc8x 5a2352b4-9036-485b-a3ee-419e815b16d0
                a=rtcp-mux
                a=rtpmap:111 opus/48000/2
                a=rtcp-fb:111 transport-cc
                a=fmtp:111 minptime=10;useinbandfec=1
                a=rtpmap:63 red/48000/2
                a=fmtp:63 111/111
                a=rtpmap:103 ISAC/16000
                a=rtpmap:104 ISAC/32000
                a=rtpmap:9 G722/8000
                a=rtpmap:0 PCMU/8000
                a=rtpmap:8 PCMA/8000
                a=rtpmap:106 CN/32000
                a=rtpmap:105 CN/16000
                a=rtpmap:13 CN/8000
                a=rtpmap:110 telephone-event/48000
                a=rtpmap:112 telephone-event/32000
                a=rtpmap:113 telephone-event/16000
                a=rtpmap:126 telephone-event/8000
                a=ssrc:2764308089 cname:F8k4LPQsRnl7LhDj
                a=ssrc:2764308089 msid:w45J5Tw5F3Z4Am1TBONlht1YJQUq5YLkdc8x 5a2352b4-9036-485b-a3ee-419e815b16d0
                "
    }
]
```

<a id="answer"></a>
**answer**
```json
42[
    "answer",
    "VkckMc1phvy9BPS5AAAz",
    {
        "type": "answer",
        "sdp": "v=0
                o=- 2370610356806417276 2 IN IP4 127.0.0.1
                s=-
                t=0 0
                a=group:BUNDLE 0
                a=extmap-allow-mixed
                a=msid-semantic: WMS jAG33FPoTapAhgQVYGBIPaptot05HA2tqavx
                m=audio 9 UDP/TLS/RTP/SAVPF 111 63 103 104 9 0 8 106 105 13 110 112 113 126
                c=IN IP4 0.0.0.0
                a=rtcp:9 IN IP4 0.0.0.0
                a=ice-ufrag:CTjw
                a=ice-pwd:5DfyUHKJ6pkW7YNUZuWqtU/M
                a=ice-options:trickle
                a=fingerprint:sha-256 B8:6A:A8:4D:F0:E9:0C:9F:D5:35:75:E3:40:7E:80:30:B3:31:66:06:01:9E:1F:F9:02:7F:B6:22:D2:C0:13:E3
                a=setup:active
                a=mid:0
                a=extmap:1 urn:ietf:params:rtp-hdrext:ssrc-audio-level
                a=extmap:2 http://www.webrtc.org/experiments/rtp-hdrext/abs-send-time
                a=extmap:3 http://www.ietf.org/id/draft-holmer-rmcat-transport-wide-cc-extensions-01
                a=extmap:4 urn:ietf:params:rtp-hdrext:sdes:mid
                a=sendrecv
                a=msid:jAG33FPoTapAhgQVYGBIPaptot05HA2tqavx 4f8c1659-f558-4a6c-bdf0-c6c7939fe68f
                a=rtcp-mux
                a=rtpmap:111 opus/48000/2
                a=rtcp-fb:111 transport-cc
                a=fmtp:111 minptime=10;useinbandfec=1
                a=rtpmap:63 red/48000/2
                a=fmtp:63 111/111
                a=rtpmap:103 ISAC/16000
                a=rtpmap:104 ISAC/32000
                a=rtpmap:9 G722/8000
                a=rtpmap:0 PCMU/8000
                a=rtpmap:8 PCMA/8000
                a=rtpmap:106 CN/32000
                a=rtpmap:105 CN/16000
                a=rtpmap:13 CN/8000
                a=rtpmap:110 telephone-event/48000
                a=rtpmap:112 telephone-event/32000
                a=rtpmap:113 telephone-event/16000
                a=rtpmap:126 telephone-event/8000
                a=ssrc:486147111 cname:Whtax2AMW4CcOavk
                "
    }
]
```

**candidate**
```json
42[
    "candidate",
    {
        "candidate": "candidate:3048585173 1 udp 2122262783 2804:1530:106:73ca:94e9:ee3f:70ff:3 44989 typ host generation 0 ufrag wiLi network-id 2 network-cost 10",
        "sdpMid": "0",
        "sdpMLineIndex": 0
    }
]

42[
    "candidate",
    "VkckMc1phvy9BPS5AAAz",
    {
        "candidate": "candidate:1713634361 1 udp 2122262783 2804:1530:106:73ca:94e9:ee3f:70ff:3 45834 typ host generation 0 ufrag CTjw network-id 2 network-cost 10",
        "sdpMid": "0",
        "sdpMLineIndex": 0
    }
]

42[
    "candidate",
    {
        "candidate": "candidate:1024563673 1 udp 2122129151 192.168.3.9 36507 typ host generation 0 ufrag wiLi network-id 1 network-cost 10",
        "sdpMid": "0",
        "sdpMLineIndex": 0
    }
]

42[
    "candidate",
    "VkckMc1phvy9BPS5AAAz",
    {
        "candidate": "candidate:2922406930 1 udp 2122129151 192.168.3.9 52477 typ host generation 0 ufrag CTjw network-id 1 network-cost 10",
        "sdpMid": "0",
        "sdpMLineIndex": 0
    }
]
```

- Transações

As transações são mensagens de requisição e resposta utilizadas na aplicação. No nosso caso dessa aplicação Web do jogo foram utilizadas apenas o par [offer](#offer) (requisição) e [answer](#answer) (resposta) com os dados importantes do SDP.

Também temos várias mensagens do tipo candidate, porém sem resposta.

São identificados os jogadores por códigos IDs gerados ao entrar no jogo.
Segue uma mensagem de que há dois jogadores na partida.

Como mostrado inicialmente, após a mensagem [entrar-na-sala](#entrar-na-sala) é recebido a mensagem do jogador mostrando o identificador do mesmo.

```json
42[
    "jogadores",
    {
        "primeiro": "OvWO4CTtQPZvjmdXAAAx"
    }
]
```

Após entrar o outro jogador recebemos a seguinte mensagem.

**jogadores**
```json
[
    "jogadores",
    {
        "primeiro": "OvWO4CTtQPZvjmdXAAAx",
        "segundo": "VkckMc1phvy9BPS5AAAz"
    }
]
```

Como podemos ver, o ID do primeiro jogador é OvWO4CTtQPZvjmdXAAAx e o do segundo é VkckMc1phvy9BPS5AAAz.

- Diálogos

Os diálogos são o conjunto de transações que ocorrem durante a aplicação, com início da conexão, comunicação e encerramento. No caso da aplicação Web analisada, temos apenas o par de requisição offer e answer como mencionado, então temos apenas a transação de estabelecimento da conexão.

Estão constantemente trocando mensagens mostrando a localização dos usuários jogadores, como podemos ver a seguir:

```json
42[
    "estadoDoJogador",
    "0",
    {
        "frame": "",
        "x": 400,
        "y": 300
    }
]
```

```json
42[
    "estadoDoJogador",
    "0",
    {
        "frame": 11,
        "x": 400,
        "y": 297.3333333333333
    }
]
```

```json
42[
    "estadoDoJogador",
    "0",
    {
        "frame": 12,
        "x": 400,
        "y": 297.3333333333333
    }
]
```

```json
42[
    "desenharOutroJogador",
    {
        "frame": "",
        "x": 300,
        "y": 400
    }
]
```

```json
42[
    "estadoDoJogador",
    "0",
    {
        "frame": 12,
        "x": 400,
        "y": 297.3333333333333
    }
]
```

## Negociação de mídia

Como podemos ver nas mensagens do tipo [offer](#offer) e [answer](#answer) e também no próprio jogo que temos como tipo de mídia que são negociadas pelo protocolo SDP:
> audio

- Codecs

Podemos observar também os codecs suportados que são:
> UDP/TLS/RTP/SAVPF 111 63 103 104 9 0 8 106 105 13 110 112 113 126

Foram aceitos por ambas as partes:

> opus/48000/2

> red/48000/2

> ISAC/16000

> ISAC/32000

> G722/8000

> PCMU/8000

> PCMA/8000

> CN/32000

> CN/16000

> CN/8000

> telephone-event/48000

> telephone-event/32000

> telephone-event/16000

> telephone-event/8000

## Escolha de caminho e Transporte de mídia

A escolha do caminho utilizada foi o Stun sobre ICE. Podemos verificar essa informação dentro do arquivo cena1.js no [arquivo de rede](boidacarapreta.github.io.har) se abrirmos ele no navegador. Segue a informação do arquivo.

```json
var ice_servers = {
  iceServers: [
    {
      urls: "stun:stun.l.google.com:19302",
    }
  ],
};
```

O RTP (Real-Time Transport Protocol) torna possível o transporte de pacotes contendo voz, vídeo ou outro tipo de mídia (informação) sobre uma rede IP

Protocolo usado tanto para escolha do caminhado quanto para transporte de mídia foi através do protocolo UDP com o IP 192.168.3.9 que seria o IP local do meu notebook pessoal na minha rede residencial. Houve comunicação na porta 36507 e porta 52477.

São utilizados como transporte de mídia o SRTP e o SRTCP. Basicamente o SRTP (Secure Real-Time Transport Protocol) é uma extensão do protocolo de transporte em tempo real (RTP) que conta com medidas de segurança otimizadas. O protocolo oferece criptografia confidencialidade, autenticação de mensagem e proteção de resposta para seu tráfego de áudio e vídeo transmitido.

O RTCP funciona juntamente com o RTP. O RTP realiza a entrega dos dados, enquanto o RTCP envia pacotes de controle aos participantes de uma chamada. Sua função principal é fornecer um feedback da qualidade dos serviços oferecidos pelo RTP. A versão SRTCP (Secure Real-Time Transport Control Protocol) é uma extensão do RTCP com medidas de segurança otimizados, assim como o SRTP.

Podemos observar essas informações nas mensagens do tipo [offer](#offer) e [answer](#answer).

> IP 192.168.3.9

> PORTA 36507

> PORTA 52477

## Qualidade de serviço

O RTP que trabalha em conjunto com o SDP permite a detecção de pacotes perdidos, variações no atraso (jitter) e chegada fora de ordem, porém não garante qualidade de serviço para a mídia sendo transportada.Pacotes RTP são tratados da mesma forma como qualquer outro pacote numa rede IP. Um trabalho em conjunto com o RTCP (Real-time Transport Control Protocol), que é usado para monitorar estatísticas referentes às trocas de pacotes RTP.

## Segurança

Há comunicação utiizando TCP e IPv6, o que serveria para garantir um pouco de segurança, porém apenas isso. No SDP tem o parâmetro "k" que é a chave de criptografia, porém nessa troca de mensagens analisadas não é encontrado.

```json
42[
    "candidate",
    {
        "candidate": "candidate:1260348225 1 tcp 1518283007 2804:1530:106:73ca:94e9:ee3f:70ff:3 9 typ host tcptype active generation 0 ufrag wiLi network-id 2 network-cost 10",
        "sdpMid": "0",
        "sdpMLineIndex": 0
    }
]
```

## Referências

[Relatório SIP + SDP + RTP + RCTP](https://boidacarapreta.github.io/smu20191/sip_sdp_rtp_rtcp.html)

[Exemplo Relatório de Projeto Final](https://boidacarapreta.github.io/smu20191/projeto_final.html)