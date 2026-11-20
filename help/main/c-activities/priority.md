---
keywords: paramètres, priorité
description: Découvrez comment [!DNL Adobe Target] détermine différemment la ou les activités à diffuser sur une page en fonction de l’interface [!DNL Target] et de la fonction de création d’activité que vous utilisez.
title: Comment [!DNL Target] Attribue-T-Il La Priorité À Différentes Activités ?
feature: Activities
exl-id: c32f1699-e564-40dd-8ff1-7c75a672c6ef
TQID: 'https://experienceleague.adobe.com/KSkJ1CDkd4hgwnLQ1RKn8l8r2MDIO-6flcHcdN0c0oQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '1043'
ht-degree: 22%
---
# Priorité {#priority}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez comment [!DNL Adobe Target] décide des activités à diffuser sur une page, en fonction du compositeur d’expérience et du type de requête [!DNL Target] utilisée.

>[!ENDSHADEBOX]

[!DNL Adobe Target] détermine quelle activité (ou quelles activités) diffuser sur une page différemment selon l’interface [!DNL Target] et la fonction de création d’activité ([**[!UICONTROL Compositeur d’expérience visuelle (VEC)]**](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) ou [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md)) que vous utilisez. Le tableau suivant résume les trois cas, qui sont détaillés dans les sections ci-dessous.

| Scénario | Activités pouvant fournir | Contenu renvoyé |
|---|---|---|
| **[!UICONTROL Compositeur d’expérience visuelle]** uniquement ou **[!UICONTROL Compositeur d’expérience d’après les formulaires]** avec une requête globale [!DNL Target] uniquement | Multiple | Contenu de toutes les activités correspondantes. Si les sélecteurs se chevauchent, le contenu de l’activité la plus prioritaire s’affiche. |
| **[!UICONTROL Compositeur d’expérience d’après les formulaires]** et **[!UICONTROL Compositeur d’expérience visuelle]** | Multiple | Si une activité basée sur des formulaires a la priorité la plus élevée, son contenu et le contenu de toutes les activités du compositeur d’expérience visuelle correspondantes. Si une activité du compositeur d’expérience visuelle a la priorité la plus élevée, le contenu de toutes les activités du compositeur d’expérience visuelle correspondantes uniquement. |
| **[!UICONTROL Compositeur d’expérience d’après les formulaires]** avec des requêtes [!DNL Target] non globales | Un par appel | Contenu de l’activité de correspondance la plus prioritaire. |

## VEC ou [!UICONTROL compositeur d’expérience d’après les formulaires] avec une requête globale {#section_4A0A317DFED345649B58B0CB5B410C8B}

Si votre société utilise exclusivement le compositeur d’expérience visuelle, le contenu de plusieurs activités peut être renvoyé pour le même appel. Les activités sont diffusées en suivant le flux décisionnel suivant :

1. L&#39;appel au serveur [!DNL Target] atteint [!DNL Target]. L’appel contient des informations sur l’URL de la page demandée.
1. [!DNL Target] extrait chaque activité exécutée sur cette URL. Ces activités sont les candidates pour la diffusion.
1. [!DNL Target] tente de faire correspondre le visiteur aux activités candidates.

   {{visitor-matching}}

1. Le contenu de toutes les activités et expériences auxquelles le visiteur correspond est renvoyé à la page, de sorte que le contenu de plusieurs activités puisse être diffusé pour le même appel.
1. [!DNL Target] compare les [sélecteurs CSS](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md) auxquels le contenu de chaque activité fait référence. Si les activités font référence à différents sélecteurs, tout le contenu s’affiche.
1. Si un sélecteur se chevauche ou est dupliqué, le contenu de l’activité dont la priorité est la plus élevée s’affiche.

   >[!IMPORTANT]
   >
   >[!DNL Target] renvoie le contenu de toutes les activités de la page, en commençant par le contenu dont la priorité est la plus faible, qui est ensuite remplacé par chaque activité, de la plus faible à la plus élevée. En règle générale, le contenu le plus prioritaire s’affiche. Cependant, si une activité de priorité inférieure modifie la structure du DOM pour la page, l’activité de priorité supérieure peut ne pas reconnaître la structure de la page. Par conséquent, le contenu de priorité inférieure s’affiche.

1. Si plusieurs activités partagent le même niveau de priorité, un coupe-file s’applique. Si une seule des activités cible une audience, cette activité s’affiche. Si toutes les activités, ou aucune, ne comporte de ciblage, l’activité qui a été approuvée en premier s’affiche.
1. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

## [!UICONTROL Compositeur d’expérience d’après les formulaires] et VEC {#section_4620253E1CE942DD830724C7822B175F}

