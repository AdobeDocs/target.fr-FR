---
keywords: mbox;mbox3rdPartyId;synchronisation des profils;synchroniser les profils;PCID
description: Découvrez comment utiliser le mbox3rdPartyId, qui est l’identifiant visiteur de votre entreprise, tel que l’identifiant de membre ou le programme de fidélité de votre entreprise.
title: Comment utiliser la synchronisation des profils en temps réel pour mbox3rdPartyId ?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: c19163020cdcb41a17ea6b65b5b500fadc9c7512
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 61%

---

# Synchronisation des profils en temps réel pour mbox3rdPartyId

Le mbox3rdPartyId dans [!DNL Adobe Target] correspond à l’identifiant visiteur de votre entreprise, tel que l’identifiant de membre pour le programme de fidélité de votre entreprise.

Lorsqu’un visiteur se connecte au site de votre entreprise, cette dernière crée généralement un identifiant qui est associé au compte du visiteur, à sa carte de fidélité, à son numéro de membre ou à tout autre identifiant applicable de l’entreprise.

Lorsqu’un visiteur accède à une page sur laquelle [!DNL Target] est activé, il se voit attribuer un PCID [!DNL Target]. Si le visiteur se connecte ensuite et si l’implémentation transmet mbox3rdPartyId à [!DNL Target], [!DNL Target]associe le mbox3rdPartyId de ce visiteur au PCID [!DNL Target].

Les mises à jour sont synchronisées avec la base de données toutes les trois à cinq minutes. Lorsque le visiteur se déconnecte, les données fusionnées remplacent les données précédentes associées au mbox3rdPartyId, ce qui crée un enregistrement complet des actions de ce visiteur. Si un même attribut existe dans les deux ID (par exemple, le PCID possède l’attribut category=hats et mbox3rdPartyId possède l’attribut category=skis ou si le visiteur affiche l’expérience A avant de se connecter mais que l’expérience B est stockée dans mbox3rdPartyId), l’attribut stocké dans mbox3rdPartyId remplace l’attribut de PCID. Si le visiteur était dans une activité ou une expérience avant de se connecter et si une activité et une expérience différentes sont stockées dans mbox3rdPartyId, ce visiteur est placé dans l’activité et l’expérience de mbox3rdPartyId une fois connecté.

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

Si votre page contient plusieurs mbox et que certaines utilisent uniquement 3rdPartyID, [!DNL Target] n’a pas de profil/contexte de visiteur distinct pour chaque requête de visiteur. Le contexte 3rdPartyID a la priorité sur le contexte PCID. Il suffit qu’une mbox transmette 3rdPartyId pour que son contexte ait la priorité sur PCID.

Supposons, par exemple, qu’un visiteur accède à une page avant de se connecter et de voir une expérience. La mbox globale n’utilise pas 3rdPartyID. Après s’être connecté, le visiteur voit l’une des trois expériences avec des mbox enfants, dont certaines utilisent 3rdPartyID. Le visiteur consulte plusieurs pages du site, puis utilise le bouton Précédent pour revenir à la page principale à laquelle il a accédé avant de se connecter et voit une expérience différente. Dans ce scénario, la mbox globale n’avait pas transmis 3rdPartyID, mais une ou plusieurs des mbox enfants l’avaient fait. 3rdPartyID a la priorité sur PCID.
