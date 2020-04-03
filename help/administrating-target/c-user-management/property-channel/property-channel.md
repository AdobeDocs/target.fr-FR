---
keywords: workspaces;manage property;permissions;product configuration;product profile;roles;project
description: Informations relatives à la création de propriétés et à l’utilisation de la fonctionnalité Propriétés et autorisations, grâce à laquelle les administrateurs de Target peuvent créer des espaces de travail (profils produit) distincts dans Target, puis attribuer aux utilisateurs différents rôles et autorisations pour des pages, propriétés ou sites web individuels en fonction de ces espaces de travail.
title: Autorisations des utilisateurs d’Enterprise
subtopic: Getting Started
uuid: 1961730d-2357-406f-acac-a36b7a63bd35
translation-type: tm+mt
source-git-commit: 207ff5d6010bf5006d31945f7a35c35860c3646c

---


# ![PREMIUM](/help/assets/premium.png) Autorisations des utilisateurs d’entreprise{#enterprise-user-permissions}

Les autorisations utilisateur d’entreprise permettent d’administrer officiellement à Target l’accès utilisateur à l’échelle de l’entreprise. Ajoutez des utilisateurs à Target, attribuez des autorisations en fonction de leur rôle et créez des espaces de travail pour les équipes en fonction de différents services, lieux globaux, canaux et autres regroupements logiques. Vous pouvez affecter aux utilisateurs les rôles d’observateur, d’éditeur ou d’approbateur.

## Déterminez si vous avez accès aux autorisations d’utilisateur d’entreprise

>[!NOTE]
>
>La fonctionnalité Propriétés et autorisations est disponible dans le cadre de la solution Target Premium. Elles ne sont pas disponibles dans Target Standard sans une licence Target Premium.
>
>Votre mise en œuvre de Target peut utiliser n’importe quelle version d’at.js ou de mbox.js.

Vous pouvez déterminer si votre organisation dispose d’une licence Standard ou Premium en cliquant sur le lien [!UICONTROL Configuration] dans la partie supérieure de l’interface utilisateur de [!DNL Target].

* **[!DNL Target Standard]Clients ** : si l’onglet[!UICONTROL Utilisateurs]s’affiche ([!UICONTROL Configuration > Utilisateurs]), votre organisation dispose d’une licence[!DNL Target Standard]. Les clients[!DNL Target Standard]doivent suivre les instructions de la rubrique[Utilisateurs](/help/administrating-target/c-user-management/c-user-management/user-management.md)pour ajouter des utilisateurs et attribuer des autorisations dans Adobe Admin Console.

   Les utilisateurs [!DNL Target Standard] voient s’afficher le message d’erreur suivant lorsqu’ils cliquent sur l’onglet [!UICONTROL Propriétés]. Il ne s’agit pas d’un dysfonctionnement de [!DNL Target]. Les utilisateurs [!DNL Target Standard] n’ont pas accès à la fonctionnalité [!DNL Target Premium] [!UICONTROL autorisations d’entreprise].

   ![Message d’erreur](/help/administrating-target/c-user-management/property-channel/assets/sorry.png)

* **[!DNL Target Premium]Clients  :**si l’onglet[!UICONTROL Propriétés]s’affiche ([!UICONTROL Configuration > Propriétés]), votre organisation dispose d’une licence[!DNL Target Premium]. Les clients[!DNL Target Premium]doivent suivre les instructions de cet article et de[Configurer les autorisations d’entreprise](/help/administrating-target/c-user-management/property-channel/properties-overview.md).

## Avant de commencer avec les autorisations d’entreprise

>[!IMPORTANT]
>
>Assurez-vous de lire la section [Mises en garde](../../../administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) ci-dessous avant de poursuivre avec les autorisations d’entreprise.

## Termes et définitions utilisés dans cette section {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

Les termes ci-après sont utilisés dans cette section et peuvent ne pas être familiers aux utilisateurs qui souhaitent utiliser la fonction Propriétés et autorisations de Target Premium.

### Propriété

Les propriétés sont de même nature que celles de la Dynamic Tag Management (Activation), dans le sens où elles utilisent un fragment de code unique pour se différencier.

Une propriété web est une bibliothèque de règles et un code incorporé. Il peut s’agir de n’importe quel regroupement d’un ou de plusieurs domaines et de sous-domaines.

