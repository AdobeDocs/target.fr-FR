---
keywords: creating custom criteria;algorithms;criteria;recommendations criteria;csv;ftp;upload csv
description: Téléchargez un fichier CSV pour personnaliser vos recommandations.
title: Téléchargement de critères personnalisés
feature: criteria
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 63%

---


# ![PREMIUM](/help/assets/premium.png) Téléchargement de critères personnalisés{#upload-custom-criteria}

Téléchargez un fichier CSV pour personnaliser vos recommandations.

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer des critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* On the **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** library screen, click **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez une [!DNL Recommendations] activité à l’aide du compositeur [!UICONTROL d’expérience] visuelle, vous accédez immédiatement à l’écran [!UICONTROL Sélectionner les critères] après avoir sélectionné un élément sur votre page et cliqué sur [!UICONTROL Remplacer par Recommendations], Insérer Recommendations Before ou sur Insérer Recommendations After.  Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Créer des critères]**. Si vous créez un nouveau critère, vous avez la possibilité d’enregistrer vos critères pour les utiliser avec d’autres [!DNL Recommendations] activités. For more information, see [Create a Recommendations activity](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une [!DNL Recommendations] activité, cliquez sur la zone [!UICONTROL Emplacement des recommandations] sur votre page, puis sélectionnez **[!UICONTROL Changer les critères]**. On the [!UICONTROL Select Criteria] screen, click **[!UICONTROL Create Criteria]**. Vous avez la possibilité d’enregistrer les nouveaux critères afin de les utiliser avec d’autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Créer de nouveaux critères] en utilisant la première méthode : l’écran **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** de bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Télécharger des critères]** personnalisés.

1. Fill in the information in the [Basic Information](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info) section.

1. Renseignez les informations de la section Source [de](/help/c-recommendations/c-algorithms/create-new-algorithm.md#data-source) données.

1. Renseignez les informations de la section [Contenu](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content) .

1. (Conditionnel) Renseignez les informations de la section Similarité [de](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity) contenu.

1. (Conditionnel) Renseignez les informations de la section Règles [d’](/help/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) inclusion.

1. (Conditionnel) Renseignez les informations de la section Pondération [des](/help/c-recommendations/c-algorithms/create-new-algorithm.md#weighting) attributs.

1. Dans la section **[!UICONTROL Télécharger CSV]** , sélectionnez l’ **[!UICONTROL emplacement]** de votre fichier CSV.

   ![Télécharger la section CSV](/help/c-recommendations/c-algorithms/assets/upload-csv.png)

   Le fichier CSV doit être correctement formaté pour pouvoir être téléchargé. Cliquez sur **[!UICONTROL Télécharger le modèle CSV]** pour obtenir un fichier CSV correctement formaté.

   Vous avez le choix entre deux options :

   * **FTP :** Pour transférer le fichier CSV depuis un serveur FTP, sélectionnez l’option **[!UICONTROL FTP]**, puis saisissez les informations requises. Vous pouvez utiliser le chiffrement SSL, qui transfère le fichier CSV en toute sécurité au moyen du protocole FTPS.
   * **URL :** Pour télécharger votre fichier CSV à partir d’une URL, sélectionnez **[!UICONTROL URL]**, puis saisissez une URL de flux.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

   >[!NOTE]
   >
   >Les entités de critères personnalisés (lignes) peuvent comporter jusqu’à 1 000 éléments recommandés (colonnes).

Les mises à jour de critères personnalisés sont par défaut « cumulatives ». Les nouvelles paires clé-valeur spécifiées dans le fichier de chargement CSV remplacent les paires clé-valeur existantes. Les paires clé-valeur existantes qui n’ont pas de clés spécifiées dans le téléchargement CSV seront toujours disponibles pour la diffusion. Elles arriveront à expiration dans 31 jours à compter du dernier téléchargement dans le fichier CSV.

Contactez le service à la clientèle pour permettre au paramètre d’ignorer les résultats existants qui ne sont pas inclus dans le prochain chargement CSV. Si ce paramètre est activé, seules les clés présentes dans le fichier de flux CSV personnalisé seront disponibles pour la livraison. Ce paramètre s’applique à tous les critères personnalisés.

Les flux de critères personnalisés sont mis à jour une fois toutes les 24 heures.

Le statut de chargement et de synchronisation de votre chargement de critères personnalisés est visible au bas de chaque carte de critère sur la page Recommandations > Critère. Vous pouvez également voir l’état dans la boîte de dialogue Modifier lors de la modification des critères personnalisés.

Le flux d’un chargement sans erreur est composé des étapes suivantes : Planifié > Téléchargement du fichier du flux > Importation > Réussite.

The following are possible error messages you might receive if [!DNL Target] encounters a problem with the upload:

| Message d’erreur | Détails |
|--- |--- |
| Erreur inconnue | Indique une erreur technique interne. |
| Erreur d’analyse | Indique probablement un problème de format du fichier du flux. Corrigez le format du fichier et enregistrez à nouveau l’algorithme. Cela redémarre le processus de téléchargement du fichier. |
| Serveur introuvable | Fournissez une adresse IP ou un nom d’hôte visible sur Internet. |
| Erreur d’informations d’identification | Fournissez un nom d’utilisateur et un mot de passe valides pour un compte actif sur le serveur. |
| Répertoire introuvable | Fournissez un répertoire qui existe sur le serveur. |
| Fichier introuvable | Fournissez le nom d’un fichier qui existe sur le serveur dans le répertoire indiqué. |

## Vidéo de formation : Créer des critères dans Recommendations (12:33) ![Badge de didacticiel](/help/assets/tutorial.png)

Cette vidéo contient les informations suivantes (les détails sur le transfert de critères personnalisés commencent à 11h43) :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)