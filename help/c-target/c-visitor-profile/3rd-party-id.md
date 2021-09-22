---
keywords: mbox;mbox3rdPartyId;synchronisation des profils;synchroniser les profils;PCID
description: Découvrez comment utiliser le mbox3rdPartyId, qui est l’identifiant visiteur de votre entreprise, tel que l’identifiant de membre ou le programme de fidélité de votre entreprise.
title: Comment utiliser la synchronisation des profils en temps réel pour mbox3rdPartyId ?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 24%

---

# Synchronisation des profils en temps réel pour mbox3rdPartyId

`mbox3rdPartyId` dans [!DNL Adobe Target] correspond à l’identifiant visiteur de votre entreprise, tel que l’identifiant de membre pour le programme de fidélité de votre entreprise.

Lorsqu’un visiteur se connecte au site de votre entreprise, cette dernière crée généralement un identifiant qui est associé au compte du visiteur, à sa carte de fidélité, à son numéro de membre ou à tout autre identifiant applicable de l’entreprise.

Lorsqu’un visiteur accède à une page sur laquelle [!DNL Target] est activé, il se voit attribuer un PCID [!DNL Target]. Si le visiteur se connecte ensuite et que l’implémentation transmet la balise `mbox3rdPartyId` à [!DNL Target], [!DNL Target] connecte la balise `mbox3rdPartyId` de ce visiteur au PCID [!DNL Target].

Les mises à jour sont synchronisées avec la base de données toutes les trois à cinq minutes. Lorsque le visiteur se déconnecte, les données fusionnées remplacent les données précédentes associées à `mbox3rdPartyId`, ce qui crée un enregistrement complet des actions de ce visiteur. Si un même attribut existe dans les deux ID (par exemple, le PCID a category=hats et `mbox3rdPartyId` a category=skis, ou si le visiteur a vu l’expérience A avant de se connecter, mais que l’expérience B est stockée dans la balise `mbox3rdPartyId`), l’attribut stocké dans la balise `mbox3rdPartyId` remplace l’attribut du PCID. Si le visiteur se trouvait dans une activité ou une expérience avant de se connecter, mais qu’une activité et une expérience différentes sont stockées dans la balise `mbox3rdPartyId`, après s’être connecté, ce visiteur est placé dans l’activité et l’expérience `mbox3rdPartyId`.

| PCID (session fermée) | mbox3rdPartyId (connecté) | Fusion et enregistrement dans mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Activité 1, Expérience A | Activité 1, Expérience B | Activité 1, Expérience B |
| Activité 1 |  | Activité 1 |

Quand le visiteur se déconnecte, le profil fusionné est conservé.

>[!NOTE]
>
>Si vous souhaitez faire la distinction entre les utilisateurs authentifiés (connectés) et non authentifiés, utilisez [!DNL Adobe Experience Cloud Identity Service] (ECID) au lieu de mbox3rdPartyID. Une fois qu’un utilisateur est associé à mbox3rdPartyID, il reste associé à l’utilisateur même après sa déconnexion.

>[!NOTE]
>
>[!DNL Adobe Analytics] les objectifs ne sont pas suivis dans les cas où les modifications d’ [!DNL Adobe Experience Cloud] ID (EDID) changent (par exemple, le visiteur change de périphérique), même si le  [!DNL Target] profil peut être fusionné en fonction du mbox3rdPartyId et comporte toujours des informations sur l’activité. Pour les visiteurs identifiés avec le même EDID (ceux qui accèdent à la page avec le même appareil), [!DNL Analytics for Target] (A4T) doit fonctionner comme prévu.

## Considérations {#considerations}

* Si votre page contient plusieurs mbox et que certaines utilisent uniquement `3rdPartyID`, [!DNL Target] ne comporte pas de profil/contexte de visiteur distinct pour chaque requête de visiteur. Le contexte `3rdPartyID` a la priorité sur le contexte PCID. Il suffit qu’une mbox transfère `3rdPartyId` pour que son contexte ait la priorité sur PCID.

   Supposons, par exemple, qu’un visiteur accède à une page avant de se connecter et de voir une expérience. La mbox globale n’utilise pas `3rdPartyID`. Après s’être connecté, le visiteur voit l’une des trois expériences avec des mbox enfants, dont certaines utilisent `3rdPartyID`. Le visiteur consulte plusieurs pages du site, puis utilise le bouton Précédent pour revenir à la page principale à laquelle il a accédé avant de se connecter et voit une expérience différente. Dans ce scénario, la mbox globale n’a pas transmis `3rdPartyID`, mais une ou plusieurs des mbox enfants l’ont fait. `3rdPartyID` a été prioritaire par rapport au PCID.

* Vous pouvez envoyer les ID de client des visiteurs à [!DNL Target] en utilisant deux méthodes :

   1. Utilisez `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` est le nom du paramètre lorsque vous utilisez  `targetPageParams` ou  `targetPageParamsAll`
      * `thirdPartyId` est le nom de paramètre que vous définissez directement dans la charge utile de l’API de diffusion.
      * Vous ne pouvez envoyer qu’une seule valeur dans ce paramètre.
   1. Utilisez la fonction `setCustomerId`/`customerIds` du service ECID.

      * `setCustomerId` est une fonction que vous pouvez utiliser dans les implémentations côté client (navigateur) lorsque VisitorAPI.js est disponible sur la page.
      * `customerIds` est le nom du paramètre utilisé lorsque vous le définissez directement dans la payload de l’API de diffusion. Il est généralement effectué sur les mises en oeuvre côté serveur ou IOT (Internet des objets).
      * Contrairement à `mbox3rdPartyId`/`thirdPartyId`, vous pouvez envoyer plusieurs ID sous la forme d’une liste dans cette approche, mais comme [!DNL Target] ne prend en charge qu’un seul ID de client par ID TnT, il utilise le premier ID de la liste avec un alias connu (alias configuré dans l’interface utilisateur Attributs du client).

   >[!IMPORTANT]
   >
   > L’utilisation des deux approches mentionnées ci-dessus de manière interchangeable pour un seul visiteur peut entraîner des fusions de profils incorrectes des profils [!DNL Target] non authentifiés et authentifiés.
   >
   >Adobe ne vous recommande pas d’utiliser à la fois `mbox3rdPartyId`/`thirdPartyId` et `setCustomerID`/`customerIds`.
   >
   >Si vous devez utiliser les deux approches de manière interchangeable, assurez-vous que le premier ID de la liste utilisé par `setCustomerID`/`customerIds` est celui utilisé par `thirdPartyId`/`mbox3rdPartyId` et vice versa.

