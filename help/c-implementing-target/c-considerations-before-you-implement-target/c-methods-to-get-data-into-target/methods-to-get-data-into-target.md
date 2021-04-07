---
keywords: implémenter;implémentation;configuration;configurer;paramètre de page;tomcat;codage URL;attribut de profil interne à la page;paramètre mbox;attributs de profil internes à la page;attribut de profil de script;API de mise à jour des profils en masse;API de mise à jour de profil individuel;attributs du client;fournisseurs de données;fournisseur de données
description: Insérez des données dans la Cible (paramètres de page, attributs de profil, attributs de profil de script, fournisseurs de données, API de mise à jour de profil unique et en bloc, attributs du client).
title: Comment puis-je obtenir des données dans la Cible ?
feature: Mise en œuvre
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 61%

---

# Présentation des méthodes

Informations sur les différentes méthodes que vous pouvez utiliser pour obtenir des données dans [!DNL Adobe Target].

Les méthodes disponibles sont les suivantes :

| Méthode | Détails |
| --- | --- |
| [Paramètres](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br> de page (également appelés &quot;paramètres de mbox&quot;) | Les paramètres de page sont des paires nom/valeur transmises directement par le biais du code de page qui ne sont pas enregistrées dans le profil du visiteur pour une utilisation ultérieure.<br>Les paramètres de page sont utiles pour envoyer des données de page à la Cible qui n’ont pas besoin d’être stockées avec le profil visiteur pour un futur ciblage. Ces valeurs sont utilisées pour décrire la page ou l’action effectuée par l’utilisateur sur cette page spécifique. |
| [Attributs](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br> de profil internes à la page (également appelés &quot;attributs de profil internes à la mbox&quot;) | Les attributs de profil internes à la page sont des paires nom/valeur transmises directement par le biais du code de page qui sont enregistrées dans le profil du visiteur pour une utilisation ultérieure.<br>Les attributs de profil internes à la page permettent d’enregistrer les données spécifiques à l’utilisateur dans le profil de Target pour un ciblage et une segmentation ultérieurs. |
| [Attributs de profil de script](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | Les attributs de profil de script sont des paires nom/valeur définies dans la solution Target. La valeur est déterminée grâce à l’exécution d’un fragment de code JavaScript sur le serveur de Target à chaque appel de serveur.<br>Les utilisateurs écrivent de petits fragments de code qui s’exécutent à chaque appel de mbox, avant l’évaluation de l’appartenance d’audience et de l’appartenance à une activité d’un visiteur. |
| [Fournisseurs de données](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | Les fournisseurs de données vous permettent de transférer facilement des données de tiers vers la Cible. |
| [API de mise à jour des profils en masse](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/bulk-profile-update-api.md) | L’API permet d’envoyer à Target un fichier .csv contenant les mises à jour des profils d’un grand nombre de visiteurs. Chaque profil du visiteur peut être mis à jour avec plusieurs attributs de profil internes à la page en un seul appel. |
| [API de mise à jour de profil individuel](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/single-profile-update-api.md) | Presque identique à l’API de mise à jour de Profil en bloc, mais un profil visiteur est mis à jour à la fois, dans la ligne de l’appel d’API au lieu d’un fichier .csv. |
| [Attributs du client](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/customer-attributes.md) | Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le téléchargement effectué, utilisez les données dans Adobe Analytics et Adobe Target. |












