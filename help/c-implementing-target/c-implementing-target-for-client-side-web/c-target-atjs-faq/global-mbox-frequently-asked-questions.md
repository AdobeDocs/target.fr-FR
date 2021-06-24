---
keywords: dépannage;questions fréquentes;FAQ;forum aux questions;globale;mbox globale
description: 'Lisez les questions fréquentes et les réponses sur les mbox globales d’Adobe. [!DNL Target] '
title: Questions fréquentes à propos de la mbox globale
feature: at.js
role: Developer
exl-id: ec8399df-5222-44bd-9e61-dfce8fd1694d
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 81%

---

# Questions fréquentes relatives aux mbox globales

Liste des questions fréquentes (FAQ) relatives aux mbox globales.

## Puis-je avoir plusieurs mbox globales si mon compte [!DNL Target] est défini sur plusieurs domaines ? {#section_B7252BA6C3BB4EF4AE9E53F47FD58ABD}

Une seule mbox globale est prise en charge pour l’ensemble du compte.

Vous pouvez limiter l’exécution des activités en ajoutant des règles d’URL à ces dernières. Pour plus d’informations, voir [Inclure la même expérience sur des pages similaires](/help/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Vous pouvez également transmettre un paramètre sur la page à l’aide de [targetPageParams](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md), puis sélectionner ces paramètres dans la section « Configurer l’URL » du [!UICONTROL Compositeur d’expérience visuelle] (VEC) ou en ajoutant les paramètres comme « ajustements » dans le compositeur d’expérience basé sur les formulaires.

## Comment puis-je transmettre des données de recettes à une mbox globale [!DNL Target] ? {#section_17AEA933BADA4D169CCEDF5833C41306}

Pour collecter des informations sur les recettes et les commandes dans la mbox target-global-mbox, les « paramètres de mbox » doivent être envoyés à Target. Ces paramètres sont des paires de nom/valeur utilisées pour envoyer des informations supplémentaires à Target. Target recherche automatiquement ces paramètres (noms réservés) pour renseigner les données de recettes.

Pour le `orderConfirmPage`, vous devez passez en `orderTotal`, `orderId` et `productPurchasedId`.

Ces paramètres doivent être envoyés à target-global-mbox via `targetPageParams()`. Pour plus d’informations, voir [Transfert de paramètres à une mbox globale](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).

Vous souhaiterez également ajouter le ciblage à la fonction de conversion afin que Target décompte les conversions de la mbox target-global-mbox seulement lorsque la page de confirmation de la commande s’affiche, comme illustré ci-dessous :

![](assets/revenue1.png)

La section Pages du site illustrée ci-dessus comporte les sélections suivantes : Page actuelle, URL, contient, orderconfirm.

![](assets/revenue2.png)

Les options de l’illustration ci-dessus incluent les paramètres suivants :

* **Que souhaitez-vous mesurer avec cette activité ? :** Recettes
* **Affichage par défaut pour les rapports :** Recettes par visiteur (RPV)
* **Quelle action a été entreprise par votre audience pour indiquer que votre objectif a été atteint ?** A affiché une mbox, target-global-mbox
