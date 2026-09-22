# DPI mājasdarbs — ko tev darīt soli pa solim

Lielākā darba daļa jau ir sagatavota: finanšu aprēķini, 100 lēmumi, galvenā lapa, `/review` un `/submission.json`.

## 1. Ievadi savu vārdu un studenta ID

Atver `submission.json` ar parastu teksta redaktoru. Faila sākumā atrodi:

```json
"student": {
  "id": "REPLACE-WITH-STUDENT-ID",
  "name": "REPLACE WITH YOUR NAME"
}
```

Nomaini abas vērtības, saglabājot pēdiņas un komatus.

## 2. Izlasi svarīgākos secinājumus

Tev jāspēj īsi izskaidrot šie skaitļi:

- Revenue: EUR 960,000.
- Net profit: EUR 65,000, nevis vadības apgalvotie EUR 312,000.
- Closing cash: EUR 60,000.
- Total assets: EUR 531,000.
- Total liabilities: EUR 406,000.
- Closing equity: EUR 125,000.
- September deposits EUR 90,000 ir saistības, nevis augusta ieņēmumi.
- Loan receipt EUR 50,000 ir aizņēmums, nevis peļņa.
- Owner spending EUR 110,000 ir sadale īpašniekam.
- Inventory modelī ir EUR 9,000 neatrisināta pretruna; tā ir apzināti atklāta.

## 3. Pārbaudi vietni savā datorā

Vienkāršākais variants: atver projekta mapi terminālī un palaid lokālu serveri, piemēram:

```text
python -m http.server 8000
```

Tad pārlūkā atver:

- `http://localhost:8000/`
- `http://localhost:8000/review/`
- `http://localhost:8000/submission.json`

Svarīgi: neatver `index.html` tikai ar dubultklikšķi, jo pārlūks var bloķēt JSON ielādi.

## 4. Izdari obligāto neatkarīgā AI pārbaudi

Šajā projektā ir sagatavoti challenge melnraksti, bet tie nav jāuzdod tam pašam AI kā pirmās analīzes kritika. Lai precīzi izpildītu pasniedzēja noteikumu:

1. Atver pilnīgi jaunu AI sarunu.
2. Iedod tai oriģinālos 01, 02, 03 un 04 failus, bet nedod šo aizpildīto `submission.json`.
3. Iekopē tekstu no `INDEPENDENT-AGENT-PROMPT.txt`.
4. Salīdzini neatkarīgā aģenta rezultātu ar `/review/` redzamo analīzi.
5. Ja otrais aģents atrod labāku risinājumu, izlabo konkrēto lēmumu un finanšu pārskatus pirms iesniegšanas.

Pēc tam atver `/review/` un pārbaudi proposal, independent challenge, final certification, evidence, financial effect un confidence. Pasniedzēja noteikumi paredz, ka gala atbildes sertificē students.

## 5. Izveido GitHub repozitoriju

1. Ieej GitHub un izveido jaunu publisku repozitoriju, piemēram, `dpi-financial-crime-scene`.
2. Augšupielādē visu šīs mapes saturu, saglabājot mapes `assets` un `review`.
3. Pārliecinies, ka repozitorija saknē atrodas `index.html`, `submission.json` un `vercel.json`.

## 6. Publicē Vercel

1. Ieej Vercel ar GitHub kontu.
2. Izvēlies **Add New → Project**.
3. Importē izveidoto GitHub repozitoriju.
4. Framework izvēlies **Other**; build komanda nav vajadzīga.
5. Nospied **Deploy**.

## 7. Pēdējā pārbaude

Privātā pārlūka logā atver savu Vercel adresi un pārbaudi:

1. Galvenā lapa ielādējas un rāda EUR 65,000 peļņu.
2. Adrese ar `/review/` atver vērtētāja skatu.
3. Adrese ar `/submission.json` rāda JSON.
4. JSON meklēšana pēc `"id": "D` dod 100 lēmumus.
5. `student.name` un `student.id` vairs nav `REPLACE...`.
6. GitHub repozitorijs ir publisks.

## 8. Ko iemācīties 15 minūšu individuālajai pārbaudei

Koncentrējies uz D041, D042, D046, D056–D059, D068 un D071–D075. Māki paskaidrot, kā katrs labojums ietekmē peļņu, naudu, aktīvus, saistības un pašu kapitālu.
