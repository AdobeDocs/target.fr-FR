---
keywords: faq sur mbox.js;questions fréquentes sur mbox.js;document.write;tt.omtrdc.net;blocage de l’analyseur
description: Découvrez l’implémentation héritée de mbox.js d’Adobe Target. Migrez vers le SDK Web Adobe Experience Platform (SDK Web AEP) ou vers la dernière version d’at.js.
title: Que sont les questions fréquentes sur  [!DNL Target] mbox.js ?
feature: at.js
role: Developer
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 75%

---

# Questions fréquentes sur mbox.js

Réponses aux questions fréquentes sur mbox.js.

>[!IMPORTANT]
>
>**Fin de vie de mbox.js** : depuis le 31 mars 2021, la bibliothèque mbox.js n’est plus prise en charge par [!DNL Adobe Target]. Après le 31 mars 2021, tous les appels effectués à partir de mbox.js échoueront et auront une influence sur vos pages qui comportent des activités [!DNL Target] qui s’exécutent en diffusant le contenu par défaut.
>
>Nous recommandons à tous les clients de migrer vers la version la plus récente de la nouvelle bibliothèque JavaScript [!DNL Adobe Experience Platform Web SDK] ou at.js avant cette date afin d’éviter tout problème potentiel sur vos sites. Pour plus d’informations, voir [Aperçu : implémentation de Target pour le web côté client](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

## Pourquoi mes mbox ne se déclenchent-elles pas sur mes pages web ? {#section_4BA5DA424B734324AAB51E4588FA50F5}

Les clients de utilisent parfois des instances basées sur le cloud avec [!DNL Target]Target à des fins de test ou de preuve de concept. Ces domaines, et de nombreux autres, font partie de la [liste des suffixes publics](https://publicsuffix.org/list/public_suffix_list.dat).

Les navigateurs modernes n’enregistrent pas les cookies si vous utilisez ces domaines, sauf si vous personnalisez le paramètre `cookieDomain` à l’aide de targetGlobalSettings(). Pour plus d’informations, voir [Utilisation d’instances basées sur Cloud avec Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566).

## À quoi correspond le domaine tt.omtrdc.net auquel les appels au serveur [!DNL Target] sont adressés ? {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] est le nom de domaine du réseau EDGE d’Adobe utilisé pour recevoir tous les appels au serveur pour Target.

## Pourquoi at.js et mbox.js n’utilisent-ils pas les indicateurs de cookie HttpOnly et Secure ? {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly ne peut être défini que via un code côté serveur. Les cookies Target, tels que mbox, étant créés et enregistrés via le code JavaScript, Target ne peut pas utiliser l’indicateur de cookie HttpOnly.

Secure ne peut être défini que via JavaScript lorsque la page a été chargée via HTTPS. Si la page se charge initialement via HTTP, JavaScript ne peut pas définir cet indicateur. En outre, si l’indicateur Secure est utilisé, le cookie sera disponible uniquement sur les pages HTTPS.

Pour vous assurer que Target peut assurer un suivi correct des utilisateurs, et parce que les cookies sont générés côté client, Target n’utilise aucun de ces indicateurs.
