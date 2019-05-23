---
description: Cette rubrique contient des réponses aux questions fréquentes sur la configuration d’Analytics comme source des rapports pour Target (A4T).
keywords: faq;questions fréquentes;analytics for target;a4t;provisionnement;provisionnement;Adobe Experience Cloud
seo-description: Cette rubrique contient des réponses aux questions fréquentes sur la configuration d’Analytics comme source des rapports pour Target (A4T).
seo-title: FAQ sur la configuration initiale - A4T
solution: Target
title: FAQ sur la configuration initiale - A4T
topic: Standard
uuid: cc80f879-ad2a-46d6-adc2-df616e8ab0b5
translation-type: tm+mt
source-git-commit: 0b4858e203c67bca85c9646e74df1111b6b5c934

---


# FAQ sur la configuration initiale - A4T{#initial-provisioning-a-t-faq}

Cette rubrique contient des réponses aux questions fréquentes sur la configuration d’Analytics comme source des rapports pour Target (A4T).

## Comment configurer une activité A 4 T multi-page ?

Pour mettre en œuvre un cas d&#39;utilisation A 4 T de base multi-page :

* Implémentez les bibliothèques JavaScript pour Target (at. js ou mbox. js) et Analytics sur l&#39;URL ou la page d&#39;accueil de l&#39;activité. Implémentation des deux solutions regroupe les données Target avec les données Analytics pour chaque visiteur. Ces données restent dans Analytics jusqu&#39;à ce qu&#39;elles expirent avec l&#39;expiration par défaut définie sur 90 jours.

* Pour les autres pages du site, où seules les mesures Analytics doivent faire l&#39;objet d&#39;un suivi, implémentez Analytics sur ces pages. Il n&#39;est pas nécessaire d&#39;implémenter Target sur ces pages. Les mesures Analytics capturées sur ces pages sont automatiquement associées à l&#39;activité Target de l&#39;utilisateur initialement qualifié pour, en fonction des informations Target associées à ce visiteur à partir de la puce précédente.

## Comment puis-je déterminer si A4T est activé dans mon compte Target ?{#section_4437D284448F4313BF953D4B6EDBACA6}

Pour qu’une suite de rapports puisse être sélectionnée lors de la définition d’une activité Analytics, vous avez besoin d’un compte utilisateur Analytics et, également, d’un compte utilisateur Target. Les comptes d’utilisateur doivent être configurés comme décrit dans la documentation. Voir [Exigences d’autorisation des utilisateurs](../../../c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083).

Une fois que vous appartenez à un ou plusieurs groupes Experience Cloud ayant accès à Analytics et Target et que vous avez accès à toutes les suites de rapports, vous devez voir l’option permettant de créer un test A/B à l’aide d’Analytics sous **[!UICONTROL Créer l’activité]**.

Si des problèmes de mise en service se produisent, vérifiez que A4T a été configuré correctement.

## Pourquoi mes suites de rapports ne se chargent-elles pas ?  {#section_6CC8B2B3568A46C499895EB9811FDC2E}

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