Les propriétés sont activées en ajoutant une paire nom/valeur spécifique comme paramètre avec un appel quelconque (mbox, api, etc.) à Target. 
Les propriétés appartiennent à des canaux spécifiques (web, mobile, courrier électronique ou API/autre).

### Espace de travail (Profil produit)

Avec un espace de travail, une organisation peut allouer un groupe d’utilisateurs spécifique à un groupe de propriétés spécifique. Un espace de travail peut être comparé à une suite de rapports dans Adobe Analytics.

Remarque : Les espaces de travail sont appelés Profils produit dans Adobe Admin Console for Enterprise.

Si vous êtes membre d’une organisation internationale, vous pouvez avoir un espace de travail dédié à vos pages web, propriétés ou sites européens et un autre espace de travail dédié à vos pages web, propriétés ou sites américains. Si vous faites partie d’une organisation multimarque, vous disposez peut-être d’un espace de travail distinct pour chacune de vos marques.

Les utilisateurs peuvent appartenir à plusieurs espaces de travail et différents rôles peuvent même leur être attribués dans chaque espace de travail.

Les utilisateurs peuvent disposer de vues différentes d’Adobe Target en se déplaçant entre les espaces de travail, de la même manière que les utilisateurs d’Analytics disposent de vues différentes d’Analytics en se déplaçant entre les suites de rapports.

Les espaces de travail peuvent inclure des audiences, des offres de code et des activités différentes.

Toutes les audiences et activités créées avant la nouvelle migration du modèle d’autorisations d’Enterprise seront regroupées dans l’espace de travail par défaut décrit ci-dessous.

Toutes les activités créées dans Adobe Experience Manager (AEM), Adobe Mobile Services et Adobe Target Classic font elles aussi partie de l’espace de travail par défaut.

### Espace de travail par défaut

Tous les espaces de travail existants (profils produit) d’Admin Console sont fusionnés en un seul espace de travail appelé « Espace de travail par défaut » lors de la migration de votre organisation vers le nouveau modèle d’autorisations d’Enterprise.

>[!IMPORTANT]
>
>Ne supprimez pas l’espace de travail par défaut.

Tous les rôles et accès utilisateur des fonctionnalités de Target restent exactement les mêmes qu’avant la migration vers le nouveau modèle d’autorisations d’Enterprise.

### Groupes d’utilisateurs

Vous pouvez créer des groupes d’utilisateurs (développeurs, analystes, responsables du marketing, directeurs, etc.) et leur allouer des droits d’accès à l’échelle de plusieurs produits et espaces de travail Adobe. Il peut être aussi facile d’affecter à un nouveau membre d’équipe tous les droits d’accès appropriés à différents produits Adobe que de les affecter à un groupe d’utilisateurs spécifique.

### Rôles et autorisations

Les rôles et autorisations déterminent les niveaux d’accès qu’ont les utilisateurs pour créer et gérer les activités dans votre mise en œuvre Target. Dans Target, les rôles sont les suivants :

* Observateur : peut visualiser des activités mais ne peut pas les créer ni les modifier.
* Éditeur : peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité.
* Approbateur : peut créer, modifier et activer ou arrêter les activités.

### Canal

Le canal se rapporte au type de contenu de l’emplacement où sont distribuées vos activités Target : pages web, applications mobiles, messages électroniques, etc.

Lorsque vous créez une activité, elle est ajoutée à l’espace de travail actuellement sélectionné. Dans la première boîte de dialogue qui s’ouvre, vous pouvez choisir un canal pour l’activité : web, application mobile, e-mail ou autre/API.

## Aperçu des autorisations {#section_DC2172520DA84605B218A5E9FB6D187A}

Les informations suivantes expliquent de quelle façon les autorisations étaient imposées auparavant dans [!DNL Target] et dont elles le sont maintenant à l’aide de la fonctionnalité [!UICONTROL Propriétés] et [!UICONTROL autorisations].

Grâce à la nouvelle fonctionnalité [!UICONTROL Autorisations], vous pouvez créer différents projets (appelés « Profils produit » dans [!DNL Adobe Admin Console for Enterprise]) afin d’affecter à un utilisateur donné différentes autorisations définissant ses droits d’accès pour chaque projet. Ces projets distincts sont comparables au fonctionnement des suites de rapports dans [!DNL Adobe Analytics]. À chacun d’eux peuvent appartenir des utilisateurs désignés avec des rôles spécifiques s’appliquant à une série de propriétés. Les clients pourront ainsi restreindre l’accès (affichage, modification et approbation) de leurs utilisateurs en fonction de leur région, de leur environnement (développement, évaluation, production), de leur canal ou d’un autre critère personnalisé, comme illustré ci-dessous :

