---
keywords: données partielles;A4T;divergences;analytics pour target;orphelin;suite de rapports virtuelle;fictive;dépannage;désassemblé;exagéré;non spécifié
description: Découvrez comment minimiser les effets d’un nombre de visiteurs ou de visites exagéré lors de l’utilisation d’Analytics pour [!DNL Target] (A4t). Découvrez ce que sont les "données partielles" et comment les réduire.
title: Comment puis-je réduire le nombre de visiteurs ou de visites exagéré dans A4T ?
feature: Analytics for Target (A4T)
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 47%

---

# Minimisation du nombre de visiteurs ou de visites exagéré dans A4T

Informations destinées à vous aider à minimiser les effets d’un nombre de visiteurs ou de visites exagéré lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports pour [!DNL Adobe Target] (A4T).

>[!IMPORTANT]
>Le 14 novembre 2016, Adobe Analytics a modifié la façon dont certaines données sont traitées pour les clients qui utilisent la création de rapports Analytics pour Target (A4T). Ces modifications améliorent l’alignement entre les données Adobe Target et le modèle de données d’Adobe Analytics. Ces modifications ont été déployées pour tous les clients utilisant A4T. Ces modifications ont pour but de résoudre un problème en raison duquel certains clients ont remarqué un nombre de visiteurs exagéré lors de l’exécution d’activités Target.
>
>Cette modification n’est pas rétroactive. Si vos rapports historiques indiquent des nombres exagérés et que vous souhaitez les exclure de vos rapports, vous pouvez créer une suite de rapports virtuelle, comme expliqué ci-dessous.
>
>En outre, plusieurs bibliothèques JavaScript ont été mises à jour afin de minimiser les décomptes exagérés. Adobe recommande d’effectuer la mise à niveau vers les versions de bibliothèque suivantes (ou plus récentes) :
>
>* Service d’identification des visiteurs d’Experience Cloud : visitorAPI.js version 2.3.0 ou ultérieure.
>* Adobe Analytics : appMeasurement.js version 2.1.
>* Adobe Target : at.js version 0.9.6 ou ultérieure (à l’exception de la version 1.1.0 si vous utilisez les offres de redirection avec A4T).


## Qu’est-ce qui a changé ?  {#section_9CCF45F5D66D48EBA88F3A178B27D986}

When [!DNL Adobe Analytics] est utilisé pour mesurer [!DNL Target] activités (appelées A4T), [!DNL Analytics] collecte des données supplémentaires qui ne sont pas disponibles lorsqu’il n’y a pas de [!DNL Target] activité sur la page. Le [!DNL Target] l’activité déclenche un appel en haut de la page, mais [!DNL Analytics] déclenche généralement ses appels de collecte de données au bas de la page. Dans l’implémentation d’A4T actuelle, l’Adobe inclut ces données supplémentaires chaque fois qu’une [!DNL Target] l&#39;activité était principale. À l’avenir, Adobe n’inclut ces données supplémentaires que lorsque la variable [!DNL Target] et [!DNL Analytics] les balises ont été déclenchées.

## Pourquoi Adobe a-t-il apporté cette modification ? {#section_92380A4BD69E4B8886692DD27540C92A}

Adobe se targue de la précision et de la qualité de ses données. Lorsque la variable [!DNL Target] se déclenche, mais la variable [!DNL Analytics] ne l’est pas, Analytics enregistre &quot;données partielles&quot; (parfois appelées &quot;accès désassemblés&quot;). Ces accès désassemblés ne sont pas capturés par [!DNL Analytics] s’il n’y avait pas [!DNL Target] activité. Même si vous incluez ces données partielles dans [!DNL Analytics] Les rapports fournissent des informations supplémentaires, mais ils créent également des incohérences par rapport aux données historiques des périodes où il n’y en avait pas [!DNL Target] activités en cours d’exécution. Cette situation peut entraîner des problèmes pour les variables [!DNL Analytics] utilisateurs qui analysent les tendances au fil du temps. Afin d’assurer la cohérence des données dans [!DNL Analytics], l’Adobe exclut toutes les données partielles.

