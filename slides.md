---
marp: true
paginate: true
transition: push
style: |
  section {
    width: 1280px;
    height: 720px;
    font-size: 28px;
  }
  @page {
    size: 1280px 720px;
    margin: 0;
  }
  section .admonition {
    border-left: 4px solid #999;
    padding: 0.75em 1em;
    margin: 1.5em 0;
    border-radius: 4px;
    background-color: #f9f9f9;
    font-size: 0.80em;
  }
  section .admonition.tip {
    border-color: #2ecc71;
    background: #f0fff0;    
  }
  section .admonition.warning {
    border-color: #e67e22;
    background: #fffaf0;
  }
  section .admonition.info {
    border-color: #3498db;
    background: #f0f8ff;
  }
  section.small {
    font-size: 1.6em;
  }  
  section.smaller {
    font-size: 1.4em;
  }
---

<!--
backgroundImage: url('./images/couverture.png')
backgroundSize: cover
color: white
-->

<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>
Bertrand Florat 
Meetup Arkup Juin 2025
© 2025 Bertrand Florat – CC BY-SA 4.0 

---
<!--
backgroundImage: none
color: #555555
-->

# 🧭 Agenda (1H)

* 0 - Les enjeux de la documentation (générale et d'architecture)
* 1 - Les challenges de la documentation traditionnelle
* 2 - La documentation d'architectrure As Code
* 3 - RETEX, tips, blueprints
* 4 - Take-away & perspectives

---

# 📚 0 — Les enjeux de la documentation
(en général et en architecture en particulier)

---

## ⚠️ Disclaimer

- La **documentation** est selon moi particulièrement  **incompris** et **mal maîtrisé** par les équipes
- Le plus souvent :  
   - 🗂️ **Trop** de documentation...  
   - 📉 **Pas assez** de documentation...  
   - 📄 **Pas le bon niveau** de documentation...  
   - ☠️ **Documentation morte** (non à jour, jamais lue) 

---
## 📈 Le ROI de la documentation

- **Une activité qui dérappe très facilement :**
  - Documentation inutile, hors sujet, inmaintenable
  - Coût élevé, retour hypothétique voire négatif
  - En **lean**, on appelle ça du **Muda** (gaspillage)

- **Écrire une doc, c'est un engagement :**
  - Beaucoup aiment écrire, peu souhaitent maintenir
  - Écrire implique maintenir dans la durée ⚠️

---

# 📊 Temps passé par un.e architecte à produire de la documentation ?  

- Conception & réflexions techniques : 30–40%  
- **Rédaction de documentation : 20–30% (15% sur projets très agiles, 40% dans secteurs très reglementés** 
- Réunions & arbitrages : 20–30%  
- Communication & vulgarisation : 10–15%  
- Veille technologique : 5–10%  

---

# 📢 Pourquoi documenter ?  

## 🌍 **Communiquer des informations importantes**  

- 📡 **Dans l’espace** :  
   - Organisations **distribuées**, télétravail, décalage horaire...  
- ⏳ mais surtout **dans le temps** :  
   - Pour les autres : **TMA**, futurs développeurs, architectes…  
   - Pour soi-même dans 6 mois 😅
   - pour les **transferts de compétence**,...   

---

## 🛡️ **Documenter pour avancer**  

- 🚫 Moins de malentendus ➔ **économies** de temps, d’argent et de frustrations
- 📚 **Tracer les choix et leurs raisons** (ex: ADR) ➔ éviter de reposer sans cesse les mêmes questions
- 🔄 *Si besoin, on pourra toujours les réévaluer plus tard... mais en conscience.*  

---


# 📌 Ce que la documentation doit contenir

- **TOUT** ce qui est nécessaire, mais **QUE** ce qui est nécessaire

- 🧪 **Tests de Litmus** : Dois-je documenter ?
  - Une **personne externe compétente** dans le domaine a-elle besoin d'explications complémentaires au code/écrans ? Si non ➔ pas de doc
  - Documenter essentiellement **ce qui ne peut pas être deviné** (ex: respect d'une réglementation)
  - Répondre à la plupart des « **WTF** » d'une nouvelle personne sur le projet
  - Est-ce que je l'**afficherais au mur** dans l'open-space ?

---

# 🚫 Et ne doit pas :

- Contenir du bullshit inutile :
  - **Historique**, **détails inutiles**, **règles de l'art**, éléments **vagues** ou trop généraux

- **Répéter** (principe DRY 🔄) :
  - Préférer référencer les documents existants

- Contenir **des informations ephemères** 

- **Compenser du code peu explicite** (voir Clean Code / Screaming Architecture 📖)

- Être **inadapté** à son audience 🎯

---

## 📋 Petit exemple fonctionnel

Une application d'état civil permet de saisir les dates de naissance avec **trois champs entier** et non pas un **Date Picker**

**WTF ????**

Que doit contenir (ou pas) la doc ?

---

## 💬 Avez vous un problème de doc ? comptez les :

    🙄 "Ça doit être quelque part dans Confluence..."

    😅 "Je l'ai fait, mais je ne sais plus comment..."

    🤔 "Tu peux demander à Maurice, c’est lui qui sait..."

    🫣 "Ah oui, le guide de DEV... mais il n’est plus à jour depuis 2021…"

---
✅ Bonne documentation

  * **Accessible** : trouvable en 2 clics ou via une recherche simple
  * **Pertinente** : adaptée au public (développeur, ops, manager…)
  * **Actionnable** : apporte des exemples concrets, des commandes, des extraits de code
  * **Vivante** : maintenue à jour, intégrée dans les cycles de développement

❌ Mauvaise documentation

  * **Inaccessible** : fichiers perdus, wiki abandonné…
  * **Encyclopédique** : trop de détails inutiles, illisible
  * **Vague** : « Il faut configurer le proxy »… Mais comment ?
  * **Périmée** : décrit un monde qui n'existe plus

---

## Quid de la documentation d'architecturte en particulier ?

- Tout ce qui a été dit précédemment s'applique aussi aux documents d'architecture

- Préférer les diagrammes au texte (**UML**, **C4**, **BPMN**, **ArchiMate** en particulier) 

- Ne pas hésiter à commenter les diagrammes (directement dans diagramme ou dans le document parent avec des détails pertinents (**tips / warnings**)

- Être honnête :  
  - Lister les hypothèses d’architecture et études en cours dans un chapitre **« Points non statués »** pour chaque vue  
  - L’incertitude doit être **affichée, pas masquée**

---

## 🛑 Les diagrammes : anti-patterns principaux

- Mélange de **niveaux d'abstraction** différents

- Trop d'éléments (**~ > 20**)

- Métaréprésentations floues  
  - Pas de légende  
  - Trop de couleurs, formes, types de flèches  
  - Légendes difficiles à comprendre

- Flèches à **double sens** 🔁 (on ne sait pas qui initie la communication)

---

![width:20%](images/anti-patterns-diagrammes.png)

---

## ✅ Les diagrammes : bonnes pratiques principales

- Métaréprésentations **simples**, niveau d’**abstraction homogène**, **nombre raisonnable** d'élements.

- **Actions explicites sur les flèches**  
  - Indiquer le type d’échange ou de flux  
  - Indiquer la nature du flux (Lecture / Écriture / Exécution) si utile
  
---
### Exemple C4 : diagramme de container
![width:20%](images/bons-diagrammes.png)

---

# 1 - Le problème avec la documentation traditionnelle

---

## 🗃️ Ce que j'entends par 'documentation traditionnelle'

Répond à la plupart de ses critères :

- **Documents bureautique** binaire Word, PDF, PowerPoint, ... (même partagés)

- **Statique et figée** dès sa publication

- **Mise à jour fastidieuse** -> risque élevé de **rapidement devenir obsolète**

- **Traçabilité des modifications** faible ou manuelle

- Peu intégrée aux **outils et processus de développement**

- Existe uniquement parce comme livrable d'un **procesus, pas orienté produit**

---

## 🗃️ Faible évolutivité et traçabilité

* Peu ou pas de **collaboration active** avec les parties prenantes  
  - Décisions prises en silo  
  - Peu adapté aux revues par pair (suivi des modifications mais pas de MR)

* Faible **traçabilité des évolutions**, en particulier sur les **diagrammes** (binaires)

* Difficulté en cas de **renommage** ou de réorganisation  
  - Références croisées cassées  
  - Renomages / refactorings risqués et peu pratiques sur un lot de documents

---

## 🗃️ Une doc moins adaptée aux LLM

* Outils bureautiques **peu formels** : structure faible, pas de validation possible du contenu ou des meta-données (type Git hooks)

* Perte de sens en cas d’**entraînement de LLM**  
  - Contenu essentiellement binaire peu structuré, plus difficile à exploiter par l'IA  
  - Plus diffile de faire générer du contenu

---

## 🔒 Plus de risque de fuites

 - Aspiration de drives partagés  
 - Export et diffusion incontrôlés des fichiers
 - Métadonnées oubliées (devis pour un autre client...)
 - 📈 **Volumétrie importante** (surtout en multi-versions)

---

## ⏱️ Des efforts de mise en page importants

  - Trop de temps consacré à la **mise en page** du texte et au **polissage des diagrammes**  
  - Esthétique privilégiée au détriment du fond  
  - Création de **diagrammes figés** qui nécessitent de lourdes reprises pour toute modification
  - Peu de **réutilisation** et pas de factorisation des représentations

---

# 2- Doc as code

## 🏛️ Documentation d'architecture : Traditionnelle vs Vivante (As Code)

| Traditionnelle 📚          | Vivante / As Code 💻          |
|----------------------------|-------------------------------|
| Fichiers Word / PDF statiques | Documentation versionnée (Git)  |
| Mise à jour manuelle        | Mise à jour via PR-MR / CI-CD    |
| Peu ou pas de traçabilité   | Historique, tags et auteurs tracés |
| Rapide obsolescence         | Mise à jour continue          |
| Non intégrée aux workflows  | Intégrée dans le cycle DevOps |
| Lecture linéaire            | Navigation hypertexte         |
| Diagrammes figés             | Diagrammes générés à partir du code (PlantUML, Structurizr) |
| Peu collaborative           | Collaboration via revues de code / merge requests |

🎯 **En résumé :** Passer d’un document que l’on subit à un **actif vivant et maîtrisé** du projet

---

## 🧰 Utiliser Git pour documenter efficacement

-  **Historique complet** : chaque modification est enregistrée  
-  **Tags** : versionnez les jalons de votre documentation (v1.0, v2.0...)  
-  **Blame** : savoir *qui* a écrit *quoi*, et *quand*  
-  **Diffs** : comparaison facile entre deux versions  
-  **Revue via merge request / pull request**  
-  **Revenir dans le temps** : checkout d'une version antérieure  

---

## 🚀 Et au-delà de Git de base

-  **CI/CD** pour valider / publier automatiquement votre doc (PDF, HTML...)
-  **Git hooks** : automatiser la mise à jour d’index ou de métadonnées  
-  **Traçabilité / conformité** via signature GPG sur commits/tags : utile dans les environnements sensibles  
-  **Collaboration distribuée** : plusieurs auteurs, plusieurs branches  

---

## 📄 L'intéret des langages de balisage légers : AsciiDoc / Markdown

-  **Lisibles en brut** : pas besoin d’outil pour lire ou modifier  
-  **Simplicité** : syntaxe intuitive pour écrire vite  
-  **Facile à générer** : ex : spécificatons exécutables des rapports de tests Spock 
-  **Faciles à versionner** : parfait pour Git (diffs propres, pas de binaire)  
-  **Intégration continue** : générer HTML, PDF, Diagrams, SBOM, etc.  
-  **Extensibles** : AsciiDoc permet des blocs structurés (admonitions, macros, includes...)

---

## 🎯 Idéal pour de la doc "as code"

> Les formats Markdown / AsciiDoc :
> - ✅ s’intègrent naturellement à votre code source (de préférence dans le même dépot)
> - ✅ évitent les formats fermés ou verbeux (Word, PDF, XML)
> - ✅ permettent l’automatisation, la réutilisation et la documentation vivante

📘 Utilisés par : GitHub, GitLab, Red Hat, Spring, Kubernetes...

---
## 🏆 Pourquoi AsciiDoc pour la doc technique avancée ?

- **Structure riche** : sections, blocs, tableaux complexes  
- **Macros & includes** : contenu réutilisable, factorisable  
- **Index, glossaires, bibliographies**  
- **Admonitions** : `NOTE`, `TIP`, `CAUTION`, etc.  
- **Diagrammes intégrés** : PlantUML, Mermaid...  
- **Sorties variées** : HTML5, PDF, DocBook...

---

## 🚀 Antora : plateforme de doc modulaire

-  **Organisation par composants, versions, modules**  
-  **Multi-dépôts Git** : chaque équipe gère sa doc dans son repo  
-  **Mise à jour automatique** des sources  
-  **Navigation unifiée** sur un portail de documentation  
-  **Thématisation et publication pro** (docs produits, API, guides, etc.)

> ✅ Parfait pour la doc d’architecture, microservices, documentation produit distribuée

---

## ✅ Les Spécifications Exécutables

- Traduction directe d’une **exigence** en un **test automatisé**
- Structuration des tests en **Gherkin** (Given/When/Then)
- Servent à la fois :
  - à **documenter** les comportements attendus
  - à **vérifier** en continu leur respect
- Forme lisible par les humains : développeurs, PO, QA...

---

## 🧪 Exemple de spécification avec Spock

```groovy
class CalculatriceSpec extends Specification {

  def "La somme de deux nombres – Gherkin style"() {
    given: "une calculatrice"
    def calculatrice = new Calculatrice()

    when: "je calcule la somme de #a et #b"
    def resultat = calculatrice.somme(a, b)

    then: "le résultat doit être #result"
    resultat == result

    where:
    a  | b  || result
    1  | 2  || 3
    0  | 0  || 0
    -1 | 1  || 0
  }
}
```

---

## 📄 Génération automatique de documentation

- Avec un plugin Spock Reports + conversion AsciiDoc/HTML/PDF
- Exemple de sortie :

```adoc
== Spécification : CalculatriceSpec

=== la somme de #a et #b doit être #result

[cols="1,1,1"]
|===
| a | b | result
| 1 | 2 | 3
| 0 | 0 | 0
| -1 | 1 | 0
|===
```
---

## 🎯 Bénéfices concrets

- Plus de divergence entre code/test/doc
- Vérifiables automatiquement à chaque build
- Réutilisables pour l'audit, l'architecture, etc.

---

## 🔄 Exemple de site Antora multi-dépots à partir de documentation générée

Spécifications 

![image](https://github.com/user-attachments/assets/7c71d669-94e1-4f3c-b4b5-9b0ca23da1d4)


---

## 🛠️ Outils de diagrammes textuels

- Description des **diagrammes en texte brut**
- Stockables en Git, versionnables, diffables
- Intégrables dans les docs AsciiDoc/Markdown
- Génération automatique dans les CI/CD

**Exemples populaires :**
- **Mermaid** : natif Markdown, supporté par GitHub, Obsidian...
- **PlantUML** : plus riche, très utilisé en architecture logicielle
- **Kroki** : agrege une vngtaine d'outils

---

### ✍️ Exemples de syntaxe

#### Mermaid (séquence)

![bg left width:300px](images/ex-mermaid.png)
![bg left width:300px ](images/ex-plantuml.png)

```mermaid
graph TD
  A[ Anyone ] -->|Can help | B( Go to github.com/yuzutech/kroki )
  B --> C{ How to contribute? }
  C --> D[ Reporting bugs ]
  C --> E[ Sharing ideas ]
  C --> F[ Advocating ]
```
#### PlantUML (use case)

```plantuml
@startuml
:Utilisateur: --> (S'authentifier)
(S'authentifier) --> (Accéder aux données)
@enduml
```

> Résultat : un diagramme lisible, versionnable, reproductible !



---

### 🔧 Autres outils de diagrammes textuels

| Outil              | Points forts                                       | Format(s)      |
|-------------------|----------------------------------------------------|----------------|
| **Graphviz / DOT** | Graphes orientés (DAG, dépendances)               | `.dot`         |
| **Draw.io CLI**    | GUI + export CLI (semi-textuel)                   | `.drawio`      |
| **Structurizr DSL**| Vue C4 modélisée textuellement                    | `.dsl`         |
| **Nomnoml**        | UML simplifié avec une syntaxe markdown-like      | `.nomnoml`     |
| **Kroki**          | Service centralisé pour +10 formats               | API, remote    |

---

### ⚙️ Intégrations populaires

- **IDE** :
  - **IntelliJ** : support natif PlantUML, Mermaid via plugins
  - **VS Code** : extensions Mermaid, PlantUML, Graphviz, Kroki
  - **Obsidian** : Mermaid intégré, PlantUML via plugins
- **Docs** : Antora, MkDocs, Asciidoctor
- **CI/CD** : génération automatique via CLI ou Kroki
- **Plateformes** : GitHub, GitLab (prévisualisation automatique)

---

## 🧱 Le modèle C4 — Définition

- Un ensemble d’**abstractions hiérarchiques** :  
  *systèmes logiciels*, *conteneurs*, *composants*, et *code*

- Un ensemble de **diagrammes hiérarchiques** :  
  *contexte système*, *conteneurs*, *composants*, et *code*

- **Indépendant de la notation**  
  (UML, texte, diagramme libre…)

- **Indépendant des outils**  
  (Structurizr, PlantUML, AsciiDoc, etc.)

---

## 🧱 Le modèle C4 — diagrammes

![width:800px](images/c4-overview.png)

Source: https://c4model.com/

---

## 💡 C4 dans la vraie vie

<!-- _class: small -->

* Coupler à Plantuml (intégré de base maintenant)
* Mes diagrammes préférés
  * Système Landscape (en ra)mplcement au Context) et servant pour l'architecture générale
  * Diagramme de container* : de loin le plus utilisé
  * Diagrammes de déploiement pour les diagrammes d'infrastrcture.
* Les diagrammes dynamiques au format séquences sont une version améliorée d'un diagramme de séquence.   
* Eviter trop de diagrammes de composant (conception détaillée -> risque de sur-documentation) et de code (UML) 
* Utiliser les sprites (milliers inclus de base dans plantuml)
* Moins adapté qu'Archimate dans certains cas (EA, TOGAF, outillage existant...)


<div class="admonition tip">
  💡 (*) Je n'aime pas le terme <i>diagramme de containeur</i> J'utilise à la place le terme <i>diagramme d'unités déployables</i>.
</div>

---

## 💡 Exemple de C4 en plantuml

![width:600px](images/28-diag-4.svg)

```
@startuml
   !include <C4/C4_Container>
   !include <tupadr3/devicons2/chrome>
   !include <tupadr3/devicons2/java>
   !include <tupadr3/devicons2/postgresql>
   LAYOUT_LEFT_RIGHT()
   Container(browser, "Browser","Firefox or Chrome", $sprite="chrome")
   Container(api_a, "API A","Spring Boot", $sprite="java")
   ContainerDb(db_a, "Database A","Postgresql", $sprite="postgresql")
   Rel(browser,api_a,"HTTPS")
   Rel_R(api_a,db_a,"pg")
@enduml
```

---

## 🥷 La factorisation des diagrammes
<!-- _class: small -->
Les diagrammes As Code permettent la factorisation de librairies (à utiliser en plantuml avec `remove @unlinked`) :

```
fragments.iuml:

!startsub dmz
  Container(browser, "Browser","Firefox or Chrome", $sprite="chrome")
  Container(api_a, "API A","Spring Boot", $sprite="java")
  Container(api_b, "API B (hors contexte)","Python", $sprite="python")
!endsub
!startsub intranet
  ContainerDb(db_a, "Database A","Postgresql", $sprite="postgresql")  
!endsub
!startsub extranet
  ContainerDb(db_b, "Database B","Postgresql", $sprite="postgresql")
!endsub

File diags-1.puml:
@startuml use-case-1
  remove @unlinked
  !includesub fragments.iuml!dmz
  !includesub fragments.iuml!intranet
    
  Rel(browser,api_a,"HTTPS")
  Rel_R(api_a,db_a,"pg")
@enduml
```

---

## 🥷 Pattern : diagrammes d'inventaire

* Regrouper les unités déployables dans des 'librairires' reutilsiables et découpés en zones. Intégrer dans le DA (vue applicative) la big picture de l'inventaire sans relations.

![bg left width:400px](images/28-diag-1.png)

---

## 🥷 Pattern : diagrammes dynamiques

* Intégrer dans le DA (vue applicative) la big picture des dépenedances principales

![bg left width:400px](images/28-diag-2.png)

---
## 🥷 Pattern : diagrammes de chaine de liaison 

* Et pour chaque feature, découper en chaine de laiison synchrones :

![bg left width:400px](images/28-diag-9.svg)

---

## 🥷 La notion de coordonnées d'architrecture

* Si un DA contient des dizaines voire centaines de diagrammes, difficile de s'y référer (pour discutter d'un flux precis en PROD par exemple)
* Nous découpons nos features en x chaines de liaison synchrones de n appels 
* Exemple de corrdonnées du flux 5 de la chaine de laison 3 de la feature enregistrement de la commande :  `timeout sur com-3:5` -> à utiliser dans les tickets et post-mortems.

---


## 📚 Confusion des concepts

- Solutions décrites **sans les exigences et contraintes correspondantes**  

- Mélange fréquent entre :  
  - **Contraintes** (imposées par le contexte)  
  - **Exigences** (attendues par le métier)  
  - **Solutions** (choix technologiques)  

- Résultat :  
  - Perte de lisibilité  
  - Difficulté pour justifier les choix faits

---



Takeaway

Présentatrion disponible à https://florat.net
https://florat.net/architecture-as-code-with-c4-and-plantuml/


---

Aller plus loin :

La living documentation (pointeur vers Cyril Martraire)


----


2)  La documentation Archi As Code

Modèle de DA orienté usage et orienté checklist
Les ADR
De l'importance de l'Ubiquitous Language
Les suivi de réunions
Les supports (Marp, reveal.js...)
Intégration dans une CI (exports...)
Possibilité de découpage par type de public pour cibler le contenu
Possibilité de filtrage par contexte (ex: pour un projet d'ETL, pas besoin des sections portant sur les GUI)
Possibilité de faire des scripts pour avoir un taux d'avancement / remplissage ? -> Bonne idée !
script avec des extractions automatique ( scan d'infra par exemple, analyse du paramétrage dans le code ou CMDB ?)  -> [BFL] A discuter, souvent une fausse bonne idée de mon expérience et faible ROI. 


3) Les challenges /REX
Comment faire pour que cette documentation technique ne soit pas qu'a la main / en responsabilité de l'archi -> Écriture / MR par les non techniques (mais filtrage)
Export PDF/HTML... -> mise en place dans la CI au MAE, export en 1 clic
Comment faire lire le DA par les devs et autres parties prenantes  ? -> syllabus , quiz
Cohabitation avec d'autres systèmes documentaires (ex: doc infra sur un autre wiki)
Taille du modèle -> découper par filtres contextuels (en cours). Contextes par organisation et/ou projet.
Petits projets / Manque d'architectes, quand les chefs de projet font l'architecture.
Les contextes propices/ non propices
Dichotomie DA/guide de développement (pour les solutions surtout)
Dichotomie DA / DEX : ne pas mélanger, pas les mêmes temporalités / confidentialité des infos.
Comment valider/suivre le cycle de vie du DA par le management ? s'impliquer dans la réalisation/qualité du DA.
Attention à ne pas confondre exigences et solution.
Problème de la maintenance toujours présent. Quelques solutions, la revue globale périodique.
Solution 'loin' des exigences -> exige des hyperliens
Business Analysts  sur specs générales: une approches Wysysig type Confluence peut être préférable (problème d’adhésion), pas de solution unique

4) Conclusion
Vers un outil Open Source (SaaS / on Prem ? ) de gestion/génération des modèles de DA/ADR ?
Aller plus loin : pointeurs vers 'Living documentation' de Cyrill Martraire , etc
