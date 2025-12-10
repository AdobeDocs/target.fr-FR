---
keywords: gestion de la relation client;service d’enregistrement client;crm;mbox3rdpartyid;attributs du client;ciblage;csv;crm;personnes adobe experience cloud
description: Découvrez comment utiliser les données client d’entreprise d’une base de données de gestion de la relation client (GRC) pour le ciblage de contenu dans  [!DNL Adobe Target].
title: Que sont les attributs du client et comment les utiliser ?
feature: Audiences
exl-id: 4a36230a-ae86-42a2-b6fe-60e7ab45e1a8
source-git-commit: 0b17b61bb60162af6bc35246219355077ab6bf44
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 29%

---

# Attributs du client

Informations sur l’utilisation des données client d’entreprise des bases de données de gestion de la relation client (CRM) pour le ciblage de contenu dans [!DNL Adobe Target] à l’aide des attributs du client dans le service [!DNL Adobe Experience Cloud People].

Les données client d’entreprise collectées à l’aide de plusieurs sources et stockées dans des bases de données CRM peuvent être utilisées de [!DNL Target] pour fournir stratégiquement aux clients le contenu le plus pertinent, en se concentrant spécifiquement sur les clients récurrents. Audiences et attributs du client dans le service [!DNL People] (anciennement Profils et audiences) associe la collecte et l’analyse des données aux tests et à l’optimisation, ce qui rend les données et les informations exploitables.

## Présentation des attributs du client {#section_B4099971FA4B48598294C56EAE86B45A}

[Attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html) dans le service [!DNL People] fait partie du [!DNL Adobe Experience Cloud] et fournit aux entreprises un outil pour transmettre leurs données client à la plateforme [!DNL Experience Cloud].

Les données intégrées à [!DNL Experience Cloud] sont accessibles par tous les workflows [!DNL Experience Cloud]. [!DNL Target] utilise ces données pour cibler les clients récurrents en fonction d’attributs. [!DNL Adobe Analytics] utilise ces attributs. Ils peuvent être utilisés pour l’analyse et la segmentation.

![exemple crs](/help/main/c-target/c-visitor-profile/assets/crs.png)

Tenez compte des informations suivantes dans votre travail avec les attributs et les [!DNL Target] du client :

* Vous devez respecter certaines conditions préalables avant de pouvoir utiliser la fonctionnalité [!UICONTROL Customer Attributes] dans le service [!DNL People]. Pour plus d’informations, voir « Conditions préalables pour le chargement des attributs du client » dans [Attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) dans le guide *Interface et administration d’Experience Cloud*.
* Gardez à l’esprit les limites relatives aux chargements de fichiers, comme indiqué dans la section [Fichiers et sources de données des attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=fr) du guide *Interface et administration d’Experience Cloud*. Bonne pratique :

   * Chargez uniquement des fichiers volumineux (dans les [limites spécifiées](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/crs-data-file.html?lang=fr)). Les fichiers volumineux uniques sont préférés à plusieurs fichiers plus petits.
   * Si vous devez diviser le chargement en plusieurs fichiers, assurez-vous que les fichiers sont entièrement traités avant d’envoyer de nouveaux fichiers. Assurez-vous que chaque fichier d’un lot est entièrement traité avant d’envoyer le fichier suivant du lot.

