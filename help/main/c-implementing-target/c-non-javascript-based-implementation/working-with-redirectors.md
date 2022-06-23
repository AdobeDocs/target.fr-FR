---
keywords: Implémentation;mbox.js sans javascript;redirection;coûts par clic;revenu par clic
description: Découvrez comment utiliser les redirecteurs dans les implémentations de messagerie, comme vous le faites avec une mbox dans votre Adobe [!DNL Target] activités.
title: Comment travailler avec des redirecteurs ?
feature: Implement Email
role: Developer
exl-id: 1e7b99e4-857b-4d0f-afbd-2c5ce6bf0557
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 68%

---

# Fonctionnement avec un redirecteur

L’utilisation d’un redirecteur s’apparente à celle d’une mbox dans vos tests.

Les redirecteurs sont créés avec une URL de redirecteur spéciale qui charge une mbox Redirecteur dans votre compte L’utilisation de ce redirecteur s’apparente à celle d’une mbox dans vos tests. Envoyez l’URL du redirecteur à votre réseau publicitaire en tant que lien de destination de l’annonce.

Utilisez le redirecteur pour effectuer les opérations suivantes :

* Assurer le suivi des clics à partir de vos publicités jusqu’à votre site.
* Créer un rapport centralisé unique pour effectuer le suivi des clics sur les publicités affichées sur plusieurs réseaux publicitaires.
* Modifier les destinations des publicités.

   Par exemple, une même bannière pointe vers votre page d’accueil, votre page de catégories et votre page de produits.

* Déterminer quelle page d’entrée entraîne le plus de conversions.

Pour obtenir de l’aide sur le choix de la configuration appropriée, reportez-vous à la rubrique [Mises en œuvre non basées sur JavaScript](https://developer.adobe.com/target/implement/email/).

## Création d’un redirecteur {#redirector}

Pour pouvoir utiliser un redirecteur, vous devez le créer.

1. Déterminez les variations de destination de l’annonce, y compris la destination par défaut.
1. Créez l’URL de redirecteur.

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * Où `yourclientcode` est le code client de votre société. Le code client de votre entreprise est en minuscules et ne comporte pas de caractères spéciaux.

      Votre code client figure dans la partie supérieure du [!UICONTROL Administration > Mise en oeuvre] de la [!DNL Target] .

   * `redirectorlink_456` est le nom de la mbox Redirecteur qui s’affiche dans votre compte pour être utilisée dans des campagnes et des tests.

      Les redirecteurs fonctionnent différemment des autres mbox, mais leur apparence est identique à celle de toute autre mbox de votre compte. Nommez le redirecteur de manière à pouvoir le différencier facilement des mbox de type standard de votre compte. Pour respecter les bonnes pratiques, commencez le nom de la mbox par redirectorlink.

   * Où `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` est la destination par défaut.

      Elle doit être en codage URL et il doit s’agir d’une référence absolue. Vous pouvez utiliser la variable [Référence de codage d’URL de HTML](https://www.w3schools.com/tags/ref_urlencode.asp) pour coder rapidement vos URL.

      >[!IMPORTANT]
      >
      >Notez qu’avec Redirecteur, vous pouvez être exposé à un risque de vulnérabilité de redirection ouverte. Pour éviter l’utilisation non autorisée de liens de redirection par des tiers, nous vous recommandons d’utiliser des &quot;hôtes autorisés&quot; pour placer sur la liste autorisée les domaines d’URL de redirection par défaut. Target utilise des hôtes pour placer sur la liste autorisée les domaines vers lesquels vous souhaitez autoriser les redirections. Pour plus d’informations, consultez [Création de listes autorisées qui spécifient les hôtes autorisés à envoyer des appels de mbox à Target](/help/main/administrating-target/hosts.md#allowlist) dans *Hôtes*.

1. Validez le redirecteur.
   1. *Bonnes pratiques en matière de sécurité*: Assurez-vous que le domaine utilisé dans le redirecteur est placé sur la liste autorisée, comme indiqué ci-dessus. Si vous utilisez un domaine qui n’est pas placé sur la liste autorisée, l’Adobe bloquera les appels vers ce domaine afin d’empêcher les acteurs malveillants d’utiliser le redirecteur pour rediriger vers des domaines potentiellement malveillants.
   1. Insérez l’URL du redirecteur dans un navigateur et procédez à l’actualisation.
   1. Connectez-vous à votre compte, actualisez votre liste de mbox et vérifiez que le nouveau redirecteur est répertorié en tant que mbox.
1. Si vous testez différentes destinations pour une même publicité, créez des [offres de redirection](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA) pour chaque version.
1. Créez la campagne.

   Voir [Mises en oeuvre non basées sur JavaScript](https://developer.adobe.com/target/implement/email/){target=_blank} pour la configuration appropriée permettant d’atteindre vos objectifs.
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

## Utilisation d’un redirecteur pour transmettre les coûts par clic et les recettes par clic {#concept_3078EF48E9C44B34992D62AAB9628853}

Informations sur l’utilisation d’un redirecteur pour transmettre des coûts par clic et des recettes par clic.

### Transmission des coûts par clic {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

Utilisez un redirecteur pour transmettre les coûts par clic.

>[!NOTE]
>
>La bonne pratique consiste à déterminer la valeur de coût à l’aide de la variable **Score par visite** mesure d’engagement.

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
>La bonne pratique consiste à déterminer la valeur des recettes à l’aide de la variable **Score par visite** mesure d’engagement.

Ajoutez `&mboxPageValue=value` à l’URL.

Exemple : pour un coût par clic de 0,10 cent :

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
