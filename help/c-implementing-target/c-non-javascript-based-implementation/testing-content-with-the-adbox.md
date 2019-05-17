---
description: Utilisez une adbox pour fournir des images à une mise en œuvre hors site.
keywords: implémentation;mbox.js sans JavaScript;mbox;adbox
seo-description: Utilisez une adbox pour fournir des images à une mise en œuvre hors site.
seo-title: Création d’une adbox pour une image
solution: Target
subtopic: Prise en main
title: Création d’une adbox pour une image
topic: Standard
uuid: 6b1763f7-08de-4bde-9e20-e79b92b02f20
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Création d’une adbox pour une image{#create-an-adbox-for-an-image}

Utilisez une adbox pour fournir des images à une mise en œuvre hors site.

Une adbox s’apparente à une mbox, mais elle est contrôlée par une URL et non par du code JavaScript. Les adbox sont créées à l’aide d’une URL d’adbox spéciale qui charge une mbox publicitaire (ou adbox) dans votre compte Adobe. Utilisez cette adbox à la place de la mbox dans les activités. Utilisez l’URL de l’adbox au lieu d’une référence d’image directe dans les mises en œuvre de messagerie ou d’autres mises en œuvre sans JavaScript.

Pour obtenir de l’aide sur le choix de la configuration appropriée, voir  [Mises en œuvre non basées sur JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

1. Créez l’URL de l’adbox : 

   ```
   https://myClientCode.tt.omtrdc.net/m2/myClientCode/ubox/
   image?mbox=emailHeroImage123_320x200
   mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif
   ```

   * Où `myClientCode` est le code client de votre entreprise ? Le code client de votre entreprise est en minuscules et ne comporte pas de caractères spéciaux.

      * **at.js :** le code client figure dans la partie supérieure de la page [!UICONTROL Configuration &gt; Implémentation &gt; Modifier les paramètres at.js.] de l’[!DNL Target]interface.

      * **mbox.js :** le code client figure dans la partie supérieure de la page [!UICONTROL Configuration &gt; Implémentation &gt; Modifier les paramètres Mbox.js.]
   * Où `image` est le type d&#39;appel. Dans ce cas, il s’agit d’une image.

   * Où `emailHeroImage123_320x200` est le nom de l&#39;adbox ?

   * Où `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fimg%2Flogo%2Egif` est le contenu par défaut de la mbox. Cela doit être une image.

      Elle doit être en codage URL et il doit s’agir d’une référence absolue. Vous pouvez utiliser la référence au codage URL [HTML](https://www.w3schools.com/tags/ref_urlencode.asp) pour coder rapidement vos URL.


1. Créez [des offres de redirection](../../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) pour chaque image alternative.

   >[!NOTE] {class=&quot;- topic/note &quot;}
   >
   >Les AdBox doivent être chargées avec une offre de redirection ou avec l’offre de contenu par défaut. Les autres types d’offre ne fonctionnent pas. Comme l’adbox est une URL, elle peut uniquement afficher les URL reçues. Seules les offres de redirection fonctionnent alors.

1. Créez l’activité.

   Voir les [Implémentations non basées sur JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) pour connaître la configuration appropriée permettant d’atteindre vos objectifs.
1. Effectuez une AQ sur l’activité.

   Pour respecter les bonnes pratiques, créez une page factice et vérifiez que toutes les expériences, le contenu par défaut et les rapports fonctionnent comme prévu sur tous les types de navigateur et ce, dans tous vos environnements. 1. Lancez l’activité.