Si votre entreprise utilise le [!UICONTROL compositeur d’expérience d’après les formulaires] *et* le compositeur d’expérience visuelle, le contenu de plusieurs [!UICONTROL activités du compositeur d’expérience d’après les formulaires] et du compositeur d’expérience visuelle peut être diffusé. Auparavant, une seule activité du workflow basé sur les formulaires pouvait être diffusée. Il n’existe plus de limite au nombre d’activités basées sur les formulaires pouvant être diffusées.

La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. L&#39;appel au serveur [!DNL Target] atteint [!DNL Target]. L’appel contient des informations sur la requête [!DNL Target] et l’URL.
1. [!DNL Target] extrait chaque activité en cours d’exécution dans cette requête [!DNL Target]. Ces activités sont les candidates pour la diffusion.
1. [!DNL Target] tente de faire correspondre le visiteur aux activités candidates.

   {{visitor-matching}}

1. [!DNL Target] vérifie laquelle des activités correspondantes a la priorité la plus élevée et si cette activité a été créée dans le [!UICONTROL Compositeur d’expérience d’après les formulaires] ou dans le compositeur d’expérience visuelle.
1. Si une activité basée sur des formulaires a la priorité la plus élevée, son contenu est renvoyé avec le contenu de toutes les activités du compositeur d’expérience visuelle correspondantes.
1. Si une activité du compositeur d’expérience visuelle a la priorité la plus élevée, le contenu de toutes les activités du compositeur d’expérience visuelle correspondantes est renvoyé, mais aucun contenu d’activité basé sur des formulaires n’est renvoyé.
1. Les résultats de toutes les activités qui s’exécutent sur la page sont comptabilisés et reflétés dans les rapports.

**Exemple**

Deux activités existent : l’une cible le mot-clé de recherche de marque « Nike » et l’autre cible le mot-clé sans marque « baskets ». Les priorités des deux activités sont vérifiées. Si l’activité Nike a une priorité supérieure, son contenu s’affiche. Si l’activité portant sur les chaussures de sport sans marque a la priorité la plus élevée, son contenu s’affiche.

Si les deux activités ciblées ont la même priorité, l’activité qui a été consultée le plus récemment s’affiche. Si le visiteur est nouveau sur la page, l’activité qui a été activée le plus récemment s’affiche.

## [!UICONTROL Compositeur d’expérience d’après les formulaires] avec des requêtes non globales {#section_C3F5F09B0B2D4EF795C5929D5C426A8C}

Si votre entreprise utilise [!DNL Target] requêtes autres que la requête [!DNL Target] globale dans le compositeur basé sur les formulaires, le contenu d’une seule activité peut être renvoyé par appel. La diffusion des activités est déterminée selon le flux décisionnel suivant :

1. L&#39;appel au serveur [!DNL Target] atteint [!DNL Target]. L’appel contient des informations sur la requête [!DNL Target] et l’URL.
1. [!DNL Target] extrait chaque activité en cours d’exécution dans cette requête [!DNL Target]. Ces activités sont les candidates pour la diffusion.
1. [!DNL Target] tente de faire correspondre le visiteur à l’activité candidate ayant la priorité la plus élevée.

   {{visitor-matching}}

1. Si plusieurs activités partagent le même niveau de priorité, un coupe-file s’applique. Si une seule des activités cible une audience, cette activité s’affiche. Si toutes les activités, ou aucune, ne comporte de ciblage, l’activité qui a été approuvée en premier s’affiche.
1. Le contenu de cette seule activité est renvoyé à la page.

## Exemples {#section_F6A788AAC3884A2FA03E47F0557A1213}

>[!NOTE]
>
>Les valeurs de priorité varient en fonction de vos paramètres. Vous pouvez utiliser les paramètres hérités de **[!UICONTROL Faible]**, **[!UICONTROL Medium]** ou **[!UICONTROL Élevé]**, ou activer des priorités affinées de 0 à 999. Pour plus d&#39;informations, voir [Paramètres d&#39;activité](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC).

**Deux activités utilisent uniquement les offres créées dans le [!UICONTROL compositeur d’expérience visuelle] pour différents sélecteurs**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector2, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

**Deux activités utilisent uniquement les offres créées dans le [!UICONTROL compositeur d’expérience visuelle] pour le même sélecteur**

* Activité 1 : target-global-mbox, selector1, visualExpCompOffer1, priorité faible
* Activité 2 : target-global-mbox, selector1, visualExpCompOffer2, priorité haute

Réponse : visualExpCompOffer1, visualExpCompOffer2

## Vidéo de formation : Paramètres de l’activité (3:02)

Cette vidéo comporte des informations sur les paramètres d’activité.

* Spécifier un objectif pour votre activité
* Définir le niveau de priorité de vos activités
* Planifier les heures de début et de fin de l’activité
* Ajouter des audiences pour la création de rapport afin de créer des filtres de rapport
* Saisir des notes pour vos activités

>[!VIDEO](https://video.tv.adobe.com/v/3507945?captions=fre_fr)
