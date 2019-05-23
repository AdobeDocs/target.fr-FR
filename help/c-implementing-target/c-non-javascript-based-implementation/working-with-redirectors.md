---
description: L’utilisation d’un redirecteur s’apparente à celle d’une mbox dans vos tests.
keywords: Implémentation;mbox.js sans javascript;redirection;coûts par clic;revenu par clic
seo-description: L’utilisation d’un redirecteur s’apparente à celle d’une mbox dans vos tests.
seo-title: Fonctionnement avec un redirecteur
solution: Target
subtopic: Prise en main
title: Fonctionnement avec un redirecteur
topic: Standard
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
translation-type: tm+mt
source-git-commit: ece87434c94501eeed1d6af9cb2a92f8585775b7

---


# Fonctionnement avec un redirecteur{#work-with-redirectors}

L’utilisation d’un redirecteur s’apparente à celle d’une mbox dans vos tests.

Les redirecteurs sont créés avec une URL de redirecteur spéciale qui charge une mbox Redirecteur dans votre compte L’utilisation de ce redirecteur s’apparente à celle d’une mbox dans vos tests. Envoyez l’URL du redirecteur à votre réseau publicitaire en tant que lien de destination de l’annonce.

Utilisez le redirecteur pour   effectuer les opérations suivantes :

* Assurer le suivi des clics à partir de vos publicités jusqu’à votre site.
* Créer un rapport centralisé unique pour effectuer le suivi des clics sur les publicités affichées sur plusieurs réseaux publicitaires.
* Modifier les destinations des publicités.

   Par exemple, une même bannière pointe vers votre page d’accueil, votre page de catégories et votre page de produits.

* Déterminer quelle page d’entrée entraîne le plus de conversions.

Pour obtenir de l’aide sur le choix de la configuration appropriée, reportez-vous à la rubrique  [Mises en œuvre non basées sur JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Création d’un redirecteur {#task_76608B0F73FC45C4A9F125B894DCF821}

Pour pouvoir utiliser un redirecteur, vous devez le créer.

1. Déterminez les variations de destination de l’annonce, y compris la destination par défaut.
1. Créez l’URL de redirecteur.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Où `yourclientcode` est le code client de votre entreprise ? Le code client de votre entreprise est en minuscules et ne comporte pas de caractères spéciaux.

      * **at.js :** le code client figure dans la partie supérieure de la page [!UICONTROL Configuration &gt; Implémentation &gt; Modifier les paramètres at.js.] de l’[!DNL Target]interface.

      * **mbox.js :** le code client figure dans la partie supérieure de la page [!UICONTROL Configuration &gt; Implémentation &gt; Modifier les paramètres Mbox.js.]
   * `redirectorlink_456` est le nom de la mbox Redirecteur qui s’affiche dans votre compte pour être utilisée dans des campagnes et des tests.

      Les redirecteurs fonctionnent différemment des autres mbox, mais leur apparence est identique à celle de toute autre mbox de votre compte. Nommez le redirecteur de manière à pouvoir le différencier facilement des mbox de type standard de votre compte. Pour respecter les bonnes pratiques, commencez le nom de la mbox par redirectorlink.

   * Où `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` est la destination par défaut.

      Elle doit être en codage URL et il doit s’agir d’une référence absolue. Vous pouvez utiliser la référence au codage URL [HTML](https://www.w3schools.com/tags/ref_urlencode.asp) pour coder rapidement vos URL. |



1. Validez le redirecteur.
   1. Insérez l’URL du redirecteur dans un navigateur et procédez à l’actualisation.
   1. Connectez-vous à votre compte, actualisez votre liste de mbox et vérifiez que le nouveau redirecteur est répertorié en tant que mbox.
1. Si vous testez différentes destinations pour une même publicité, créez des [offres de redirection](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) pour chaque version.
1. Créez la campagne.

   Consultez les [Implémentations non basées sur JavaScript](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) pour connaître la configuration appropriée permettant d’atteindre vos objectifs.
1. Effectuez une AQ sur la campagne.

   Créez une page factice avec une `<a href>` contenant l’URL de redirection. Exemple :

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Vérifiez que toutes les expériences, le contenu par défaut et les rapports fonctionnent comme prévu sur tous les types de navigateur et ce, dans tous vos environnements.

   >[!NOTE] {class=&quot;- topic/note &quot;}
   >
   >* Les redirecteurs ne sont pas pris en charge par la méthode Aperçu de l’offre ou Rechercher les mbox. Prévisualisez les expériences directement dans un navigateur.
   >* `mboxDebug` ne fonctionne pas avec les redirecteurs.


1. Envoyez l’URL complète du redirecteur à votre réseau d’affichage publicitaire en tant que destination de l’annonce.

## Utilisation d’un redirecteur pour transmettre les coûts par clic et les recettes par clic {#concept_3078EF48E9C44B34992D62AAB9628853}

Informations sur l’utilisation d’un redirecteur pour transmettre des coûts par clic et des recettes par clic.

### Transmission des coûts par clic {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Utilisez un redirecteur pour transmettre les coûts par clic.

>[!NOTE]
>
>La bonne pratique consiste à déterminer la valeur de coût à l&#39;aide de **la mesure** d&#39;engagement Score par visite, comme décrit dans [Engagement](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Ajoutez `&mboxPageValue=-value` à l’URL. Nous attirons votre attention sur la valeur négative.

Exemple : pour un coût par clic de 0,10 cent :

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### Transmission des recettes par clic  {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Utilisez un redirecteur pour transmettre les recettes par clic.

>[!NOTE]
>
>La bonne pratique consiste à déterminer la valeur des recettes à l&#39;aide de **la mesure** d&#39;engagement Score par visite, comme décrit [dans Engagement](https://marketing.adobe.com/resources/help/en_US/tnt/help/c_Capturing_Engagement.html).

Ajoutez `&mboxPageValue=value` à l’URL.

Exemple : pour un coût par clic de 0,10 cent :

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
