# Progetto Tecnologie Web: Sistema di Analisi e Gestione Dati Cinematografici

Progetto Tecnologie Web (TWEB) UniTo anno 2024-2025

**NB!** Questo repository contiene una descrizione completa del progetto. Il codice sorgente e i dati sono organizzati secondo l'architettura multi-tier descritta di seguito.

**Nota sui Dataset:** I dataset cinematografici (~1.8 GB) sono esclusi dal repository per limitazioni di GitHub e questioni di copyright. 

## Introduzione

Il progetto consiste nello sviluppo di un sistema completo per l'analisi e la gestione di dati cinematografici, implementato utilizzando tecnologie web moderne. Il sistema integra diversi componenti:

- **Data Analysis Layer**: Analisi e pulizia dei dataset cinematografici utilizzando Jupyter Notebooks
- **Backend Services**: Server Express.js con MongoDB e server Spring Boot con PostgreSQL
- **Frontend Interface**: Interfaccia web per la visualizzazione e interazione con i dati
- **API Gateway**: Server principale per la coordinazione dei servizi

La soluzione gestisce dati provenienti da diverse fonti cinematografiche, inclusi Rotten Tomatoes, Oscar Awards, e altre banche dati del settore.

## Tecnologie e Strumenti Usati

### Linguaggi e Tecnologie

**Data Analysis & Processing:**
- **Python** - Analisi e pulizia dei dati con Jupyter Notebooks
- **Pandas** - Manipolazione e analisi dei dataset
- **NumPy** - Calcoli numerici e operazioni matematiche

**Backend Development:**
- **Node.js + Express.js** - Server web per l'interfaccia con MongoDB
- **Java + Spring Boot** - Server enterprise con PostgreSQL
- **JavaScript** - Logica di frontend e server-side

**Database Technologies:**
- **MongoDB** - Database NoSQL per dati semi-strutturati
- **PostgreSQL** - Database relazionale per dati strutturati

**Web Technologies:**
- **HTML5/CSS3** - Struttura e presentazione
- **Handlebars (HBS)** - Template engine per rendering dinamico
- **REST APIs** - Comunicazione tra servizi
- **Socket.IO** - Comunicazione real-time (se implementata)

**Documentation & API:**
- **Swagger/OpenAPI** - Documentazione automatica delle API
- **JSDoc** - Documentazione JavaScript
- **JavaDoc** - Documentazione Java (Spring Boot)

### Strumenti di Sviluppo

**Development Environment:**
- **Webstorm/Intellij IDEA** - IDE principale
- **PyCharm** - Ambiente di sviluppo Python
- **Jupyter Lab/Notebook** - Ambiente di data analysis

**Build & Package Management:**
- **npm** - Gestione dipendenze Node.js
- **Gradle** - Build automation per Spring Boot
- **pip** - Gestione pacchetti Python

**Database Tools:**
- **MongoDB Compass** - Interfaccia grafica MongoDB
- **pgAdmin** - Gestione PostgreSQL

### Sistema Operativo
- **Cross-platform** - Supporto Windows, Linux, macOS

## Contenuto Relazione Finale

La relazione finale comprende tutta la documentazione dettagliata del progetto e la sua architettura:

**Architettura del Sistema:**
Il sistema è composto da quattro layer principali:

1. **Data Analysis Layer** - Jupyter Notebooks per analisi e pulizia dati
2. **Express Server (MongoDB)** - Gestione recensioni e dati semi-strutturati
3. **Spring Boot Server (PostgreSQL)** - Gestione dati strutturati e operazioni complesse
4. **Main Server** - Coordinamento e interfaccia utente principale

**Flusso dei Dati:**
- Acquisizione e pulizia dati cinematografici
- Elaborazione tramite algoritmi di data science
- Archiviazione distribuita su MongoDB e PostgreSQL
- Esposizione tramite API REST
- Visualizzazione attraverso interfaccia web

## Contenuto Codice

Il codice sorgente è organizzato nella directory `Solution/` e include:

