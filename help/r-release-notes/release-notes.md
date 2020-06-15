---
keywords: Release notes;new features;releases;updates;update;release;enhancement;enhancements;fixes;bug fixes;updates
description: Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version d’Adobe Target Standard et Target Premium.
title: 'Notes de mise à jour de Adobe Target (en cours) '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 8bd08463509e06673bedd0fedf9ee15e46472826
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 31%

---


# Notes de mise à jour de Target (actualisées){#target-release-notes-current}

Ces notes de mise à jour contiennent des informations sur les fonctionnalités, les améliorations, les correctifs et les problèmes connus de chaque version de Target Standard et Target Premium. En outre, des notes de mise à jour sur les API de Cible, les SDK, la bibliothèque JavaScript (at.js) et d’autres modifications de plate-forme sont également incluses, le cas échéant.

>[!NOTE]
>
>* **Dépréciation** de mbox.js : Le 30 août 2020, Adobe Target ne prendra plus en charge la bibliothèque mbox.js. Après le 30 août 2020, tous les appels effectués à partir de mbox.js échoueront et affecteront vos pages pour lesquelles des activités de Cible sont en cours d’exécution. Nous recommandons à tous les clients de migrer vers la version la plus récente de la bibliothèque at.js avant cette date afin d’éviter tout problème potentiel avec vos sites. Pour plus d’informations, voir [Fonctionnement d’At.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) et [Adobe Target Skill Builder : Messagerie instantanée des développeurs, mbox.js d’Adobe Target est migré vers at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
   >
   >   
   Bien que mbox.js soit actuellement pris en charge, nous n’avons fourni aucune mise à jour des fonctionnalités à cette bibliothèque depuis juillet 2017. Le nouveau fichier at.js offre de nombreux avantages par rapport au fichier mbox.js. Autres avantages : at.js réduit les délais de chargement des pages pour les implémentations Web, renforce la sécurité et offre de meilleures options d’implémentation pour les applications d’une seule page.
   >
   >   
   En déplaçant tous les clients vers at.js, nos ingénieurs et notre personnel d&#39;assistance seront en mesure de vous fournir de nouvelles fonctionnalités et d&#39;offre l&#39;assistance que vous attendez d&#39;Adobe.
   >
   >
* **Annonces** de Cible : Consultez la page des annonces de Cible pour en savoir plus sur les événements à venir, y compris les sessions du Générateur de compétences en Cible, les discussions de développeur, les webinars et les sessions de pause café Cible. Pour plus d’informations, voir Annonces [de](/help/r-release-notes/target-announcements.md)Cible.


Les numéros de problème entre parenthèses sont destinés à une utilisation interne par [!DNL Adobe].

## versions d’at.js 1.8.2 et d’at.js 2.3.1 (15 juin 2020)

Les améliorations et correctifs suivants ont été apportés aux bibliothèques [!DNL Target] at.js :

| Fonctionnalité / Amélioration | Description |
| --- | --- |
| Paramètres at.js 1.8.2 | Cette version d’at.js est une version de maintenance et comprend les correctifs suivants :<ul><li>Correction d’un problème lors de l’utilisation de CNAME et du remplacement de bord, at.js 1.*x* peut créer de manière incorrecte le domaine du serveur, ce qui entraîne l’échec de la [!DNL Target] demande. (TNT-35064)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| Paramètres at.js 2.3.1 | Cette version d’at.js est une version de maintenance qui comprend les améliorations et correctifs suivants :<ul><li>Possibilité de remplacer le `deviceIdLifetime` paramètre par [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)</li><li>Correction d’un problème lors de l’utilisation de CNAME et du remplacement de bord, at.js 2.*x* peut créer de manière incorrecte le domaine du serveur, ce qui entraîne l’échec de la [!DNL Target] demande. (TNT-35065)</li><li>Correction d’un problème lors de l’utilisation de l’ [!DNL Target] extension v2 et de l’ [!DNL Launch] extension, qui entraînait [!DNL Adobe Analytics] le report de l’ [!DNL Launch][!DNL Target] [!DNL Analytics] `sendBeacon` appel. (TNT-36407, TNT-35990, TNT-36000)</li></ul>For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |

## Modifications de l’API d’état du lot de Profils v2 (14 mai 2020)

Avec la version du 20 mai, l’état du lot de Profils ne retournera que les données d’échec au niveau des lignes (les données de réussite ne seront pas renvoyées). Les ID de profil en échec seront renvoyés par l&#39;API à l&#39;avenir.

Les réponses précédentes et les nouvelles API sont les suivantes :

`ProfileBatchStatus Api
http://<<edge>>/m2/<<client>>/profile/batchStatus?batchId=<batchid>`

**Actuellement, nous voyons la réponse comme suit :**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>1514187733806-729395</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>1573612762055-214017</id>
 
        <status>success</status>
 
    </profile>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

**Après le 4 mai, la réponse sera :**

```
<response>
 
    <batchId>samplebatch-1585929692655-59449976</batchId>
 
    <status>complete</status>
 
    <batchSize>164</batchSize>
 
    <profile>
 
        <id>some profile id</id>
 
        <status>failed</status>
 
    </profile>
 
</response>
```

## Target Standard/Premium 20.4.1 (6 mai 2020)

Cette version comprend les améliorations, correctifs et modifications suivants :

* Correction d’un problème en raison duquel un périphérique et un type de navigateur étaient incorrectement qualifiés pour une audience. (TGT-36266)
* Correction d’un problème en raison duquel les données du rapport ne s’affichaient pas sur des écrans de moins de 963 pixels de large. (TGT-36549)
* Correction d’un problème en raison duquel les rapports Personnalisation automatique ne s’affichaient pas correctement. (TGT-36619)
* Correction d’un problème en raison duquel les mesures incompatibles étaient sélectionnées dans les activités d’affectation automatique et de Cible automatique qui utilisaient Analytics pour la Cible (A4t). (TGT-36646)
* Correction d’un problème en raison duquel certaines options du compositeur d’expérience visuelle ne s’affichaient pas correctement. (TGT-36571)
* Correction d’un problème dans l’interface utilisateur de la Cible en raison duquel d’autres prévisualisations d’offre de recommandations affichaient le contenu modifié lorsqu’un utilisateur remplaçait le contenu dans une seule expérience. (TGT-36053 et TGT-36894)
* Correction d’un problème qui empêchait certains utilisateurs de supprimer des éléments d’un catalogue de recommandations. (TGT-36455)
* Correction d’un problème qui empêchait les utilisateurs d’enregistrer des critères de recommandations sur une activité de plusieurs pages. (TGT-36249)
* Correction d’un problème en raison duquel les boutons radio de la source de données comportementales disparaissaient lors de la modification des critères pour une deuxième fois consécutive. (TGT-36796)
* Correction d’un problème d’affichage en raison duquel un algorithme de recommandations affichait des &quot;résultats de récupération&quot; pendant une période prolongée. (TGT-36550 et TGT-36551)
* Mise à jour de nombreuses chaînes d’interface localisées dans différentes langues.

## Notes de mise à jour supplémentaires et détails sur la version

| Ressource | Détails |
|--- |--- |
| [Notes de mise à jour - API côté serveur de Target](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Notes de mise à jour relatives aux API côté serveur d’Adobe Target. |
| [Notes de mise à jour - SDK Target Node.js](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Notes de mise à jour relatives au SDK Node.js d’Adobe Target. |
| [Notes de mise à jour - Cible Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Notes de mise à jour relatives au SDK Java d’Adobe Target. |
| [Informations détaillées sur les versions du fichier at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Informations détaillées sur les modifications apportées à chaque version de la bibliothèque JavaScript at.js d’Adobe Target. |
| [Informations détaillées sur les versions du fichier mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | Cette page présente les modifications apportées à chaque version de mbox.js.<br>Notez que la bibliothèque mbox.js n’est plus développée. Tous les clients doivent migrer de mbox.js vers at.js. |

## Modifications de la documentation, notes de mise à jour des versions antérieures et notes de mise à jour d’Experience Cloud {#section_1BC5F5208DA548E9B4344A0836E4B943}

Outre les notes de chaque version, les ressources suivantes fournissent des informations supplémentaires :

| Ressource | Détails |
|--- |--- |
| Modifications de la documentation | Affichez des informations détaillées sur les mises à jour apportées à ce guide et susceptibles de ne pas être incluses dans les notes de mise à jour.<br>Pour plus d’informations, voir [Modifications de la documentation](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C). |
| Notes de mise à jour pour les versions antérieures | Affichez des informations sur les nouvelles fonctionnalités et améliorations des versions précédentes de Target Standard et Target Premium.<br>Pour plus d’informations, voir [Notes de mise à jour des versions précédentes](../r-release-notes/release-notes-for-previous-releases.md). |
| Notes de mise à jour d’Adobe Experience Cloud | Affichez les dernières notes de mise à jour au sujet des solutions Adobe Experience Cloud.<br>Pour plus d’informations, voir Notes [de mise à jour d’](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)Experience Cloud. |

## Informations préliminaires {#section_5D588F0415A2435B851A4D0113ACA3A0}

Les ressources suivantes vous permettent de connaître les fonctionnalités à venir dans la prochaine version de Target.

| Ressource | Détails |
|--- |--- |
| Liste de mise à jour prioritaire des produits Adobe | Pour recevoir des notifications avancées sur les améliorations à venir des produits à Target et à d’autres solutions Adobe Experience Cloud, inscrivez-vous à la mise à jour produit prioritaire Adobe :<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html |
| Notes de mise à jour à venir | Pour plus d’informations sur les versions de Target du mois en cours, notamment les informations de version préliminaire, voir la page [Notes de mise à jour de Target (préliminaires)](/help/r-release-notes/target-release-notes.md). |
