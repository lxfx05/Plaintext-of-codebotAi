# Plaintext-of-Free-Ai

offline-dev-chatbot/
├── README.md                       # Descrizione generale e setup
├── LICENSE                         # Licenza del progetto
├── .gitignore                      # File e cartelle da escludere da Git
├── requirements.txt                # Dipendenze Python (FastAPI, llama-cpp, ecc.)
├── Dockerfile                      # Costruzione container offline
├── setup.sh                        # Script rapido di configurazione
│
├── backend/                        # Backend principale in Python (FastAPI)
│   ├── app.py                      # Entry point del server API (Mode1, Mode2)
│   ├── config.py                   # Configurazioni globali (porte, percorsi modelli, ecc.)
│   ├── local_llm.py                # Wrapper per il modello LLM locale (llama-cpp / transformers)
│   │
│   ├── prompts/                    # Prompt predefiniti per LLM
│   │   ├── system_prompt.txt       # Prompt di sistema base
│   │   └── templates/
│   │       ├── clarify_prompt.txt  # Prompt per chiedere chiarimenti
│   │       ├── generator_prompt.txt# Prompt per generazione codice/progetto
│   │       └── code_explainer_prompt.txt # Prompt per spiegazioni del codice
│   │
│   ├── code_check/                 # Moduli di verifica del codice (Mode 1)
│   │   ├── __init__.py
│   │   ├── python_checker.py       # Analisi Python (ast, flake8)
│   │   ├── java_checker.py         # Compilazione e analisi .java
│   │   ├── cpp_checker.py          # g++ -fsyntax-only
│   │   ├── js_checker.py           # eslint locale via Node
│   │   ├── go_checker.py           # go vet / go fmt
│   │   └── sql_checker.py          # sqlparse o sqlite3 parser
│   │
│   ├── models/                     # Area per modelli LLM locali
│   │   ├── README.txt              # Istruzioni su dove mettere i pesi
│   │   ├── model.gguf              # File del modello Llama, Phi, Mistral ecc.
│   │   └── tokenizer.model         # Tokenizer compatibile
│   │
│   ├── utils/                      # Strumenti di supporto
│   │   ├── sandbox_runner.py       # Sandbox opzionale per eseguire codice in sicurezza
│   │   ├── diff_utils.py           # Generatore di patch/suggerimenti di fix
│   │   ├── file_ops.py             # Operazioni su file temporanei
│   │   └── logging_utils.py        # Logger centralizzato
│   │
│   └── tests/                      # Test automatici backend
│       ├── test_api.py
│       ├── test_checkers.py
│       └── test_llm.py
│
├── frontend/                       # Interfaccia utente locale (HTML + CSS + JS)
│   ├── index.html                  # Pagina principale stile ChatGPT
│   ├── main.js                     # Gestione logica chat e chiamate API
│   ├── style.css                   # Tema dark mode (Tailwind o CSS custom)
│   │
│   ├── assets/                     # Risorse grafiche
│   │   ├── logo.svg
│   │   └── icons/
│   │       ├── send.svg
│   │       ├── code.svg
│   │       └── terminal.svg
│   │
│   └── components/                 # Parti modulari dell’interfaccia
│       ├── chat_ui.html            # Struttura conversazionale
│       ├── code_result.html        # Visualizzazione risultati checker
│       └── project_viewer.html     # Vista file generati (modo 2)
│
├── data/                           # Dati locali (tutto offline)
│   ├── history.db                  # Database SQLite per cronologia chat/code
│   ├── logs/
│   │   ├── app.log
│   │   └── error.log
│   └── cache/
│       └── temp_code/              # File temporanei creati dai checkers
│
├── scripts/                        # Script di supporto
│   ├── download_model.sh           # Scarica i pesi del modello (manuale/offline)
│   ├── build_frontend.sh           # Compila Tailwind o bundle statici
│   ├── run_server.sh               # Avvio locale completo (backend + frontend)
│   └── sandbox_test.sh             # Test di sicurezza su codice utente
│
└── docs/                           # Documentazione tecnica e guida d’uso
    ├── SYSTEM_OVERVIEW.md          # Architettura e componenti
    ├── API_REFERENCE.md            # Descrizione endpoint /mode1 e /mode2
    ├── LOCAL_SETUP.md              # Istruzioni installazione offline
    ├── SECURITY_NOTES.md           # Linee guida sicurezza e sandbox
    └── MODEL_GUIDE.md              # Modelli supportati e formati compatibili
    
