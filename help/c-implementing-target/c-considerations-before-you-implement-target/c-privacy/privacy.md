---
keywords: confidentialité ; adresse ip ; géosegmentation ; opt-out ; optout ; exclusion ; confidentialité des données ; réglementation gouvernementale ; régulations ; gdpr ; ccpa
description: Découvrez comment l'Adobe [!DNL Target] se conforme aux lois applicables en matière de confidentialité des données, notamment la collecte et le traitement des adresses IP et les instructions d'exclusion.
title: Comment  [!DNL Target] gère-t-on les problèmes de confidentialité ?
feature: Confidentialité et sécurité
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 70%

---

# Confidentialité

[!DNL Adobe Target] a activé des processus et des paramètres qui vous permettent de les utiliser  [!DNL Target] en conformité avec les lois applicables en matière de confidentialité des données.

## Collection d&#39;adresses IP {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

L’adresse IP d’un visiteur de votre site Web est transmise à un centre de traitement de données Adobe. Selon la configuration du réseau du visiteur, l’adresse IP collectée ne correspond pas nécessairement à l’adresse IP de son ordinateur. Il peut par exemple s’agir de l’adresse IP externe d’un pare-feu NAT (traduction d’adresses réseau), d’un proxy HTTP ou d’une passerelle Internet. Target ne stocke aucune adresse IP de l’utilisateur ni aucune information personnelle identifiable. Les adresses IP sont utilisées uniquement par Target pour la durée de la session (en mémoire, jamais conservées).

## Remplacement du dernier octet des adresses IP {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe a mis en place un nouveau paramètre de « respect de la vie privée dès la conception » qui peut être activé par le service à la clientèle d’Adobe pour Adobe Target. Si ce paramètre est activé, le dernier octet (dernière partie) de l’adresse IP est immédiatement masqué lorsque l’adresse IP est recueillie par Adobe. Cette anonymisation a lieu avant le traitement des adresses IP et avant la géolocalisation facultative de l’adresse IP.

Si cette fonction est activée, l’adresse IP est suffisamment anonyme pour ne plus être identifiable en tant qu’information personnelle. En conséquence, Adobe Target peut être utilisé conformément aux règles de confidentialité des données dans les pays qui n’autorisent pas la collecte d’informations personnelles. L’obtention d’informations sur les villes sera considérablement entravée par l’obscurcissement de l’adresse IP, tandis que l’obtention des informations sur les régions et les pays ne sera que légèrement entravée.

Les méthodes suivantes sont disponibles :

* Pas d&#39;obscurcissement : La cible ne masque aucune partie de l’adresse IP.
* Dernier octet : La cible masque le dernier octet de l’adresse IP.
* IP complète : La cible masque l’adresse IP complète.

La cible reçoit l’adresse IP complète et l’obscurcit (si elle est définie sur Dernier octet ou IP complet) comme spécifié. Cible conserve ensuite l’adresse IP obscurcie en mémoire pendant la durée de la session.

>[!NOTE]
>
>[Contactez l’Adobe Client ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Career pour déterminer quel paramètre vous utilisez actuellement ou pour activer la fonction d’obscurcissement d’IP.

## Géosegmentation {#section_BB69F96559BD44BDA4177537C4A5345A}

Si vous activez le remplacement du dernier octet de l’adresse IP, les valeurs restantes de l’adresse IP peuvent être analysées à l’aide des rapports dans Adobe Target. Si le dernier octet de l’adresse IP n’a pas été obscurci, l’adresse IP complète peut être analysée dans Adobe Target. Vous pouvez utiliser la fonctionnalité de géosegmentation pour dessiner l’emplacement du visiteur par zone géographique. Les données de géosegmentation sont alors détaillées au niveau des villes ou des codes postaux uniquement, mais pas au niveau individuel.

Si les adresses IP sont entièrement obscurcies, la géosegmentation et le géociblage ne sont pas disponible.

## Lien d’exclusion {#section_E7A62B7B99C94B3A806CB262D16E27FC}

Vous pouvez ajouter un lien d’exclusion à vos sites pour permettre aux visiteurs de s’exclure de tout comptage et diffusion de contenu.

1. Ajoutez le lien suivant sur votre site :

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`
1. Remplacez le texte `clientcode` par le code du client et ajoutez le texte ou l’image à lier à l’URL d’exclusion.

Les visiteurs qui cliquent sur ce client ne sont pas inclus dans les requêtes de mbox appelées à partir de leur session de navigation tant qu’ils ne suppriment par leurs cookies ou pendant une durée de 2 ans, le premier événement prévalant. Ce lien définit un cookie, appelé `disableClient`, pour le visiteur dans le domaine `clientcode.tt.omtrdc.net`.

Même si vous utilisez une implémentation avec cookies propriétaires, l’exclusion par défaut est définie par l’intermédiaire d’un cookie tiers. Si le client utilise uniquement un cookie propriétaire, Target vérifie si un cookie d’exclusion est défini.

## Réglementations relatives à la confidentialité et à la protection des données

Voir [Réglementations relatives à la protection de la vie privée et des données](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) pour plus d&#39;informations sur le Règlement général sur la protection des données (RGPD) de l&#39;Union européenne, la Loi sur la protection des renseignements personnels des consommateurs de Californie (ACCP) et d&#39;autres exigences internationales relatives à la protection de la vie privée, ainsi que sur l&#39;impact de ces réglementations sur votre organisation et votre Adobe Target.
