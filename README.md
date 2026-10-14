# 🏥 Gestionale Ospedaliero — Java OOP

![Build & Test](https://github.com/Lavitar-code/gestionale-ospedaliero/actions/workflows/pipeline.yaml/badge.svg)
![Java](https://img.shields.io/badge/Java-25-orange?logo=openjdk)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-database-336791?logo=postgresql&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-build-C71A36?logo=apachemaven)

Applicazione desktop per la gestione di una struttura ospedaliera: reparti, stanze, letti, personale medico, pazienti, ricoveri, visite e interventi chirurgici.
Interfaccia grafica in **Java Swing**, dati salvati su **PostgreSQL**, architettura a livelli verificata con test automatici.

> Progetto del corso di **Programmazione Orientata agli Oggetti** — Laurea in Informatica, Università degli Studi di Napoli Federico II (A.A. 2025/26), sviluppato in team.

## Funzionalità

- **Login con due ruoli**: Amministratore e Medico, con permessi diversi
- **Gestione struttura**: reparti, stanze e letti (inserimento, modifica, eliminazione)
- **Gestione personale**: medici, amministratori e turni di lavoro
- **Gestione pazienti**: anagrafica, ricoveri con assegnazione del letto
- **Attività cliniche**: visite e interventi chirurgici, con assegnazione dei medici e del loro ruolo

## Architettura

Il codice segue un'architettura a livelli (pattern **MVC + DAO**):

```
gui/                  → interfaccia grafica (Swing)
controller/           → logica applicativa, collega GUI e dati
model/                → classi del dominio (Paziente, Medico, Ricovero, ...)
dao/                  → interfacce di accesso ai dati
implementazione_dao/  → implementazioni JDBC dei DAO
database_conn/        → connessione al database (Singleton)
exceptions/           → eccezioni personalizzate
```

Il rispetto dell'architettura è controllato da test automatici con **ArchUnit**: separazione dei livelli, assenza di dipendenze cicliche, best practice.

## Tecnologie

| Ambito | Strumenti |
|---|---|
| Linguaggio | Java 25 |
| GUI | Swing, JCalendar, JGoodies Forms |
| Database | PostgreSQL via JDBC |
| Build | Maven |
| Test | JUnit 4, ArchUnit |
| CI | GitHub Actions |

## Come avviarlo

**Requisiti:** JDK 25 e PostgreSQL in locale, con un database `ospedale_db`.

1. Imposta la password del database come variabile d'ambiente (non è scritta nel codice):
   ```bash
   # Windows (PowerShell)
   $env:DB_PASSWORD = "la-tua-password"
   # Linux / macOS
   export DB_PASSWORD="la-tua-password"
   ```
2. Apri il progetto in IntelliJ IDEA (o un altro IDE con supporto Maven) ed esegui la classe `gui.MainGUI`.
3. Per compilare e lanciare i test:
   ```bash
   ./mvnw verify
   ```

## Documentazione

- 📄 [Documentazione del progetto (PDF)](doc/documentazioneFinale/DOCUMENTAZIONE%20Progetto-2.pdf)
- 📚 Javadoc completo in [`doc/documentazioneFinale/javadoc`](doc/documentazioneFinale/javadoc)

## Autore

**Vittorio Gaudiello** — [@Lavitar-code](https://github.com/Lavitar-code)