## Qu’est-ce qui contribue aux données partielles ?  {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobe a rencontré des clients enregistrant des taux élevés de données partielles dans [!DNL Analytics]. Un taux élevé de données partielles peut résulter d’une implémentation incorrecte, mais il existe également des causes légitimes.

Les causes identifiées des données partielles incluent :

* **Alignement incorrect des identifiants de suites de rapports (implémentation) :** la suite de rapports spécifiée lors de la configuration d’une activité ne correspond pas à la suite de rapports de la page où le test est diffusé. Les données ne peuvent pas être réconciliées sur [!DNL Analytics] qui ressemble donc à des données partielles.
* **Pages lentes :** [!DNL Target] Les appels se trouvent en haut de la page et [!DNL Analytics] Les appels se trouvent généralement au bas de la page. Si la page se charge lentement, cela augmente la probabilité qu’un visiteur quitte la page après l’événement [!DNL Target] se déclenche, mais avant la variable [!DNL Analytics] appelez . Les pages lentes peuvent être particulièrement problématiques sur les sites web mobiles où les connexions sont souvent plus lentes.
* **Erreurs de page :** En cas d’erreurs JavaScript ou d’autres scénarios où chacun des points de contact ne se déclenche pas (service d’ID Experience Cloud, Target et Analytics), des résultats de données partiels sont générés.
* **Offres de redirection dans [!DNL Target] activité :** Pour les offres de redirection dans les activités utilisant A4T, votre mise en oeuvre doit respecter certaines exigences minimales. En outre, il y a des informations importantes que vous devez connaître. Pour plus d’informations, voir [FAQ sur les offres de redirection (A4T)](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58).
* **Anciennes versions des bibliothèques :** Au cours de l’année écoulée, l’Adobe a apporté plusieurs améliorations aux bibliothèques JavaScript ( [!DNL appMeasurement.js], `at.js`, et `visitorAPI.js`) pour vous assurer que les données sont envoyées aussi efficacement que possible. Pour en savoir plus sur les exigences d’implémentation, voir [Avant l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543).

## Quelles sont les bonnes pratiques pour réduire les données partielles ? {#section_065C38501527451C8058278054A1818D}

Pour réduire la collecte de données partielles, passez en revue les étapes suivantes :

