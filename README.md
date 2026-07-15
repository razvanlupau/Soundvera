# Soundvera
*Hear the sound, See the science*

Soundvera e o platformă educațională despre sunet. Ideea de la care am pornit e că sunetul nu ține de o singură materie — aceeași undă sonoră e în același timp fizică, matematică, biologie, muzică și încă multe altele. Am vrut să arăt asta printr-un singur proiect care leagă 12 domenii diferite, toate pornind de la sunet.

## Ce poți face pe platforma
- Îți faci cont (cu email sau cu Google) și îți alegi un nume de utilizator.
- Parcurgi cele **12 domenii** din secțiunea *Teorie* — fiecare cu explicații, exemple reale și fapte mai puțin știute.
- Rezolvi **quiz-uri** pentru fiecare domeniu. Când greșești, îți arată răspunsul corect și de ce.
- După ce le termini pe toate, se deblochează **quiz-ul final**, iar la final îți poți descărca un certificat cu numele tău.
- În **Melody Studio** compui melodii pe o grilă de note, alegi instrumentul, tempo-ul și volumul.
- Progresul tău se salvează, așa că poți continua de unde ai rămas.

## Cum se folosește
Platforma e găzduită online, nu trebuie instalat nimic. Deschizi linkul, îți faci cont din pagina *Register* și gata.

## Cum e făcută
Proiectul e scris în HTML, CSS și JavaScript, fără niciun framework. Nu are server propriu — paginile vorbesc direct cu Firebase (pentru conturi și baza de date) și cu EmailJS (pentru formularul de contact). Am ales varianta asta pentru că e simplă, ușor de găzduit și se potrivește cu ce voiam: o platformă pe care oricine o poate deschide direct din browser.


Datele se țin în Cloud Firestore: profilul fiecărui utilizator și lista quiz-urilor completate, legate de contul lui.

Toate paginile se adaptează la telefon și tabletă — pe ecran mic meniul devine hamburger, iar grila de note din Melody Studio se poate derula lateral ca să rămână utilizabilă cu degetul.

## Ce am folosit și de ce
- **HTML / CSS / JavaScript**, fără framework — ca proiectul să fie ușor și să poată fi citit cap-coadă.
- **Firebase Authentication** pentru conturi (inclusiv login cu Google), ca să nu scriu un sistem de autentificare de la zero.
- **Cloud Firestore** pentru salvarea progresului.
- **Web Audio API** pentru Melody Studio. Sunetul nu vine dintr-o bibliotecă gata făcută — l-am construit direct, cu oscilatoare, pornind de la frecvențele reale ale notelor.
- **Canvas** pentru a desena certificatul și a-l salva ca imagine.
- **EmailJS** pentru a trimite mesajele din formularul de contact fără un server propriu.

