---
keywords: customer relationship management;customer record service;crs;crm;mbox3rdpartyid;customer attributes;targeting;csv;crm;adobe experience cloud people
description: Informations relatives à l’utilisation des données des clients d’Enterprise provenant de bases de données CRM (gestion de la relation client ) pour le ciblage de contenu dans Adobe Target en utilisant les attributs du client dans le service principal Personnes d’Adobe Experience Cloud.
title: Attributs du client en Adobe Target
feature: visitor profiles
subtopic: Getting Started
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 42%

---


# Attributs du client {#customer-attributes}

Information about using enterprise customer data from Customer Relationship Management (CRM) databases for content targeting in [!DNL Adobe Target] by using customer attributes in the [!DNL Adobe Enterprise Cloud People] core service.

Enterprise customer data collected through multiple sources and stored inside CRM databases can be used in [!DNL Target] to strategically deliver the most relevant content to customers, specifically focusing on returning customers. Audiences and customer attributes in the [!DNL People] core service (formerly Profiles and Audiences) brings together data collection and analysis with testing and optimization, making data and insights actionable.

## Customer attributes overview {#section_B4099971FA4B48598294C56EAE86B45A}

[Les attributs](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html) du client dans le service [!DNL People] principal font partie du [!DNL Adobe Experience Cloud] et fournissent aux entreprises un outil pour transmettre leurs données client à la [!DNL Experience Cloud] plate-forme.

Les données intégrées à [!DNL Experience Cloud] sont accessibles par tous les workflows [!DNL Experience Cloud]. [!DNL Target] utilise ces données pour cibler le client qui revient en fonction d’attributs. [!DNL Adobe Analytics] utilise ces attributs. Ils peuvent être utilisés pour l’analyse et la segmentation.

![exemple crs](/help/c-target/c-visitor-profile/assets/crs.png)

Tenez compte des informations suivantes lorsque vous utilisez des attributs du client et [!DNL Target]:

