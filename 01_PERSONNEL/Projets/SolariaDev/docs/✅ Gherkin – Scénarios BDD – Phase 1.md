> Ces scénarios décrivent les comportements attendus pour les principales fonctionnalités du cœur de la plateforme.

## 🏢 Création d’un projet (Entreprise)

```gherkin
Feature: Création d’un projet par une entreprise

  Scenario: Une entreprise crée un projet avec un titre et une description
    Given une entreprise authentifiée
    When elle soumet un formulaire de création de projet avec un titre et une description valides
    Then le projet est enregistré en base de données
    And le projet apparaît dans la liste publique des projets
```

## 👨‍💻 Consultation de projets (Développeur)

```gherkin
Feature: Consultation des projets disponibles

  Scenario: Un développeur consulte la liste des projets
    Given un développeur connecté
    When il accède à la page des projets disponibles
    Then il voit la liste des projets ouverts avec titre, description et compétences requises
```

## 👨‍💻 Rejoindre un projet (Développeur)

```gherkin
Feature: Participation à un projet

  Scenario: Un développeur rejoint un projet ouvert
    Given un projet public avec des places disponibles
    And un développeur connecté
    When il clique sur "Rejoindre le projet"
    Then il est ajouté à la liste des contributeurs du projet
    And une notification est envoyée à l’entreprise créatrice
```

## 📤 Soumettre une solution (Développeur)

```gherkin
Feature: Soumission d’un livrable

  Scenario: Un développeur soumet une solution à un projet
    Given un développeur membre d’un projet
    When il téléverse un livrable ou publie un lien de dépôt
    Then la soumission est enregistrée
    And elle est visible pour l’entreprise
```

## 🗂 Ajouter un projet au portfolio

```gherkin
Feature: Enregistrement d’un projet terminé dans le portfolio

  Scenario: Un projet terminé est ajouté au portfolio du développeur
    Given un développeur ayant complété un projet validé
    When il clique sur "Ajouter au portfolio"
    Then le projet est listé dans son profil personnel
```

## 📝 Donner un feedback (Mentor/Entreprise)

```gherkin
Feature: Feedback sur une contribution

  Scenario: Un mentor donne un retour sur une soumission
    Given un projet avec une contribution soumise par un développeur
    And un mentor connecté
    When il rédige un commentaire et l’envoie
    Then le développeur est notifié
    And le feedback est enregistré et visible dans l'historique
```

## 📌 Tags

`#gherkin` `#bdd` `#phase1` `#backend` `#tests` `#obsidian`

## 🔗 Liens
[[📘 User Stories – Phase 1 – Cœur de la plateforme]]