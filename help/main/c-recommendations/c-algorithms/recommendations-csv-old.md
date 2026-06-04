---
keywords: création de critères personnalisés;algorithmes;critères;critères de recommandations;csv;ftp;télécharger un csv
description: Découvrez comment télécharger un fichier CSV pour personnaliser vos recommandations dans  [!DNL Target] Recommendations.
title: Comment télécharger des critères personnalisés dans Recommendations ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=fr#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 32%

---

# Téléchargement de critères personnalisés

Chargez un fichier CSV pour personnaliser vos recommandations dans [!DNL Adobe Target].

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer des critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur l’écran de bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**, cliquez sur **[!UICONTROL Créer des critères]** > **[!UICONTROL Créer des critères]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez une activité [!DNL Recommendations] à l’aide du [!UICONTROL compositeur d’expérience visuelle] (VEC), vous êtes immédiatement redirigé(e) vers l’écran [!UICONTROL Sélectionner des critères] après avoir sélectionné un élément de votre page et cliqué sur [!UICONTROL Remplacer avec Recommendations], [!UICONTROL Insérer des recommandations avant] ou [!UICONTROL Insérer des recommandations après]. Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Créer un critère]**. Si vous créez un critère, vous pouvez l’enregistrer pour l’utiliser avec d’autres activités [!DNL Recommendations]. Pour plus d’informations, voir [Créer une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une activité [!DNL Recommendations], cliquez dans une zone [!UICONTROL Emplacement Recommendations] de votre page, puis sélectionnez **[!UICONTROL Modifier les critères]**. Sur l’écran [!UICONTROL Sélectionner les critères], cliquez sur **[!UICONTROL Créer des critères]**. Vous pouvez enregistrer vos nouveaux critères en vue de les utiliser avec d’autres activités [!DNL Recommendations].

Les étapes suivantes supposent que vous accédez à l’écran [!UICONTROL Créer de nouveaux critères] en utilisant la première méthode : l’écran de bibliothèque **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]**.

1. Renseignez les informations de la section [Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

   1. Dans la liste déroulante **[!UICONTROL Sélectionner l’algorithme]** le type, sélectionnez **[!UICONTROL Critères personnalisés]**.

   1. Dans la liste déroulante **[!UICONTROL Algorithme]**, sélectionnez **[!UICONTROL Algorithme personnalisé]**.

      >[!NOTE]
      >
      >Les étapes précédentes entraînent l’affichage de la section [!UICONTROL Télécharger CSV] au bas de la boîte de dialogue [!UICONTROL Créer de nouveaux critères].

1. (Conditionnel) Renseignez les informations de la section [Contenu de sauvegarde](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. (Conditionnel) Renseignez les informations de la section [Règles d’inclusion](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion).

1. Dans la section **[!UICONTROL Télécharger CSV]**, sélectionnez le **[!UICONTROL emplacement]** de votre fichier CSV.

   ![Section Charger CSV](assets/upload-csv.png)

   Le fichier CSV doit être correctement formaté pour pouvoir être téléchargé. Cliquez sur **[!UICONTROL Télécharger le modèle CSV]** pour obtenir un fichier CSV correctement formaté.

   Vous avez le choix entre deux options :

   * **FTP :** pour charger votre fichier CSV à partir d’un serveur FTP, sélectionnez **[!UICONTROL FTP]**, puis saisissez les informations requises. Vous pouvez utiliser SSL, qui utilise le protocole FTPS pour transférer votre fichier CSV en toute sécurité.
   * **URL :** pour charger votre fichier CSV à partir d’une URL, sélectionnez **[!UICONTROL URL]**, puis saisissez une URL de flux.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Considérations

* Les entités de critères personnalisés (lignes) peuvent comporter jusqu’à 1 000 éléments recommandés (colonnes).

* Les mises à jour de critères personnalisés sont par défaut « cumulatives ». Les nouvelles paires clé-valeur spécifiées dans le fichier de chargement CSV remplacent les paires clé-valeur existantes. Les paires clé-valeur existantes qui n’ont pas de clés spécifiées dans le téléchargement CSV sont toujours disponibles pour diffusion et expirent dans 31 jours à partir du dernier téléchargement dans le cadre du fichier CSV.

  Contactez le service à la clientèle pour permettre au paramètre d’ignorer les résultats existants qui ne sont pas inclus dans le prochain chargement CSV. Si ce paramètre est activé, seules les clés présentes dans le fichier de flux CSV personnalisé sont disponibles pour la diffusion. Ce paramètre s’applique à tous les critères personnalisés.

* Les flux de critères personnalisés sont mis à jour une fois toutes les 24 heures.

  Le statut de chargement et de synchronisation de votre chargement de critères personnalisés s’affiche au bas de chaque carte de critère sur la page [!UICONTROL Recommendations] > [!UICONTROL Critères]. Vous pouvez également consulter le statut dans la boîte de dialogue [!UICONTROL Modifier] lors de la modification de critères personnalisés.

* Le flux d’un chargement sans erreur doit être [!UICONTROL Planifié] > [!UICONTROL Téléchargement du fichier de flux] > [!UICONTROL Importation] > [!UICONTROL Réussite].

* Voici quelques messages d’erreur que vous pouvez recevoir si [!DNL Target] rencontrez un problème avec le chargement :

  | Message d’erreur | Détails |
  |--- |--- |
  | Erreur inconnue | Indique une erreur technique interne. |
  | Erreur d’analyse | Indique probablement un problème de format du fichier du flux. Corrigez le format du fichier et réenregistrez l’algorithme, ce qui redémarre le processus de téléchargement du fichier. |
  | Serveur introuvable | Fournissez une adresse IP ou un nom d’hôte visible sur Internet. |
  | Erreur d’informations d’identification | Fournissez un nom d’utilisateur et un mot de passe valides pour un compte actif sur le serveur. |
  | Répertoire introuvable | Fournissez un répertoire qui existe sur le serveur. |
  | Fichier introuvable | Fournissez le nom d’un fichier qui existe sur le serveur dans le répertoire indiqué. |

## Vidéo de formation : créer des critères dans Recommendations (12:33) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo contient les informations suivantes (les détails sur le chargement des critères personnalisés commencent à 11:43) :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
