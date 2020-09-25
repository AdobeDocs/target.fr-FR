---
keywords: mboxDefine;mboxdefine;mbox define;mboxUpdate;mboxupdate;mbox update;at.js;functions;function
description: Informations sur les fonctions mboxDefine() et mboxUpdate() pour la bibliothèque JavaScript at.js d’Adobe Target.
title: mboxDefine () et mboxUpdate () - at.js 1.x
feature: client-side
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 8789d750e9e0245d88d54a8d3fe342e5b2e616fc
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

---


# mboxDefine () et mboxUpdate () - at.js 1.x

Définissez et mettez à jour une mbox dans Adobe Target.

>[!NOTE]
>
>Ces fonctions sont disponibles pour at.js versions 1.*x* uniquement. Ces fonctions ont été abandonnées avec la version d’at.js 2.x. Elles renvoient le contenu par défaut si elles sont utilisées avec at.js 2.x.

Les fonctions `mboxDefine()` et `mboxCreate()` sont liées aux éléments HTML DIV dans lesquels l’offre doit s’afficher. Ces éléments HTML DIV doivent avoir la classe `mboxDefault`. Si cette classe n’est pas attachée aux éléments HTML, un scintillement peut être visible.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Crée un mappage interne entre un nodeId et le nom d’une mbox, mais n’exécute pas la demande. Cette fonction est utilisée avec `mboxUpdate()`. Elle est intégrée à [!DNL at.js] pour faciliter principalement la transition de [!DNL mbox.js] vers [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Exécute la demande et applique l’offre à l’élément identifié par le `nodeId` dans la fonction `mboxDefine()`. Cette fonction peut être également utilisée pour mettre à jour une mbox initiée par `mboxCreate`. Elle est intégrée à [!DNL at.js] pour faciliter principalement la transition de [!DNL mbox.js] vers [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` peut être remplacé par [adobe.target.getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) et [adobe.target.applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) à l’aide de l’option de sélecteur.

## Exemple {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
