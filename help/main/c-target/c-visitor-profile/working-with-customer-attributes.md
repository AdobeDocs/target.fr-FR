---
keywords: gestion des relations client;service d’enregistrement client;crs;crm;mbox3rdpartyid;attributs du client;ciblage;csv;crm;personnes adobe experience cloud
description: Découvrez comment utiliser les données clients d’entreprise d’une base de données de gestion de la relation client pour le ciblage de contenu dans  [!DNL Adobe Target].
title: Quels sont les attributs du client et comment les utiliser ?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1513'
ht-degree: 32%

---

# Attributs du client

Informations sur l’utilisation des données des clients d’Enterprise provenant de bases de données CRM (Customer Relationship Management) pour le ciblage de contenu dans [!DNL Adobe Target] en utilisant les attributs du client dans le service [!DNL Adobe Enterprise Cloud People].

Les données des clients d’entreprise collectées à partir de plusieurs sources et stockées dans des bases de données CRM peuvent être utilisées dans [!DNL Target] pour fournir stratégiquement le contenu le plus pertinent aux clients, en se concentrant spécifiquement sur les clients récurrents. Les audiences et les attributs du client dans le service [!DNL People] (anciennement Profiles and Audiences) rassemblent la collecte et l’analyse de données avec les tests et l’optimisation, ce qui rend les données et les informations exploitables.

## Présentation des attributs du client {#section_B4099971FA4B48598294C56EAE86B45A}

[Attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html?lang=fr) dans le service [!DNL People] fait partie de [!DNL Adobe Experience Cloud] et fournit aux entreprises un outil pour transmettre leurs données client à la plateforme [!DNL Experience Cloud].

Les données intégrées à [!DNL Experience Cloud] sont accessibles par tous les workflows [!DNL Experience Cloud]. [!DNL Target] utilise ces données pour cibler le client récurrent en fonction d’attributs. [!DNL Adobe Analytics] utilise ces attributs. Ils peuvent être utilisés pour l’analyse et la segmentation.

![Exemple de crs](/help/main/c-target/c-visitor-profile/assets/crs.png)

Tenez compte des informations suivantes dans votre travail avec les attributs du client et [!DNL Target] :

