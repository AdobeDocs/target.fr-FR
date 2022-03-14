---
keywords: implémenter;implémentation;configuration;configurer;paramètre de page;tomcat;codage URL;attribut de profil interne à la page;paramètre mbox;attributs de profil internes à la page;attribut de profil de script;API de mise à jour des profils en masse;API de mise à jour de profil individuel;attributs du client;fournisseurs de données;fournisseur de données
description: Obtenir des données dans [!DNL Target] (paramètres de page, attributs de profil, attributs de profil de script, fournisseurs de données, API de mise à jour de profil uniques et en masse, attributs du client).
title: Comment puis-je obtenir des données dans Target ?
feature: Implementation
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 63%

---

# Présentation des méthodes

Informations sur les différentes méthodes permettant d’intégrer des données [!DNL Adobe Target].

Les méthodes disponibles sont les suivantes :

| Méthode | Détails |
| --- | --- |
| [Paramètres de page](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>(Également appelé &quot;paramètres de mbox&quot;) | Les paramètres de page sont des paires nom/valeur transmises directement par le biais du code de page qui ne sont pas enregistrées dans le profil du visiteur pour une utilisation ultérieure.<br>Les paramètres de page sont utiles pour envoyer à Target des données de page qui n’ont pas besoin d’être stockées avec le profil du visiteur pour une utilisation ultérieure dans le cadre du ciblage. Ces valeurs sont utilisées pour décrire la page ou l’action effectuée par l’utilisateur sur cette page spécifique. |
| [Attributs de profil internes à la page](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>(Également appelé &quot;attributs de profil internes à la mbox&quot;) | Les attributs de profil internes à la page sont des paires nom/valeur transmises directement par le biais du code de page qui sont enregistrées dans le profil du visiteur pour une utilisation ultérieure.<br>Les attributs de profil internes à la page permettent d’enregistrer les données spécifiques à l’utilisateur dans le profil de Target pour un ciblage et une segmentation ultérieurs. |
| [Attributs de profil de script](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | Les attributs de profil de script sont des paires nom/valeur définies dans la solution Target. La valeur est déterminée grâce à l’exécution d’un fragment de code JavaScript sur le serveur de Target à chaque appel de serveur.<br>Les utilisateurs écrivent de petits fragments de code qui s’exécutent à chaque appel de mbox, avant l’évaluation de l’appartenance d’audience et de l’appartenance à une activité d’un visiteur. |
| [Fournisseurs de données](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | Les fournisseurs de données vous permettent de transmettre facilement des données provenant de tiers à Target. |
| [API de mise à jour des profils en masse](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/bulk-profile-update-api.md) | L’API permet d’envoyer à Target un fichier .csv contenant les mises à jour des profils d’un grand nombre de visiteurs. Chaque profil du visiteur peut être mis à jour avec plusieurs attributs de profil internes à la page en un seul appel. |
| [API de mise à jour de profil individuel](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/single-profile-update-api.md) | Presque identique à l’API de mise à jour de profil en bloc, mais un profil du visiteur est mis à jour à la fois, en ligne dans l’appel d’API au lieu d’être associé à un fichier .csv. |
| [Attributs du client](/help/main/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/customer-attributes.md) | Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le chargement effectué, utilisez les données dans Adobe Analytics et Adobe Target. |












