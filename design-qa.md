# Design QA

**Findings**

- [P1] Comparatia vizuala standard nu poate fi inchisa cu dovezi salvate.
  Location: Home / Desktop, Figma node `26:2` si prototipul local.
  Evidence: exista un ecran Figma capturat la 1280 x 2510 px si implementarea a fost deschisa in browser, insa captura implementarii nu a fost exportata ca fisier si source + implementation nu au fost comparate in aceeasi imagine de control.
  Impact: tipografia, proportiile, crop-ul bannerului si ritmul pe pagina nu pot fi aprobate formal numai pe baza inspectarii separate.
  Fix: exporta sursa si captura browserului la aceeasi latime, stare si densitate; pune-le in acelasi canvas si documenteaza rezultatul.

- [P1] Validarea exacta a layoutului responsive ramane deschisa.
  Location: viewport-urile 390, 430, 768, 1440 si 1920 CSS px.
  Evidence: build-ul raspunde la CSS responsive, dar dimensiunile cerute nu au fost verificate individual in browser. Lansarea runnerului automat a esuat in acest mediu.
  Impact: nu putem confirma inca lipsa overflow-ului, ordinea blocurilor, lizibilitatea sau accesul la controale pe fiecare marime ceruta.
  Fix: retesteaza pe cele cinci viewport-uri in browser si ajusteaza daca apar probleme.

- [P2] Capturile Figma principale nu acopera toate paginile si starile.
  Location: Figma `Screens - Desktop`; cadre Home / Desktop `26:2`, Product / Desktop `27:2`, Shop / Desktop `30:2`.
  Evidence: exista capturi editabile pentru trei ecrane desktop si un Design System; blog, articol, cos, retur si variantele mobile nu au cadre echivalente in acest fisier.
  Impact: dezvoltatorul nu are inca o referinta Figma completa pentru toate sabloanele cerute.
  Fix: adauga ecrane si stari Figma pentru sabloanele lipsa, apoi leaga parcursurile principale.

**Open Questions**

- Confirmati daca Georgia ramane fontul editorial final si ce familie sans-serif este aprobata pentru UI.
- Confirmati destinatiile reale, regulile de transport, metodele de plata, politica de retragere si imaginile catalogului.
- Confirmati daca toate paginile responsive trebuie livrate ca layout-uri Figma distincte sau sunt suficiente componente responsive documentate.

**Implementation Checklist**

- [ ] Captureaza comparativ Home / Desktop din Figma si browser la aceeasi dimensiune si densitate.
- [ ] Verifica viewport-urile 390, 430, 768, 1440 si 1920 px.
- [ ] Extinde Figma cu paginile si starile lipsa si traseaza legaturile interactive.
- [ ] Reia QA dupa integrarea datelor, imaginilor si regulilor aprobate.

**Follow-up Polish**

- Exporta capturi pentru formular, preferinte cookies, cos gol/plin si meniul mobil dupa ce sunt disponibile stari responsive de referinta.

source visual truth path: `/Users/apple/.codex/generated_images/01a18328-05d7-7993-b2c1-e0458caa8c75/exec-bf4e1277-70e0-4924-ae2a-b26fb6e22b14.png` (directie vizuala; 1536 x 1024 px)
implementation screenshot path: indisponibil ca fisier exportat; browser preview local `http://127.0.0.1:5173/`, Figma captures `https://www.figma.com/design/O3IOhN1F4sWIE1i7uYj6mB` nodes `26:2`, `27:2`, `30:2`
viewport: browser preview aproximativ 1280 px latime; exactul nu a fost citit din browser. Figma Home / Desktop 1280 x 2510 px.
source and implementation pixel dimensions: source mockup 1536 x 1024 px; Figma captures 1280 x 2510 px, 1280 x 2022 px, 1280 x 1702 px. Nu reprezinta aceeasi pagina/stare si nu sunt comparabile pixel-cu-pixel.
CSS size and density normalization: neconfirmate pentru captura browserului; nu s-a facut normalizare.
state: Home, initial; functional state checks: consent acceptat, categorie filtrata, produs Black / M, cos cu cantitate 2 si cos gol dupa eliminare.
full-view comparison evidence: lipseste captura combinata source + implementation.
focused region comparison evidence: lipseste din acelasi motiv; zonele de logo, banner, navigatie, CTA si card produs necesita comparatie dedicata.
comparison history: implementarea a fost actualizata cu logo-ul si bannerul oficial, apoi cadrele Home, Shop si Product au fost recapturate in Figma. Comparatia vizuala combinata si fixurile evaluate dupa ea nu au fost documentate.
final result: blocked
