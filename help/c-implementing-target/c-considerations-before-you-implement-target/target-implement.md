---
keywords: document.write;target;implement;implement target;dtm;dynamic tag management;at.js;mbox.js;target.js;mbox
description: Implémentez Target en référençant les bibliothèques Target (at.js ou mbox.js) sur vos pages web.
title: Présentation des bibliothèques JavaScript Target
feature: implementation general
topic: Target
uuid: c8a254c9-afc9-4a55-be01-788c11bef7cc
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 100%

---


# Comprendre les [!DNL Target]bibliothèques JavaScript{#understand-the-target-javascript-libraries}

Implémentez [!DNL Target] en référençant les bibliothèques [!DNL Target] (at.js ou mbox.js) sur vos pages Web.

>[!NOTE]
>
>La bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. Pour plus d’informations, voir [Migration vers at.js depuis mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## Différences entre les deux bibliothèques {#section_40117C78C2F84FECAC4F1BA40CC4F171}

Le tableau suivant explique les différences entre les deux bibliothèques :

| Référence de bibliothèque | Description |
|--- |--- |
| at.js | at.js remplace mbox.js pour les implémentations de [!DNL Target].<br>Autres avantages : at.js optimise les délais de chargement des pages pour les mises en œuvre web, renforce la sécurité, bloque les avertissements document.write dans Google Chrome et fournit de meilleures options d’implémentation pour les applications d’une seule page.<br>Pour plus d’informations, consultez [Implémentation de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md). |
| mbox.js | Avant la version [!DNL Target]16.3.1 (mars 2016), [!DNL Target] devait appeler mbox.js pour créer la mbox globale nécessaire pour que [!DNL Target] puisse assurer les activités, suivre les clics ainsi que la plupart des mesures de succès. Ce fichier contient les bibliothèques nécessaires pour toutes vos activités. Vous n’avez ainsi pas à conserver différentes versions spécifiques à une activité du fichier.<br>Si vos pages contiennent déjà des mbox d’encapsulation issues d’un ancien style de mise en œuvre de [!DNL Target], vous pouvez continuer à les utiliser dans la nouvelle interface. Le fichier mbox.js mis à jour reste requis ; toutefois, il est possible de sélectionner ces mbox pour des activités et de les modifier à l’aide du compositeur d’expérience visuelle.<br>[!DNL Target] Standard et Target Premium mettent à jour et complètent mbox.js avec une référence à un fichier target.js. Ce fichier target.js est hébergé par Adobe. Il permet de modifier le contenu sur n’importe quelle page à l’aide du compositeur d’expérience visuelle, et ce même si la page ne contient pas de mbox prédéfinies. Vous devez référencer ce fichier sur chaque page de votre site.<br>Pour plus d’informations, consultez [Implémentation de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md).<br>**Important** : la bibliothèque mbox.js est toujours prise en charge, mais ses fonctionnalités ne seront plus mises à jour. Tous les clients doivent migrer vers at.js. Pour plus d’informations, voir [Migration vers at.js à partir de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md)<br> |

## Impact d’at.js et de mbox.js sur le délai de chargement des pages {#section_16630CD0FF0A498EB596A51381366A5A}

Bon nombre de clients et de consultants souhaitent connaître l’impact d’[!DNL at.js] et de [!DNL mbox.js] sur le délai de chargement des pages, particulièrement en ce qui concerne les nouveaux utilisateurs et les utilisateurs réguliers. Il est, malheureusement, difficile de mesurer l’influence d’[!DNL at.js] ou de [!DNL mbox.js] sur le délai de chargement des pages et d’avancer des chiffres concrets en raison de l’implémentation de chaque client.

Toutefois, si l’API visiteur est présente sur la page, nous pouvons mieux comprendre comment [!DNL at.js] et [!DNL mbox.js] influencent le délai de chargement des pages.

>[!NOTE]
>
>L’API visiteur et [!DNL at.js] ou [!DNL mbox.js] ont un impact sur le délai de chargement des pages uniquement lorsque vous utilisez la mbox globale (en raison de la technique de masquage du corps). Les mboxes régionales ne sont pas impactées par l’intégration de l’API visiteur.

Les sections suivantes décrivent la séquence d’actions pour les nouveaux visiteurs et les visiteurs récurrents :

### Nouveaux visiteurs

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js / mbox.js est chargé, analysé, puis exécuté.
1. Si la fonction de création automatique de mbox globale est activée, la bibliothèque JavaScript de Target :

   * instancie l’objet visiteur ;
   * la bibliothèque Target tente de récupérer les données de l’identifiant visiteur Experience Cloud ;
   * vu qu’il s’agit d’un nouveau visiteur, l’API visiteur déclenche une requête inter-domaines sur demdex.net.
   * Une fois les données de l’identifiant de visiteur Experience Cloud récupérée, une requête est déclenchée sur Target.

### Visiteurs récurrents

1. L’API visiteur est chargée, analysée et exécutée.
1. at.js / mbox.js est chargé, analysé, puis exécuté.
1. Si la fonction de création automatique de mbox globale est activée, la bibliothèque JavaScript de Target :

   * instancie l’objet visiteur ;
   * la bibliothèque Target tente de récupérer les données de l’identifiant visiteur Experience Cloud ;
   * l’API visiteur récupère les données du cookies ;
   * Une fois les données de l’identifiant de visiteur Experience Cloud récupérée, une requête est déclenchée sur Target.

>[!NOTE]
>
>Pour les nouveaux visiteurs, si l’API visiteur est présente, Target doit se connecter plusieurs fois pour s’assurer que les requêtes Target contiennent les données de l’identifiant de visiteur Experience Cloud. Pour les visiteurs réguliers, Target se connecte uniquement pour récupérer le contenu personnalisé.
