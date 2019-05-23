---
description: Informations relatives à l’utilisation des données des clients d’Enterprise provenant de bases de données CRM (gestion de la relation client ) pour le ciblage de contenu dans Adobe Target en utilisant les attributs du client dans le service principal Profils et audiences d’Adobe.
keywords: service d’enregistrement clients;crs;crm;mbox3rdpartyid;attributs client;ciblage
seo-description: Informations relatives à l’utilisation des données des clients d’Enterprise provenant de bases de données CRM (gestion de la relation client ) pour le ciblage de contenu dans Adobe Target en utilisant les attributs du client dans le service principal Profils et audiences d’Adobe.
seo-title: Attributs du client
solution: Target
subtopic: Prise en main
title: Attributs du client
topic: Standard
uuid: fc3c9a02-30d7-43df-838d-10ce1aa17f16
translation-type: tm+mt
source-git-commit: f0c1a87c82dcdaad48568b20db8619690ca13c30

---


# Attributs du client{#customer-attributes}

Informations relatives à l’utilisation des données des clients d’Enterprise provenant de bases de données CRM (gestion de la relation client ) pour le ciblage de contenu dans Adobe Target en utilisant les attributs du client dans le service principal Profils et audiences d’Adobe.

Les données sur les clients d’Enterprise collectées à partir de plusieurs sources et stockées dans une base de données CRM (gestion de la relation client) peuvent être utilisées dans [!DNL Target] pour fournir stratégiquement le contenu le plus pertinent aux clients, en se concentrant spécifiquement sur les clients récurrents. Le service principal [!DNL People] (anciennement Profils et Audiences) regroupe la collecte et l’analyse des données avec les tests et l’optimisation, ce qui rend les données et les observations exploitables.

## Présentation des attributs du client {#section_B4099971FA4B48598294C56EAE86B45A}

Le service principal Personnes fait partie de [!DNL Adobe Experience Cloud] et fournit aux entreprises un outil permettant de transférer leurs données clients vers la plateforme [!DNL Experience Cloud]. Les données intégrées à [!DNL Experience Cloud] sont accessibles par tous les workflows [!DNL Experience Cloud]. [!DNL Adobe Target] utilise ces données pour cibler le client récurrent en fonction d’attributs. [!DNL Adobe Analytics] utilise ces attributs. Ils peuvent être utilisés pour l’analyse et la segmentation.

![](assets/crs.png)

Tenez compte des informations suivantes lorsque vous utilisez des attributs du client et Target :

