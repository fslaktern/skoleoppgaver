# Stein Saks Papir - Socket.io

## Oppsett

1. Initialisering
   1.1 Søk etter lobby.
   1.2 Hopp til steg 2 om ledig lobby finnes.
   1.3.1 Opprett lobby.
   1.3.2 Vent på andre spillere.
   1.3.3 Hvis alle spillere er innmeldt, hopp til steg 2.

2. Spill
   2.1.1 Vent til begge spillere er klare.
   2.1.2 Broadcast spillstart.
   2.2 Vent på begge spillerhandlinger.

3. Resultat
    3.1 Broadcast resultat.
    3.2 Søk etter ny lobby (steg 1) eller spill igjen (steg 2).

## Variabler

Server:
- const `io`: Socket.io-objekt.
- const `gameid`: Lobby-ID.
  - `users`: [`userid`, `userid`]
- const `userid`: Spiller-ID.
- let `actions`: Spiller-handlinger.
- let `gameHistory`: Spillhistorikk.

Klient:
- inherited `gameid`: Lobby-ID.
- const `username`: Spiller-navn.
- let `action`: Spiller-handling.