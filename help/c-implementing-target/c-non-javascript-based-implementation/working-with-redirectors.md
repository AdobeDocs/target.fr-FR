---
keywords: Implementation;mbox.js non javascript;redirector;costs per click;revenue per click
description: L’utilisation d’un redirecteur s’apparente à celle d’une mbox dans vos tests.
title: Fonctionnement avec un redirecteur
feature: email implementation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 69%

---


# Fonctionnement avec un redirecteur{#work-with-redirectors}

L’utilisation d’un redirecteur s’apparente à celle d’une mbox dans vos tests.

Les redirecteurs sont créés avec une URL de redirecteur spéciale qui charge une mbox Redirecteur dans votre compte L’utilisation de ce redirecteur s’apparente à celle d’une mbox dans vos tests. Envoyez l’URL du redirecteur à votre réseau publicitaire en tant que lien de destination de l’annonce.

Utilisez le redirecteur pour effectuer les opérations suivantes :

* Assurer le suivi des clics à partir de vos publicités jusqu’à votre site.
* Créer un rapport centralisé unique pour effectuer le suivi des clics sur les publicités affichées sur plusieurs réseaux publicitaires.
* Modifier les destinations des publicités.

   Par exemple, une même bannière pointe vers votre page d’accueil, votre page de catégories et votre page de produits.

* Déterminer quelle page d’entrée entraîne le plus de conversions.

Pour obtenir de l’aide sur le choix de la configuration appropriée, reportez-vous à la rubrique [Mises en œuvre non basées sur JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Créer un redirecteur {#redirector}

Pour pouvoir utiliser un redirecteur, vous devez le créer.

1. Déterminez les variations de destination de l’annonce, y compris la destination par défaut.
1. Créez l’URL de redirecteur.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Où `yourclientcode` est le code client de votre société. Le code client de votre entreprise est en minuscules et ne comporte pas de caractères spéciaux.

      Votre code client est disponible en haut de la page [!UICONTROL Administration > Implémentation] de l’interface [!DNL Target].

   * `redirectorlink_456` est le nom de la mbox Redirecteur qui s’affiche dans votre compte pour être utilisée dans des campagnes et des tests.

      Les redirecteurs fonctionnent différemment des autres mbox, mais leur apparence est identique à celle de toute autre mbox de votre compte. Nommez le redirecteur de manière à pouvoir le différencier facilement des mbox de type standard de votre compte. Pour respecter les bonnes pratiques, commencez le nom de la mbox par redirectorlink.

   * Où `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` est la destination par défaut.

      Elle doit être en codage URL et il doit s’agir d’une référence absolue. Vous pouvez utiliser la [référence de codage d’URL HTML](https://www.w3schools.com/tags/ref_urlencode.asp) pour coder rapidement vos URL.

      >[!IMPORTANT]
      >
      >Notez qu&#39;avec Redirecteur, vous pouvez être exposé à un risque de vulnérabilité de redirection ouverte. Pour éviter l’utilisation non autorisée de liens Redirecteur par des tiers, nous vous recommandons d’utiliser des &quot;hôtes autorisés&quot; pour placer sur la liste autorisée les domaines d’URL de redirection par défaut. Cible utilise des hôtes pour placer sur la liste autorisée les domaines auxquels vous souhaitez autoriser les redirections. Pour plus d’informations, voir [Création de Listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à la Cible](/help/administrating-target/hosts.md#allowlist) dans *Hôtes*.

1. Validez le redirecteur.
   1. *Meilleure pratique* en matière de sécurité : Assurez-vous que le domaine utilisé dans le redirecteur est placé sur la liste autorisée, comme indiqué ci-dessus. Si vous utilisez un domaine qui n’est pas placé sur la liste autorisée, l’Adobe bloquera tout appel à ce domaine afin d’empêcher les acteurs malveillants d’utiliser le redirecteur pour rediriger vers des domaines potentiellement malveillants.
   1. Insérez l’URL du redirecteur dans un navigateur et procédez à l’actualisation.
   1. Connectez-vous à votre compte, actualisez votre liste de mbox et vérifiez que le nouveau redirecteur est répertorié en tant que mbox.
1. Si vous testez différentes destinations pour une même publicité, créez des [offres de redirection](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) pour chaque version.
1. Créez la campagne.

   Consultez les [Implémentations non basées sur JavaScript](/help/c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4) pour connaître la configuration appropriée permettant d’atteindre vos objectifs.
1. Effectuez une AQ sur la campagne.

   Créez une page factice avec une `<a href>` contenant l’URL de redirection. Exemple :

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. Vérifiez que toutes les expériences, le contenu par défaut et les rapports fonctionnent comme prévu sur tous les types de navigateur et ce, dans tous vos environnements.

   >[!NOTE]
   >
   >* Les redirecteurs ne sont pas pris en charge par la méthode Aperçu de l’offre ou Rechercher les mbox. Prévisualisez les expériences directement dans un navigateur.
   >* `mboxDebug` ne fonctionne pas avec les redirecteurs.


1. Envoyez l’URL complète du redirecteur à votre réseau d’affichage publicitaire en tant que destination de l’annonce.

## Utilisez un redirecteur pour transmettre les coûts par clic et les recettes par clic {#concept_3078EF48E9C44B34992D62AAB9628853}

Informations sur l’utilisation d’un redirecteur pour transmettre des coûts par clic et des recettes par clic.

### Transmission des coûts par clic {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Utilisez un redirecteur pour transmettre les coûts par clic.

>[!NOTE]
>
>Il est recommandé de déterminer la valeur de coût à l’aide de la mesure d’engagement **Score par visite**.

Ajoutez `&mboxPageValue=-value` à l’URL. Nous attirons votre attention sur la valeur négative.

Exemple : pour un coût par clic de 0,10 cent :

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### Transmission des recettes par clic {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

Utilisez un redirecteur pour transmettre les recettes par clic.

>[!NOTE]
>
>Il est recommandé de déterminer la valeur des recettes à l’aide de la mesure d’engagement **Score par visite**.

Ajoutez `&mboxPageValue=value` à l’URL.

Exemple : pour un coût par clic de 0,10 cent :

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
