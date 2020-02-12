---
keywords: account preferences;preferences;site details;custom mbox name;Experience Cloud solution used for reporting;Show estimated lift in revenue;css selectors;use element classes;Default Visual Experience Composer URL;Enable Enhanced Experience Composer;Generate Experience Snapshots;mobile viewport configuration;Industry Vertical;Filter Incompatible Criteria
description: Définissez les préférences du compte pour configurer Adobe Target Standard ou Target Premium en vue d’un fonctionnement correct avec votre compte.
title: Préférences
subtopic: Getting Started
topic: Standard
uuid: ed3904c8-533b-4b9c-a3a1-079c61b1bf2a
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# Préférences{#preferences}

Définissez les préférences du compte pour configurer [!DNL Target Standard] ou [!DNL Target Premium] en vue d’un fonctionnement correct avec votre compte.

Pour définir vos paramètres du compte, cliquez sur **[!UICONTROL Configuration]** > **[!UICONTROL Préférences]**, configurez vos préférences comme vous le souhaitez, puis cliquez sur **[!UICONTROL Envoyer]**.

L’illustration suivante montre les paramètres disponibles sur la page [!UICONTROL Préférences de compte].

![page Préférences](/help/administrating-target/r-target-account-preferences/assets/target-account-preferences.png)