### Data Analysis Components
**1st_JupyterProject/**
- `DataAnalysis.ipynb` - Analisi esplorativa dei dataset
- `File Cleaning Nb.ipynb` - Pulizia e preprocessing generale
- `Rotten Tomatoes Cleaning.ipynb` - Pulizia dati Rotten Tomatoes
- `The Oscar Awards Cleaning.ipynb` - Pulizia dati Oscar Awards
- `data/` - Dataset cinematografici (movies, actors, reviews, etc.)

### Backend Services

**ExpressServer-ToMongo/**
- `app.js` - Server principale Express
- `controllers/` - Logic di controllo per API REST
- `models/` - Modelli dati MongoDB
- `routes/` - Definizione endpoints API
- `databases/` - Configurazione connessione MongoDB

**JavaServer-ToPostgre/**
- `SpringBootServer/` - Applicazione Spring Boot
- `src/main/` - Codice sorgente principale
- `src/test/` - Test unitari e integrazione
- `build.gradle` - Configurazione build e dipendenze

**MainServer/**
- `app.js` - Server coordinatore principale
- `routes/` - Routing delle richieste
- `public/` - Asset statici (CSS, JS, immagini)
- `views/` - Template engine per rendering pagine
- `lib/socket.js` - Gestione comunicazioni real-time

### Caratteristiche Implementate

**Data Processing:**
- Pulizia e normalizzazione dataset cinematografici
- Analisi esplorativa e statistiche descrittive
- Gestione dati mancanti e outlier
- Trasformazione e aggregazione dati

**Backend Architecture:**
- Architettura microservizi con Express e Spring Boot
- Database poliglotti (MongoDB + PostgreSQL)
- API REST per comunicazione inter-servizi
- Gestione errori e logging

**Frontend Features:**
- Interfaccia responsive per visualizzazione dati
- Template dinamici con Handlebars (HBS)
- Dashboard interattive per analytics
- Filtri e ricerca avanzata
- Visualizzazioni grafiche (se implementate)

**Documentation & Standards:**
- Documentazione automatica API con Swagger/OpenAPI
- JSDoc per documentazione JavaScript
- JavaDoc per documentazione Spring Boot
- Code documentation e API testing integrati

## Compilazione ed Esecuzione

### Prerequisiti

**Data Analysis:**
- Python 3.8+
- Jupyter Lab/Notebook
- Pandas, NumPy, Matplotlib (vedi requirements.txt)

**Backend Services:**
- Node.js 16+
- Java 11+
- MongoDB 4.4+
- PostgreSQL 12+

### Setup Database

**MongoDB:**
```bash
# Avvio servizio MongoDB locale
mongod --dbpath /path/to/data/db
```

**PostgreSQL:**
```bash
# Creazione database
createdb moviedb
```

### Avvio Data Analysis
```bash
cd Solution/1st_JupyterProject
pip install -r requirements.txt
jupyter lab
```

### Avvio Express Server
```bash
cd Solution/ExpressServer-ToMongo/ExpressServer
npm install
npm start
```

### Avvio Spring Boot Server
```bash
cd Solution/JavaServer-ToPostgre/SpringBootServer
./gradlew bootRun
```

### Avvio Main Server
```bash
cd Solution/MainServer/MainServer
npm install
npm start
```

## Configurazione

### Configurazione Database
- **MongoDB**: Configurazione in `ExpressServer/databases/database.js`
- **PostgreSQL**: Configurazione in `SpringBootServer/src/main/resources/application.properties`

### Variabili d'Ambiente
```bash
# MongoDB
MONGODB_URI=mongodb://localhost:27017/moviedb

# PostgreSQL
DB_HOST=localhost
DB_PORT=5432
DB_NAME=moviedb
DB_USER=username
DB_PASSWORD=password

# Server Ports
EXPRESS_PORT=3001
SPRING_PORT=8080
MAIN_PORT=3000
```

### Dataset
I dataset cinematografici sono localizzati in `Solution/1st_JupyterProject/data/` e includono:
- Movies, actors, crew data
- Rotten Tomatoes reviews
- Oscar Awards information
- Generi, paesi, studi cinematografici

**Nota importante:** La cartella `data/` è esclusa dal controllo versione Git (tramite `.gitignore`) per questioni di copyright e dimensioni dei file. I dataset contengono dati reali che potrebbero essere soggetti a diritti d'autore.

## API Documentation

La documentazione delle API è automaticamente generata utilizzando Swagger/OpenAPI:

### Express Server Endpoints
- `GET /api/reviews` - Recupera recensioni
- `GET /api/top-critics` - Top critics reviews
- Documentazione completa disponibile nella cartella `Swagger/`

### Spring Boot Endpoints
- `GET /api/movies` - Lista film
- `GET /api/movies/top250` - Top 250 film per rating
- `GET /api/movies/recent` - Film recenti
- **Swagger UI disponibile su:** `http://localhost:8080/swagger-ui.html` (documentazione interattiva OpenAPI)

### Main Server
- Documentazione API tramite Swagger JSDoc
- Interfaccia Swagger UI integrata per test interattivi

## Struttura Progetto

```
Solution/
├── 1st_JupyterProject/          # Data Analysis & Cleaning
├── ExpressServer-ToMongo/       # Node.js + MongoDB Service  
├── JavaServer-ToPostgre/        # Spring Boot + PostgreSQL Service
└── MainServer/                  # Coordination & Frontend Server
```

## Query Examples

Esempi di query implementate sono disponibili nella cartella `QueryExamples/`:
- Express: Top critic reviews
- Spring Boot: Top 250 movies, film per anno
