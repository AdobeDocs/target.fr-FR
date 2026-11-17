---
keywords: ciblage automatique;ciblage;affectation de trafic;questions fréquentes;faq;résolution de problèmes;dépannage;trafic
description: Consultez les rubriques de dépannage et les questions fréquentes sur les activités de [!UICONTROL ciblage automatique].
title: Comment Résoudre Les Problèmes Liés Aux Activités De [!UICONTROL Ciblage Automatique] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
TQID: 'https://experienceleague.adobe.com/LXOa1Ma0y8VbncCPN1Az33p-GDsd-bW-BDqJjSGbVQU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '1841'
ht-degree: 10%
---
# [!UICONTROL FAQ et dépannage du ciblage automatique] {#auto-target-faqs}

>[!BEGINSHADEBOX]

**Sur cette page :** Trouvez des réponses aux questions fréquentes sur les activités de **[!UICONTROL ciblage automatique]** et des solutions suggérées aux problèmes courants.

>[!ENDSHADEBOX]

Cette page répond aux questions fréquentes et décrit les étapes de dépannage pour les activités de **[!UICONTROL ciblage automatique]** dans [!DNL Adobe Target].

## Questions fréquentes {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consultez les questions et réponses suivantes lorsque vous utilisez des activités de **[!UICONTROL ciblage automatique]**.

+++ Quelles sont les bonnes pratiques pour configurer une activité de [!UICONTROL ciblage automatique] ?

* Décidez si la valeur commerciale d’une mesure de succès **[!UICONTROL Chiffre d’affaires par visite]** (RPV) vaut les exigences de trafic supplémentaires. Pour qu’une activité fonctionne, RPV nécessite généralement au moins 1 000 conversions par expérience, par rapport aux conversions.
* Déterminez l’affectation entre les expériences de contrôle et personnalisées avant de commencer l’activité, en fonction de vos objectifs.
* Déterminez si vous disposez d’un trafic suffisant vers la page sur laquelle s’exécute votre activité de **[!UICONTROL ciblage automatique]** pour que les modèles de personnalisation soient créés dans un délai raisonnable.
* Si vous testez l’algorithme de personnalisation, ne modifiez pas les expériences ou n’ajoutez pas ou ne supprimez pas les attributs de profil lorsque l’activité est active.
* Envisagez d’effectuer une activité A/B entre les offres et les emplacements que vous prévoyez d’utiliser dans votre activité de **[!UICONTROL ciblage automatique]**, afin de vous assurer que les emplacements et les offres ont un impact sur l’objectif d’optimisation. Si une activité A/B ne parvient pas à démontrer une différence significative, le **[!UICONTROL ciblage automatique]** ne parvient probablement pas non plus à générer l’effet élévateur.

  Si un test A/B ne montre aucune différence statistiquement significative entre les expériences, il est probable que les offres que vous considérez ne soient pas suffisamment différentes les unes des autres, que les emplacements que vous avez sélectionnés n’aient pas d’incidence sur la mesure de succès ou que l’objectif d’optimisation soit trop loin dans le funnel de conversion pour être affecté par vos offres sélectionnées.

* N’apportez pas de modifications substantielles aux expériences au cours de l’activité.

+++

+++ Adobe recommande-t-il d’utiliser le ciblage automatique avec une répartition de 90 (contrôle)/10 (ciblé) jusqu’à ce que les modèles soient créés ?

La répartition optimale de l’affectation du trafic dépend de ce que vous souhaitez accomplir.

Si votre objectif est de personnaliser le plus de trafic possible, vous pouvez conserver une affectation ciblée de 90 % et un contrôle de 10 % pendant la durée de vie de l’activité. Si votre objectif est d’exécuter une expérience qui compare les performances des algorithmes de personnalisation par rapport au contrôle, une répartition 50/50 est préférable pour la durée de vie de l’activité.

La bonne pratique consiste à maintenir la répartition de l’affectation du trafic pendant toute la durée de vie de l’activité, de sorte que les visiteurs ne basculent pas entre les expériences ciblées et les expériences de contrôle.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There is no way to go back and see when a model was completed.
-->

+++

+++ Si un visiteur ne voit pas l’activité de [!UICONTROL ciblage automatique] et effectue une conversion, celle-ci est-elle prise en compte dans mon activité ?

Non. Seuls les visiteurs éligibles ayant visualisé l’activité de **[!UICONTROL ciblage automatique]** sont comptabilisés dans les rapports.

+++

+++ Pourquoi mon activité de [!UICONTROL ciblage automatique] ne génère-t-elle aucun effet élévateur ?