* There are some prerequisite requirements that you must meet before you can use the [!UICONTROL Customer attributes] feature in the [!DNL People] core service. For more information, see &quot;Prerequisites for uploading Customer Attributes&quot; in [Customer attributes](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html#section_BD38693AFBF34926BA28E964963B4EA0) in the *Experience Cloud and Core Services Product documentation*.

   >[!NOTE]
   >
   >[!DNL at.js] (toute version) ou [!DNL mbox.js] version 58 ou ultérieure est requise.

* [!DNL Adobe] ne garantit pas que 100 % des données d’attributs du client (profil visiteur) provenant des bases de données de gestion de la relation client seront intégrées à la [!DNL Experience Cloud] et, par conséquent, seront disponibles pour le ciblage dans [!DNL Target]. Dans notre conception actuelle, il est possible qu&#39;un petit pourcentage de données (jusqu&#39;à 0,1 % des grands lots de production) ne soient pas intégrées.
* The lifetime of customer attributes data imported from the [!DNL Experience Cloud] to [!DNL Target] depends on the lifetime of the visitor profile, which is 14 days by default. Pour plus d’informations, voir [Durée de vie du profil du visiteur](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* If the `vst.*` parameters are the only thing identifying the visitor, the existing &quot;authenticated&quot; profile will not be fetched as long as `authState` is UNAUTHENTICATED (0). The profile will come into play only if `authState` is changed to AUTHENTICATED (1).

   For example, if the `vst.myDataSource.id` parameter is used to identify the visitor (where `myDataSource` is the data source alias) and there is no MCID or third-party ID, using the parameter `vst.myDataSource.authState=0` won&#39;t fetch the profile that might have been created through a Customer Attributes import. If the desired behavior is to fetch the authenticated profile, the `vst.myDataSource.authState` must have the value of 1 (AUTHENTICATED).

* Vous ne pouvez pas envoyer les caractères suivants dans `mbox3rdPartyID` : signe plus (+) et barre oblique (/).

## Accès aux attributs du client dans le service principal Personnes

1. Dans la [!DNL Adobe Experience Cloud], cliquez sur l’icône de menu ( icône ![de](/help/c-target/c-visitor-profile/assets/menu-icon.png) menu ), puis sur **[!UICONTROL Personnes]**.

   ![Personnes](/help/c-target/c-visitor-profile/assets/people.png)

1. Cliquez sur l’onglet Attributs **** du client.

   ![Onglet Attributs du client](/help/c-target/c-visitor-profile/assets/customer-attributes-tab.png)

## Customer attribute workflow for Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Exécutez les étapes illustrées ci-dessous pour utiliser les données CRM dans [!DNL Target] :

![flux de travaux crm](/help/c-target/c-visitor-profile/assets/crm_workflow.png)

Detailed instructions for completing each of the following tasks can be found in [Create a customer attribute source and upload the data file](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) in the *Experience Cloud and Core Services Product Documentation*.

1. Création d’un fichier de données.

   Exportez les données client du format CRM au format CSV pour créer un fichier .csv. Vous pouvez également créer un fichier zip ou gzip pour le transfert. Assurez-vous que la première ligne du fichier CSV correspond à l’en-tête et que toutes les lignes (données client) comportent le même nombre d’entrées.

   L’illustration suivante présente un exemple de fichier de données client d’entreprise :

   ![exemple crs](/help/c-target/c-visitor-profile/assets/CRS_sample.png)

   L’illustration suivante présente un exemple de fichier .csv client d’entreprise :

   ![exemple csv](/help/c-target/c-visitor-profile/assets/CRS_CSV_sample.png)

1. Créez une source d’attributs et transférez le fichier de données.

   Spécifiez un nom et une description de la source de données ainsi que l’ID d’alias. L’ID d’alias est un identifiant unique à utiliser dans le code d’attribut du client dans `VisitorAPI.js`.

   >[!IMPORTANT]
   >
   >Les noms de la source de données et des attributs ne peuvent pas contenir de point.

   Votre fichier de données doit être conforme aux exigences de téléchargement des fichiers et ne doit pas dépasser 100 Mo. Si votre fichier est trop volumineux ou si vous disposez de données qui devront être téléchargées de façon récurrente, vous pouvez FTP vos fichiers à la place.

   * **HTTPS :** Vous pouvez faire glisser le fichier de données .csv ou cliquer sur **[!UICONTROL Parcourir]** pour le télécharger à partir de votre système de fichiers.
   * **FTP :** Cliquez sur le lien FTP pour [télécharger le fichier par FTP](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-upload-attributes-ftp.html). La première étape consiste à fournir un mot de passe pour le serveur FTP fourni par Adobe. Specify the password, then click **[!UICONTROL Done]**.

   Transférez maintenant le fichier CSV/ZIP/GZIP vers le serveur FTP. Une fois que ce transfert de fichier a réussi, créez un nouveau fichier portant le même nom et l’extension .fin. Transférez ce fichier vide vers le serveur. This indicates a End Of Transfer and the [!DNL Experience Cloud] starts to process the data file.

1. Validez le schéma.

   Le processus de validation permet de mapper les noms d’affichage et les descriptions aux attributs transférés (chaînes, nombres entiers, numéros, etc.). Mappez chaque attribut à son type de données, à son nom d’affichage et à sa description appropriés.

   Click **[!UICONTROL Save]** after the schema validation is complete. La durée de transfert du fichier varie en fonction de sa taille.

   ![Valider le schéma](/help/c-target/c-visitor-profile/assets/SchemaValidate.png)

   ![Schéma de transfert](/help/c-target/c-visitor-profile/assets/upload1.png)

1. Configurez les abonnements et activez la source d’attributs.

   Cliquez sur **[!UICONTROL Ajouter un abonnement]**, puis sélectionnez la solution pour abonner ces attributs. [Configurez les abonnements](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/subscription.html) pour configurer le flux de données entre les solutions [!DNL Experience Cloud] et. Activez la source d’attributs pour que les données circulent vers les solutions abonnées. Les enregistrements de client que vous avez transférés sont mis en correspondance avec les signaux d’identifiants entrants issus de votre site web ou de votre application.

   ![Configuration de la solution](/help/c-target/c-visitor-profile/assets/solution.png)

   ![Activer](/help/c-target/c-visitor-profile/assets/activate.png)

   Lors de l’exécution de cette étape, notez les limitations suivantes :

   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode HTTP est de 100 Mo.
   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode FTP est de 4 Go.
   * Nombre d’attributs autorisés à s’abonner : 5 pour [!DNL Target Standard] et 200 pour [!DNL Target Premium].

## Utilisation des attributs du client dans Target {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Vous pouvez utiliser les attributs du client dans [!DNL Target] comme suit :

### Création des audiences ciblées

Dans [!DNL Target], vous pouvez sélectionner un attribut du client à partir de la section Profil du visiteur lors de la création d’une audience.  Tous les attributs client comportent le préfixe &lt; data_source_name > dans la liste. Combinez ces attributs suivant les besoins avec d’autres attributs de données afin de créer des audiences.

![Public cible](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### Création de scripts de profil à l’aide de jetons

Les attributs client peuvent être référencés dans les scripts de profil en utilisant le format `crs.get('<Datasource Name>.<Attribute name>')`.

Vous pouvez utiliser ce script de profil directement dans des offres pour fournir des attributs appartenant au visiteur actuel.

### Utilisation de mbox3rdPartyID sur votre site web pour une mise en œuvre et une utilisation réussies

Pass `mbox3rdPartyId` as a parameter to the global mbox inside the `targetPageParams()` method. The value of `mbox3rdPartyId` should be set to the customer ID that was present in the CSV data file.

```
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Utilisation du service Experience Cloud ID

Si vous utilisez le service Experience Cloud ID, vous devez définir un ID de client et un état d’authentification pour utiliser les attributs du client dans le ciblage. For more information, see [Customer IDs and Authentication State](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) in the *Experience Cloud Identity Service Help*.

Pour plus d’informations sur l’utilisation des attributs du client dans [!DNL Target], voir les ressources suivantes :

* [Créez une source d’attributs du client et téléchargez le fichier](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html) de données dans la documentation du produit *Experience Cloud.*
* [Attributs du client : plus vous en savez, mieux vous êtes connecté](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) dans le blog du marketing numérique *Digital Marketing Blog*

## Issues frequently encountered by customers {#section_BE0F70E563F64294B17087DE2BC1E74C}

You might encounter the following issues when working with customer attributes and [!DNL Target].

>[!NOTE]
>
>Les questions 1 et 2 causent environ 60 % des problèmes dans ce domaine. La question 3 entraîne environ 30 % des problèmes. La question 4 est à l&#39;origine d&#39;environ 5 % des problèmes. Les 5 % restants sont dus à des problèmes divers.

### Question 1 : Les attributs du client sont supprimés car le profil est trop volumineux

Il n’existe pas de limite de caractères pour un champ particulier du profil de l’utilisateur, mais si le profil dépasse 64 Ko, il est tronqué en supprimant les attributs les plus anciens jusqu’à ce que le profil soit à nouveau inférieur à 64 Ko.

### Issue 2: Attributes not listing in the Audience Library in [!DNL Target], even after several days

Il s’agit généralement d’un problème de connexion de canal. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux.

### Question 3 : La diffusion ne fonctionne pas en fonction de l&#39;attribut

Le profil n’a pas encore été mis à jour dans Edge. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux.

### Question 4 : Problèmes de mise en oeuvre

Notez les problèmes de mise en œuvre suivants :

* L’identifiant visiteur n’a pas été transmis correctement. The ID was passed in `mboxMCGVID` instead of `setCustomerId`.
* L’identifiant du visiteur a été transmis correctement, mais l’état AUTHENTIFICATION n’a pas été défini sur Authentifié.
* `mbox3rdPartyId` n’a pas été correctement transmis.

### Question 5 : `mboxUpdate` non effectué correctement

`mboxUpdate` ne s’est pas exécuté correctement avec `mbox3rdPartyId`.

### Issue 6: Customer attributes are not being imported into [!DNL Target]

If you cannot find Customer Attributes data in Target, ensure that the import occurred within the last *x* days where *x* is the Target [Visitor Profile Lifetime](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) value (14 days by default).

## Training video: Upload Offline Data using Customer Attributes ![Tutorial badge](/help/assets/tutorial.png) {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

This video shows you how to import offline CRM, help desk, point-of-sale, and other marketing data into the [!DNL Experience Cloud People] service and associate it with visitors using their known IDs.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
