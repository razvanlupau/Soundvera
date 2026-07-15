# Soundvera

*Hear the sound, See the science*

Soundvera e o platformă web educațională despre sunet. Ideea de la care am pornit e că sunetul nu ține de o singură materie — aceeași undă sonoră e în același timp fizică, matematică, biologie, muzică și încă multe altele. Am vrut să arăt asta printr-un singur proiect care leagă 12 domenii diferite, toate pornind de la sunet.

Am ales tema pentru că eu cânt la mai multe instrumente (chitară, fluier, caval) și mi-am dat seama de-a lungul timpului că sunetul pe care îl produc e, de fapt, și fizică, și matematică, și acustică — depinde doar din ce parte îl privești.

**Autor:** Lupau Razvan, Clasa a-XI-a, Colegiul National "Samuil Vulcan", Beius
**Coordonator:** Buran Claudia


## Ce poți face pe site

- Îți faci cont (cu email sau cu Google) și îți alegi un nume de utilizator.
- Parcurgi cele **12 domenii** din secțiunea *Teorie* — fiecare cu explicații, exemple reale și fapte mai puțin știute.
- Rezolvi **quiz-uri** pentru fiecare domeniu. Când greșești, îți arată răspunsul corect și de ce.
- După ce le termini pe toate, se deblochează **quiz-ul final**, iar la final îți poți descărca un certificat cu numele tău.
- În **Melody Studio** compui melodii pe o grilă de note, alegi instrumentul, tempo-ul și volumul.
- Progresul tău se salvează, așa că poți continua de unde ai rămas.

## Cum se folosește

Site-ul e găzduit online, nu trebuie instalat nimic. Deschizi linkul, îți faci cont din pagina *Register* și gata.

Dacă vrei să-l rulezi local, descarci fișierele și deschizi `index.html`. E bine să-l pornești cu un server local simplu (de exemplu `python -m http.server`), pentru ca autentificarea să funcționeze corect. Ai nevoie de un browser modern și de conexiune la internet, pentru că partea de conturi și de salvare a progresului merge prin Firebase.

## Cum e făcut

Proiectul e scris în HTML, CSS și JavaScript, fără niciun framework. Nu are server propriu — paginile vorbesc direct cu Firebase (pentru conturi și baza de date) și cu EmailJS (pentru formularul de contact). Am ales varianta asta pentru că e simplă, ușor de găzduit și se potrivește cu ce voiam: un site pe care oricine îl poate deschide direct din browser.

Structura, pe scurt:

- `index.html`, `login.html`, `register.html` — intrarea și conturile
- `home.html`, `teorie.html`, `quiz.html` — paginile principale
- câte o pagină de teorie și una de quiz pentru fiecare din cele 12 domenii (fizică, chimie, biologie, medicină, muzică, matematică, informatică, astronomie, geografie, arhitectură, artă, psihologie)
- `quiz-final.html` — quizul final și certificatul
- `joc.html` — Melody Studio
- `assets/` — logo și imagini

Datele se țin în Cloud Firestore: profilul fiecărui utilizator și lista quiz-urilor completate, legate de contul lui.

Toate paginile se adaptează la telefon și tabletă — pe ecran mic meniul devine hamburger, iar grila de note din Melody Studio se poate derula lateral ca să rămână utilizabilă cu degetul.

## Ce am folosit și de ce

- **HTML / CSS / JavaScript**, fără framework — ca proiectul să fie ușor și să poată fi citit cap-coadă.
- **Firebase Authentication** pentru conturi (inclusiv login cu Google), ca să nu scriu un sistem de autentificare de la zero.
- **Cloud Firestore** pentru salvarea progresului.
- **Web Audio API** pentru Melody Studio. Sunetul nu vine dintr-o bibliotecă gata făcută — l-am construit direct, cu oscilatoare, pornind de la frecvențele reale ale notelor.
- **Canvas** pentru a desena certificatul și a-l salva ca imagine.
- **EmailJS** pentru a trimite mesajele din formularul de contact fără un server propriu.

## Despre securitate

Cheia de configurare Firebase e vizibilă în cod, dar asta e normal la Firebase — ea e publică prin design. Protecția reală o dau regulile Firestore, care rulează pe server și fac ca fiecare utilizator să poată modifica doar propriile date.
