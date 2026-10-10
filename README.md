# mnrs-vigia

Vigia externo do servidor que hospeda `mnrs.com.br`.

O servidor tem um vigia interno (`health-sentinel`) que roda a cada 5 minutos e
publica o instante da última rodada em `https://plantoes.mnrs.com.br/_vigia`.
Este repositório só existe para olhar esse pulso **de fora**: se o servidor, a
rede ou o próprio vigia interno pararem, ninguém lá dentro consegue avisar.

- `.github/workflows/vigia.yml` roda a cada 15 minutos nos runners do GitHub.
- Sem resposta, ou pulso com mais de 20 minutos, manda mensagem no Telegram.
- Repete a cada rodada enquanto durar. Silêncio = tudo certo.

Segredos do repositório: `TG_TOKEN` e `TG_CHAT` (os mesmos do vigia interno).
