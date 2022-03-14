---
keywords: mboxDefine;mboxdefine;mbox define;mboxUpdate;mboxupdate;mbox update;at.js;fonctions;fonction
description: Utilisation des fonctions mboxDefine() et mboxUpdate() pour l’Adobe [!DNL Target] Bibliothèque JavaScript at.js pour définir ou mettre à jour une mbox. (at.js 1.x)
title: Comment utiliser les fonctions mboxDefine() et mboxUpdate() ?
feature: at.js
role: Developer
exl-id: 48261be0-c4d0-4961-9712-ef7e0d2cb1c0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 75%

---

# mboxDefine () et mboxUpdate () - at.js 1.x

Définissez et mettez à jour une mbox dans Adobe Target.

>[!NOTE]
>
>Ces fonctions sont disponibles pour at.js versions 1.*x* uniquement. Ces fonctions ont été abandonnées avec la version d’at.js 2.x. Elles renvoient le contenu par défaut si elles sont utilisées avec at.js 2.x.

Les fonctions `mboxDefine()` et `mboxCreate()` sont liées aux éléments HTML DIV dans lesquels l’offre doit s’afficher. Ces éléments HTML DIV doivent avoir la classe `mboxDefault`. Si cette classe n’est pas attachée aux éléments HTML, un scintillement peut être visible.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Crée un mappage interne entre un nodeId et le nom d’une mbox, mais n’exécute pas la demande. Cette fonction est utilisée avec `mboxUpdate()`. Intégré à [!DNL at.js] pour faciliter principalement la transition [!DNL mbox.js] (désormais obsolète) en [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Exécute la demande et applique l’offre à l’élément identifié par le `nodeId` dans la fonction `mboxDefine()`. Cette fonction peut être également utilisée pour mettre à jour une mbox initiée par `mboxCreate`. Intégré à [!DNL at.js] pour faciliter principalement la transition [!DNL mbox.js] (désormais obsolète) en [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` peut être remplacé par [adobe.target.getOffer()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) et [adobe.target.applyOffer()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) à l’aide de l’option de sélecteur.

## Exemple {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
