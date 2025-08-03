# 🔏 VAPT su OWASP Juice Shop
Ho sviluppato questo progetto in collaborazione con [sofcaroli2](https://github.com/sofcaroli2) e [Anapaxx](https://github.com/Anapaxx).
Questo documento riassume le attività di **Vulnerability Assessment & Penetration Testing (VAPT)** condotte sull'applicazione web **OWASP Juice Shop**. 
L'obiettivo era applicare le fasi di Information Gathering, Vulnerability Assessment, Exploitation e Post-Exploitation.

## ✨ Caratteristiche dell'Applicazione
- **Piattaforma**: OWASP Juice Shop è un'applicazione web intenzionalmente vulnerabile a scopo didattico;
- **Tecnologie**: L'applicazione è sviluppata con Node.js, Express, Angular, JavaScript e utilizza database SQLite e MongoDB;
- **Infrastruttura**: La demo pubblica è ospitata su Heroku, che utilizza AWS come infrastruttura sottostante.

## 🔢 Fasi del VAPT
### 1. Information Gathering: 
Abbiamo raccolto informazioni sull'applicazione tramite fonti pubbliche, analisi dell'immagine Docker e dell'infrastruttura.
Sono stati inoltre utilizzati strumenti come:
- docker inspect;
- whatweb;
- wafw00f;
- nslookup;
- Shodan.
  
per raccogliere dati su porte, tecnologie e provider cloud. 

### 2. Vulnerability Assessment: 
In questa fase abbiamo identificato e classificato le vulnerabilità presenti, incluse quelle della **OWASP Top 10 - 2021**, scoprendo: 
- SQL Injection;
- Cross-Site Scripting (XSS);
- Broken Access Control;
- Identification and Authentication Failures;
- Security Misconfiguration;
- SSRF.
  
Una volta trovate quest'ultime, con i relativi punti di ingressi, abbiamo proceduto a stilare delle Proof-Of-Concept (PoC) per confermarle o confutarle.

### 3. Exploitation: 
È stata eseguita una **prioritizzazione** delle vulnerabilità per identificare quelle che più valesse sfruttare.
Le vulnerabilità con il punteggio più alto sono state **XSS Injection, SQL Injection, Broken Access Control e Identification and Authentication Failures**, 
abbiamo quindi porceduto con l'attività di Exploit a partire prorpio da queste.

### 4. Post-Exploitation: 
La fase di Post-Exploitation ha esaminato la possibilità di persistenza nell'applicativo, movimento laterale, pillaging ed esfiltrazione dati.
La reportistica ha concluso che è possibile esfiltrare dati sensibili degli utenti (e-mail, password, ruoli, etc..), mantenere il controllo illimitato dell'applicativo e creare attacchi rivolti agli user. 

## 👥 Collaboratori

Questo progetto è stato sviluppato in collaborazione con:
* [sofcaroli2](https://github.com/sofcaroli2)
* [Anapaxx](https://github.com/Anapaxx)

## Scarica la relazione completa
- Relazione: [VAPT_su_Juice-Shop.pdf](https://github.com/GbriRci/TopTrails/blob/main/TopTrails_relazione.pdf)
- Comandi: [Comandi & Strumenti.pdf](https://github.com/GbriRci/VAPT_on_Juice_Shop/blob/main/Comandi%20%26%20Strumenti.pdf)
