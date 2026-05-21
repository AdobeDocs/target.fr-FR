---
keywords: ;offre distante;administration;modèles d’URL;validation;activités;offres;caractère générique;regex
description: Découvrez comment afficher, rechercher, ajouter et supprimer des URL placées sur la liste autorisée pour les offres distantes dans la section Administration d’Adobe Target, y compris le comportement de validation et la portée à l’échelle du compte.
title: Gestion des URL d’offres distantes placées sur la liste autorisée
feature: Administration & Configuration
topic: Implementation
role: Admin
level: Intermediate
solution: Target
product: Target
source-git-commit: 882c91244e5dae0977c8a6a1e5878525f497a720
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# URL PLACÉES SUR LA LISTE AUTORISÉE

Les URL Placées sur la liste autorisée définissent des modèles d’URL de confiance où votre entreprise peut créer et exécuter des expériences [!DNL Adobe Target], y compris lorsque vous utilisez des offres distantes ou de redirection. La liste fonctionne avec [gestion des hôtes](/help/main/administrating-target/hosts.md) et [environnements](/help/main/administrating-target/environments.md), mais s’applique spécifiquement aux modèles d’URL d’offre distante autorisés et aux validations associées.

Pour gérer les URL placées sur la liste autorisée, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Allowlisted URLs]**.

Page ![URL Placées sur la liste autorisée affichant la liste des URL, le champ de recherche et le contrôle Ajouter une URL](../administrating-target/assets/allowlist-1.png)

## Gérer les URLs placées sur la liste autorisée {#add-url}

Le tableau principal répertorie chaque modèle placé sur la liste autorisée dans une seule colonne. Les entrées prises en charge peuvent inclure des URL exactes, des chemins d’accès par des caractères génériques ou des formats de modèle acceptés par votre entreprise pour les expériences distantes.

1. Cliquez sur **[!UICONTROL Add URL]**.

   ![](../administrating-target/assets/allowlist-2.png)

1. Dans la boîte de dialogue, saisissez l’URL ou le modèle que votre organisation doit autoriser.

   ![](../administrating-target/assets/allowlist-3.png)

1. Enregistrez vos modifications.

   Une fois le modèle placé sur la liste autorisée, les utilisateurs et utilisatrices peuvent créer ou exécuter des activités et des offres qui reposent sur cette URL, sous réserve de vos autres règles de [!DNL Target].

1. Utilisez le champ **[!UICONTROL Search URLs]** pour filtrer le tableau.

1. Pour supprimer une URL, recherchez la ligne du modèle dont vous n’avez plus besoin et cliquez sur l’icône ![Supprimer](../administrating-target/assets/do-not-localize/Smock_Delete_18_N.svg).

   ![](../administrating-target/assets/allowlist-4.png)


