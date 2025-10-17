# SmartBallot
Questo repository contiene il progetto SmartBallot, una soluzione per votazioni condominali decentralizzate che combina una API backend, un frontend React e smart contract Ethereum/Hardhat.

## Panoramica

- `backend/` — API Node.js/TypeScript che gestisce autenticazione, utenti, condomìni, e integrazione con la blockchain e il database (MongoDB).
- `blockchain/` — smart contract, configurazione Hardhat e script per il deploy (Contratti per votazioni condominali e factory).
- `frontend/` — applicazione client in React + Vite che fornisce l'interfaccia utente per registrazione, login, gestione condomìni e votazioni.

## Struttura del progetto (principali file/cartelle)

- `backend/`
	- `src/` — codice TypeScript del server (routes, services, utils)
	- `package.json` — script e dipendenze per il backend
	- `requirements.txt` — dipendenze Python (se presenti per script)

- `blockchain/`
	- `contracts/` — smart contract Solidity
	- `scripts/` — script Hardhat (deploy, test)
	- `hardhat.config.ts` — configurazione Hardhat
	- `package.json` — script e dipendenze per la build blockchain

- `frontend/`
	- `src/` — codice React (componenti, contesti, utils)
	- `package.json` — script per sviluppo e build (vite)

## Requisiti

- Node.js (consigliata LTS >= 18)
- pnpm (opzionale, il repository include pnpm-lock.yaml)
- MongoDB (locale o remoto)
- npx / npm per eseguire script Hardhat

## Setup rapido (locale)

1. Clona il repository:

	 git clone https://github.com/GianmarcoBasile/SmartBallot-Blockchain.git
	 cd SmartBallot-Blockchain

2. Installazione dipendenze

	 - Backend
		 - Entra nella cartella `backend` e installa le dipendenze (npm o pnpm):
      ```bash
        cd backend
        pnpm install
      ```

	 - Blockchain
    ```bash
      cd ../blockchain
      pnpm install
    ```
		 - Usa Hardhat per compilare o deployare gli smart contract.

	 - Frontend
      ```bash
			 cd ../frontend
			 pnpm install
      ```
		 - Avvia il dev server con `pnpm dev` o `npm run dev`.

3. Variabili d'ambiente

	 - Crea file `.env` nelle cartelle che lo richiedono (`backend`, eventualmente `blockchain` e `frontend`) basandoti su esempi o sulle costanti nel codice.
	 - Valori tipici per il backend:
		 - `MONGODB_URI` — stringa di connessione MongoDB
		 - `JWT_SECRET` — segreto per token JWT
		 - `PORT` — porta del server (es. 4000)
	 - Per la blockchain, configura provider/chiavi se vuoi deployare su testnet/mainnet (es. INFURA_KEY, PRIVATE_KEY).