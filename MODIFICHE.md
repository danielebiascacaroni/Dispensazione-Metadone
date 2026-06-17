# REGISTRO MODIFICHE — Terapie Alternative
> File: `index.html` | Ultimo aggiornamento: 2026-04-03

---

## Modifiche apportate

### 1. Autenticazione Firebase
**Prima:** `firebase.auth().signInAnonymously()`
**Dopo:** `firebase.auth().signInWithEmailAndPassword('farmacia.ascona@gmail.com', ...)`
L'autenticazione anonima permetteva a chiunque di accedere a Firestore.

---

### 2. Sistema di controllo dispositivi
Aggiunto overlay di autorizzazione all'avvio della webapp.

**Comportamento:**
- Dispositivo non riconosciuto → schermata con campo codice admin
- Codice corretto → assegna nome → dispositivo registrato su Firestore (`dispositivi`)
- Accessi successivi → controllo automatico, accesso diretto
- Dispositivo revocato dall'admin → overlay riappare

**Codice admin:** verificato tramite hash SHA-256 hardcoded nel file.

---

## Stato sicurezza attuale

| Controllo | Stato |
|-----------|-------|
| Auth anonima Firebase disabilitata | ✅ |
| Login con email/password dedicata | ✅ |
| Firestore Security Rules aggiornate | ✅ |
| Controllo dispositivi operativo | ✅ |
| Codice admin hardcoded come hash SHA-256 | ✅ |
