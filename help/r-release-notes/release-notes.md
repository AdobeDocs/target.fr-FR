---
keywords: notes de mise à jour;nouvelles fonctionnalités;versions;mises à jour;mise à jour;version;amélioration;améliorations;correctifs;correctifsde bogues
description: Découvrez les nouvelles fonctionnalités, les améliorations et les correctifs inclus dans la version actuelle de  [!DNL Adobe Target], notamment les SDK, les API et les bibliothèques JavaScript.
title: Quelles nouvelles fonctionnalités sont incluses dans la version actuelle ?
feature: Notes de mise à jour
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 146395f5453093ca34b259a143ff4e4c63be949b
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 58%

---

# Notes de mise à jour de Target (actualisées)

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’[!DNL Adobe Target Standard] et de [!DNL Target Premium]. En outre, des notes de mise à jour sur les API, les SDK et la bibliothèque JavaScript (at.js) de Target et d’autres modifications de plateforme sont également incluses, le cas échéant.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Migrez vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js afin d’éviter tout problème potentiel sur vos sites. Pour plus d’informations, consultez [Aperçu : implémentation de Target pour le Web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

(Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].)

## Target Standard/Premium 21.6.1 (7 juin 2021) 

Les améliorations suivantes ont été apportées à cette version :

| Fonctionnalité | Détails |
| --- | --- |
| ![Badge Premium ](/help/assets/premium.png) [!DNL Recommendations] [!UICONTROL Catalog ] SearchAPI | Recherchez votre [!DNL Recommendations] catalogue de contenu et de produit par programmation via l’API pour identifier les éléments qui correspondent à des critères de recherche et simplifier l’administration de votre catalogue.<br>**Limites et remarques** :<ul><li>La recherche catalogue via l’API n’est pas prise en charge pour les environnements comportant plus de 2 000 000 éléments.</li><li>Les résultats de la recherche catalogue via l’API sont mis à jour plus rapidement que les résultats de la recherche catalogue via l’interface utilisateur [!DNL Target]. La recherche catalogue dans l’interface utilisateur [!DNL Target] peut prendre plus de temps pour refléter les derniers résultats.</li></ul>Pour plus d’informations, voir [Recherche d’entités](http://developers.adobetarget.com/api/recommendations/#tag/Searching-Entities) dans le guide *[!DNL Adobe Target][!DNL Recommendations] API*. |

Cette version de maintenance comprend les correctifs suivants.

* Correction d’un problème en raison duquel l’espace de travail par défaut était remplacé par un autre espace de travail lors de l’actualisation de la page [!UICONTROL Audiences]. (TGT-38871)
* Correction d’un problème dans [!UICONTROL Administration] > [!UICONTROL Mise en oeuvre] qui entraînait parfois un message d’erreur stipulant : &quot;Votre mbox globale n’est peut-être pas synchronisée. S&#39;il vous plaît, essayez de le sauver.&quot;

## ![Badgegeversion 2.5.0 ](/help/assets/platform.png) [!DNL Adobe Experience Platform Web SDK] du SDK Web Adobe Experience Platform (1er juin 2021)

Cette version de [!DNL Platform Web SDK] prend en charge les éléments suivants :

| Fonctionnalité | Détails |
| --- | --- |
| Prise en charge des redirections avec [!UICONTROL Analytics pour Target] (A4T) | Le SDK Web Platform prend désormais en charge les redirections [!DNL Target] lors de l’utilisation de [A4T](/help/c-integrating-target-with-mac/a4t/a4t.md).<br>Pour plus d’informations, voir  [Analytics  [!DNL Target] pour la mise en oeuvre](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## at.js version 2.5.0 (13 mai 2021)

Cette version d’at.js s’accompagne des améliorations et modifications suivantes :

* Prise en charge de la [prise de décision sur l’appareil](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) pour at.js.
* Prise en charge des [liens d’aperçu](/help/c-activities/c-activity-qa/activity-qa.md) pour les activités Automated Personalization.

Cette version supprime également la prise en charge de Microsoft Internet Explorer 10, d’Internet Explorer 11 et de toutes les versions antérieures. Microsoft Edge est toujours pris en charge dans at.js 2.5.0 et versions ultérieures.

## Notes de mise à jour supplémentaires et informations détaillées sur les versions

| Ressource | Détails |
|--- |--- |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js [!DNL Adobe Target]. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Obtenez des informations détaillées sur les mises à jour apportées à ce guide qui ne sont pas incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](/help/r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, consultez [Notes de mise à jour d’Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=fr). |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits Target et d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
