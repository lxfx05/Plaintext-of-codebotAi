## Tree view of Chatbot 
```
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
│   ├── config.py                   # Configurazioni globali
│   ├── local_llm.py                # Wrapper per il modello LLM locale
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
│   │   ├── sandbox_runner.py       # Sandbox opzionale per codice
│   │   ├── diff_utils.py           # Generatore di patch/fix
│   │   ├── file_ops.py             # Gestione file temporanei
│   │   └── logging_utils.py        # Logger centralizzato
│   │
│   └── tests/                      # Test automatici backend
│       ├── test_api.py
│       ├── test_checkers.py
│       └── test_llm.py
│
├── frontend/                       # Interfaccia utente locale (HTML + CSS + JS)
│   ├── index.html                  # Pagina principale stile ChatGPT
│   ├── main.js                     # Gestione logica chat/API
│   ├── style.css                   # Tema dark mode
│   │
│   ├── assets/                     # Risorse grafiche
│   │   ├── logo.svg
│   │   └── icons/
│   │       ├── send.svg
│   │       ├── code.svg
│   │       └── terminal.svg
│   │
│   └── components/                 # Parti modulari UI
│       ├── chat_ui.html            # Layout chat
│       ├── code_result.html        # Risultati checker
│       └── project_viewer.html     # Vista file generati
│
├── data/                           # Dati locali (tutto offline)
│   ├── history.db                  # SQLite per cronologia
│   ├── logs/
│   │   ├── app.log
│   │   └── error.log
│   └── cache/
│       └── temp_code/              # File temporanei checker
│
├── scripts/                        # Script di supporto
│   ├── download_model.sh           # Scarica pesi modello
│   ├── build_frontend.sh           # Compila Tailwind
│   ├── run_server.sh               # Avvio backend + frontend
│   └── sandbox_test.sh             # Test di sicurezza
│
└── docs/                           # Documentazione tecnica
    ├── SYSTEM_OVERVIEW.md          # Architettura e componenti
    ├── API_REFERENCE.md            # Chatbot /mode1 e /mode2
    ├── LOCAL_SETUP.md              # Installazione offline
    ├── SECURITY_NOTES.md           # Linee guida sicurezza
    └── MODEL_GUIDE.md              # Guida ai modelli compatibili
```

## 💡 Have an Idea?

If you have an idea to improve **Offline Dev Chatbot** —  
whether it’s a new feature, optimization, or language support — feel free to contribute!

You can:
1. Open an **Issue** with your proposal or bug report.  
2. Fork the repository and submit a **Pull Request**.  
3. Discuss ideas in the **Discussions** tab if enabled.

Please include:
- a short description of the idea,
- the motivation (why it helps the project),
- optional implementation hints or examples.

Together, we can make this offline assistant even smarter 🚀
Tree
