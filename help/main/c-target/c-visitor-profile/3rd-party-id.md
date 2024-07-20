---
keywords: mbox;mbox3rdPartyId;synchronisation des profils;synchroniser les profils;PCID
description: Découvrez comment utiliser le mbox3rdPartyId. Il s’agit de l’identifiant visiteur de votre organisation, tel que l’identifiant d’abonnement pour le programme de fidélité de votre organisation.
title: Comment utiliser la synchronisation des profils en temps réel pour mbox3rdPartyId ?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 80%

---

# Synchronisation des profils en temps réel pour mbox3rdPartyId

Dans [!DNL Adobe Target], le `mbox3rdPartyId` représente l’identifiant visiteur de votre société. Il s’agit par exemple de l’identifiant d’abonnement pour le programme de fidélité de votre société.

Lorsqu’un visiteur se connecte au site de votre entreprise, cette dernière crée généralement un identifiant qui est associé au compte du visiteur, à sa carte de fidélité, à son numéro de membre ou à tout autre identifiant applicable de l’entreprise.

Lorsqu’un visiteur accède à une page sur laquelle [!DNL Target] est activé, il se voit attribuer un PCID [!DNL Target]. Si le visiteur se connecte par la suite et si l’implémentation transmet le `mbox3rdPartyId` à [!DNL Target], [!DNL Target] associe le `mbox3rdPartyId` de ce visiteur au PCID [!DNL Target].

Les mises à jour sont synchronisées avec la banque de profils toutes les 5 à 10 minutes. À la fin de la session du visiteur, les données fusionnées remplacent les données précédentes associées à l’ `mbox3rdPartyId`, créant ainsi un enregistrement complet des actions de ce visiteur. Si un même attribut existe dans les deux ID (par exemple, le PCID possède l’attribut category=hats et `mbox3rdPartyId` possède l’attribut category=skis ou si le visiteur affiche l’expérience A avant de se connecter mais que l’expérience B est stockée dans `mbox3rdPartyId`), l’attribut stocké dans `mbox3rdPartyId` remplace l’attribut de PCID. Si le visiteur était dans une activité ou une expérience avant de se connecter et si une activité et une expérience différentes sont stockées dans `mbox3rdPartyId`, ce visiteur est placé dans l’activité et l’expérience de `mbox3rdPartyId` une fois connecté.

| PCID (session fermée) | mbox3rdPartyId (connecté) | Fusion et enregistrement dans mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|   | store=94103 | store=94103 |
| Activité 1, Expérience A | Activité 1, Expérience B | Activité 1, Expérience B |
| Activité 1 |  | Activité 1 |

Quand le visiteur se déconnecte, le profil fusionné est conservé.

>[!NOTE]
>
>Si vous souhaitez faire la distinction entre les utilisateurs authentifiés (connectés) et non authentifiés, utilisez [!DNL Adobe Experience Cloud Identity Service] (ECID) au lieu de mbox3rdPartyID. Une fois qu’un utilisateur est associé à mbox3rdPartyID, celui-ci reste associé à l’utilisateur même après sa déconnexion.

>[!NOTE]
>
>Les objectifs [!DNL Adobe Analytics] ne sont pas suivis dans les cas où les modifications de l’ [!DNL Adobe Experience Cloud] ID (ECID) changent (par exemple, le visiteur change d’appareil), même si le profil [!DNL Target] peut être fusionné en fonction de mbox3rdPartyId et comporte toujours des informations sur l’activité. Pour les visiteurs identifiés avec le même ECID (ceux qui accèdent à la page avec le même appareil), [!DNL Analytics for Target] (A4T) doit fonctionner comme prévu.

## Considérations {#considerations}

* Si votre page contient plusieurs mbox et que certaines utilisent uniquement `3rdPartyID`, [!DNL Target] ne dispose pas d’un profil/contexte de visiteur distinct pour chaque requête de visiteur. Le contexte `3rdPartyID` a la priorité sur le contexte PCID. Il suffit qu’une mbox transmette `3rdPartyId` pour que son contexte ait la priorité sur PCID.

  Supposons, par exemple, qu’un visiteur accède à une page avant de se connecter et de voir une expérience. La mbox globale n’utilise pas `3rdPartyID`. Après s’être connecté, le visiteur voit l’une des trois expériences avec des mbox enfants, dont certaines utilisent `3rdPartyID`. Le visiteur consulte plusieurs pages du site, puis utilise le bouton Précédent pour revenir à la page principale à laquelle il a accédé avant de se connecter et voit une expérience différente. Dans ce scénario, la mbox globale n’avait pas transmis `3rdPartyID`, mais une ou plusieurs des mbox enfants l’avaient fait. `3rdPartyID` a pris la priorité sur PCID.

* Vous pouvez envoyer les ID client des visiteurs à [!DNL Target] à l’aide de deux approches :

   1. Utilisez `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` est le nom du paramètre lorsque vous utilisez `targetPageParams` ou `targetPageParamsAll`.
      * `thirdPartyId` est le nom du paramètre que vous définissez directement dans la payload de l’API de diffusion.
      * Vous ne pouvez envoyer qu’une seule valeur dans ce paramètre.

   1. Utilisez la fonction `setCustomerId`/`customerIds` du service ECID.

      * `setCustomerId` est une fonction que vous pouvez utiliser dans les implémentations côté client (navigateur) lorsque VisitorAPI.js est disponible sur la page.
      * `customerIds` est le nom du paramètre utilisé lorsque vous le définissez directement dans la payload de l’API de diffusion. Il est généralement utilisé sur les implémentations côté serveur ou IOT (Internet des objets).
      * Contrairement à `mbox3rdPartyId`/`thirdPartyId`, cette approche vous permet d’envoyer plusieurs ID sous forme de liste. Toutefois, étant donné que [!DNL Target] ne prend en charge qu’un seul ID client par ID TnT, il utilise le premier ID de la liste avec un alias connu (alias configuré dans l’interface utilisateur Attributs du client).

  Vous pouvez utiliser `mbox3rdPartyId`/`thirdPartyId` si [!DNL Target] est votre seule solution [!DNL Adobe Experience Cloud] et que vous ne souhaitez pas utiliser les attributs du client. Pour tous les autres cas, nous vous recommandons d’utiliser `setCustomerId`/`customerIds` pour envoyer vos ID de client.

  >[!IMPORTANT]
  >
  > L’utilisation des deux approches mentionnées ci-dessus de manière interchangeable pour un seul visiteur peut entraîner des fusions de profils incorrectes entre les profils [!DNL Target] authentifiés et non authentifiés.
  >
  >Adobe vous déconseille d’utiliser à la fois `mbox3rdPartyId`/`thirdPartyId` et `setCustomerID`/`customerIds`.
  >
  >Si vous devez utiliser les deux approches de manière interchangeable, assurez-vous que le premier ID de la liste utilisé par `setCustomerID`/`customerIds` est celui utilisé par `thirdPartyId`/`mbox3rdPartyId` et vice versa.

