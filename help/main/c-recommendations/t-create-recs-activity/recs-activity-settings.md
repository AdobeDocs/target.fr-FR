---
keywords: recommandations;paramètres;nom;objectif;priorité;durée;paramètres de création de rapports;autres métadonnées
description: Découvrez comment configurer les paramètres utilisés pour décrire et contrôler une activité Recommendations dans Adobe Target.
title: Comment Configurer Les Paramètres D’Activité De Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
TQID: 'https://experienceleague.adobe.com/pfMAvl6MmLCtH3PZfOR4Ve-WFIc3e2iN2Bh-cIzjeC0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 13%
---
# Paramètres des activités Recommandations {#recs-activity-settings}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez les paramètres qui décrivent et contrôlent une activité [!DNL Recommendations] dans [!DNL Adobe Target].

>[!ENDSHADEBOX]

Les paramètres d&#39;activité identifient une activité [!DNL Recommendations], contrôlent quand et où elle s&#39;affiche et définissent la manière dont ses résultats sont signalés.

## Nom

Cliquez sur l’icône Plus d’actions (![Icône Plus d’actions](/help/main/assets/icons/MoreSmallListVert.svg) ), puis sur **[!UICONTROL Renommer]** pour donner à l’activité un nom explicite qui permet de l’identifier.

Les caractères suivants ne sont pas autorisés dans un nom d’activité : `/`, `?`, `#`, `:`, `=`, `+`, `-` et `@`.

Si le nom d’une activité [!DNL Recommendations] existe déjà pour une autre activité dans [!UICONTROL Recommendations Classic], la nouvelle activité est resynchronisée avec un nouveau nom. Le nouveau nom est le nom d’origine avec un horodatage ajouté, pour le rendre unique. Elle s’affiche à la fois dans [!DNL Target Standard/Premium] et [!UICONTROL Recommendations Classic].

## Intention

(Facultatif) Décrivez l’objectif de l’activité.

## Priorité

Réglez le curseur pour définir le niveau de priorité.

La priorité est utilisée lorsque plusieurs activités sont affectées au même emplacement avec la même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche.

## Durée

Définissez la durée de l’activité.

L’activité peut commencer lorsqu’elle est activée ou à une date et une heure spécifiques. De même, elle peut se terminer lorsqu’elle est désactivée, ou à une date et une heure spécifiques.

Le sélecteur d’heures utilise une horloge de 24 heures, où 00:00 correspond à minuit. Le fuseau horaire est celui configuré dans le navigateur. Pour utiliser un fuseau horaire différent, définissez le navigateur sur ce fuseau horaire et redémarrez le navigateur.

## Paramètres de création de rapports

Les paramètres suivants définissent la manière dont les résultats de l’activité sont signalés.

* **[!UICONTROL Reporting Source]:** Spécifie la solution à partir de laquelle les données sont collectées : [!DNL Adobe Target], [!DNL Adobe Analytics] ou [!DNL Adobe Customer Journey Analytics].

  Si une solution de création de rapports est spécifiée dans les [paramètres du compte](/help/main/administrating-target/reporting.md), cette solution est utilisée et ce paramètre n&#39;est pas visible. La source de création de rapports ne peut pas être modifiée une fois l’activité activée, pour que les rapports restent cohérents.

  **[!DNL Adobe Analytics]** : consultez [[!DNL Adobe Analytics]  comme source de création de rapports pour  [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) pour connaître les différences entre les solutions de création de rapports et les avantages de chacune d’elles. Pour la sélection de la suite de rapports [!DNL Analytics] et du serveur de suivi, consultez [Reporting Source](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source).

  **[!DNL Adobe Customer Journey Analytics]** : voir la section [[!DNL Target] reporting dans [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) pour plus d’informations sur l’intégration entre [!DNL Adobe Customer Journey Analytics] et [!DNL Target].

* **[!UICONTROL Mesure d’objectif]:** sélectionne la mesure de succès qui détermine si l’activité a réussi.
* **[!UICONTROL Mesures supplémentaires] :** configure des mesures de succès supplémentaires pour les rapports.
* **[!UICONTROL Audiences pour le reporting] :** définit les audiences qui peuvent être utilisées pour filtrer les rapports.

## Autres métadonnées

Saisissez les notes relatives à l’activité.

## Vidéo de formation : paramètres d’activité (3:02) ![Badge du tutoriel](/help/main/assets/tutorial.png)

Cette vidéo couvre les paramètres d’activité suivants :

* Saisissez un objectif pour l’activité.
* Définissez le niveau de priorité de l’activité.
* Planifiez les heures de début et de fin.
* Ajoutez des audiences pour la création de rapports afin de créer des filtres de rapport.
* Saisissez les notes de l’activité.

>[!VIDEO](https://video.tv.adobe.com/v/3507945?captions=fre_fr)
