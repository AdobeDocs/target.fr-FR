---
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
description: 'Informations sur le profil en temps réel '
title: Synchronisation des profils en temps réel pour mbox3rdPartyId dans Adobe Target
feature: visitor profiles
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 81%

---


# Synchronisation des profils en temps réel pour mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

Le mbox3rdPartyId représente l’identifiant visiteur de votre entreprise (comme l’identifiant de membre pour le programme de fidélité de votre entreprise).

Lorsqu’un visiteur se connecte au site de votre entreprise, cette dernière crée généralement un identifiant qui est associé au compte du visiteur, à sa carte de fidélité, à son numéro de membre ou à tout autre identifiant applicable de l’entreprise.

Lorsqu’un visiteur accède à une page sur laquelle [!DNL Target] est activé, il se voit attribuer un PCID [!DNL Target]. Si le visiteur se connecte ensuite et si l’implémentation transmet mbox3rdPartyId à [!DNL Target], [!DNL Target]associe le mbox3rdPartyId de ce visiteur au PCID [!DNL Target].

Les mises à jour sont synchronisées avec la base de données toutes les trois à cinq minutes. Lorsque le visiteur se déconnecte, les données fusionnées remplacent les données précédentes associées au mbox3rdPartyId, ce qui crée un enregistrement plus complet des actions du visiteur. Si un même attribut existe dans les deux ID (par exemple, le PCID possède l’attribut category=hats et mbox3rdPartyId possède l’attribut category=skis ou si le visiteur affiche l’expérience A avant de se connecter mais que l’expérience B est stockée dans mbox3rdPartyId), l’attribut stocké dans mbox3rdPartyId remplace l’attribut de PCID. Si le visiteur était dans une activité ou une expérience avant de se connecter et si une activité et une expérience différentes sont stockées dans mbox3rdPartyId, ce visiteur est placé dans l’activité et l’expérience de mbox3rdPartyId une fois connecté.

| PCID (session fermée) | mbox3rdPartyId (connecté) | Fusion et enregistrement dans mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Activité 1, Expérience A | Activité 1, Expérience B | Activité 1, Expérience B |
| Activité 1 |  | Activité 1 |

Quand le visiteur se déconnecte, le profil fusionné est conservé.

>[!NOTE]
>
>Si vous souhaitez faire la distinction entre les utilisateurs authentifiés (connectés) et non authentifiés, utilisez le service d’identité Adobe Experience Cloud (ECID) au lieu de mbox3rdPartyID. Une fois qu’un utilisateur est associé à mbox3rdPartyID, il reste associé à l’utilisateur même après sa déconnexion.

>[!NOTE]
>
>[!DNL Adobe Analytics] les objectifs ne seront pas suivis lorsque l’ [!DNL Adobe Experience Cloud] ID (EDID) change (par exemple, le visiteur change de périphérique), même si le [!DNL Target] profil peut être fusionné en fonction de mbox3rdPartyId et contient toujours des informations d’activité. For visitors identified with the same EDID (those who access the page with the same device), [!DNL Analytics for Target] (A4T) should work as expected.

## Considérations {#considerations}

Si votre page contient plusieurs mbox et que certaines utilisent uniquement 3rdPartyID, Target ne dispose pas d’un profil/contexte de visiteur distinct pour chaque requête de visiteur. Le contexte 3rdPartyID a la priorité sur le contexte PCID. Il suffit qu’une mbox transmette 3rdPartyId pour que son contexte ait la priorité sur PCID.

Supposons, par exemple, qu’un visiteur accède à une page avant de se connecter et de voir une expérience. La mbox globale n’utilise pas 3rdPartyID. Après s’être connecté, le visiteur voit l’une des trois expériences avec des mbox enfants, dont certaines utilisent 3rdPartyID. Le visiteur consulte plusieurs pages du site, puis utilise le bouton Précédent pour revenir à la page principale à laquelle il a accédé avant de se connecter et voit une expérience différente. Dans ce scénario, la mbox globale n’avait pas transmis 3rdPartyID, mais une ou plusieurs des mbox enfants l’avaient fait. 3rdPartyID a la priorité sur PCID.