![](assets/permissions.png)

Par exemple, un utilisateur donné peut avoir un accès « approbation » aux sites web américains, mais un accès « affichage » seulement à l’application mobile européenne. Ce même utilisateur peut aussi ne pas être autorisé à afficher les activités proposées sur les propriétés web et mobiles dans la région APAC.

Actuellement, le modèle [!DNL Target] [!UICONTROL d’autorisations] de se compose de trois rôles (observateur, éditeur et approbateur), comme illustré ci-après :

![](assets/permissions_1.png)

À chaque rôle correspondent différents niveaux d’autorisations :

| Rôle | Description |
|--- |--- |
| Observateur | A accès en lecture seule aux activités. Peut visualiser des activités mais ne peut pas les créer ni les modifier. |
| Éditeur | Peut créer et modifier des activités avant qu’elles ne soient activées, mais ne peut pas approuver le lancement d’une activité. |
| Approbateur | Peut créer, modifier et activer ou arrêter les activités. |

Important : Chaque rôle d’utilisateur s’applique à chaque page, propriété ou site de votre compte qui comprend des balises [!DNL Target], comme indiqué ci-après :

![](assets/permissions_2.png)

Le nouveau modèle [!DNL Target] [!UICONTROL d’autorisations] de se compose des mêmes trois rôles (observateur, éditeur et approbateur). Vous pouvez toutefois affecter à un même utilisateur des autorisations distinctes pour chaque page, propriété ou site, comme illustré ci-après :

![](assets/permissions_3.png)

Dans cet exemple, Jeanne a les autorisations associées à son rôle d’approbatrice pour la page d’accueil et le site américains et les autorisations associées à son rôle d’observatrice pour le site français.

En outre, Jeanne n’aura pas accès aux pages, propriétés ou sites pour lesquels elle n’a pas d’autorisation dans [!DNL Target], comme illustré ci-après :

![](assets/permissions_4.png)

Dans cet exemple, Jeanne ne peut pas afficher les pages produit, le site de Russie ni le site Carrières.

## Cas d’utilisation {#section_F3CE8576959E4F4CB13BEEED38311DD8}

Les cas d’utilisation suivants peuvent s’avérer utiles pour comprendre de quelle façon les propriétés, les projets, les rôles et les autorisations peuvent vous aider à atteindre vos objectifs marketing avec [!DNL Target] :

### Organisation multinationale

Si vous êtes membre d’une organisation internationale, vous pouvez avoir un espace de travail dédié à vos pages web, propriétés ou sites européens et un autre espace de travail dédié à vos pages web, propriétés ou sites américains. Après une réorganisation, en utilisant les personnages des illustrations ci-dessus, vous pouvez configurer des espaces de travail et des autorisations semblables à ce qui suit :

* **Jeanne** : Jeanne est responsable de l’optimisation du Centre d’excellence pour les pages Web, les propriétés et les sites de son organisation aux États-Unis. Elle détient probablement les droits d’administrateur système dans Adobe Experience Cloud.

   Elle a les autorisations associées à son rôle d’approbatrice pour la page d’accueil et le site des États-Unis. Grâce à ces autorisations, elle peut créer, modifier et activer ou interrompre les activités.

   Jeanne collabore également avec l’équipe d’optimisation en France et a par conséquent les autorisations associées à son rôle d’observatrice pour le site français, ce qui lui permet d’accéder aux activités en lecture seule. Elle peut visualiser les activités mais ne peut pas les créer ni les modifier.

   Puisqu’aucun de ses rôles ne justifie qu’elle consulte les pages produit, le site russe ou le site Carrières, Jeanne n’a pas accès aux activités de ces sites.

