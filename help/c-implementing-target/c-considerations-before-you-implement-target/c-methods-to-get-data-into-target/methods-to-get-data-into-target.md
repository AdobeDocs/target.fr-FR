---
keywords: implémenter;implémentation;configuration;configurer;paramètre de page;tomcat;codage URL;attribut de profil interne à la page;paramètre mbox;attributs de profil internes à la page;attribut de profil de script;API de mise à jour des profils en masse;API de mise à jour de profil individuel;attributs du client;fournisseurs de données;fournisseur de données
description: Insérez des données dans la Cible (paramètres de page, attributs de profil, attributs de profil de script, fournisseurs de données, API de mise à jour de profil unique et en bloc, attributs du client).
title: Comment puis-je obtenir des données dans la Cible ?
feature: Mise en œuvre
role: Developer
exl-id: b42eb846-d423-4545-a8fe-0b8048ab689e
translation-type: tm+mt
source-git-commit: 70d4c5b4166081751246e867d90d43b67efa5469
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 84%

---

# Présentation des méthodes

Informations sur les différentes méthodes que vous pouvez utiliser pour obtenir des données dans [!DNL Adobe Target].

Les méthodes disponibles sont les suivantes :

| Méthode | Détails |
| --- | --- |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/page-parameters.md)<br>Paramètres de page (également appelés « paramètres de mbox ») | Les paramètres de page sont des paires nom/valeur transmises directement par le biais du code de page qui ne sont pas enregistrées dans le profil du visiteur pour une utilisation ultérieure.<br>Les paramètres de page sont utiles pour envoyer à Target des données de page supplémentaires qui ne doivent pas être enregistrées avec le profil du visiteur pour une utilisation ultérieure dans le cadre du ciblage. Ces valeurs sont utilisées pour décrire la page ou l’action effectuée par l’utilisateur sur cette page spécifique. |
| [](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/in-page-profile-attributes.md)<br>Attributs de profil internes à la page (également appelés « attributs de profil internes à la mbox ») | Les attributs de profil internes à la page sont des paires nom/valeur transmises directement par le biais du code de page qui sont enregistrées dans le profil du visiteur pour une utilisation ultérieure.<br>Les attributs de profil internes à la page permettent d’enregistrer les données spécifiques à l’utilisateur dans le profil de Target pour un ciblage et une segmentation ultérieurs. |
| [Attributs de profil de script](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/script-profile-attributes.md) | Les attributs de profil de script sont des paires nom/valeur définies dans la solution Target. La valeur est déterminée grâce à l’exécution d’un fragment de code JavaScript sur le serveur de Target à chaque appel de serveur.<br>Les utilisateurs écrivent de petits fragments de code qui s’exécutent à chaque appel de mbox, avant l’évaluation de l’appartenance d’audience et de l’appartenance à une activité d’un visiteur. |
| [Fournisseurs de données](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/data-providers.md) | Les fournisseurs de données sont une fonctionnalité qui vous permet de transmettre facilement des données de tiers à la Cible. |
| API de mise à jour des profils en masse | L’API permet d’envoyer à Target un fichier .csv contenant les mises à jour des profils d’un grand nombre de visiteurs. Chaque profil du visiteur peut être mis à jour avec plusieurs attributs de profil internes à la page en un seul appel. |
| API de mise à jour de profil individuel | Presque identique à l’API de mise à jour de Profil en bloc, mais un profil visiteur est mis à jour à la fois, dans la ligne de l’appel d’API au lieu d’un fichier .csv. |
| Attributs du client | Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le chargement effectué, vous pouvez exploiter les données dans Adobe Analytics et Adobe Target. |







## API de mise à jour des profils en masse {#section_92AB4820A5624C669D9A1F1B6220D4FA}

L’API permet d’envoyer à Target un fichier .csv contenant les mises à jour des profils d’un grand nombre de visiteurs. Chaque profil du visiteur peut être mis à jour avec plusieurs attributs de profil internes à la page en un seul appel.

Cette option est très similaire à l’option Attributs du client, avec quelques différences :

* Les attributs du client utilisent le transfert FTP, tandis que l’API de mise à jour des profils en masse de Target utilise une API HTTP POST.
* Les données d’attributs du client peuvent être partagées avec Analytics. La mise à jour des profils en masse peut uniquement être utilisée dans Target.
* Les attributs du client prennent en charge la création d’un profil pour un utilisateur que Target n’a pas encore vu. L’API de mise à jour des profils en masse met uniquement à jour les profils Target existants.
* Les attributs du client requièrent l’utilisation de l’Experience Cloud ID (ECID). L’API de mise à jour des profils en masse requiert soit l’ID TNT, soit l’ID `mbox3rdPartyId`.
* Vous ne pouvez pas envoyer les caractères suivants dans `mbox3rdPartyID` : signe plus (+) et barre oblique (/).