* [!DNL Adobe] ne garantit pas que 100 % des données d’attributs du client (profil du visiteur) provenant des bases de données CRM seront intégrées à la [!DNL Experience Cloud] et pourront ainsi être utilisées pour le ciblage dans [!DNL Target]. Dans la conception actuelle, il est possible qu’un petit pourcentage de données (jusqu’à 0,1 % des grands lots de production) ne soient pas intégré.
* La durée de vie des données d’attributs du client importées de [!DNL Experience Cloud] vers [!DNL Target] dépend de la durée de vie du profil du visiteur, qui est de 14 jours par défaut. Pour plus d’informations, voir [Durée de vie du profil du visiteur](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Si les paramètres `vst.*` sont les seuls éléments identifiant le visiteur, le profil « authentifié » existant ne sera pas récupéré tant que `authState` n’est PAS AUTHENTIFIÉ (0). Le profil n’entre en jeu que si `authState` est remplacé par AUTHENTIFIÉ (1).

  Par exemple, si le paramètre `vst.myDataSource.id` est utilisé pour identifier le visiteur (où `myDataSource` est l’alias de la source de données) et qu’il n’existe aucun MCID ou ID tiers, l’utilisation du paramètre `vst.myDataSource.authState=0` ne récupère pas le profil qui a pu être créé lors d’une importation d’attributs du client. Si le comportement souhaité consiste à récupérer le profil authentifié, la valeur du `vst.myDataSource.authState` doit être 1 (AUTHENTICATED).

* Vous ne pouvez pas envoyer les caractères suivants dans `mbox3rdPartyID` : signe plus (+) et barre oblique (/).

## Accéder aux attributs du client dans le service Personnes

1. Dans [!DNL Experience Cloud], cliquez sur l’icône de menu ( ![icône de menu](/help/main/c-target/c-visitor-profile/assets/menu-icon.png) ), puis sur **[!UICONTROL People]**.

   ![Personnes](/help/main/c-target/c-visitor-profile/assets/people.png)

1. Cliquez sur **[!UICONTROL Customer Attributes]**.

   ![Onglet Attributs du client](/help/main/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Workflow Attributs du client pour [!DNL Target] {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Exécutez les étapes illustrées ci-dessous pour utiliser les données CRM dans [!DNL Target] :

![workflow crm](/help/main/c-target/c-visitor-profile/assets/crm_workflow.png)

Vous trouverez des instructions détaillées pour effectuer chacune des tâches suivantes dans [Création d’une source d’attributs du client et chargement du fichier de données](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/t-crs-usecase.html) dans le guide *Interface et administration d’Experience Cloud*.

1. Création d’un fichier de données.

   Exportez les données client de votre CRM au format CSV pour créer un fichier .csv. Vous pouvez également créer un fichier zip ou gzip pour le transfert. Assurez-vous que la première ligne du fichier CSV est l’en-tête et que toutes les lignes (données client) ont le même nombre d’entrées.

   L’illustration suivante présente un exemple de fichier de données client d’entreprise :

   ![exemple crs](/help/main/c-target/c-visitor-profile/assets/CRS_sample.png)

   L’illustration suivante présente un exemple de fichier .csv client d’entreprise :

   ![exemple csv](/help/main/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Créez une source d’attributs et transférez le fichier de données.

   Spécifiez un nom et une description de la source de données ainsi que l’ID d’alias. L’ID d’alias est un ID unique à utiliser dans le code d’attributs du client dans `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >Les noms de la source de données et des attributs ne peuvent pas contenir de point.

   Votre fichier de données doit être conforme aux exigences de chargement de fichier et ne doit pas dépasser 100 Mo. Si votre fichier est trop volumineux ou que vous disposez de données qui doivent être chargées de manière récurrente, vous pouvez utiliser le FTP pour vos fichiers à la place.

   * **HTTPS :** faites glisser et déposez le fichier de données .csv ou cliquez sur **[!UICONTROL Browse]** pour effectuer un chargement à partir de votre système de fichiers.
   * **FTP :** cliquez sur le lien FTP pour [télécharger le fichier par FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). La première étape consiste à fournir un mot de passe pour le serveur FTP fourni par Adobe. Indiquez le mot de passe, puis cliquez sur **[!UICONTROL Done]**.

   Transférez maintenant le fichier CSV/ZIP/GZIP vers le serveur FTP. Une fois ce transfert de fichier réussi, créez un fichier portant le même nom et une extension `.fin`. Transférez ce fichier vide vers le serveur. Cela indique la fin du transfert et le [!DNL Experience Cloud] commence à traiter le fichier de données.

1. Validez le schéma.

   Le processus de validation permet de mapper les noms d’affichage et les descriptions aux attributs transférés (chaînes, nombres entiers, numéros, etc.). Mappez chaque attribut à son type de données, à son nom d’affichage et à sa description appropriés.

   Cliquez sur **[!UICONTROL Save]** une fois la validation du schéma terminée. La durée de transfert du fichier varie en fonction de sa taille.

   ![Validation du schéma](/help/main/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Charger le schéma](/help/main/c-target/c-visitor-profile/assets/upload1.png)

1. Configurez les abonnements et activez la source d’attributs.

   Cliquez sur **[!UICONTROL Add Subscription]**, puis sélectionnez la solution pour abonner ces attributs. [Configurer les abonnements](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) configure le flux de données entre le [!DNL Experience Cloud] et les solutions. Activez la source d’attributs pour que les données circulent vers les solutions abonnées. Les enregistrements de client que vous avez transférés sont mis en correspondance avec les signaux d’identifiants entrants issus de votre site web ou de votre application.

   ![Configurer la solution](/help/main/c-target/c-visitor-profile/assets/solution.png)

   ![Activer](/help/main/c-target/c-visitor-profile/assets/activate.png)

   Lors de l’exécution de cette étape, notez les limitations suivantes :

   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode HTTP est de 100 Mo.
   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode FTP est de 4 Go.
   * Nombre d’attributs autorisés à s’abonner : 5 pour [!DNL Target Standard] et 200 pour [!DNL Target Premium].

## Utilisation des attributs du client dans [!DNL Target] {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Vous pouvez utiliser les attributs du client dans [!DNL Target] comme suit :

### Créer des audiences de ciblage

Dans [!DNL Target], vous pouvez sélectionner un attribut du client dans la section [!UICONTROL Visitor Profile] lors de la création d’une audience. Tous les attributs client comportent le préfixe &lt; data_source_name > dans la liste. Combinez ces attributs suivant les besoins avec d’autres attributs de données afin de créer des audiences.

![audience cible](/help/main/c-target/c-visitor-profile/assets/TargetAudience.png)

### Création de scripts de profil à l’aide de jetons

Les attributs client peuvent être référencés dans les scripts de profil en utilisant le format `crs.get('<Datasource Name>.<Attribute name>')`.

Vous pouvez utiliser ce script de profil directement dans des offres pour fournir des attributs appartenant au visiteur actuel.

### Utilisez mbox3rdPartyID dans votre site web pour une implémentation et une utilisation réussies

Transmettez le `mbox3rdPartyId` en tant que paramètre à la mbox globale dans la méthode `targetPageParams()`. La valeur de `mbox3rdPartyId` doit être définie sur l’ID de client présent dans le fichier de données CSV.

```javascript
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Utilisation du service Experience Cloud ID

Si vous utilisez le service Experience Cloud ID, vous devez définir un ID de client et un état d’authentification pour utiliser les attributs du client dans le ciblage. Pour plus d’informations, voir [ID de client et état d’authentification](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) dans le guide *Service Experience Cloud ID*.

Pour plus d’informations sur l’utilisation des attributs du client dans [!DNL Target], consultez les ressources suivantes :

* [Création et chargement de données d’attributs du client](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) dans le guide *interface et administration d’Experience Cloud*

## Problèmes fréquemment rencontrés par les clients {#section_BE0F70E563F64294B17087DE2BC1E74C}

Vous pouvez rencontrer les problèmes suivants lors de l’utilisation des attributs et des [!DNL Target] du client.

>[!NOTE]
>
>Les questions 1 et 2 sont à l&#39;origine d&#39;environ 60 % des problèmes dans ce domaine. Le problème 3 est à l&#39;origine d&#39;environ 30 % des problèmes. Le problème 4 est à l&#39;origine d&#39;environ 5 % des problèmes. Les 5 % restants sont dus à des problèmes divers.

### Problème 1 : les attributs du client sont supprimés car le profil est trop grand

Il n’existe pas de limite de caractères pour un champ particulier du profil de l’utilisateur, mais si le profil dépasse 64 Ko, il est tronqué en supprimant les attributs les plus anciens jusqu’à ce que le profil soit à nouveau inférieur à 64 Ko.

### Problème 2 : attributs ne figurant pas dans la bibliothèque d’audiences d’[!DNL Target], même après plusieurs jours

Il s’agit généralement d’un problème de connexion de canal. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux.

### Problème 3 : la diffusion ne fonctionne pas en fonction de l’attribut .

Le profil n’a pas encore été mis à jour dans Edge. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux.

### Problème 4 : Problèmes de mise en œuvre

Notez les problèmes de mise en œuvre suivants :

* L’identifiant visiteur n’a pas été transmis correctement. L’identifiant a été transmis dans `mboxMCGVID` au lieu de `setCustomerId`.
* L’identifiant du visiteur a été transmis correctement, mais l’état AUTHENTIFICATION n’a pas été défini sur Authentifié.
* `mbox3rdPartyId` n’a pas été correctement transmis.

### Problème 5 : `mboxUpdate` non effectué correctement

`mboxUpdate` n’a pas été correctement effectuée avec `mbox3rdPartyId`.

### Problème 6 : les attributs du client ne sont pas importés dans [!DNL Target]

Si vous ne trouvez pas de données d’attributs du client dans Target, assurez-vous que l’importation s’est produite au cours des *x* derniers jours, où *x* est la valeur de Target [durée de vie du profil du visiteur](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) (14 jours par défaut).

## Vidéo de formation : charger des données hors ligne à l’aide des attributs du client ![Badge du tutoriel](/help/main/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Cette vidéo vous explique comment importer des données de gestion de la relation client (CRM) hors ligne, de bureau d’aide, de point de vente et d’autres données marketing dans le service [!DNL Experience Cloud People] et les associer aux visiteurs à l’aide de leurs identifiants connus.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
