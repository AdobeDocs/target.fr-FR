---
keywords: notes de mise à jour;versions;mises à jour;futures mises à jour;améliorations;nouvelles fonctionnalités;correctifs;préliminaire
description: Découvrez les nouvelles fonctionnalités, améliorations et correctifs de la prochaine version d’Adobe Target, notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la prochaine version ?
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: bd7032b915bf1b333fa5cc3cb4825eaa7e4f83fb
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 43%

---

# Notes de mise à jour de Target (préliminaires)

Cet article contient des informations préliminaires. Les dates de publication, fonctions et autres informations peuvent changer sans préavis.

**Dernière mise à jour : 6 octobre 2021**

Pour consulter des informations sur la version actuelle, voir [Notes de mise à jour de Target](release-notes.md). Les informations sur ces pages peuvent être identiques selon le timing des versions. Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Depuis le 31 mars 2021, tous les appels effectués à partir de mbox.js échouent et ont une incidence sur les pages comportant des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Pour éviter tout problème potentiel sur vos sites, migrez vers la version la plus récente du nouveau [!DNL Adobe Experience Platform Web SDK] ou de la bibliothèque JavaScript at.js. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## [!DNL Target Standard/Premium] 21.10.1 (6 octobre 2021)

Cette version comprend les nouvelles fonctionnalités suivantes :

| Fonctionnalité | Détails |
| --- | --- |
|  Actualisation d’AudiencesUI | Dans le cadre des efforts déployés par l’équipe [!DNL Adobe Target] pour améliorer l’expérience utilisateur des [!DNL Target] utilisateurs, cette version actualise les pages [!UICONTROL Audiences] et [!UICONTROL Scripts de profil] dans l’interface utilisateur de [!DNL Target]. Cette mise à jour unifie et normalise les modèles de conception précédemment incohérents, tout en ajoutant de nouvelles améliorations, telles que :<ul><li>la possibilité de sélectionner et de supprimer plusieurs audiences simultanément ;</li><li>Une [conception du générateur d’audiences](/help/c-target/c-audiences/create-audience.md) actualisée</li><li>Prise en charge des règles d’exclusion dans le créateur de règles de bibliothèque [!UICONTROL Audience]</li><li>Un nouveau filtre &quot;Source d’audience&quot;, pour permettre une découverte d’audience plus rapide</li><li>Options de recherche persistante et de filtrage de session</li></ul>Pour plus d’informations, consultez [Audiences](/help/c-target/target.md).<br>**Remarque** : La nouvelle interface utilisateur   Audiences et   Scripts de profil sera déployée dans toutes les régions la semaine prochaine. |
| [!UICONTROL Actualisation ] de l’interface utilisateur des scripts de profil | La bibliothèque [!UICONTROL Scripts de profil] a également été mise à jour. Elle comprend une interface actualisée ainsi que plusieurs mises à jour de productivité :<ul><li>La possibilité de sélectionner et de supprimer plusieurs scripts de profil simultanément</li><li>Un nouvel éditeur de code pour les scripts de profil</li><li>Mise en surbrillance de la syntaxe et vérification des erreurs dans l’éditeur de code</li><li>Saisie automatique des jetons (paramètres de mbox ou de profil) à l’aide de raccourcis clavier</li></ul>Pour plus d’informations, voir [Profils de visiteur](/help/c-target/c-visitor-profile/visitor-profile.md).<br>**Remarque** : La nouvelle interface utilisateur   Audiences et   Scripts de profil sera déployée dans toutes les régions la semaine prochaine. |
| ![Badge Premium ](/help/assets/premium.png) Badge Recommendations Critères de création et de modification | Le workflow de création et d’édition [!UICONTROL Critères Recommendations] a été simplifié afin de simplifier le choix de l’algorithme et des paramètres de recommandations adaptés pour atteindre vos objectifs.<br>Pour plus d’informations, voir  [Création de critères](/help/c-recommendations/c-algorithms/create-new-algorithm.md). |
| ![Amélioration de l’intervalle de recherche en amont des recommandations ](/help/assets/premium.png) badge Premium et du taux d’actualisation de l’algorithme | Vous pouvez désormais exécuter les algorithmes &quot;Les plus consultés&quot; et &quot;Meilleurs vendeurs&quot; avec une période de recherche arrière de six heures pour capturer le contenu qui est en tendance dernièrement. Lorsque l’intervalle de recherche en amont de six heures est sélectionné, les résultats de vos recommandations sont mis à jour toutes les 3 à 6 heures toute la journée.<br>Pour plus d’informations, voir  [Source de données ](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) dans  *Création de critères*. |

## Informations préliminaires {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Pour recevoir des notifications anticipées sur les améliorations à apporter aux produits Target et aux autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour de produit Adobe Priority :

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