* **Ernie** : Ernie est le directeur du marketing pour les États-Unis dans l’organisation.

   Il a rejoint l’organisation depuis peu et connaît assez mal Target. Il dispose des autorisations associées à son rôle d’éditeur pour la page d’accueil et le site États-Unis, ainsi que pour les pages produit. Il peut donc créer et modifier les activités avant qu’elles ne soient activées, mais il ne peut pas approuver le lancement d’une activité : une personne ayant les autorisations associées à un rôle d’approbateur, telle que Jeanne, doit approuver l’activité avant qu’elle ne passe en production.

   Puisqu’aucun de ses rôles ne justifie qu’il consulte les sites Russie, France ou Carrières, Ernest n’a pas accès aux activités de ces sites.

* **Diana** : Diana est analyste pour l’organisation. Elle détient les autorisations associées à son rôle d’observatrice pour la page d’accueil et le site des États-Unis, les pages produit et les sites français et russe, ce qui lui permet d’accéder aux activités en lecture seule. Elle peut visualiser des activités, mais elle ne peut pas les créer ni les modifier.

   Puisqu’aucun de ses rôles ne justifie qu’elle consulte le site Carrières, Diana n’a pas accès aux activités de ce site.

### Organisation multimarque

Si vous faites partie d’une organisation multimarque, il est possible qu’il existe un espace de travail distinct pour les pages web, propriétés ou sites de chaque marque.

Après une réorganisation, en utilisant les personnages des illustrations ci-dessus, vous pouvez configurer des projets et des autorisations semblables à ce qui suit :

* **Jeanne** : Jeanne est responsable de l’optimisation du Centre d’excellence pour une organisation de soins de santé, impliquée dans les espaces des produits hospitaliers et de consommation. Elle détient probablement les droits d’administrateur système dans Adobe Experience Cloud.

   Elle a les autorisations associées à son rôle d’approbatrice pour le site de l’hôpital. Grâce à ces autorisations, elle peut créer, modifier et activer ou interrompre les activités.

   Jeanne collabore également avec l’équipe d’optimisation de l’espace des produits de consommation et a par conséquent les autorisations associées à son rôle d’observatrice pour ce site, ce lui permet d’accéder aux activités en lecture seule. Elle peut visualiser les activités mais ne peut pas les créer ni les modifier.

* **Ernest :** Ernest est directeur marketing en charge du marketing de l’espace des produits de consommation.

   Il a rejoint l’organisation depuis peu et connaît assez mal Target. Il a donc les autorisations associées à son rôle d’éditeur pour le site dédié aux consommateurs. Il peut ainsi créer et modifier des activités avant qu’elles ne soient activées, mais il ne peut pas approuver le lancement d’une activité : une personne ayant les autorisations associées à un rôle d’approbateur pour le site dédié aux consommateurs (qui n’est pas Jeanne dans ce scénario) doit approuver l’activité avant qu’elle ne passe en production.

   Ernest n’ayant aucun rôle justifiant qu’il consulte le site de l’hôpital, il n’a pas accès aux activités de ce site.

* **Diana :** Diana est analyste pour l’organisation. Elle détient des autorisations associées à son rôle d’observatrice pour le site de l’hôpital et celui dédié aux consommateurs, ce qui lui permet d’accéder aux activités en lecture seule. Elle peut visualiser des activités, mais elle ne peut pas les créer ni les modifier.

## Points de contact des propriétés et autorisations dans l’interface utilisateur de Target {#section_3414371393BB42999A268628B5456EC9}

La nouvelle fonctionnalité Autorisations est accessible depuis différents emplacements dans l’interface utilisateur de [!DNL Target].

* **Liste déroulante Espace de travail (profil produit) :** La liste déroulante Espace de travail s’affiche en haut des pages [!UICONTROL Activités], [!UICONTROL Audiences] et [!UICONTROL Offres]. Sélectionnez l’espace de travail désiré pour filtrer la liste afin de n’afficher que les éléments situés dans l’espace de travail sélectionné.

   ![](assets/workspace_drop-down.png)

* **Création d’activité** : quand vous créez une activité, elle l’est dans l’espace de travail actif. Dans la première boîte de dialogue qui s’ouvre, vous pouvez choisir un canal pour l’activité : web, application mobile, e-mail ou autre/API.

   ![](assets/channel_options.png)

* **Création d’audience :** Lorsque vous créez une nouvelle audience, celle-ci est créée dans l’espace de travail sélectionné.
* **Création d’offre :** Lorsque vous créez une nouvelle offre, celle-ci est créée dans l’espace de travail sélectionné.
* **Page Propriétés (Configuration > Propriétés)** : utilisez le champ [!UICONTROL Rechercher] et les options [!UICONTROL Canal] et [!UICONTROL Profil produit] pour filtrer la liste [!UICONTROL Propriétés].

   ![](assets/properties_list.png)

