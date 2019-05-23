---
description: Le mbox3rdPartyID représente l’identifiant visiteur de votre entreprise (comme l’identifiant de membre pour le programme de fidélité de votre entreprise).
keywords: mbox;mbox3rdPartyID;synchronisation des profils;synchroniser les profils
seo-description: Le mbox3rdPartyID représente l’identifiant visiteur de votre entreprise (comme l’identifiant de membre pour le programme de fidélité de votre entreprise).
seo-title: Synchronisation des profils en temps réel pour mbox3rdPartyID
solution: Target
title: Synchronisation des profils en temps réel pour mbox3rdPartyID
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 17f0612559bae335d261ebc7654bc5d7fe3c0d12

---


# Synchronisation des profils en temps réel pour mbox3rdPartyID{#real-time-profile-syncing-for-mbox-rdpartyid}

Le mbox3rdPartyID représente l’identifiant visiteur de votre entreprise (comme l’identifiant de membre pour le programme de fidélité de votre entreprise).

Lorsqu’un visiteur se connecte au site de votre entreprise, cette dernière crée généralement un identifiant qui est associé au compte du visiteur, à sa carte de fidélité, à son numéro de membre ou à tout autre identifiant applicable de l’entreprise.

Lorsqu’un visiteur accède à une page sur laquelle Target est activé, il se voit attribuer un PCID Target. Si le visiteur se connecte ensuite et si l’implémentation transmet mbox3rdPartyID à Target, Target associe le mbox3rdPartyID de ce visiteur au PCID Target.

Les mises à jour sont synchronisées avec la base de données toutes les trois à cinq minutes. Lorsque le visiteur se déconnecte, les données fusionnées remplacent les données précédentes associées au mbox3rdPartyID, ce qui crée un enregistrement plus complet des actions du visiteur. Si un même attribut existe dans les deux ID (par exemple, le PCID possède l’attribut category=hats et mbox3rdPartyID possède l’attribut category=skis ou si le visiteur affiche l’expérience A avant de se connecter mais que l’expérience B est stockée dans mbox3rdPartyID), l’attribut stocké dans mbox3rdPartyID remplace l’attribut de PCID. Si le visiteur était dans une activité ou une expérience avant de se connecter et si une activité et une expérience différentes sont stockées dans mbox3rdPartyID, ce visiteur est placé dans l’activité et l’expérience de mbox3rdPartyID une fois connecté.

| PCID (non connecté) | mbox3rdPartyID (session ouverte) | Fusion et enregistrement dans mbox3rdPartyID |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Activité 1, Expérience A | Activité 1, Expérience B | Activité 1, Expérience B |
| Activité 1 |  | Activité 1 |

Quand le visiteur se déconnecte, le profil fusionné est conservé.

>[!NOTE]
>
>[!DNL Adobe Analytics] les objectifs ne sont pas suivis dans les cas où les [!DNL Adobe Experience Cloud] modifications d&#39;ID (MID) changent (par exemple, le visiteur change de périphérique), même si [!DNL Target] le profil peut être fusionné sur la base du mbox 3 rdpartyid et comporte toujours des informations sur l&#39;activité. Pour les visiteurs identifiés avec le même MID (ceux qui accèdent à la page avec le même appareil) [!DNL Analytics for Target] , (A 4 T) fonctionnent normalement.
