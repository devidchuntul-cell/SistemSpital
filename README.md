# 🏥 Sistem de Gestiune Spitalicesc Național

Un sistem informatic multilevel pentru triaj clinic și gestiune spitalicească dezvoltat în **C#** și bazat pe paradigma **Programării Orientate pe Obiect (POO)**. Aplicația simulează fluxul interactiv parcurs de un pacient din momentul în care acuză simptome medicale la domiciliu și până la alocarea resurselor logistice (spital, etaj, cabinet) și umane (medic specialist, diagnostic, tratament).

---

## 📁 Structura Proiectului (Arhitectura Fișierelor)

Mai jos este prezentată organizarea fișierelor în cadrul soluției Visual Studio, respectând principiul modularității și al separării conceptelor (Separation of Concerns):

SistemSpital
│
├── 📄 SistemSpital.sln         # Soluția principală a proiectului
│
└── 📁 SistemSpital/            # Folderul cu codul sursă
    ├── 📄 Program.cs           # Punctul de pornire (Meniul, logica de consolă)
    ├── 📄 Doctor.cs            # Clasa pentru entitatea Medic (Nume, Specializare)
    ├── 📄 Spital.cs            # Clasa pentru unitățile spitalicești (Nume, Adresă)
    ├── 📄 Problema.cs          # Clasa nucleu (Corelează simptomul cu locația și doctorul)
    ├── 📄 Pacient.cs           # Clasa de agregare superioară (Adună toate datele în fișă)
    ├── 📄 Programare.cs        # Clasa pentru gestionarea recontrolului medical
    └── 📄 SistemSpitalManager.cs # Managerul care populează cele 15 simptome clinice

🚀 Caracteristici Principale
Gestiune Multilevel a Datelor: Separare completă între entitățile logistice (Spital), resursele umane (Doctor), cazurile clinice (Problema) și datele administrative (Programare).

Catalog Extins de Triaj: Include o bază de date în-memory simulată cu 15 afecțiuni medicale unice mapate pe 3 etaje și specializări clinice diferite.

Programare Automatizată: Generarea automată a unei programări pentru recontrol medical la exact 7 zile de la triajul inițial, utilizând API-ul nativ DateTime.

Interfață Utilizator Personalizată: Afișare structurată în consolă cu o tematică vizuală galbenă unificată pentru o lizibilitate optimă.

🛠️ Concepte POO Aplicate
Proiectul folosește concepte fundamentale ale programării orientate pe obiect pentru a modela un flux din lumea reală:

Încapsulare: Toate atributele claselor sunt protejate prin proprietăți auto-implementate ({ get; set; }).

Asociere și Agregare: Clasa Problema conține o referință către un Doctor, iar clasa Pacient agregă obiecte de tip Spital, Problema, Doctor și Programare pentru a crea un profil medical complet.

🛡️ Programare Defensivă și Validări
Pentru a asigura o stabilitate maximă în rulare și a elimina riscul crash-urilor la inputuri eronate, aplicația integrează mecanisme defensive avansate:

Validarea Textului: Utilizarea string.IsNullOrWhiteSpace() într-o structură repetitivă pentru a bloca înregistrarea numelor goale sau formate doar din spații.

Parsare Securizată: Utilizarea int.TryParse() combinat cu tehnici de boundary checking pentru selectarea simptomului (1-15), prevenind excepțiile de tip FormatException.

💻 Ghid de Rulare și Utilizare
Deschide proiectul în Visual Studio sau orice IDE compatibil .NET Core.

Rulează aplicația (apasă F5 sau butonul Start).

Introdu numele complet al pacientului (sistemul va valida inputul).

Selectează unitatea spitalicească dorită din meniul interactiv (1 sau 2).

Alege numărul corespunzător simptomului raportat din lista extinsă de 15 afecțiuni.

Sistemul va genera instant Fișa Medicală a Pacientului, afișând resursele alocate.

📊 Matricea Cazurilor Clinice (Catalog Triaj)
Aici sunt prezentate cele 15 cazuri integrate în sistem, structurate clar într-o singură coloană pentru o citire impecabilă pe orice dispozitiv:

[ID 1] Durere de cap
📍 Locație: Etaj 1, Cabinet 101
🩺 Medic: Dr. Popescu (Neurologie)
📝 Diagnostic: Migrena acuta

[ID 2] Durere de stomac
📍 Locație: Etaj 1, Cabinet 102
🩺 Medic: Dr. Marinescu (Gastroenterologie)
📝 Diagnostic: Gastrita reactiva

[ID 3] Os rupt
📍 Locație: Etaj 1, Cabinet 103
🩺 Medic: Dr. Ionescu (Ortopedie)
📝 Diagnostic: Fractura osoasa deschisa

[ID 4] Febra mare
📍 Locație: Etaj 1, Cabinet 104
🩺 Medic: Dr. Radu (Medicina Generala)
📝 Diagnostic: Sindrom infectios viral

[ID 5] Tuse puternica
📍 Locație: Etaj 1, Cabinet 105
🩺 Medic: Dr. Stan (Pneumologie)
📝 Diagnostic: Bronsita acuta

[ID 6] Durere in piept
📍 Locație: Etaj 2, Cabinet 201
🩺 Medic: Dr. Dumitrescu (Cardiologie)
📝 Diagnostic: Investigatie cardiaca

[ID 7] Problems de vedere
📍 Locație: Etaj 2, Cabinet 202
🩺 Medic: Dr. Georgescu (Oftalmologie)
📝 Diagnostic: Tulburare de acomodare

[ID 8] Durere de spate
📍 Locație: Etaj 2, Cabinet 203
🩺 Medic: Dr. Pavel (Recuperare Medicala)
📝 Diagnostic: Lombalgie acuta subiacenta

[ID 9] Alergie
📍 Locație: Etaj 2, Cabinet 204
🩺 Medic: Dr. Enache (Alergologie)
📝 Diagnostic: Reactie alergica imediata

[ID 10] Arsura
📍 Locație: Etaj 2, Cabinet 205
🩺 Medic: Dr. Mihai (Chirurgie)
📝 Diagnostic: Arsura termica de grad superficial

[ID 11] Insomnie si anxietate
📍 Locație: Etaj 3, Cabinet 301
🩺 Medic: Ionescu Radu (Psihiatrie)
📝 Diagnostic: Tulburare de somn pe fond de stres

[ID 12] Puncte rosii pe piele
📍 Locație: Etaj 3, Cabinet 302
🩺 Medic: Popa Elena (Dermatologie)
📝 Diagnostic: Dermatita de contact

[ID 13] Durere acuta de măsea
📍 Locație: Etaj 3, Cabinet 303
🩺 Medic: Marcu Andrei (Stomatologie)
📝 Diagnostic: Pulpita acuta

[ID 14] Scaderea vederii
📍 Locație: Etaj 3, Cabinet 304
🩺 Medic: Sandu Violeta (Oftalmologie)
📝 Diagnostic: Viciu de refractie clinic / Miopie

[ID 15] Durere spate + amorteala
📍 Locație: Etaj 3, Cabinet 305
🩺 Medic: Enache Stefan (Neurologie)
📝 Diagnostic: Hernie de disc lombara
