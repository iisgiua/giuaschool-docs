---
layout: default
title: Ultimo aggiornamento
nav_order: 11
---

# Ultimo aggiornamento
{: .text-center .fw-400 .pb-5}

_Le modifiche seguenti non sono ancora validate né definitive:<br>se ne sconsiglia l'installazione se non in ambiente di test_
{: .text-center .pb-5}

**Data e ora dell'ultimo aggiornamento: 12/11/2026 16:23**

Lista delle modifiche effettuate dopo il rilascio della Versione {{ site.data.version.tag }}:

- [3d9d469f](http://github.com/iisgiua/giuaschool/commit/3d9d469ff1dca3f6ba433b1e106aac9808683d54) - Fix: test
- [a46ff46a](http://github.com/iisgiua/giuaschool/commit/a46ff46ab6e0b40e01a42e9fedc77af93bac783b) - sicurezza: azioni di modifica in POST e token CSRF fuori dalla URL
- [9acc28a1](http://github.com/iisgiua/giuaschool/commit/9acc28a15a1acbfd10073357fa8baacb64a862a6) - Richiede POST e token CSRF sulle rotte distruttive
- [62f18abd](http://github.com/iisgiua/giuaschool/commit/62f18abd1c05b182403d7f55ae7b38c81c47be79) - Fix: procedura di aggiornamento
- [60dfc010](http://github.com/iisgiua/giuaschool/commit/60dfc0108fa4f46f9dbf5798c68474e61d9dedcf) - Fix: template di default per il verbale
- [32e3af6f](http://github.com/iisgiua/giuaschool/commit/32e3af6f82724e4a1abdb6576e7a051a014eaeaf) - controller/entity: null guard su classe e cattedra, validazione payload API, timeout in scaricaUrl; PagelleUtil inizializza le liste e usa getArrayResult
- [710afa84](http://github.com/iisgiua/giuaschool/commit/710afa84d64bef9fb55ae1009820fff2427fba8e) - pagelle: accesso nullable a scrutinio/presenze e fallback template verbale
- [0df70791](http://github.com/iisgiua/giuaschool/commit/0df707913ada18acaff70b18babffd9ec3d0ba55) - Coordinatore: inizializza configErrore; DocumentiController: controllo null su alunno prima di ricostruire percorso storico
- [659d1582](http://github.com/iisgiua/giuaschool/commit/659d1582644664cc0e82afdb7483c97b3fdb29fc) - PagelleUtil: throw su periodo non gestito; PdfManager: try/catch su writeHTML per evitare errori TCPDF opachi
- [0e8c2534](http://github.com/iisgiua/giuaschool/commit/0e8c2534a2367cb780ecee4539fc45b402793ae9) - sicurezza: richiesta password per disattivare OTP
- [edbefb3a](http://github.com/iisgiua/giuaschool/commit/edbefb3a25c6cc3a37ae1d408680f634fd359294) - MessageType: formattaMessaggio sicuro con htmlspecialchars e traduzioni correlate
- [b8ec3afc](http://github.com/iisgiua/giuaschool/commit/b8ec3afcf209c571b4b37fe9cfe00b074e76f251) - SistemaController: manutenzione cache/logout/debug POST con token e aggiorna step>0 con token CSRF in query
- [9a5fbb5d](http://github.com/iisgiua/giuaschool/commit/9a5fbb5dada983824a0571204eaf805b95dfd36e) - Fix install
- [28cc15f2](http://github.com/iisgiua/giuaschool/commit/28cc15f284a5babbab564fade45981d16156938f) - install/updater: parametri scalari validati, escape del file .env, percorsi assoluti e file SQL verificati
- [3c7135e0](http://github.com/iisgiua/giuaschool/commit/3c7135e0d64a4c36308362db7dbc5ef52cba1ab2) - install/updater: procedure come Closure invece di eval()
- [7b5a6fde](http://github.com/iisgiua/giuaschool/commit/7b5a6fde4ef925d709e9b6a65522787d82c599a5) - Installer/Updater: nuovo InstallAuthException, separazione auth da errori operativi e link di ripetizione senza token prima dell'autenticazione
- [ef227175](http://github.com/iisgiua/giuaschool/commit/ef22717524774db63438a25d89503c65bb7a99b4) - Rafforza la validazione dei dati nell'installer
- [01e1434d](http://github.com/iisgiua/giuaschool/commit/01e1434de0a72c21d8bb1a639b9920fd16cb3d97) - Usa confronti in tempo costante e un generatore crittografico
- [faaac2cd](http://github.com/iisgiua/giuaschool/commit/faaac2cdd361d40f9c0f1b011321b9a31983723c) - Correggeva il popolamento di listaurl nel menu
- [d9ebb036](http://github.com/iisgiua/giuaschool/commit/d9ebb0367c060cc2bf7f5e51e6fe7f28e48be5d5) - Valida il token CSRF nell'azzeramento dell'OTP dei docenti
- [18247bf9](http://github.com/iisgiua/giuaschool/commit/18247bf961612d17cde3977910e992afe70131fd) - Repository DQL sicure: escaping output con htmlspecialchars(ENT_QUOTES) e test di regressione su Alunno/DocenteRepository
- [40b500a3](http://github.com/iisgiua/giuaschool/commit/40b500a302f3589e6df62fe5aa9e458e6d519544) - Colloqui: enable/disdetta tornano a GET con token in query, prenotazione con transazione e lock pessimistico, messaggio posti esauriti
- [f071287c](http://github.com/iisgiua/giuaschool/commit/f071287c8540591930ad66c9107b43b1a70774e9) - CSRF sulle azioni GET sensibili
- [7a4cfebc](http://github.com/iisgiua/giuaschool/commit/7a4cfebcb4ca13340b90bc84e8c9327aedf85630) - CSRF sulle azioni GET sensibili: token in query string per password/firma/legge/pubblica/circolari
- [be652f1d](http://github.com/iisgiua/giuaschool/commit/be652f1d580948dad9bc25d9a988e3383c5585a6) - FileController: whitelist estensioni, token CSRF su upload/remove, gestione array file singolo
- [80c9d901](http://github.com/iisgiua/giuaschool/commit/80c9d901f0b7c3ebe9c0a64e533abbd31a1e120d) - sicurezza: rimozione dell'header X-Powered-By
- [c58efeba](http://github.com/iisgiua/giuaschool/commit/c58efeba9d6443dd9a91ae3ea61af5b2bb603474) - Allegati: verifica PDF reale con finfo/mime_content_type e rispostaAllegato per inline/download
- [2d02a58c](http://github.com/iisgiua/giuaschool/commit/2d02a58c51504df12936949708056d7d68ed6d72) - Rimuove le query Uscita duplicate in giustifiche
- [0795bef6](http://github.com/iisgiua/giuaschool/commit/0795bef658a6038ae21af93658eec39a3b765ecd) - Corregge il conteggio delle uscite nel riepilogo mensile
- [65226e4f](http://github.com/iisgiua/giuaschool/commit/65226e4f79d82a7dac49d50604fc7c74fc9cea3f) - Aggiunge noopener alla finestra di logout
- [0e906e29](http://github.com/iisgiua/giuaschool/commit/0e906e2915bafa35fdef987d95e42db049e8f6d6) - Corregge l'escaping dei valori nelle esportazioni CSV
- [6e5030fa](http://github.com/iisgiua/giuaschool/commit/6e5030fa31dec74586885d7c54470c9462896f30) - Aggiorna controller, installer e traduzioni
- [3dc56921](http://github.com/iisgiua/giuaschool/commit/3dc56921fdb07c6a795498bd79090f45c3189158) - Fix: install
- [a99ab035](http://github.com/iisgiua/giuaschool/commit/a99ab035b119cabea7f238fd1be262a26bd19ad0) - Fix: assegnazioni evacuazione
- [9af74dfd](http://github.com/iisgiua/giuaschool/commit/9af74dfda7da67a3dbbe44da465f52d157c5377c) - Fix: provisioning
- [9a957a50](http://github.com/iisgiua/giuaschool/commit/9a957a507076775f0a095a48a3613e5242c341c0) - Aggiunta: gestione designazione evacuazione
- [6512d8b7](http://github.com/iisgiua/giuaschool/commit/6512d8b75e4a385d1a5de7926bbdcc4060d90d2d) - Modifiche: nuova autenticazione da app
- [27d04619](http://github.com/iisgiua/giuaschool/commit/27d0461940cb546ba3c0393c394d58e3ed2749f8) - Modica: gestione app
- [b21e7494](http://github.com/iisgiua/giuaschool/commit/b21e749479c7e666b0590128bccd35e746684248) - Modifica: gestione SPID
- [4bcee070](http://github.com/iisgiua/giuaschool/commit/4bcee070469e8ffba1199e5f833d082da8fc5ce0) - Fix
- [b3ffe280](http://github.com/iisgiua/giuaschool/commit/b3ffe280fa80056eb9c526d5f9a808ede5bf5786) - Fix: chiamata AJAX
- [77f63293](http://github.com/iisgiua/giuaschool/commit/77f632936b8e31e2b69a564f3b2fae972796fcea) - Fix: ancora chiamata AJAX
- [45d1400d](http://github.com/iisgiua/giuaschool/commit/45d1400d5ebe7501f8cd5fd36c7596aec83c83f0) - fix: chiamata AJAX
- [41ebf59b](http://github.com/iisgiua/giuaschool/commit/41ebf59b6517ea5ad9b5c1151438868398bad297) - Fix: firma registro su supplenza
- [c2588392](http://github.com/iisgiua/giuaschool/commit/c25883927d3b2990bc5598ed9c9093983a7a5e51) - Fix: test
- [7bd609fb](http://github.com/iisgiua/giuaschool/commit/7bd609fb3ea727190e456493d94cfb2942308790) - Fix: test
- [855fe5eb](http://github.com/iisgiua/giuaschool/commit/855fe5eb43665f4a767fb82b5bc93853f226ac4c) - Fix test
- [9dd676e9](http://github.com/iisgiua/giuaschool/commit/9dd676e9b31dcee7baf8c4fb3c95785a534b0ace) - Fix test
- [f266e347](http://github.com/iisgiua/giuaschool/commit/f266e3471d9f094d6c85fe3899940314681f2d50) - Fix test
- [d67c1edd](http://github.com/iisgiua/giuaschool/commit/d67c1edda4b240900777e7fc22e2ee845727c5cd) - Modifica: nuova procedura di accesso da app
- [f1994ad9](http://github.com/iisgiua/giuaschool/commit/f1994ad9c8e463f5fdfa28a94003d12a13eeee2d) - Fix: installazione
- [a893f13d](http://github.com/iisgiua/giuaschool/commit/a893f13d1c8469e09bdd0e06ef74032a1f9c6e3f) - Fix test
- [40e37458](http://github.com/iisgiua/giuaschool/commit/40e3745839aaf75800a46ea88a9a544998849965) - Fix tests
- [ff330e69](http://github.com/iisgiua/giuaschool/commit/ff330e69d47a69d7f0447bd1e8b337f88c2da6ce) - Fix install
- [b47fc1de](http://github.com/iisgiua/giuaschool/commit/b47fc1de304b9d49650f4023478986b5d9d79b04) - Fix install
- [b18d00d2](http://github.com/iisgiua/giuaschool/commit/b18d00d2c8051de3bcdf4eb329278131328523e9) - Fix
- [8c399f71](http://github.com/iisgiua/giuaschool/commit/8c399f71d68b84c5cb6f25c81830962258c2413c) - Fix install
- [69b236e7](http://github.com/iisgiua/giuaschool/commit/69b236e7066445e6df498b2c36943a75080f8538) - Fix tests
- [c4e2b0bb](http://github.com/iisgiua/giuaschool/commit/c4e2b0bbc6fd69485085bd18c2654f3684e39997) - Modifica: gestione login
- [3913e5f9](http://github.com/iisgiua/giuaschool/commit/3913e5f98d6ca78463ec109bb8651c5969ea1d3c) - Fix login speciale per amministratotr
- [966754ab](http://github.com/iisgiua/giuaschool/commit/966754ab87fd8d937014220d53c0a171d5a61e97) - Fix: installation
- [a853d2d3](http://github.com/iisgiua/giuaschool/commit/a853d2d3d94608f2e4fbfe180d83c6df358f5ec5) - Fix GHA
- [01a04942](http://github.com/iisgiua/giuaschool/commit/01a04942f1bce91b45c600483c13c8881168d884) - Modica: gestione accesso
- [6569ee44](http://github.com/iisgiua/giuaschool/commit/6569ee44bf31cb73e779f36cfbb89be65576e703) - Fix: tests
- [aa4ebbea](http://github.com/iisgiua/giuaschool/commit/aa4ebbea9df1276e3bc8fda31332c5db019be66f) - Modifica: login speciale
- [f28f7144](http://github.com/iisgiua/giuaschool/commit/f28f71443b7618f4ec683e6eb762f98be9cc84ca) - Modifica: campo per il login speciale
- [b6d2d32c](http://github.com/iisgiua/giuaschool/commit/b6d2d32c8f2891fc32802eca772c2490c450c028) - Fix: installazione
- [f87e6fc8](http://github.com/iisgiua/giuaschool/commit/f87e6fc87f848a52b84eec06b088037f35d4ee7e) - Modifica: gestione RSPP
- [c7ff1997](http://github.com/iisgiua/giuaschool/commit/c7ff1997a6e2a5988e734bf22e4227fed7917b94) - Fix
- [184fb9ab](http://github.com/iisgiua/giuaschool/commit/184fb9ab377fec244422269a46bf880d1d28c1f6) - Fix: cancellazione vecchio SPID
- [7e15c8b3](http://github.com/iisgiua/giuaschool/commit/7e15c8b3f546ed3ee1c0ba01c02fe6f49fc0f904) - Fix installation
- [9cc91716](http://github.com/iisgiua/giuaschool/commit/9cc91716d8f994e1ed6428e5c39e23c43a91ae60) - Elimina: file vecchia implementazione SPID
- [b7583026](http://github.com/iisgiua/giuaschool/commit/b75830261d380a6dc2a37e629a78cea5267b7b0b) - Fix installation
- [b72f4ca5](http://github.com/iisgiua/giuaschool/commit/b72f4ca552b2836c160436b4d677b13d980a46ff) - Fix: installazione
- [12d02872](http://github.com/iisgiua/giuaschool/commit/12d028726773d9007242671253f75bc14b809e89) - Fix
- [7e83cfab](http://github.com/iisgiua/giuaschool/commit/7e83cfaba4a3a4bbcf4b6a3b388bbfc3d2069eaf) - Fix
- [e0bb281f](http://github.com/iisgiua/giuaschool/commit/e0bb281ff2c38eff51a6afe17011bdef3bc0dc8d) - Modifica: template per gestione SPID/CIE

