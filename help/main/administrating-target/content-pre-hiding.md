---
keywords: scintillement,prémasquage,prémasquage,personnalisation,implémentation,antiscintillement,VEC,compositeur d’expérience visuelle
description: Découvrez comment le prémasquage du contenu réduit le scintillement en masquant uniquement les régions que la personnalisation Adobe Target active modifiera, à l’aide d’un paramètre au niveau du compte, d’une bibliothèque de pages allégée et de contrôles par activité.
title: Prémasquage du contenu pour les expériences personnalisées
feature: Administration & Configuration
role: Admin
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true?lang=fr" tooltip="Quelles sont les fonctionnalités Beta dans  [!DNL Adobe Target] ?"
hide: true
source-git-commit: dfda53d7efb93ab4cbd980d27b47c0b67ee3e561
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# Prémasquage du contenu pour les expériences personnalisées

>[!AVAILABILITY]
>
>Le prémasquage du contenu pour le contenu personnalisé est disponible en version **bêta**.

Lorsqu’un visiteur charge une page, le contenu par défaut peut apparaître brièvement, puis être remplacé par du contenu personnalisé provenant de [!DNL Adobe Target]. Ce commutateur visible est souvent appelé **scintillement** et il s’agit d’un problème d’expérience courant pour les programmes de personnalisation.

Grâce au pré-masquage du contenu, vous pouvez gérer le scintillement en masquant uniquement les parties de la page que vos activités personnalisent pendant le chargement de la page, de sorte que vos clients voient moins de scintillement et moins de temps vide à l’écran.

Voici comment fonctionne le pré-masquage du contenu, depuis le compte par défaut jusqu’à vos choix d’implémentation de page et de per-activité.

1. Activez le pré-masquage du contenu pour votre compte afin de définir la valeur par défaut globale. Cette option est désactivée par défaut. [En savoir plus](#content-pre-hiding-enable-account)

1. Ajoutez la bibliothèque de pré-masquage de contenu à la `<head>` de toutes les pages sur lesquelles vous exécutez des activités de personnalisation.

1. [!DNL Target] crée un ensemble de règles à partir d’activités Live [!UICONTROL Visual Experience Composer] et [!UICONTROL Enhanced Experience Composer] . L’ensemble de règles répertorie les sélecteurs et les régions que la diffusion peut modifier.

   Notez que les activités [!UICONTROL Form-Based Composer] ne sont pas prises en charge.

1. La bibliothèque récupère cet ensemble de règles à partir du réseau CDN Adobe et prémasque les éléments correspondants uniquement pendant que le contenu personnalisé est toujours en cours de chargement.

1. En **[!UICONTROL Goals & Settings]**, vous pouvez désactiver **[!UICONTROL Content pre-hiding]** pour des activités individuelles, mais uniquement si elle est activée au niveau du compte. [En savoir plus](#content-pre-hiding-activity)

## Activation du pré-masquage du contenu pour votre instance {#content-pre-hiding-enable-account}

>[!IMPORTANT]
>
>Pour activer le masquage préalable du contenu pour l’instance, vous devez être un **administrateur**.

Le pré-masquage du contenu est désactivé pour votre instance jusqu’à ce que vous l’activiez. Utilisez **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** pour activer la fonctionnalité, définir les valeurs par défaut et accéder au téléchargement pour votre équipe d’implémentation.

1. Dans [!DNL Target], cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

1. Dans le menu **[!UICONTROL Content pre-hiding]** , activez l’option Prémasquage du contenu .

   ![](assets/content-pre-hiding-1.png)

1. Si nécessaire, mettez à jour le **[!UICONTROL Pre-hiding timeout]** en secondes.

1. Cliquez sur **[!UICONTROL Save]**. Les paramètres de gestion du scintillement seront alors appliqués à votre instance.

1. Une fois activé, cliquez sur **[!UICONTROL Download]**, puis ajoutez le fichier au `<head>` de la page afin qu’il se charge avant le [!DNL at.js] ou la [!DNL Web SDK].

   ![](assets/content-pre-hiding-2.png)

Votre instance utilise désormais les paramètres de masquage préalable du contenu enregistré et de délai d’expiration par défaut pour les activités qui souscrivent.

## Activation du pré-masquage du contenu pour votre activité {#content-pre-hiding-activity}

Lorsque le masquage préalable est activé pour votre instance, choisissez si chaque activité l’utilise dans **[!UICONTROL Goals & Settings]**. Les activités pour lesquelles vous activez le pré-masquage sont incluses dans le comportement ciblé lorsqu’elles sont actives.

[!DNL Target] crée ensuite un jeu de règles léger à partir d’activités en direct créées dans le [!UICONTROL Visual Experience Composer] (VEC) et le [!UICONTROL Form-Based Composer], décrivant les sélecteurs et les zones que la diffusion peut modifier.

Lorsque vous créez ou modifiez une activité :

1. Accédez à l’activité pour laquelle vous souhaitez activer l’option de pré-masquage.

1. Accédez à la liste déroulante **[!UICONTROL Edit activity]** et sélectionnez **[!UICONTROL Edit Goals & Settings]**.

   ![](assets/content-pre-hiding-3.png)

1. Dans le menu **[!UICONTROL Content pre-hiding]**, activez/désactivez l’option **[!UICONTROL Enable content pre-hiding]** pour activer ou désactiver le masquage préalable de cette activité.

   ![](assets/content-pre-hiding-4.png)

1. Une fois que vous avez terminé, cliquez sur **[!UICONTROL Save & Close]**.

Une fois que vous avez enregistré et que les activités sont mises en ligne ou désactivées, l’ensemble de règles est mis à jour afin que le pré-masquage reste aligné sur ce qui est réellement diffusé, sans modifications de votre code de page pour chaque lancement.

Du côté des visiteurs, la bibliothèque récupère cet ensemble de règles du réseau CDN Adobe à chaque chargement de page et prémasque les éléments correspondants uniquement lorsque cela est nécessaire jusqu’à ce que le contenu personnalisé soit prêt.