## Avertissements {#section_9714311B1CD9497A86F4910F8AE635E2}

Prenez en compte les aspects suivants lorsque vous utilisez ou configurez des propriétés et des autorisations dans Target Premium :

* **Important** : ne supprimez pas les espaces de travail comportant des activités. Si cela se produit, contactez le service à la clientèle pour récupérer ces activités.
* Lors de l’utilisation de la vue Tous mes espaces de travail :

   * Vous pouvez voir les activités, les audiences et les offres pour tous les espaces de travail auxquels vous pouvez accéder, disposant des rôles et des autorisations appropriés.
   * Lorsque vous sélectionnez la vue Tous mes espaces de travail, une nouvelle colonne est ajoutée à la page Activités, Audiences et Offres qui répertorie l’espace de travail de l’élément et votre autorisation utilisateur associée à cet élément (observateur, éditeur ou approbateur),
   * Lorsque vous créez une activité, une audience ou une offre dans la vue Tous mes espaces de travail, vous devez sélectionner l’espace de travail dans lequel l’élément doit être créé. Seuls les espaces de travail pour lesquels vous disposez de l’autorisation éditeur ou approbateur peuvent être sélectionnés.
   * Lors de la copie d’une activité, d’une audience ou d’une offre dans la vue Tous mes espaces de travail, vous devez sélectionner l’espace de travail où l’élément doit être copié. Seuls les espaces de travail pour lesquels vous disposez de l’autorisation éditeur ou approbateur peuvent être sélectionnés.

* Tout paramètre des pages Configuration suivantes peut être contrôlé par n’importe quel approbateur dans n’importe quel espace de travail :

   * Préférences
   * Mise en œuvre
   * Paramètres de Scene7
   * Hôtes

* Les utilisateurs ne peuvent pas déplacer des ressources d’un espace de travail (profil produit) vers un autre. La copie, cependant, est prise en charge.
* Lorsque vous affichez les de la page [!DNL Audiences]Audiences, la page se charge plus lentement que prévu. Les audiences s’affichent plus rapidement si vous utilisez la barre de recherche. Il s’agit d’un problème connu, qui sera corrigé dans une mise à jour ultérieure. Ce problème n’a toutefois aucune incidence sur la sélection des audiences durant la création de l’activité.
* Les ressources suivantes font partie du nouveau modèle d’autorisations d’Enterprise :

   * Les activités, les audiences et les offres de code créées dans Target Standard/Premium après l’activation des autorisations pour le client. (Remarque : Les clients doivent avoir accès à Target Premium.)
   * Vous pouvez ajouter des propriétés à des activités existantes dans l’espace de travail par défaut. Cependant, cette fonction est sujette à changement.
   * Seules les nouvelles ressources (telles que les activités, les offres de code et les audiences) créées dans Target Premium (après l’activation des autorisations d’Enterprise) sont disponibles pour une limitation par autorisations.
   * Les ressources externes sont disponibles uniquement pour les utilisateurs de l’espace de travail par défaut. Le rôle d’un utilisateur de l’espace de travail par défaut s’applique globalement (à toutes les demandes et ressources Target).