>[!NOTE]
>
>Certaines de ces préférences ne sont disponibles que si vous êtes équipé de [Target Premium](/help/c-intro/intro.md#premium).

## Détails du site {#section_04A3340FC29B46978DB77058259F4EE0}

Spécifiez la manière dont votre site a été configuré.

### Mbox globale personnalisée

Sélectionnez le nom de mbox personnalisé facultatif que vous utilisez pour dispenser les activités [!DNL Target]. Cette mbox globale doit être vide, ce qui signifie qu’elle n’a aucun contenu par défaut. Enregistrez ce paramètre seulement une fois que le fichier [!DNL at.js] ou [!DNL mbox.js] mis à jour est installé sur votre site.

>[!CAUTION]
>
>Une configuration incorrecte de ce paramètre peut entraîner un arrêt des activités.

## Résultats et création de rapports {#section_47C887AABD704A96BCD1C00BEABF4BCE}

Définissez des options qui déterminent les données utilisées pour vos résultats et rapports.

| Option | Description |
|--- |--- |
| Solution Experience Cloud utilisée pour la création de rapports | Sélectionnez [!DNL Target] ou Adobe Analytics comme source de création de rapports pour vos activités. Vous pouvez également choisir de sélectionner votre source de création de rapports pour chaque activité. Tenez compte des informations suivantes pour le choix de votre source de création de rapports :<ul><li>La création, l’activation et la désactivation d’activités d’[!UICONTROL attribution automatique], de [!UICONTROL ciblage automatique] et de [!UICONTROL personnalisation automatisée] (PA) sont autorisées, quelle que soit la source de création de rapports sélectionnée. Ces activités ne sont pas prises en charge lorsque vous choisissez [Adobe Analytics comme source de création de rapports pour Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Même si vous désignez Analytics comme étant votre source de création de rapports, [!DNL Target] se charge de la création des rapports pour ces activités.</li><li>Si la source de création de rapports désignée est Analytics, vous ne pouvez pas activer une activité dont la source de création de rapports est [!DNL Target] (la désignation de Target comme source de création de rapports se fait activité par activité). Vous devez désigner Analytics comme source de création de rapports directement dans l’activité ou modifier la sélection dans Sélection par activité, dans Configuration > Préférences.</li><li>Si cette option est définie sur [!DNL Target], vous ne pouvez pas activer une activité dont la source de création de rapports est Analytics. Vous devez désigner [!DNL Target] comme source de création de rapports directement dans l’activité ou modifier la sélection dans Sélection par activité, dans Configuration > Préférences.</li><li>Si cette option est définie sur Sélection par activité, vous pouvez créer, activer et désactiver les activités prises en charge par la source de création de rapports sélectionnée. Pour consulter une matrice des activités prises en charge, voir [Adobe Analytics comme source de création de rapports pour Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).</li><li>Lorsque vous passez du test A/B manuel à l’[!UICONTROL attribution automatique] ou au [!UICONTROL ciblage automatique], toutes les mesures et audiences pour la création de rapports sont perdues, dans le cas où l’activité A/B manuelle n’est pas prise en charge dans les activités d’[!UICONTROL attribution automatique] et de [!UICONTROL ciblage automatique].</li></ul> |
| Afficher l’effet élévateur estimé dans les recettes | Vous pouvez également choisir d’afficher l’effet élévateur estimé dans les recettes si vous saisissez une valeur monétaire pour votre objectif. [!DNL Target] peut estimer l’effet élévateur dans les recettes que vous atteindriez si tous les utilisateurs consultaient l’expérience gagnante. La fonctionnalité d’effet élévateur estimé est désactivée par défaut.<br>Seuls les utilisateurs administrateurs d’Experience Cloud peuvent l’activer ou la désactiver. Si l’effet élévateur estimé est activé, les champs correspondants ne s’affichent pas dans l’interface. La désactivation de cette fonctionnalité n’entraîne pas une perte des données, notamment des données utilisées pour les estimations. Celles-ci reposent sur les données collectées, que la fonctionnalité soit activée ou non.<br>Pour plus d’informations, voir [Estimation de l’effet élévateur dans les recettes](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md). |
| Activation des priorités affinées | Autorise les entrées numériques pour une priorité comprise entre 0 et 999.<br>En fonction de vos paramètres, l’interface utilisateur et les options pour Priorité peuvent varier. Vous pouvez utiliser les anciens paramètres (Faible, Moyen ou Élevé) ou vous pouvez activer les priorités affinées de 0 à 999.<br>Le niveau de priorité est utilisé lorsque plusieurs activités sont affectées à un emplacement identique avec une même audience. Si deux activités ou davantage sont affectées au même emplacement, l’activité dont le niveau de priorité est le plus élevé s’affiche. |

## Sélecteurs CSS {#section_8155EDBF449E4198863235F94D1EA872}

Spécifiez comment [!DNL Target] génère des sélecteurs CSS.

Ces options aident [!DNL Target] à comprendre la structure de votre site afin de générer de meilleurs sélecteurs CSS pour la distribution de contenu. Par défaut, [!DNL Target] génère les sélecteurs selon les identifiants d’élément de la page. Si votre site utilise peu d’ID, ou des ID en double sur la même page, l’utilisation de classes peut être une meilleure option.

Vous pouvez sélectionner une des options suivantes ou les deux :

| Option | Description |
|--- |--- |
| Utiliser les ID d’élément | Désélectionnez cette option si le même ID est utilisé pour plusieurs éléments ou si l’ID d’élément peut changer au chargement de la page. |
| Utiliser les classes d’éléments | Par défaut, [!DNL Target] utilise uniquement les identifiants d’élément. Néanmoins, si votre page est conçue pour utiliser des classes pour identifier les éléments, par exemple une page créée avec [!DNL Adobe Experience Manager], vous devez également sélectionner [!UICONTROL Utiliser les classes d’éléments].<br>**Remarque :**Bien que tout ait été fait pour garantir la précision, gardez à l’esprit que l’utilisation de classes peut provoquer des erreurs. Si vous ne sélectionnez aucune des deux options, la précision est également affectée. L’ordre de précision est ID > classes > aucune des options. Assurez-vous de systématiquement tester votre page pour garantir que les sélecteurs sont corrects.<br>Vous pouvez remplacer ce paramètre par activité (cliquez sur l’icône en forme d’engrenage[!UICONTROL Paramètres], puis sélectionnez[!UICONTROL Sélecteurs CSS]). Cette fonctionnalité est particulièrement utile si vous avez plusieurs sites qui sont configurés différemment.<br>**Remarque :** Le remplacement du paramètre par activité n’est pas disponible dans les activités de [!UICONTROL personnalisation automatisée] et [!UICONROL tests multivariés.]  Voir [Sélecteurs d’éléments utilisés dans le compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/vec-selectors.md) pour plus d’informations sur les sélecteurs. |

## compositeur d’expérience visuelle {#section_CD9BDD372CF54E678F88E8BA95757A5A}

| Option | Description |
|--- |--- |
| URL du compositeur d’expérience visuelle par défaut | Définissez l’URL par défaut utilisée par le [!UICONTROL compositeur d’expérience visuelle]. Il s’agit de la page par défaut, par exemple votre page d’accueil, utilisée lorsque vous configurez une expérience pour chaque nouvelle activité. Si vous ne définissez pas d’URL par défaut, vous devez saisir une URL pour chaque activité lors de sa création. |
| Activer le compositeur d’expérience avancé | Autorise la modification des sites avec des iFrames ou avec un contenu mixte. Certains sites peuvent ne pas être compatibles avec la version améliorée. Décochez cette option pour revenir au compositeur d’expérience d’origine. La répartition des activités sur les sites n’est pas affectée par ce choix.<br>Pour plus d’informations, voir [Résolution des problèmes du compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).<br>**Remarque :**Vous pouvez également activer le compositeur d’expérience avancé au niveau de l’activité. |
| Chargement du contenu mixte | Activez le contenu mixte lors de l’ouverture d’un site web à l’aide du compositeur d’expérience amélioré (EEC). L’activation de cette option évite les frais supplémentaires liés au chargement de ressources statiques via des serveurs proxy de Target.<br>Cette option s’avère utile, par exemple, si les en-têtes CSP (Content Security Policy) permettent le chargement de contenu mixte sans l’utilisation de serveurs proxy avec la fonction EEC activée.<br>Cette option s’avère également utile si le temps de chargement des sites Web HTTP est augmenté dans la fonction EEC, où JavaScript, les images, etc. prennent plus de temps à se charger via proxy. |
| Générer des instantanés d’expérience | L’activation des instantanés d’expérience génère des miniatures pour vos expériences dans le diagramme de processus de l’activité. Pour certains utilisateurs, la désactivation des instantanés peut permettre d’obtenir des performances plus rapides. |

## Configuration des fenêtres d’affichage mobiles {#section_42176D062BCE4A28ADBB784CC4BEF84D}

Vous pouvez ajouter des périphériques à utiliser lors de la prévisualisation d’expériences. Chaque périphérique est associé à une audience.

| Option | Description |
|--- |--- |
| ![Badge Premium](/help/assets/premium.png) Ajouter un nouveau badge | Cliquez sur [!UICONTROL Ajouter], attribuez un nom explicite à la fenêtre d’affichage mobile, spécifiez la largeur et la hauteur, sélectionnez le système d’exploitation désiré, puis cliquez sur [!UICONTROL Enregistrer]. Pour obtenir des informations sur l’ajout d’une fenêtre d’affichage mobile, voir [Configuration de fenêtre d’affichage mobile](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md). |

## Vidéo de formation : préférences du compte (7:33) badge ![Aperçu](/help/assets/overview.png)

Cette vidéo comporte des informations sur les préférences de compte.

* Description des paramètres du compte disponibles dans [!DNL Target Standard]

>[!VIDEO](https://video.tv.adobe.com/v/17379)