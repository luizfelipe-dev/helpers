sudo iptables -A INPUT -p icmp --icmp-type echo-request -j DROP

-----------------------------------------------------------

## Bloquear 10 pings por segundo:

Bloquear por tempo:

1) Criar a regra para aceitar:

sudo iptables -A INPUT -p icmp --icmp-type echo-request -m limit --limit 6/minute -j ACCEPT

2) Criar a regra  para rejeitar:

sudo iptables -A INPUT -p icmp --icmp-type echo-request -j REJECT

--------------------------------
Legenda:

-A = ADD (ou -D para Deletar)

INPUT = entrada

-p = PROTOCOLO (ex: icmp é o protocolo do ping)

-j = Qual ação?

DROP = (ou reject)

---------------------------------
APAGAR TODAS AS REGRAS:

sudo iptables --flush
