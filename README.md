# Flowly

Flowly – minimalistinė užduočių ir progreso valdymo aplikacija, kuriama naudojant React ir  ir Vite.

Projektas orientuotas į paprastą užduočių valdymą, progreso stebėjimą ir modernų, tamsios temos vartotojo interfeisą.

## Funkcionalumas

Šiuo metu Flowly turi:

- prisijungimo formą;
- užduočių sąrašą;
- naujų užduočių pridėjimą;
- užduoties termino pasirinkimą;
- užduoties statuso pasirinkimą;
- progreso juostą;
- viršutinę navigacijos juostą;
- responsive dizainą mobiliems įrenginiams.

## Naujos užduoties pridėjimas

Naudotojas gali paspausti:

`+ Nauja užduotis`

Atsidariusioje formoje galima įvesti:

- užduoties pavadinimą;
- terminą;
- statusą.

Galimi statusai:

- `Nepradėta`
- `Vykdoma`
- `Atlikta`

Paspaudus **„Pridėti užduotį“**, nauja užduotis pridedama prie esamo užduočių sąrašo.

Šiuo metu užduotys saugomos React state, todėl perkrovus puslapį naujai pridėtos užduotys nėra išsaugomos.

## Technologijos

Projektas naudoja:

- React
- Vite
- JavaScript
- JSX
- CSS
- React `useState`

Projektas šiuo metu nenaudoja:

- TypeScript
- Tailwind CSS
- CSS Modules
- backend
- duomenų bazės

## Projekto struktūra

```text
Flowly/
├── public/
├── src/
│   ├── assets/
│   ├── AddTaskForm.css
│   ├── AddTaskForm.jsx
│   ├── alert.jsx
│   ├── App.css
│   ├── App.jsx
│   ├── index.css
│   ├── main.jsx
│   ├── Navbar.css
│   ├── Navbar.jsx
│   ├── ProgressBar.css
│   ├── ProgressBar.jsx
│   ├── TaskList.css
│   └── TaskList.jsx
│
├── .gitignore
├── eslint.config.js
├── index.html
├── package-lock.json
├── package.json
├── README.md
└── vite.config.js

Pagrindiniai komponentai
App
App.jsx yra pagrindinis aplikacijos komponentas.
Jame saugoma:
- prisijungimo formos būsena;
- užduočių būsena;
- pagrindinė puslapio struktūra.
Užduotys saugomos naudojant React useState.
const [tasks, setTasks] = useState([
  {
    id: 1,
    title: "Sukurti prisijungimo formą",
    status: "Atlikta",
    deadline: "2026-10-01",
  },
  {
    id: 2,
    title: "Sukurti užduočių sąrašą",
    status: "Vykdoma",
    deadline: "2026-10-05",
  },
]);

Nauja užduotis pridedama naudojant:
function handleAddTask(newTask) {
  setTasks((currentTasks) => [...currentTasks, newTask]);
}

AddTaskForm
AddTaskForm.jsx atsakingas už naujų užduočių kūrimą.
Komponentas leidžia pasirinkti:
- pavadinimą;
- terminą;
- statusą.
Sukurta užduotis perduodama pagrindiniam App komponentui per onAddTask prop.
TaskList
TaskList.jsx atsakingas už užduočių sąrašo atvaizdavimą.
Užduotys perduodamos per:
<TaskList tasks={tasks} loading={false} />

ProgressBar
ProgressBar.jsx atvaizduoja bendrą progresą.
Šiuo metu pradinis progresas nustatytas į:
<ProgressBar initialProgress={50} />

Tai reiškia, kad progreso reikšmė šiuo metu dar nėra automatiškai skaičiuojama pagal atliktas užduotis.
Navbar
Navbar.jsx atvaizduoja pagrindinę Flowly navigaciją.
Navigacijoje yra:
- Pagrindinis
- Užduotys
- Progresas
- Profilis
Navigacijos punktai šiuo metu yra neaktyvūs.
Flowly logotipas sukurtas naudojant inline SVG, todėl papildomas logotipo failas nėra reikalingas.
Dizainas
Flowly naudoja tamsią minimalistinę dizaino kryptį.
Pagrindiniai dizaino principai:
- tamsus fonas;
- tamsios kortelės;
- subtilūs borderiai;
- šviesus pagrindinis tekstas;
- pilkas antrinis tekstas;
- violetinis pagrindinis akcentas;
- apvalinti kampai;
- responsive išdėstymas.
Projekto paleidimas
Pirmiausia įdiek dependencies:
npm install

Tada paleisk development serverį:
npm run dev

Terminale bus parodytas lokalus aplikacijos adresas.
Dažniausiai Vite naudoja:
http://localhost:5173

Development
Kuriant naujus komponentus naudojama tokia struktūra:
ComponentName.jsx
ComponentName.css

Pavyzdžiui:
AddTaskForm.jsx
AddTaskForm.css

Komponentai laikomi src/ kataloge.
Dabartiniai apribojimai
Projektas vis dar yra ankstyvoje kūrimo stadijoje.
Šiuo metu:
- nėra tikro autentifikavimo;
- nėra backend;
- nėra duomenų bazės;
- naujos užduotys neišsaugomos po puslapio perkrovimo;
- progreso juosta dar nėra automatiškai susieta su užduotimis;
- navigacijos punktai dar neatlieka veiksmų;
- nėra užduočių redagavimo;
- nėra užduočių ištrynimo;
- nėra užduočių filtravimo.
Galimi tolimesni patobulinimai
Planuojamos arba galimos funkcijos:
1. Automatinis progreso skaičiavimas pagal atliktas užduotis.
2. Užduoties statuso keitimas.
3. Užduočių redagavimas.
4. Užduočių ištrynimas.
5. Užduočių filtravimas pagal statusą.
6. Užduočių paieška.
7. Duomenų išsaugojimas naudojant localStorage.
8. Dashboard su užduočių statistika.
9. Veikianti navigacija.
10. Tikras naudotojo autentifikavimas.
11. Backend ir duomenų bazė.
Projekto tikslas
Flowly kuriamas kaip praktinis React projektas, palaipsniui pridedant naują funkcionalumą.
Projektas leidžia praktiškai mokytis:
- React komponentų;
- props;
- useState;
- formų valdymo;
- masyvų būsenos keitimo;
- komponentų tarpusavio komunikacijos;
- responsive CSS;
- aplikacijos struktūros organizavimo.
Flowly – paprastesnis būdas valdyti užduotis ir stebėti progresą.

### Kur įklijuoti

Projekto pagrindiniame kataloge jau turi `README.md`. Atidaryk jį, **ištrink visą dabartinį turinį** ir įklijuok aukščiau pateiktą tekstą.

Tik viena pastaba: tavo pateiktame `FLOWLY_PROJECT_CONTEXT.md` vis dar aprašyta senesnė būsena, kur `tasks` yra hardcodintas masyvas ir nėra `AddTaskForm`. Kadangi ką tik patvirtinai, jog naujos užduoties funkcija jau veikia, README turinyje rėmiausi **naujesne dabartine projekto būsena**, kurią sukūrėme šiame pokalbyje.
```