* Vous devez respecter certaines conditions préalables requises pour pouvoir utiliser la fonction [!UICONTROL Customer attributes] dans le service [!DNL People]. Pour plus d’informations, voir &quot;Conditions préalables au téléchargement des attributs du client&quot; dans [Attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=fr#section_BD38693AFBF34926BA28E964963B4EA0) dans la *documentation sur les services et l’administration Experience Cloud*.
* Gardez à l’esprit les limites relatives aux chargements de fichiers, comme indiqué dans la section [À propos du fichier de données et des sources de données pour les attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=fr) du *Guide des composants de l’interface centrale Experience Cloud*. Bonne pratique :

   * Chargez des fichiers volumineux uniques (dans les [limites spécifiées](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=fr)). Les fichiers volumineux uniques sont préférés aux fichiers plus petits.
   * Si vous devez diviser le chargement en plusieurs fichiers, assurez-vous qu’ils sont entièrement traités avant d’envoyer de nouveaux fichiers. Assurez-vous que chaque fichier d’un lot est entièrement traité avant d’envoyer le fichier suivant dans le lot.

* [!DNL Adobe] ne garantit pas que 100 % des données d’attributs du client (profil du visiteur) provenant des bases de données CRM seront intégrées à [!DNL Experience Cloud] et, par conséquent, seront disponibles pour un ciblage dans [!DNL Target]. Dans la conception actuelle, il est possible qu’un faible pourcentage de données (jusqu’à 0,1 % des grands lots de production) ne soient pas intégrées.
* La durée de vie des données d’attributs du client importées de [!DNL Experience Cloud] vers [!DNL Target] dépend de la durée de vie du profil du visiteur, qui est de 14 jours par défaut. Pour plus d’informations, voir [Durée de vie du profil du visiteur](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Si les paramètres `vst.*` sont la seule chose qui identifie le visiteur, le profil &quot;authentifié&quot; existant ne sera pas récupéré tant que `authState` est NON-IDENTIFIÉ (0). Le profil entre en jeu uniquement si `authState` est remplacé par AUTHENTICATED (1).

  Par exemple, si le paramètre `vst.myDataSource.id` est utilisé pour identifier le visiteur (où `myDataSource` est l’alias de la source de données) et qu’il n’existe aucun MCID ou ID tiers, l’utilisation du paramètre `vst.myDataSource.authState=0` ne permet pas de récupérer le profil qui peut avoir été créé par le biais d’une importation des attributs du client. Si le comportement souhaité consiste à récupérer le profil authentifié, la valeur de `vst.myDataSource.authState` doit être 1 (AUTHENTICATED).

* Vous ne pouvez pas envoyer les caractères suivants dans `mbox3rdPartyID` : signe plus (+) et barre oblique (/).

## Accès aux attributs du client dans le service People

1. Dans [!DNL Adobe Experience Cloud], cliquez sur l’icône de menu ( ![icône de menu](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ), puis sur **[!UICONTROL People]**.

   ![Personnes](/help/main/c-target/c-visitor-profile/assets/people.png)

1. Cliquez sur l’onglet **[!UICONTROL Customer Attributes]** .

   ![Onglet Attributs du client](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Workflow d’attributs du client pour [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Exécutez les étapes illustrées ci-dessous pour utiliser les données CRM dans [!DNL Target] :

![workflow crm](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

Vous trouverez des instructions détaillées sur la réalisation de chacune des tâches suivantes dans la section [Création d’une source d’attributs du client et transfert du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html?lang=fr) de la *documentation sur les services et l’administration des Experience Cloud*.

1. Création d’un fichier de données.

   Exportez les données client du format CRM au format CSV pour créer un fichier .csv. Vous pouvez également créer un fichier zip ou gzip pour le transfert. Assurez-vous que la première ligne du fichier CSV est l’en-tête et que toutes les lignes (données client) ont le même nombre d’entrées.

   L’illustration suivante présente un exemple de fichier de données client d’entreprise :

   ![crs sample](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   L’illustration suivante présente un exemple de fichier .csv client d’entreprise :

   ![exemple csv](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Créez une source d’attributs et transférez le fichier de données.

   Spécifiez un nom et une description de la source de données ainsi que l’ID d’alias. L’ID d’alias est un ID unique à utiliser dans votre code d’attribut du client dans `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >Les noms de la source de données et des attributs ne peuvent pas contenir de point.

   Votre fichier de données doit respecter les exigences en matière de téléchargement de fichier et ne doit pas dépasser 100 Mo. Si votre fichier est trop volumineux ou si vous disposez de données à charger de manière récurrente, vous pouvez transférer vos fichiers par FTP.

   * **HTTPS :** Vous pouvez faire glisser et déposer le fichier de données .csv ou cliquer sur **[!UICONTROL Browse]** pour le charger à partir de votre système de fichiers.
   * **FTP :** Cliquez sur le lien FTP pour [télécharger le fichier par FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html?lang=fr). La première étape consiste à fournir un mot de passe pour le serveur FTP fourni par Adobe. Indiquez le mot de passe, puis cliquez sur **[!UICONTROL Done]**.

   Transférez maintenant le fichier CSV/ZIP/GZIP vers le serveur FTP. Une fois le transfert de fichier réussi, créez un fichier portant le même nom et une extension `.fin`. Transférez ce fichier vide vers le serveur. Cela indique une fin de transfert et [!DNL Experience Cloud] commence à traiter le fichier de données.

1. Validez le schéma.

   Le processus de validation permet de mapper les noms d’affichage et les descriptions aux attributs transférés (chaînes, nombres entiers, numéros, etc.). Mappez chaque attribut à son type de données, à son nom d’affichage et à sa description appropriés.

   Cliquez sur **[!UICONTROL Save]** une fois la validation du schéma terminée. La durée de transfert du fichier varie en fonction de sa taille.

   ![Valider le schéma](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Télécharger le schéma](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. Configurez les abonnements et activez la source d’attributs.

   Cliquez sur **[!UICONTROL Add Subscription]**, puis sélectionnez la solution pour abonner ces attributs. [ Configurez les abonnements ](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html?lang=fr) pour configurer le flux de données entre [!DNL Experience Cloud] et les solutions. Activez la source d’attributs pour que les données circulent vers les solutions abonnées. Les enregistrements de client que vous avez transférés sont mis en correspondance avec les signaux d’identifiants entrants issus de votre site web ou de votre application.

   ![Configurer la solution](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![Activer](/help/main/c-target/c-visitor-profile/assets/activate.png)

   Lors de l’exécution de cette étape, notez les limitations suivantes :

   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode HTTP est de 100 Mo.
   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode FTP est de 4 Go.
   * Nombre d’attributs autorisés à s’abonner : 5 pour [!DNL Target Standard] et 200 pour [!DNL Target Premium].

## Utilisation des attributs du client dans [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Vous pouvez utiliser les attributs du client dans [!DNL Target] comme suit :

### Création des audiences ciblées

Dans [!DNL Target], vous pouvez sélectionner un attribut du client à partir de la section [!UICONTROL Visitor Profile] lors de la création d’une audience. Tous les attributs client comportent le préfixe &lt; data_source_name > dans la liste. Combinez ces attributs suivant les besoins avec d’autres attributs de données afin de créer des audiences.

![Public cible](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### Création de scripts de profil à l’aide de jetons

Les attributs client peuvent être référencés dans les scripts de profil en utilisant le format `crs.get('<Datasource Name>.<Attribute name>')`.

Vous pouvez utiliser ce script de profil directement dans des offres pour fournir des attributs appartenant au visiteur actuel.

### Utilisation de mbox3rdPartyID sur votre site web pour une mise en œuvre et une utilisation réussies

Transmettez `mbox3rdPartyId` comme paramètre à la mbox globale dans la méthode `targetPageParams()`. La valeur de `mbox3rdPartyId` doit être définie sur l’ID de client présent dans le fichier de données CSV.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Utilisation du service Experience Cloud ID

Si vous utilisez le service d’ID d’Experience Cloud, vous devez définir un ID de client et un état d’authentification afin d’utiliser les attributs du client dans le ciblage. Pour plus d’informations, voir [ID de client et état d’authentification](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=fr) dans l’ *aide du service d’ID Experience Cloud*.

Pour plus d’informations sur l’utilisation des attributs du client dans [!DNL Target], voir les ressources suivantes :

* [Créez une source d’attributs du client et chargez le fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html?lang=fr) dans la *documentation sur les services et l’administration Experience Cloud*

## Problèmes fréquemment rencontrés par les clients {#section_BE0F70E563F64294B17087DE2BC1E74C}

Vous pouvez rencontrer les problèmes suivants lorsque vous utilisez les attributs du client et [!DNL Target].

>[!NOTE]
>
>Les problèmes 1 et 2 causent environ 60 % des problèmes dans ce domaine. Le problème 3 provoque environ 30 % des problèmes. Le problème 4 provoque environ 5 % des problèmes. Les 5 % restants sont dus à des problèmes divers.

### Problème 1 : les attributs du client sont supprimés car le profil est trop volumineux

Il n’existe pas de limite de caractères pour un champ particulier du profil de l’utilisateur, mais si le profil dépasse 64 Ko, il est tronqué en supprimant les attributs les plus anciens jusqu’à ce que le profil soit à nouveau inférieur à 64 Ko.

### Problème 2 : Attributs ne figurant pas dans la bibliothèque d’audiences de [!DNL Target], même après plusieurs jours

Il s’agit généralement d’un problème de connexion de canal. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux.

### Problème 3 : la diffusion ne fonctionne pas en fonction de l’attribut

Le profil n’a pas encore été mis à jour dans Edge. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux.

### Problème 4 : Problèmes de mise en oeuvre

Notez les problèmes de mise en œuvre suivants :

* L’identifiant visiteur n’a pas été transmis correctement. L’ID a été transmis dans `mboxMCGVID` au lieu de `setCustomerId`.
* L’identifiant du visiteur a été transmis correctement, mais l’état AUTHENTIFICATION n’a pas été défini sur Authentifié.
* `mbox3rdPartyId` n’a pas été correctement transmis.

### Problème 5 : `mboxUpdate` non exécuté correctement

`mboxUpdate` n&#39;a pas été exécuté correctement avec `mbox3rdPartyId`.

### Problème 6 : les attributs du client ne sont pas importés dans [!DNL Target]

Si vous ne trouvez pas les données Attributs du client dans Target, assurez-vous que l’importation s’est déroulée au cours des derniers *x* jours où *x* est la valeur [Durée de vie du profil du visiteur](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) cible (14 jours par défaut).

## Vidéo de formation : téléchargement de données hors ligne à l’aide des attributs du client ![Badge du tutoriel](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Cette vidéo vous explique comment importer des données de gestion de la relation client hors ligne, d’assistance, de point de vente et autres données marketing dans le service [!DNL Experience Cloud People] et les associer aux visiteurs à l’aide de leurs identifiants connus.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
