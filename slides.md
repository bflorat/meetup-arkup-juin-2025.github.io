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

* 1 - A quoi sert la documentation ? (générale et d'architecture)
* 2 - Les challenges de la documentation traditionnelle
* 3 - La Documentation d'Architectrure As Code
* 4 - RETEX, tips, blueprints
* 5 - Conclusions/perspectives
---




A quoi sert la doc technique ?  -> communiquer dans l'espace et dans le temps, éviter les quiproquos, faire gagner du temps et de la confiance.

Le coût de la doc  -> très élevé -> moins on en a, mieux on se porte. Il faut TOUTE la doc nécessaire, QUE la doc nécessaire.

Les points communs de toute bonne doc  -> 1) light 2) maintenable (ex: éviter les screenshots), 3) DRY, 4) ne contient que les infos non devinables ou contractuelles, 5) adaptées au public + principe d'empathie technologique (répond d'emblée aux questions qu'un public adapté devrait se poser), 5) maintenue ou supprimée.

En archi : 

types : ADR, DA, CR, presentations, Etudes