### Format

Le fichier .csv doit désigner chaque visiteur par son PCID ou son mboxThirdPartyId Target. L’Experience Cloud ID (ECID) n’est pas pris en charge. Tous les attributs/valeurs de profil sont créés et mis à jour via l’API. Les détails relatifs au format sont disponibles dans la documentation de l’API.

### Exemples de cas d’utilisation

Votre logiciel de gestion de la relation client ou autre système interne stocke des données importantes sur vos visiteurs que vous souhaitez constamment mettre à jour dans Target, sans exposer les données du profil dans l’implémentation de votre page.

### Avantages de la méthode

Nombre d’attributs de profil illimité.

Les attributs de profil envoyés via le site peuvent être mis à jour via l’API et vice versa.

### Avertissements

La taille du fichier de traitement par lot doit être inférieure à 50 Mo. En outre, le nombre total de lignes ne doit pas dépasser 500 000 lignes par téléchargement.

Le nombre de lignes pouvant être téléchargées en lots ultérieurs sur une période de 24 heures est illimité. Cependant, le processus d’assimilation peut être ralenti pendant les heures ouvrables pour s’assurer que les autres processus s’exécutent efficacement.

Les [appels de mise à jour de lots V2](https://developers.adobetarget.com/api/#updating-profiles) consécutifs non espacés par des appels mbox pour le même identifiant tiers remplacent les propriétés mises à jour au premier appel de mise à jour de lots.

### Exemples de code

Voir [Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles).

### Liens vers les informations connexes

[Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles)

## API de mise à jour de profil individuel {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Presque identique à l’API de mise à jour de Profil en bloc, mais un profil visiteur est mis à jour à la fois, dans la ligne de l’appel d’API au lieu d’un fichier .csv.

### Format

Le visiteur doit être identifié à l’aide de la valeur mboxPC ou mboxThirdPartyId de Target. L’Experience Cloud ID (ECID) n’est pas pris en charge.

### Exemples de cas d’utilisation

Vous souhaitez mettre à jour Target en temps réel lorsqu’un visiteur effectue une action hors ligne, telle que contacter un centre d’appel, financer un prêt, utiliser une carte de fidélité en boutique, accéder à un kiosque, etc.

### Avantages de la méthode

Nombre d’attributs de profil illimité.

Les attributs de profil envoyés via le site peuvent être mis à jour via l’API et vice versa.

### Avertissements

Limite de 1 000 000 d’appels de l’API (1 million) par période de 24 heures.

Met à jour le profil uniquement. Ne prend pas en charge la création d’un profil pour un utilisateur que Target n’a pas encore vu.

### Exemples de code

Prise en charge des commandes GET et POST. `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Liens vers les informations connexes

[Mise à jour des profils](https://developers.adobetarget.com/api/#updating-profiles)

## Attributs du client {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Les attributs du client permettent de télécharger les données des profils de visiteur vers Experience Cloud par FTP. Une fois le chargement effectué, vous pouvez exploiter les données dans Adobe Analytics et Adobe Target.

Les clients Target Standard peuvent utiliser 5 attributs et les clients Target Premium peuvent utiliser 200 attributs.

### Format

Un fichier .csv contenant des Experience Cloud IDs (ECID) et des paires nom/valeur d’attributs est chargé par FTP ou manuellement dans l’interface utilisateur d’Experience Cloud.

### Exemples de cas d’utilisation

Votre logiciel de gestion de la relation client ou autre système interne stocke des informations importantes que vous voulez partager avec la solution Experience Cloud d’Adobe, notamment Target et Analytics.

### Avantages de la méthode

Le chargement des données d’un client crée une entrée de profil pour ce visiteur dans Target, même si Target ne l’a pas encore vu.

Les mêmes données sont automatiquement disponibles dans Target et Analytics.

Le chargement par FTP peut constituer une méthode d’implémentation plus simple que l’API.

### Avertissements

Les clients Target Standard peuvent utiliser 5 attributs et les clients Target Premium peuvent utiliser 200 attributs.

Les valeurs peuvent uniquement être mises à jour par le biais des attributs du client, pas sur la page.

Cette méthode requiert l’implémentation de l’Experience Cloud ID (ECID).

### Exemples de code

Vous trouverez des détails dans [Création d’une source d’attributs du client et téléchargement du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Liens vers les informations connexes

[Création d’une source d’attributs du client et transfert du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
