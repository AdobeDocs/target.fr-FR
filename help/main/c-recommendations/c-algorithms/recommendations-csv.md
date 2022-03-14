---
keywords: création de critères personnalisés;algorithmes;critères;critères de recommandations;csv;ftp;télécharger un csv
description: Découvrez comment télécharger un fichier CSV pour personnaliser vos recommandations dans Adobe [!DNL Target] Recommendations.
title: Comment télécharger des critères personnalisés dans Recommendations ?
feature: Recommendations
exl-id: 33434121-e0ae-4b82-b1dd-78b9738026cb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 39%

---

# ![PREMIUM](/help/main/assets/premium.png) Téléchargement de critères personnalisés

Chargement d’un fichier CSV pour personnaliser vos recommandations dans [!DNL Adobe Target].

Il existe plusieurs méthodes pour accéder à l’écran [!UICONTROL Créer des critères]. Certaines options de l’écran varient en fonction de l’accès à ce dernier.

* Sur le **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** écran de bibliothèque, cliquez sur **[!UICONTROL Création de critères]** > **[!UICONTROL Création de critères]**. Les critères que vous créez à cet emplacement deviennent automatiquement disponibles pour toutes les activités [!DNL Recommendations].
* Lorsque vous créez une [!DNL Recommendations] à l’aide de la fonction [!UICONTROL Compositeur d’expérience visuelle] (VEC), vous êtes immédiatement dirigé vers le [!UICONTROL Sélectionner des critères] une fois que vous avez sélectionné un élément sur votre page, cliquez sur [!UICONTROL Remplacer par Recommendations], [!UICONTROL Insérer Recommendations avant]ou [!UICONTROL Insérer Recommendations après]. Vous pouvez ensuite sélectionner un critère disponible ou cliquer sur **[!UICONTROL Création de critères]**. Si vous créez un nouveau critère, vous pouvez l’enregistrer pour l’utiliser avec d’autres [!DNL Recommendations] activités. Pour plus d’informations, voir [Création d’une activité Recommendations](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md).
* Lorsque vous modifiez une [!DNL Recommendations] activité, cliquez sur la zone [!UICONTROL Emplacement des recommandations] sur votre page, puis sélectionnez **[!UICONTROL Changer les critères]**. Sur le [!UICONTROL Sélectionner des critères] écran, cliquez sur **[!UICONTROL Création de critères]**. Vous pouvez enregistrer vos nouveaux critères pour les utiliser avec d’autres [!DNL Recommendations] activités.

Les étapes suivantes supposent que vous accédez au [!UICONTROL Création de critères] écran en utilisant la première méthode : la valeur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]** écran de la bibliothèque.

1. Cliquez sur **[!UICONTROL Recommendations]** > **[!UICONTROL Critères]**.

1. Cliquez sur **[!UICONTROL Créer des critères]**.

1. Renseignez les informations de la section [Informations de base](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) .

   1. Dans la **[!UICONTROL Sélectionner l’algorithme]** Liste déroulante Type, sélectionnez **[!UICONTROL Critères personnalisés]**.

   1. Dans la **[!UICONTROL Algorithme]** liste déroulante, sélectionnez **[!UICONTROL Algorithme personnalisé]**.

      >[!NOTE]
      >
      >Les étapes précédentes provoquent l’événement [!UICONTROL Téléchargement d’un fichier CSV] à afficher au bas de la section [!UICONTROL Création de critères] de la boîte de dialogue

1. (Conditionnel) Renseignez les informations de la variable [Contenu de sauvegarde](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content) .

1. (Conditionnel) Renseignez les informations de la variable [Règles d’inclusion](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#inclusion) .

1. Dans le **[!UICONTROL Téléchargement d’un fichier CSV]** , sélectionnez **[!UICONTROL Emplacement]** de votre fichier CSV.

   ![Téléchargement de la section CSV](assets/upload-csv.png)

   Le fichier CSV doit être correctement formaté pour pouvoir être téléchargé. Cliquez sur **[!UICONTROL Télécharger le modèle CSV]** pour obtenir un fichier CSV correctement formaté.

   Vous avez le choix entre deux options :

   * **FTP :** Pour transférer le fichier CSV depuis un serveur FTP, sélectionnez l’option **[!UICONTROL FTP]**, puis saisissez les informations requises. Vous pouvez utiliser le protocole SSL, qui utilise le protocole FTPS pour transférer votre fichier CSV en toute sécurité.
   * **URL :** Pour charger votre fichier CSV à partir d’une URL, sélectionnez **[!UICONTROL URL]**, puis saisissez une URL de flux.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Considérations

* Les entités de critères personnalisés (lignes) peuvent comporter jusqu’à 1 000 éléments recommandés (colonnes).

* Les mises à jour de critères personnalisés sont par défaut « cumulatives ». Les nouvelles paires clé-valeur spécifiées dans le fichier de chargement CSV remplacent les paires clé-valeur existantes. Les paires clé-valeur existantes qui n’ont pas de clés spécifiées dans le transfert CSV sont toujours disponibles pour diffusion et expirent dans 31 jours à compter du dernier chargement dans le cadre du fichier CSV.

   Contactez le service à la clientèle pour permettre au paramètre d’ignorer les résultats existants qui ne sont pas inclus dans le prochain chargement CSV. Si ce paramètre est activé, seules les clés présentes dans le fichier de flux CSV personnalisé sont disponibles pour la diffusion. Ce paramètre s’applique à tous les critères personnalisés.

* Les flux de critères personnalisés sont mis à jour une fois toutes les 24 heures.

   Vous pouvez voir l’état de chargement et de synchronisation de votre chargement de critères personnalisés au bas de chaque carte de critères sur la page [!UICONTROL Recommendations] > [!UICONTROL Critères] page. Vous pouvez également voir l’état dans la variable [!UICONTROL Modifier] lors de la modification de critères personnalisés.

* Le flux d’un chargement sans erreur doit être : [!UICONTROL Planifié] > [!UICONTROL Téléchargement du fichier de flux] > [!UICONTROL Importer] > [!UICONTROL Réussite].

* Vous trouverez ci-dessous les messages d’erreur que vous pourriez recevoir si [!DNL Target] rencontre un problème avec le téléchargement :

   | Message d’erreur | Détails |
   |--- |--- |
   | Erreur inconnue | Indique une erreur technique interne. |
   | Erreur d’analyse | Indique probablement un problème de format du fichier du flux. Corrigez le format de fichier et réenregistrez l’algorithme, qui redémarre le processus de téléchargement de fichier. |
   | Serveur introuvable | Fournissez une adresse IP ou un nom d’hôte visible sur Internet. |
   | Erreur d’informations d’identification | Fournissez un nom d’utilisateur et un mot de passe valides pour un compte actif sur le serveur. |
   | Répertoire introuvable | Fournissez un répertoire qui existe sur le serveur. |
   | Fichier introuvable | Fournissez le nom d’un fichier qui existe sur le serveur dans le répertoire indiqué. |

## Vidéo de formation : Créer des critères dans Recommendations (12:33) ![Badge de tutoriel](/help/main/assets/tutorial.png)

Cette vidéo contient les informations suivantes (les détails du téléchargement de critères personnalisés commencent à 11h43) :

* Création de critères
* Création d’une séquence de critères
* Téléchargement de critères personnalisés

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
