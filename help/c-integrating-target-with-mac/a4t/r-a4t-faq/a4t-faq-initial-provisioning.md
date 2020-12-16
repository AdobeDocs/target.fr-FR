---
keywords: faq;frequently asked questions;analytics for target;a4t;provisioning;provisioning;adobe Experience Cloud
description: Cette rubrique contient des réponses aux questions fréquentes sur la configuration d’Analytics comme source des rapports pour Target (A4T).
title: FAQ sur la configuration initiale - A4T
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 100%

---


# FAQ sur la configuration initiale - A4T{#initial-provisioning-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur la configuration d’Analytics comme source des rapports pour Target (A4T).

## Comment configurer une activité A4T multi-page ?

Pour implémenter un cas d’utilisation A4T multipage de base :

* Implémentez les bibliothèques JavaScript pour Target (at.js ou mbox.js) et pour Analytics sur l’URL ou la page d’accueil de l’activité. Implémenter les deux solutions regroupe les données Target avec les données Analytics pour chaque visiteur. Ces données restent dans Analytics jusqu’à ce qu’elles expirent. Le délai d’expiration est défini par défaut sur 90 jours.

* Pour les autres pages du site, où seules les mesures Analytics doivent faire l’objet d’un suivi, implémentez Analytics sur ces pages. Il n’est pas nécessaire d’implémenter Target sur ces pages. Les mesures Analytics capturées sur ces pages sont automatiquement associées à l’activité Target initialement qualifiée par l’utilisateur, en fonction des informations Target associées à ce visiteur à partir de l’étape précédente.

## Comment puis-je déterminer si A4T est activé dans mon compte Target ?{#section_4437D284448F4313BF953D4B6EDBACA6}

Pour qu’une suite de rapports puisse être sélectionnée lors de la définition d’une activité Analytics, vous avez besoin d’un compte utilisateur Analytics et, également, d’un compte utilisateur Target. Les comptes d’utilisateur doivent être configurés comme décrit dans la documentation. Voir [Exigences d’autorisation des utilisateurs](/help/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

Une fois que vous appartenez à un ou plusieurs groupes Experience Cloud ayant accès à Analytics et Target et que vous avez accès à toutes les suites de rapports, vous devez voir l’option permettant de créer un test A/B à l’aide d’Analytics sous **[!UICONTROL Créer l’activité]**.

Si des problèmes de mise en service se produisent, vérifiez que A4T a été configuré correctement.

## Pourquoi mes suites de rapports ne se chargent-elles pas ? {#section_6CC8B2B3568A46C499895EB9811FDC2E}

Vérifiez les éléments suivants si l’un de ces problèmes survient :

* Assurez-vous que vos comptes Analytics et Target sont liés dans Experience Cloud.
* Si vous utilisez plusieurs identifiants de société Analytics pour la même société Experience Cloud, assurez-vous que la dernière société Analytics à laquelle vous vous êtes connecté est celle qui est liée au compte Target pour l’intégration.
* Si vous êtes connecté à Experience Cloud depuis plusieurs heures, il arrive que la session Analytics expire. Déconnectez-vous puis connectez-vous à nouveau pour réessayer.

## Pourquoi les options Analytics ne s’affichent-elles pas dans Target ?  {#section_EDD996AFB08B4DB196DD934BE55BF48D}

Voir « Pourquoi mes suites de rapports ne se chargent-elles pas ? » ci-dessus. La cause à l’origine de ce problème est la même.

## Pourquoi les rapports A4T ne sont-ils pas visibles dans Analytics ?  {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

Voir « Pourquoi mes suites de rapports ne se chargent-elles pas ? » ci-dessus. La cause à l’origine de ce problème est la même.

## Pourquoi mes rapports dans Target sont-ils vides ?  {#section_3837104757464CB488C5A83014A669A1}

Voir « Pourquoi mes suites de rapports ne se chargent-elles pas ? » ci-dessus. La cause à l’origine de ce problème est la même.
