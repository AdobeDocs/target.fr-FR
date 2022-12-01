---
keywords: faq;questions fréquentes;analytics for target;a4t;provisionnement;provisionnement;Adobe Experience Cloud
description: Trouver des réponses aux questions fréquentes sur la configuration d’Analytics pour [!DNL Target] (A4T), qui vous permet d’utiliser les rapports Analytics pour [!DNL Target] activités.
title: Où puis-je trouver des informations sur la configuration initiale d’A4T ?
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 47%

---

# FAQ sur l&#39;approvisionnement initial - A4T

Cette rubrique contient des réponses aux questions fréquentes sur la configuration. [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

## Comment configurer une activité A4T multi-page ?

+++Réponse Pour mettre en oeuvre un cas d’utilisation A4T multipage de base :

* Implémentez les bibliothèques JavaScript pour Target et Analytics sur l’URL/la page d’entrée de l’activité. Implémenter les deux solutions regroupe les données Target avec les données Analytics pour chaque visiteur. Ces données restent dans Analytics jusqu’à ce qu’elles expirent. Le délai d’expiration est défini par défaut sur 90 jours.

* Pour les autres pages du site, où seules les mesures Analytics doivent faire l’objet d’un suivi, implémentez Analytics sur ces pages. Il n’est pas nécessaire d’implémenter Target sur ces pages. Les mesures Analytics capturées sur ces pages sont automatiquement associées à l’activité Target initialement qualifiée par l’utilisateur, en fonction des informations Target associées à ce visiteur à partir de l’étape précédente.

+++

## Comment puis-je savoir si A4T est activé sur mon [!DNL Target] compte ? {#section_4437D284448F4313BF953D4B6EDBACA6}

+++Réponse Avant de pouvoir sélectionner une suite de rapports lors de la définition d’une activité Analytics, vous avez besoin d’un compte utilisateur Analytics et d’un compte utilisateur Target. Les comptes d’utilisateur doivent être configurés comme décrit dans la documentation. Voir [Exigences d’autorisation des utilisateurs](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

Une fois que vous appartenez à un ou plusieurs groupes d’Experience Cloud ayant accès à Analytics et Target et que vous avez accès à toutes les suites de rapports, l’option permettant de créer un test A/B à l’aide d’Analytics sous **[!UICONTROL Création d’une activité]**.

Si des problèmes de mise en service se produisent, vérifiez que A4T a été configuré correctement.

+++

## Pourquoi mes suites de rapports ne se chargent-elles pas ? {#section_6CC8B2B3568A46C499895EB9811FDC2E}

+++Réponse Vérifiez les points suivants si l’un de ces problèmes se produit :

* Assurez-vous que vos comptes Analytics et Target sont liés dans l’Experience Cloud.
* Certains clients utilisent plusieurs identifiants de société Analytics dans la même société Experience Cloud. Si vous utilisez plusieurs connexions, assurez-vous que la dernière société Analytics à laquelle vous vous êtes connecté est celle qui est liée au compte Target pour l’intégration.
* Si vous êtes connecté à Experience Cloud depuis plusieurs heures, il arrive que la session Analytics expire. Déconnectez-vous puis connectez-vous à nouveau pour réessayer.

+++

## Pourquoi les options Analytics ne s’affichent-elles pas dans Target ? {#section_EDD996AFB08B4DB196DD934BE55BF48D}

+++Réponse Voir &quot;Pourquoi mes suites de rapports ne se chargent-elles pas ?&quot; Au-dessus. La cause à l’origine de ce problème est la même.

+++

## Pourquoi les rapports A4T ne sont-ils pas visibles dans Analytics ? {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

+++Réponse Voir &quot;Pourquoi mes suites de rapports ne se chargent-elles pas ?&quot; ci-dessus. La cause à l’origine de ce problème est la même.

+++

## Pourquoi mes rapports sont-ils dans [!DNL Target] vide ? {#section_3837104757464CB488C5A83014A669A1}

+++Réponse Voir &quot;Pourquoi mes suites de rapports ne se chargent-elles pas ?&quot; ci-dessus. La cause à l’origine de ce problème est la même.

+++