* Vous devez respecter certaines conditions requises pour pouvoir utiliser la fonctionnalité [!UICONTROL Attributs du client] dans le service principal [!DNL People]. Pour plus d’informations, voir « Conditions requises pour le transfert des attributs du client » de la page [Attributs du client](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) de la *Documentation du produit sur Experience Cloud et les services principaux*. Notez que [!DNL at.js] (toute version) ou [!DNL mbox.js] version 58 ou ultérieure est requise.
* Adobe ne garantit pas que 100 % des données d’attributs du client (profil du visiteur) provenant des bases de données CRM seront intégrées à Experience Cloud et pourront ainsi être utilisées pour le ciblage dans Target. Dans notre conception actuelle, il est possible qu’un petit pourcentage de données ne soit pas intégré.
* La durée de vie des données d’attributs du client importées depuis Experience Cloud vers Target dépend de la durée de vie du profil du visiteur, qui est de 14 jours par défaut. Pour plus d’informations, voir [Durée de vie du profil du visiteur](../../c-target/c-visitor-profile/visitor-profile-lifetime.md#concept_D9F21B416F1F49159F03036BA2DD54FD).
* Si les paramètres `vst.*` sont les seuls éléments d’identification de l’utilisateur, le profil « authentifié » existant ne sera pas récupéré tant que `authState` reste NON-IDENTIFIE (0). Le profil est uniquement récupéré si `authState` passe à UNAUTHENTICATED (1).

   Par exemple, si le paramètre `vst.myDataSource.id` est utilisé pour identifier l’utilisateur (où `myDataSource` est l’alias de la source de données) et qu’il n’y a aucun MCID ou ID tiers, l’utilisation du paramètre `vst.myDataSource.authState=0` ne permet pas de récupérer le profil, qui peut avoir été créé par une importation des attributs du client. Si le comportement souhaité consiste à récupérer le profil authentifié, le paramètre `vst.myDataSource.authState` doit avoir la valeur 1 (AUTHENTICATED).

* Vous ne pouvez pas envoyer les caractères suivants dans `mbox3rdPartyID`: signe plus (+) et barre oblique (/).

## Processus des attributs du client pour Target {#section_00DAE94DA9BA41398B6FD170BC7D38A3}

Exécutez les étapes illustrées ci-dessous pour utiliser les données CRM dans [!DNL Target] :

![](assets/crm_workflow.png)

Vous trouverez des instructions détaillées sur la réalisation de chacune des tâches suivantes dans [Création d’une source d’attributs du client et transfert du fichier de données](https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html) dans la *Documentation du produit sur Experience Cloud et les services principaux*.

1. Création d’un fichier de données.

   Exportez les données client du format CRM au format CSV pour créer un fichier [!DNL .csv]. Vous pouvez également créer un fichier zip ou gzip pour le transfert. Assurez-vous que la première ligne du fichier CSV est l’en-tête et que toutes les lignes (données client) ont le même nombre d’entrées.

   ![](assets/CRS_sample.png)

   ![](assets/CRS_CSV_sample.png)

1. Créez une source d’attributs et transférez le fichier de données.

   Spécifiez un nom et une description de la source de données ainsi que l’ID d’alias. L’ID d’alias est un identifiant unique à utiliser dans le code d’attribut du client dans VisitorAPI.js.

   >[!IMPORTANT]
   >
   >Les noms de la source de données et des attributs ne peuvent pas contenir de point.

   Les fichiers de données jusqu’à 100 Mo peuvent être transférés à l’aide de la méthode HTTP. Les fichiers de plus de 100 Mo, jusqu’à 4 Go, peuvent être transférés par FTP.

   * **HTTPS :** vous pouvez faire glisser-déposer le fichier de données [!DNL .csv] ou cliquer sur [!UICONTROL Parcourir] pour télécharger le fichier depuis votre système de fichiers.
   * **FTP :** cliquez sur le lien FTP pour [transférer le fichier par FTP](https://marketing.adobe.com/resources/help/en_US/mcloud/t_upload_attributes_ftp.html). La première étape consiste à fournir un mot de passe pour le serveur FTP fourni par Adobe. Saisissez le mot de passe, puis cliquez sur [!UICONTROL Terminé].

      Transférez maintenant le fichier CSV/ZIP/GZIP vers le serveur FTP. Une fois le transfert de fichier réussi, créez un nouveau fichier portant le même nom et l’extension [!DNL .fin]. Transférez ce fichier vide vers le serveur. Une fin de transfert est indiquée et Experience Cloud commence à traiter le fichier de données.

1. Validez le schéma.

   Le processus de validation permet de mapper les noms d’affichage et les descriptions aux attributs transférés (chaînes, nombres entiers, numéros, etc.). Mappez chaque attribut à son type de données, à son nom d’affichage et à sa description appropriés.

   Cliquez sur [!UICONTROL Enregistrer] une fois la validation du schéma terminée. La durée de transfert du fichier varie en fonction de sa taille.

   ![](assets/SchemaValidate.png)

   ![](assets/upload1.png)

1. Configurez les abonnements et activez la source d’attributs.

   Cliquez sur **[!UICONTROL Ajouter un abonnement]**, puis sélectionnez la solution pour abonner ces attributs. La [Configuration des abonnements](https://marketing.adobe.com/resources/help/en_US/mcloud/subscription.html) configure le flux de données entre Experience Cloud et les solutions. Activez la source d’attributs pour que les données circulent vers les solutions abonnées. Les enregistrements de client que vous avez transférés sont mis en correspondance avec les signaux d’identifiants entrants issus de votre site web ou de votre application.

   ![](assets/solution.png)

   ![](assets/activate.PNG)

   Lors de l’exécution de cette étape, notez les limitations suivantes :

   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode HTTP est de 100 Mo.
   * La taille maximale du fichier pour chaque transfert à l’aide de la méthode FTP est de 4 Go.
   * Nombre d’attributs autorisés à s’abonner : 5 pour [!DNL Target Standard] et 200 pour [!DNL Target Premium].

## Utilisation des attributs du client dans Target {#section_107E3A0F0EC7478E82E6DBD17B30B756}

Vous pouvez utiliser les attributs du client dans [!DNL Target] comme suit :

### Création des audiences ciblées

Dans [!DNL Target], vous pouvez sélectionner un attribut du client à partir de la section Profil du visiteur lors de la création d’une audience. Tous les attributs du client comportent le préfixe &lt; data_ source_ name &gt; dans la liste. Combinez ces attributs suivant les besoins avec d’autres attributs de données afin de créer des audiences.

![Public cible](/help/c-target/c-visitor-profile/assets/TargetAudience.png)

### Création de scripts de profil à l’aide de jetons

Les attributs client peuvent être référencés dans les scripts de profil en utilisant le format `crs.get('<Datasource Name>.<Attribute name>')`.

Vous pouvez utiliser ce script de profil directement dans des offres pour fournir des attributs appartenant au visiteur actuel.

### Utilisation de mbox3rdPartyID sur votre site web pour une mise en œuvre et une utilisation réussies

Passez mbox3rdPartyId en paramètre de la mbox globale dans la méthode `targetPageParams()`. La valeur de mbox3rdPartyId doit être définie sur l’ID de client présent dans le fichier de données CSV.

```
<script type="text/javascript">
            function targetPageParams() {
               return 'mbox3rdPartyId=2000578';
            }
</script>
```

### Utilisation du service Experience Cloud ID

Si vous utilisez le service Experience Cloud ID, vous devez définir un ID de client et un état d’authentification pour utiliser les attributs du client dans le ciblage. Pour plus d’informations, voir [ID de client et états d’authentification](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html) dans la documentation du *Service Experience Cloud ID*.

Pour plus d’informations sur l’utilisation des attributs du client dans [!DNL Target], voir les ressources suivantes :

* [Création d’une source d’attributs du client et transfert du fichier de données](https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html) dans la *Documentation du produit sur Experience Cloud et les services principaux*
* [Attributs du client : plus vous en savez, mieux vous êtes connecté](https://blogs.adobe.com/digitalmarketing/analytics/customer-attributes-know-better-connect/) dans le blog du marketing numérique *Digital Marketing Blog*

## Problèmes fréquemment rencontrés par les clients {#section_BE0F70E563F64294B17087DE2BC1E74C}

Vous risquez de rencontrer les problèmes suivants lorsque vous utilisez les attributs du client et [!DNL Target] :

| Problème | Détails |
|--- |--- |
| Attributs du client supprimés car le profil est trop volumineux | Il n’existe pas de limite de caractères pour un champ particulier du profil de l’utilisateur, mais si le profil dépasse 64 Ko, il est tronqué en supprimant les attributs les plus anciens jusqu’à ce que le profil soit à nouveau inférieur à 64 Ko. |
| Attributs ne figurant pas dans la bibliothèque d’audiences de [!DNL Target], même après plusieurs jours | Il s’agit généralement d’un problème de connexion de canal. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux. |
| La diffusion ne fonctionne pas en fonction de l’attribut | Le profil n’a pas encore été mis à jour dans Edge. Comme résolution, demandez à l’équipe chargée des attributs du client de republier le flux. |
| Problèmes de mise en œuvre | Notez les problèmes de mise en œuvre suivants :<ul><li>L’identifiant visiteur n’a pas été transmis correctement. L’identifiant a été transmis dans mboxMCGVID au lieu de `setCustomerId`.</li><li>L’identifiant du visiteur a été transmis correctement, mais l’état AUTHENTIFICATION n’a pas été défini sur Authentifié.</li><li>`mbox3rdPartyId` n’a pas été correctement transmis.</li> |
| `mboxUpdate` n’a pas été exécuté correctement | mboxUpdate ne s’est pas exécuté correctement avec `mbox3rdPartyId`. |
| Les attributs du client ne sont pas importés dans Target. | Si vous ne trouvez pas les données Attributs Client dans Target, vérifiez que l’importation s’est déroulée au cours des x derniers jours où x correspond à la valeur [Durée de vie du profil visiteur](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) Target (14 jours par défaut). |

Les problèmes des lignes 1 et 2 ci-dessus causent environ 60 % des problèmes dans ce domaine. Les problèmes de la ligne 3 causent environ 30 % des problèmes. Le problème de la ligne 4 cause environ 5 % des problèmes. Les 5 % restants sont dus à des problèmes divers.

## Vidéo de formation : téléchargement de données hors ligne à l’aide des Attributs client {#section_9A4E0FA0D0934D06BD8D5BFA673E9BD8}

Cette vidéo indique comment importer des données de gestion de la relation client hors ligne, d’assistance, de point de vente et autres données marketing dans le service Experience Cloud People et associer ces données aux visiteurs à l’aide de leurs ID connus.

>[!VIDEO](https://video.tv.adobe.com/v/17802t1/)