* Les ressources suivantes ne font *pas* partie du nouveau modèle d’autorisations d’Enterprise :

   * Offres d’image
   * Toutes les ressources de recommandations, y compris la bibliothèque de critères, la bibliothèque de conception, le catalogue et la configuration des recommandations.
   * Les ressources existantes (telles que les activités, les offres de code et les audiences) créées dans Target Premium avant d’activer les autorisations d’Enterprise peuvent être copiées mais ne peuvent pas être déplacées vers d’autres espaces de travail.
   * Les activités, audiences, offres de code, offres d’images ou toute autre ressource créée à l’aide des solutions ou méthodes suivantes ne peuvent pas être contrôlées par le modèle Autorisations d’entreprise, mais font partie de l’espace de travail par défaut : Target Classic, Adobe Experience Manager (AEM), Adobe Mobile Services et les ressources créées via l’API. Ressources créées via une API (y compris les activités, les audiences, les offres de code et les offres d’images).
   * À l’heure actuelle, les offres d’images (ressources stockées sous `https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library`) ne peuvent pas être contrôlées par le modèle d’autorisations d’Enterprise.
   * Le suivi des clics et les redirections fonctionnent uniquement lorsque le lien ou la page de destination fait partie d’une propriété incluse dans l’activité. En outre, le suivi des clics peut ne pas fonctionner lorsque vous utilisez la fonction `targetPageParams()`. `targetPageParamsAll()` est la fonction recommandée.
   Actuellement, Target exige qu’un jeton `at_property` soit présent sur toutes les pages où se produit le suivi. Dans le cas où le jeton (1) n’est pas présent, (2) n’est pas détecté au moment de la configuration de l’activité (dans le compositeur d’expérience virtuelle) ou (3) n’est pas transmis à la mbox clickTracking par le biais de la fonction `targetPageParamsAll()`, la mesure ne sera pas incrémentée et s’affichera comme « 0 ».

   La même règle s’applique pour les activités utilisant les redirections. La page de destination doit comporter un jeton `at_property` et être reconnue au moment de la configuration dans le compositeur d’expérience visuelle.

   Dans une version ultérieure, Target fonctionnera sur les pages où aucun jeton `at_property` n’est présent ou sur les pages où un autre jeton `at_property` est présent.

* La fonctionnalité Autorisations des utilisateurs d’Enterprise n’est pas prise en charge dans les [appels de l’API d’Adobe I/O](https://developers.adobetarget.com).

## Questions fréquentes {#faqs}

Les questions fréquentes concernant les autorisations d’entreprise sont les suivantes :

### Puis-je déplacer une activité d’un espace de travail à un autre ?

Malheureusement, vous ne pouvez pas déplacer une activité d’un espace de travail à un autre. Cependant, vous pouvez copier une activité dans n’importe quel espace de travail, sachant que les données des rapports ne seront pas transférées. Pour plus d’informations, voir la rubrique [Copie ou édition d’une activité lors de l’utilisation des espaces de travail](../../../c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6).

Les activités créées avant la migration continuent de fonctionner de la même façon dans l’espace de travail par défaut, sauf en cas de modification ou d’allocation de propriétés. Les activités d’un espace de travail spécifique respectent les propriétés allouées à cet espace de travail. Par conséquent, leur comportement peut changer après la migration.

### Pourquoi un message d’erreur indique qu’aucune propriété n’est associée à cette activité, même si une propriété est assignée ?

Si vous avez implémenté [!DNL Target] avec [!DNL Adobe Launch] et que vous avez reçu un message d’erreur indiquant qu’aucune propriété n’est associée à l’activité, transmettez le paramètre `at_property` avec la fonction `targetPageParams`.

### Les conversions de suivi des clics sont-elles enregistrées si une page de redirection et l’URL d’activité appartiennent à des propriétés différentes ?

Le suivi des clics n’est pas enregistré sur les pages où l’URL de page et d’activité appartient à des propriétés différentes.

Examinez le scénario suivant (s’applique à la fois à at.js et à mbox.js) :

* La page 1 appartient à la Propriété 1.
* La page 2 appartient à la Propriété 2.
* Dans l’activité, la page 1 redirige vers la page 2, qui contient des traqueurs de clics.

Lorsqu’un visiteur ouvre la page 1 dans un navigateur, il est redirigé vers la page 2. Comme la page 2 ne remplit pas les critères de diffusion de l’activité, son appel Target ne contient pas de traqueurs de clics dans sa réponse.

Si la page de redirection et l’URL d’activité appartiennent à la même propriété, les traqueurs de clics fonctionnent comme prévu. Pour plus d’informations, voir [Suivi des clics](/help/c-activities/r-success-metrics/click-tracking.md).

## Vidéo de formation : Vidéo de formation sur les autorisations d’Enterprise ![badge Aperçu](/help/assets/overview.png)

Objectifs de la formation :

* Les trois niveaux de rôle que les utilisateurs d’Adobe Target peuvent détenir
* Les concepts de propriétés et d’espaces de travail, et comment ces limites et regroupements fonctionnent pour permettre le contrôle des niveaux d’accès des utilisateurs
* Différents exemples de propriétés dont votre organisation doit tenir compte

>[!VIDEO](https://video.tv.adobe.com/v/19042/)