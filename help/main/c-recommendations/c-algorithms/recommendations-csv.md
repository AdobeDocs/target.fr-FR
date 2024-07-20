---
keywords: création de critères personnalisés;algorithmes;critères;critères de recommandations;csv;ftp;télécharger un csv
description: Découvrez comment télécharger un fichier CSV pour personnaliser vos recommandations dans Adobe [!DNL Target] Recommendations.
title: Comment télécharger des critères personnalisés dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Découvrez les fonctionnalités incluses dans Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 32%

---

# Téléchargement de critères personnalisés

Téléchargez un fichier CSV pour personnaliser vos recommandations dans [!DNL Adobe Target].

Il existe plusieurs façons d’accéder à l’écran [!UICONTROL Create New Criteria]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur l’écran de la bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, cliquez sur **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez une activité [!DNL Recommendations] à l’aide du [!UICONTROL Visual Experience Composer] (VEC), vous accédez immédiatement à l’écran [!UICONTROL Select Criteria] après avoir sélectionné un élément sur votre page et cliqué sur [!UICONTROL Replace w/ Recommendations], [!UICONTROL Insert Recommendations Before] ou [!UICONTROL Insert Recommendations After]. Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Create Criteria]**. Si vous créez un nouveau critère, vous pouvez enregistrer votre critère pour l’utiliser avec d’autres activités [!DNL Recommendations]. Pour plus d’informations, voir [Création d’une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une activité [!DNL Recommendations], cliquez dans la zone [!UICONTROL Recommendations Location] de votre page, puis sélectionnez **[!UICONTROL Change Criteria]**. Sur l’écran [!UICONTROL Select Criteria], cliquez sur **[!UICONTROL Create Criteria]**. Vous pouvez enregistrer vos nouveaux critères pour les utiliser avec d&#39;autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Create New Criteria] à l’aide de la première méthode : l’écran de bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** .

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Cliquez sur **[!UICONTROL Create Criteria]**.

1. Renseignez les informations de la section [Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) .

   1. Dans la liste déroulante **[!UICONTROL Select Algorithm]** Type , sélectionnez **[!UICONTROL Custom Criteria]**.

   1. Dans la liste déroulante **[!UICONTROL Algorithm]**, sélectionnez **[!UICONTROL Custom Algorithm]**.

      >[!NOTE]
      >
      >Les étapes précédentes entraînent l’affichage de la section [!UICONTROL Upload CSV] au bas de la boîte de dialogue [!UICONTROL Create New Criteria].

1. (Conditionnel) Renseignez les informations de la section [Contenu de sauvegarde](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) .

1. (Conditionnel) Renseignez les informations de la section [Règles d’inclusion](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) .

1. Dans la section **[!UICONTROL Upload CSV]** , sélectionnez le **[!UICONTROL Location]** de votre fichier CSV.

   ![Télécharger la section CSV](assets/upload-csv.png)

   Le fichier CSV doit être correctement formaté pour pouvoir être téléchargé. Cliquez sur **[!UICONTROL Download the CSV template]** pour obtenir un fichier CSV correctement formaté.

   Vous avez le choix entre deux options :

   * **FTP :** Pour télécharger votre fichier CSV depuis un serveur FTP, sélectionnez **[!UICONTROL FTP]**, puis saisissez les informations requises. Vous pouvez utiliser le protocole SSL, qui utilise le protocole FTPS pour transférer votre fichier CSV en toute sécurité.
   * **URL :** Pour charger votre fichier CSV à partir d’une URL, sélectionnez **[!UICONTROL URL]**, puis saisissez une URL de flux.

1. Cliquez sur **[!UICONTROL Save]**.

## Considérations

* Les entités de critères personnalisés (lignes) peuvent comporter jusqu’à 1 000 éléments recommandés (colonnes).

* Les mises à jour de critères personnalisés sont par défaut « cumulatives ». Les nouvelles paires clé-valeur spécifiées dans le fichier de chargement CSV remplacent les paires clé-valeur existantes. Les paires clé-valeur existantes qui n’ont pas de clés spécifiées dans le transfert CSV sont toujours disponibles pour diffusion et expirent dans 31 jours à compter du dernier chargement dans le cadre du fichier CSV.

  Contactez le service à la clientèle pour permettre au paramètre d’ignorer les résultats existants qui ne sont pas inclus dans le prochain chargement CSV. Si ce paramètre est activé, seules les clés présentes dans le fichier de flux CSV personnalisé sont disponibles pour la diffusion. Ce paramètre s’applique à tous les critères personnalisés.

* Les flux de critères personnalisés sont mis à jour une fois toutes les 24 heures.

  Vous pouvez voir l’état de chargement et de synchronisation de votre chargement de critères personnalisés au bas de chaque carte de critères sur la page [!UICONTROL Recommendations] > [!UICONTROL Criteria]. Vous pouvez également voir l’état dans la boîte de dialogue [!UICONTROL Edit] lors de la modification de critères personnalisés.

* Le flux d’un chargement sans erreur doit être [!UICONTROL Scheduled] > [!UICONTROL Downloading Feed File] > [!UICONTROL Importing] > [!UICONTROL Successful].

* Voici les messages d’erreur possibles que vous pourriez recevoir si [!DNL Target] rencontre un problème avec le téléchargement :

  | Message d’erreur | Détails |
  |--- |--- |
  | Erreur inconnue | Indique une erreur technique interne. |
  | Erreur d’analyse | Indique probablement un problème de format du fichier du flux. Corrigez le format de fichier et réenregistrez l’algorithme, qui redémarre le processus de téléchargement de fichier. |
  | Serveur introuvable | Fournissez une adresse IP ou un nom d’hôte visible sur Internet. |
  | Erreur d’informations d’identification | Fournissez un nom d’utilisateur et un mot de passe valides pour un compte actif sur le serveur. |
  | Répertoire introuvable | Fournissez un répertoire qui existe sur le serveur. |
  | Fichier introuvable | Fournissez le nom d’un fichier qui existe sur le serveur dans le répertoire indiqué. |

## Vidéo de formation : Création de critères dans Recommendations (12:33) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo contient les informations suivantes (les détails du téléchargement de critères personnalisés commencent à 11h43) :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