| Étape | Tâche |
| --- | --- |
| ![Étape 1](assets/step1_icon.png) | Assurez-vous que la suite de rapports sélectionnée dans [!DNL Target] est identique à celui des pages où l’activité est présentée. |
| ![Étape 2](assets/step2_icon.png) | Assurez-vous que les bibliothèques visitorAPI.js, appMeasurement.js et at.js se trouvent sur des versions compatibles avec A4T. Pour en savoir plus sur les exigences d’implémentation, voir [Avant l’implémentation](/help/main/c-integrating-target-with-mac/a4t/before-implement.md). |
| ![Étape 3](assets/step3_icon.png) | Assurez-vous que le SDID est défini sur tous les [!DNL Target] et [!DNL Analytics] appelle en quittant la page et qu’ils correspondent.<br/>Utilisez un analyseur de réseau ou un outil de débogage pour vous assurer que la variable `mboxMCSDID` paramètre on [!DNL Target] Les appels correspondent au paramètre SDID dans la variable [!DNL Analytics] appelez . |
| ![Étape 4](assets/step4_icon.png) | Vérifiez que les bibliothèques d’implémentation se chargent dans l’ordre correct sur vos sites. Pour plus d’informations, voir [Implémentation d’Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## Comment puis-je voir de combien de données partielles je dispose ? {#section_89B663E2824A4805AB934153508A0F4B}

Ces informations ne sont pas directement disponibles dans [!DNL Analytics], mais vous pouvez contacter l’Assistance clientèle d’Adobe pour obtenir un rapport de données partielles. Ce rapport est destiné à faciliter le débogage.

## Comment puis-je afficher les tendances historiques sans les données partielles ? {#section_4C9DED560FAD4428B362DDA2064897C3}

Cette modification du traitement des données n’affecte les données qu’après la date de publication (14 novembre 2016). Si vous souhaitez ajuster vos mesures historiques pour qu’elles correspondent, Adobe vous recommande de créer un segment afin d’exclure les données partielles.

Les informations suivantes relatives à cette modification incluent des instructions destinées à vous aider à définir le segment et à l’appliquer à une suite de rapports virtuelle pour que ce segment soit toujours appliqué à vos vues [!DNL Analytics].

Dans la plupart des cas, un [!DNL Target] accès est associé à un [!DNL Analytics] accès sur chaque page web. Cet assemblage se produit lorsqu’un paramètre SDID cohérent se trouve à la fois dans un appel [!DNL Target] et [!DNL Analytics] et qu’un appel [!DNL Experience Cloud ID] (MCID) se trouve dans un appel [!DNL Analytics] sur la même page. [!DNL Target] comporte généralement le MCID, mais si l’appel à [!DNL Target] survient avant le renvoi de l’identifiant visiteur, l’accès est toujours assemblé en raison du SDID. L’utilisateur peut également rester suffisamment longtemps sur la page pour déclencher un appel [!DNL Analytics] après qu’un appel [!DNL Target] ait été déclenché. Ce scénario est idéal.

**Accès aux données partielles :** les utilisateurs ne restent parfois pas suffisamment longtemps sur une page pour envoyer un [!DNL Analytics] appel, mais [!DNL Target] dispose d’un MCID correct. Ce scénario génère des accès à données partielles (accès sans [!DNL Analytics] page vue). Si ces utilisateurs reviennent sur votre site et affichent une page contenant [!DNL Analytics] , ils sont correctement comptabilisés comme visiteurs récurrents. Ces accès auraient été perdus si vous n’aviez [!DNL Analytics] du code sur la page. Certains clients ne souhaitent pas récupérer les données de ces accès car elles exagèrent certaines mesures (visites) et diminuent d’autres mesures (nombre de pages vues par visite, durée par visite, etc.). Vous voyez également des visites sans aucune page vue. Toutefois, il existe de bonnes raisons de conserver ces données.

Afin de minimiser les accès à données partielles, vous pouvez faire charger votre page plus rapidement, mettre à jour les bibliothèques vers les versions les plus récentes ou créer une [suite de rapports virtuelle](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) qui exclut ces accès. Pour obtenir des instructions détaillées, voir [Création de suites de rapports virtuelles](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) dans le *Guide des composants Analytics*.

L’illustration suivante présente la définition de segment pour la suite de rapports virtuelle :

![](assets/ts_a4t.png)

Lors de la création de la suite de rapports virtuelle, spécifiez la configuration suivante pour la définition de segment (comme présenté dans l’illustration ci-dessus) :

* **Afficher les accès :**
* Analytics for Target : Existe
* Et
* Pages vues : N’existe pas
* Et
* Instances de liens personnalisés : N’existe pas
* Et
* Instances de lien de téléchargement : N’existe pas
* Et
* Instances de lien de sortie : N’existe pas

**Accès orphelins :** il arrive parfois que les utilisateurs ne restent pas suffisamment longtemps sur la page pour un appel Analytics et Target n’obtient pas de MCID correct. Ces accès sont ce que l’Adobe définit comme des accès &quot;orphelins&quot;. Ils représentent les clients qui reviennent rarement et ils exagèrent le nombre de visites et de visiteurs de manière inappropriée.

Afin de minimiser ces accès « orphelins », vous pouvez créer une [suite de rapports virtuelle](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) qui exclut ces accès, comme expliqué ci-dessus.

## Quel impact cette modification a-t-elle sur mes [!DNL Target] rapports ?  {#section_AAD354C722BE46D4875507F0FCBA5E36}

Une fois cette modification effectuée, vous pouvez constater une diminution du nombre de nouveaux visiteurs et de visites dans les tests en direct, car [!DNL Adobe] ne traite pas les données partielles entrantes. Les conversions et les accès aux autres mesures [!DNL Analytics] ne connaîtront aucun changement.