Pour connaître les quatre facteurs requis pour générer un effet élévateur et la solution suggérée, consultez l’élément de dépannage [Mon activité de ciblage automatique ne génère aucun effet élévateur](#section_23995AB813F24525AF294D20A20875C8).

+++

+++ Quand dois-je arrêter mon activité de [!UICONTROL ciblage automatique] ?

Le **[!UICONTROL ciblage automatique]** peut être utilisé comme une personnalisation « toujours active » qui s’optimise en permanence. Dans le cas des contenus sans cesse renouvelés, notamment, il n’est pas nécessaire d’arrêter votre activité de **[!UICONTROL ciblage automatique]**.

Si vous souhaitez apporter des modifications substantielles au contenu de votre activité de **[!UICONTROL ciblage automatique]**, la bonne pratique consiste à démarrer une nouvelle activité, afin que les autres utilisateurs qui examinent les rapports n’en confondent pas les résultats, ou ne les associent pas à d’anciens résultats portant sur des contenus différents.

+++

+++ Combien de temps dois-je attendre la compilation des modèles ?

Le temps nécessaire aux modèles pour créer votre activité de **[!UICONTROL ciblage automatique]** dépend généralement du trafic vers les emplacements d’activité sélectionnés et des taux de conversion associés à la mesure de succès de votre activité.

Le **[!UICONTROL ciblage automatique]** ne tente pas de créer un modèle personnalisé pour une expérience donnée tant qu’il n’y a pas au moins 50 conversions pour cette expérience. En outre, si la qualité du modèle créé est insuffisante (comme déterminé par l’évaluation hors ligne sur des données de « test » retenues, à l’aide de [une mesure appelée AUC](https://fr.wikipedia.org/wiki/Courbe_ROC)), le modèle n’est pas utilisé pour diffuser le trafic de manière personnalisée.

Gardez à l’esprit les points suivants concernant la création de modèles dans le **[!UICONTROL ciblage automatique]** :

* Une fois qu’une activité est active, le **[!UICONTROL ciblage automatique]** prend en compte les 45 derniers jours de données diffusées de manière aléatoire lorsqu’il tente de créer des modèles. Par exemple, le trafic de contrôle, ainsi que certaines données supplémentaires diffusées de manière aléatoire et retenues par l’algorithme.
* Lorsque **[!UICONTROL Chiffre d’affaires par visite]** est votre mesure de succès, ces activités nécessitent généralement plus de données pour créer des modèles, car l’écart dans le chiffre d’affaires des visites est généralement plus élevé que dans le taux de conversion.
* Les modèles sont créés sur la base de chaque expérience. Par conséquent, le remplacement d’une expérience par une autre signifie que vous devez collecter suffisamment de trafic (au moins 50 conversions) pour la nouvelle expérience avant de pouvoir recréer les modèles personnalisés.

Si la création de vos modèles prend trop de temps, consultez [Mon activité de ciblage automatique prend trop de temps pour créer des modèles](#section_23995AB813F24525AF294D20A20875C8).

+++

+++ Un modèle est créé dans mon activité. Les visites de cette expérience sont-elles personnalisées ?

Non. Au moins deux modèles doivent être créés dans votre activité pour que la personnalisation puisse commencer.

+++

+++ Quand puis-je commencer à consulter les résultats de mon activité de [!UICONTROL ciblage automatique] ?

Vous pouvez commencer à consulter les résultats de votre activité de **[!UICONTROL ciblage automatique]** après la création de modèles pour au moins deux expériences (coche verte).

+++

+++ Puis-je spécifier une expérience spécifique à utiliser comme contrôle ?

Vous pouvez sélectionner une expérience à utiliser comme contrôle lors de la création d’une activité de [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Cette fonctionnalité vous permet d’acheminer l’ensemble du trafic de contrôle vers une expérience spécifique, en fonction du pourcentage d’affectation du trafic configuré dans l’activité. Vous pouvez ensuite évaluer les rapports de performances du trafic personnalisé par rapport au trafic de contrôle sur cette expérience.

Pour plus d’informations, voir [Utilisation d’une expérience spécifique comme contrôle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

+++ Puis-je modifier la mesure d’objectif au cours d’une activité de [!UICONTROL ciblage automatique] ?

Adobe ne recommande pas de modifier la mesure d’objectif au cours d’une activité. Bien qu’il soit possible de modifier la mesure d’objectif au cours d’une activité à l’aide de l’interface utilisateur de [!DNL Target], vous devez toujours démarrer une nouvelle activité. Adobe ne garantit pas ce qui se produit si vous modifiez la mesure d’objectif dans une activité après son exécution.

Cette recommandation s’applique aux activités d’**[!UICONTROL affectation automatique]**, de **[!UICONTROL ciblage automatique]** et d’**[!UICONTROL Automated Personalization]** qui utilisent [!DNL Target] ou [!DNL Analytics] (A4T) comme source de création de rapports.

+++

+++ Puis-je utiliser l’option [!UICONTROL Réinitialiser les données du rapport] lors de l’exécution d’une activité de [!UICONTROL ciblage automatique] ?

L’utilisation de l’option **[!UICONTROL Réinitialiser les données du rapport]** pour les activités de **[!UICONTROL ciblage automatique]** n’est pas recommandée. Bien qu’elle supprime les données de rapports visibles, cette option ne supprime pas tous les enregistrements d’identification du modèle de **[!UICONTROL ciblage automatique]**. Au lieu d’utiliser l’option **[!UICONTROL Réinitialiser les données du rapport]**, créez une activité et désactivez l’activité d’origine.

Ces conseils s’appliquent également aux activités d’**[!UICONTROL affectation automatique]** et d’**[!UICONTROL Automated Personalization]**.

+++

+++ Que se passe-t-il si je supprime une expérience unique d’une activité de [!UICONTROL ciblage automatique] ?

[!DNL Target] crée un modèle par expérience. La suppression d’une expérience signifie donc que [!DNL Target] crée un modèle de moins et n’affecte pas les modèles des autres expériences.

Supposons, par exemple, que vous ayez une activité de **[!UICONTROL ciblage automatique]** avec huit expériences et que vous ne soyez pas satisfait des performances d’une expérience. Vous pouvez supprimer cette expérience sans affecter les modèles des sept expériences restantes.

+++

## Dépannage Du [!UICONTROL Ciblage Automatique] {#section_23995AB813F24525AF294D20A20875C8}

Parfois, les activités ne se déroulent pas comme prévu. Les éléments suivants décrivent les défis potentiels auxquels vous pourriez être confronté lors de l’utilisation du **[!UICONTROL ciblage automatique]**, avec les solutions suggérées.

+++ Mon activité de [!UICONTROL ciblage automatique] prend trop de temps pour créer des modèles.

Plusieurs modifications de la configuration de l’activité peuvent réduire le temps prévu pour créer des modèles, notamment le nombre d’expériences dans votre activité de **[!UICONTROL ciblage automatique]**, le trafic sur votre site et votre mesure de succès sélectionnée.

**Solution :** Vérifiez la configuration de votre activité et voyez si vous êtes prêt à apporter des modifications pour accélérer la création des modèles.

* Si votre mesure de succès est définie sur **[!UICONTROL RPV]**, pouvez-vous passer à la conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdez pas de données d’activité si vous modifiez la mesure de succès de RPV à conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité inférieur augmente les exigences de trafic pour la création des modèles, car un nombre minimum de conversions est requis.
* Y a-t-il des expériences que vous pouvez supprimer de votre activité ? La réduction du nombre d’expériences dans une activité réduit le temps de création de modèles.
* Existe-t-il une page à trafic élevé sur laquelle cette activité serait plus efficace ? Plus il y a de trafic et de conversions dans les emplacements de vos activités, plus les modèles se créent rapidement.

Pour plus d&#39;informations sur le temps dont les modèles ont besoin, voir [Combien de temps dois-je attendre la génération des modèles ?](#section_5C120A2B11D14D9BAF767BBAB50FED23).

+++

+++ Mon activité de [!UICONTROL ciblage automatique] ne génère aucun effet élévateur.

Quatre facteurs sont requis pour qu’une activité de **[!UICONTROL ciblage automatique]** génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées à un emplacement qui fait la différence par rapport à l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** tout d’abord, assurez-vous que votre activité personnalise le trafic. Si des modèles ne sont pas créés pour toutes les expériences, votre activité de **[!UICONTROL ciblage automatique]** diffuse toujours de manière aléatoire une partie significative des visites afin de tenter de créer tous les modèles le plus rapidement possible. Si les modèles ne sont pas créés, le **[!UICONTROL ciblage automatique]** ne personnalise pas le trafic.

Ensuite, assurez-vous que les offres et les emplacements des activités font réellement la différence sur les taux de réponse globaux à l’aide d’un test A/B simple et non personnalisé. Calculez les tailles d&#39;échantillon à l&#39;avance pour vous assurer qu&#39;il y a suffisamment de puissance pour voir une élévation raisonnable, et exécutez le test A/B pendant une durée fixe sans l&#39;arrêter ni apporter de modifications. Si les résultats des tests A/B montrent une augmentation statistiquement significative sur une ou plusieurs expériences, il est probable qu’une activité personnalisée fonctionne. Personalization peut fonctionner même s’il n’existe aucune différence dans les taux de réponse globaux des expériences. En règle générale, le problème provient du fait que les offres et les emplacements n’ont pas un impact suffisamment important sur l’objectif d’optimisation pour être détectés avec une signification statistique.

+++

+++ Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties.

Ce comportement est attendu.

Dans une activité de **[!UICONTROL ciblage automatique]**, une fois qu’une mesure de conversion (objectif d’optimisation ou objectif de publication) est convertie, l’utilisateur est libéré de l’expérience et l’activité est redémarrée.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 dépend de C1. Lorsqu’un visiteur accède à l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas remplis, la mesure A1 n’est pas convertie en raison de la dépendance aux mesures de succès. Si le visiteur convertit C1, puis convertit A1, A1 n’est toujours pas converti, car lorsque C1 est converti, le visiteur est libéré.

+++
