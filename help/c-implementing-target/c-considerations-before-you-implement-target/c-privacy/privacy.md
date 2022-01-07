---
keywords: confidentialité;adresse ip;géosegmentation;opt-out;opt-out;opt-out;confidentialité des données;réglementation gouvernementale;réglementations;gdpr;ccpa
description: Découvrez comment Adobe [!DNL Target] se conforme aux lois sur la confidentialité des données en vigueur, notamment la collecte et le traitement des adresses IP, ainsi qu’aux instructions d’exclusion.
title: Comment [!DNL Target] Gestion des problèmes de confidentialité ?
feature: Privacy & Security
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: 8fe168950effe60ead262c842fe9d89d1e376e57
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 55%

---

# Confidentialité

[!DNL Adobe Target] dispose de processus et de paramètres activés qui vous permettent d’utiliser [!DNL Target] conformément aux lois sur la confidentialité des données en vigueur.

## Collecte de données d’utilisation des fonctionnalités

Les données d’utilisation des fonctionnalités individuelles sont collectées pour les [!DNL Adobe] les objectifs à atteindre pour déterminer si [!DNL Target] Les fonctions se comportent comme prévu ou pour identifier les fonctions qui sont sous-utilisées. Diverses mesures de latence sont collectées pour répondre aux problèmes de performances. Les données personnelles ne sont pas collectées.

Vous pouvez exclure les données d’utilisation des rapports dans nos SDK en définissant `telemetryEnabled` sur false dans les options d’initialisation du client. Pour plus d’informations, voir [telemetryEnabled dans targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#telemetry).

## Collecte d’adresses IP {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

L’adresse IP d’un visiteur de votre site Web est transmise à un centre de traitement de données Adobe. Selon la configuration du réseau du visiteur, l’adresse IP collectée ne correspond pas nécessairement à l’adresse IP de son ordinateur. Il peut par exemple s’agir de l’adresse IP externe d’un pare-feu NAT (traduction d’adresses réseau), d’un proxy HTTP ou d’une passerelle Internet. Target ne stocke aucune adresse IP de l’utilisateur ni aucune information personnelle identifiable. Les adresses IP sont utilisées uniquement par Target pendant la session (en mémoire, elles ne sont jamais conservées).

## Remplacement du dernier octet des adresses IP {#section_AE84EB0D7CE04E93B279B77732ADD61E}

Adobe a mis en place un nouveau paramètre de « respect de la vie privée dès la conception » qui peut être activé par le service à la clientèle d’Adobe pour Adobe Target. Si ce paramètre est activé, le dernier octet (dernière partie) de l’adresse IP est immédiatement masqué lorsque l’adresse IP est recueillie par Adobe. Cette anonymisation est effectuée avant tout traitement de l’adresse IP, y compris avant une recherche géographique facultative de l’adresse IP.

Si cette fonction est activée, l’adresse IP est suffisamment anonyme pour ne plus être identifiable en tant qu’information personnelle. En conséquence, Adobe Target peut être utilisé conformément aux règles de confidentialité des données dans les pays qui n’autorisent pas la collecte d’informations personnelles. L’obtention d’informations sur les villes sera considérablement entravée par l’obscurcissement de l’adresse IP, tandis que l’obtention des informations sur les régions et les pays ne sera que légèrement entravée.

Les méthodes suivantes sont disponibles :

* Aucun obscurcissement : Target ne masque aucune partie de l’adresse IP.
* Dernier octet : Target masque le dernier octet de l’adresse IP.
* IP complète : Target masque l’adresse IP complète.

Target reçoit l’adresse IP complète et l’obscurcit (s’il est défini sur le dernier octet ou l’adresse IP complète) comme indiqué. Target conserve ensuite l’adresse IP obscurcie en mémoire pendant la session.

>[!NOTE]
>
>[Contacter le service à la clientèle d’Adobe](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) pour déterminer le paramètre que vous utilisez actuellement ou activer la fonction d’obscurcissement d’IP.

## Géosegmentation {#section_BB69F96559BD44BDA4177537C4A5345A}

Si vous activez le remplacement du dernier octet de l’adresse IP, les valeurs restantes de l’adresse IP peuvent être analysées à l’aide des rapports dans Adobe Target. Si le dernier octet de l’adresse IP n’a pas été obscurci, l’adresse IP complète peut être analysée dans Adobe Target. Vous pouvez utiliser la fonctionnalité de géosegmentation pour dessiner l’emplacement du visiteur par zone géographique. Les données de géosegmentation sont alors détaillées au niveau des villes ou des codes postaux uniquement, mais pas au niveau individuel.

Si les adresses IP sont entièrement obscurcies, la géosegmentation et le géociblage ne sont pas disponible.

## Lien d’exclusion {#section_E7A62B7B99C94B3A806CB262D16E27FC}

Vous pouvez ajouter un lien d’exclusion à vos sites pour permettre aux visiteurs de s’exclure de tout comptage et diffusion de contenu.

1. Ajoutez le lien suivant sur votre site :

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. (Conditionnel) Si vous utilisez CNAME, le lien doit contenir &quot;client=`clientcode` par exemple : https://my.cname.domain/optout?client=clientcode.

1. Remplacer `clientcode` avec votre code client et ajoutez le texte ou l’image à lier à l’URL d’exclusion.

Les visiteurs qui cliquent sur ce client ne sont pas inclus dans les requêtes de mbox appelées à partir de leur session de navigation tant qu’ils ne suppriment par leurs cookies ou pendant une durée de 2 ans, le premier événement prévalant. Ce lien définit un cookie, appelé `disableClient`, pour le visiteur dans le domaine `clientcode.tt.omtrdc.net`.

Même si vous utilisez une implémentation avec cookies propriétaires, l’exclusion par défaut est définie par l’intermédiaire d’un cookie tiers. Si le client utilise uniquement un cookie propriétaire, Target vérifie si un cookie d’exclusion est défini.

## Réglementations relatives à la confidentialité et à la protection des données

Voir [Réglementations relatives à la confidentialité et à la protection des données](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) pour plus d’informations sur le Règlement général sur la protection des données (RGPD) de l’Union européenne, la loi sur la protection de la vie privée des consommateurs (CCPA) de Californie et d’autres exigences internationales en matière de confidentialité, ainsi que sur la manière dont ces réglementations affectent votre organisation et Adobe Target.
