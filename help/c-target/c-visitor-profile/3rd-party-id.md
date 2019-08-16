---
description: Le mbox3rdPartyID représente l’identifiant visiteur de votre entreprise (comme l’identifiant de membre pour le programme de fidélité de votre entreprise).
keywords: mbox;mbox3rdPartyID;synchronisation des profils;synchroniser les profils; PCID
seo-description: 'Informations sur le profil en temps réel '
seo-title: Synchronisation des profils en temps réel pour mbox 3 rdpartyid dans Adobe Target
solution: Target
title: Synchronisation des profils en temps réel pour mbox3rdPartyID
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 647776170531230a0d0f0aa3d97565fbb75bc963

---


# Synchronisation des profils en temps réel pour mbox3rdPartyID{#real-time-profile-syncing-for-mbox-rdpartyid}

Le mbox3rdPartyID représente l’identifiant visiteur de votre entreprise (comme l’identifiant de membre pour le programme de fidélité de votre entreprise).

Lorsqu’un visiteur se connecte au site de votre entreprise, cette dernière crée généralement un identifiant qui est associé au compte du visiteur, à sa carte de fidélité, à son numéro de membre ou à tout autre identifiant applicable de l’entreprise.

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyID to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyID with the [!DNL Target] PCID.

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
>[!DNL Adobe Analytics] les objectifs ne sont pas suivis dans les cas où les modifications d’ID [!DNL Adobe Experience Cloud] (MID) changent (par exemple, le visiteur change de périphérique), même si le profil [!DNL Target] peut être fusionné sur la base du mbox3rdPartyID et comporte toujours des informations sur l’activité. Pour les visiteurs identifiés avec le même MID (ceux qui accèdent à la page avec le même appareil), [!DNL Analytics for Target] (A4T) fonctionne normalement.

## Considérations {#considerations}

Si votre page contient plusieurs mbox et que certains utilisent uniquement 3 rdpartyid, Target ne dispose pas d'un profil/contexte de visiteur distinct pour chaque requête de visiteur. Le contexte 3 rdpartyid a priorité sur le contexte PCID. Il suffit d'une mbox pour transmettre 3 rdpartyid pour que son contexte soit prioritaire sur PCID.

Supposons, par exemple, qu'un visiteur accède à une page avant de se connecter et de voir une expérience. La mbox globale n'utilise pas 3 rdpartyid. Après la connexion, le visiteur voit l'une des trois expériences avec des mbox enfants, dont certains utilisent 3 rdpartyid. Le visiteur visite diverses pages du site, puis utilise le bouton Retour pour revenir à la page principale affichée avant de se connecter et de voir une expérience différente. Dans ce scénario, la mbox globale n'avait pas transmis 3 rdpartyid, mais une ou plusieurs des mbox enfants ont été effectuées. 3 Rdpartyid a priorité sur PCID.
