---
keywords: placer sur la liste autorisée placer sur la liste bloquée hôte;hôtes;groupe d’hôtes;dépannage;bonnes pratiques;ubox;redirections;redirection;liste blanche;;liste noire;
description: Découvrez comment organiser vos sites web et vos environnements de préproduction pour une gestion facile et des rapports séparés dans Adobe Target.
title: Que sont les hôtes et comment les utiliser ?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 17%

---

# Hôtes

Organisez vos sites et environnements de pré-production pour une gestion facile et des rapports séparés en [!DNL Adobe Target].

La gestion des hôtes vise principalement à garantir qu’aucun contenu inactif ne s’affiche par inadvertance sur les sites web. Host Management vous permet également de séparer les données de rapport par [environnement](/help/main/administrating-target/environments.md).

Un hôte est tout domaine à partir duquel une requête [!DNL Target] est effectuée. Sur un site web, il s’agit généralement de la propriété `location.hostname` de l’URL qui effectue la requête [!DNL Target].

Par défaut, [!DNL Target] ne limite pas un hôte qui peut effectuer des requêtes [!DNL Target] et recevoir des réponses [!DNL Target]. Lorsque de nouveaux hôtes effectuent des requêtes, elles fonctionnent automatiquement. Ce processus permet également de tester différents domaines que vous ne connaissez pas ou ne pouvez pas anticiper. Si vous souhaitez remplacer ce comportement par défaut, vous pouvez configurer une liste autorisée ou une liste bloquée pour limiter les hôtes [!DNL Target].

{{permissions-update}}

To manage hosts, click **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

To recognize a host and add it to the [!UICONTROL Hosts] list, the following conditions must be met:

* At least one [!DNL Target] request must exist on the host
* Une page sur l’hôte doit contenir les éléments suivants :

   * Une référence at.js précise
   * Une requête [!DNL Target] ou une requête [!DNL Target] globale générée automatiquement

* La page contenant la demande de [!DNL Target] doit être consultée dans un navigateur

Une fois la page consultée, l’hôte est répertorié dans la liste [!UICONTROL Hosts], ce qui vous permet de le gérer dans un environnement, ainsi que de prévisualiser et de lancer des activités et des tests.

>[!NOTE]
>
>Cela inclut les serveurs de développement personnel.

Une fois qu’un hôte est ajouté à la liste [!UICONTROL Host], assurez-vous qu’il est reconnu.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Si votre hôte n’apparaît pas dans la liste, actualisez votre navigateur.

   Par défaut, un hôte nouvellement reconnu est placé dans l’environnement [!UICONTROL Production]. L’environnement [!UICONTROL Production] est l’environnement le plus sûr, car il ne permet pas d’afficher les activités inactives à partir de ces hôtes.

1. (Conditionnel) Cliquez sur l’icône **[!UICONTROL Move]** ( ![icône de déplacement](/help/main/administrating-target/assets/icon-move.png) ) pour déplacer l’hôte vers le [!UICONTROL Development], le [!UICONTROL Staging] ou un autre environnement.

>[!NOTE]
>
>L’environnement [!UICONTROL Production] ne peut pas être supprimé, même si vous le renommez. Il est supposé que cet environnement est l’endroit où vous effectuez les activités et les tests finaux et actifs. L’environnement par défaut n’autorise pas l’affichage des campagnes inactives.

## Trier ou rechercher la liste des hôtes {#section_068B23C9D8224EB78BC3B7C8580251B0}

Pour trier la liste [!UICONTROL Hosts], cliquez sur un en-tête de colonne ([!UICONTROL Name], [!UICONTROL Environment] ou [!UICONTROL Last Requested]) pour trier la liste par ordre croissant ou décroissant.

Pour effectuer une recherche dans la liste [!UICONTROL Hosts], saisissez un terme de recherche dans la zone de [!UICONTROL Search Hosts].

## Placer sur la liste autorisée Créez des qui spécifient les hôtes autorisés à envoyer des requêtes [!DNL Target] à [!DNL Target]. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send [!DNL Target] requests to [!DNL Target]. All other hosts generating requests get a commented-out authorization error response. By default, any host that contains a [!DNL Target] request registers with [!DNL Target] in the [!UICONTROL Production] environment and has access to all active and approved activities. If this approach is not desired, you can instead use the allowlist to record specific hosts that are eligible to make [!DNL Target] requests and receive [!DNL Target] content. All hosts continue to display in the [!UICONTROL Hosts] list, and environments can still be used to group these hosts and assign different levels to each, such as whether the host can see active and/or inactive activities.

To create an allowlist:

1. From the [!UICONTROL Hosts] list, click **[!UICONTROL Authorize Hosts]**.
1. Activez le bouton (bascule) **[!UICONTROL Enable Authorized Hosts for content delivery]** .
1. Ajoutez les hôtes souhaités dans la zone de **[!UICONTROL Host contains]**, selon vos besoins.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Ajoutez les hôtes souhaités dans la zone de **[!UICONTROL Host does not contains]**, selon vos besoins.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Cliquez sur **[!UICONTROL Save]**.

Si une requête [!DNL Target] est effectuée sur un hôte non autorisé, l’appel répond par `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>placer sur la liste autorisée **Bonnes pratiques de sécurité** : si vous utilisez la fonctionnalité ubox de [!DNL Target], cette contrôle également la liste des domaines vers lesquels vos [redirecteurs](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html?lang=fr){target=_blank} peuvent naviguer. Veillez à ajouter tous les domaines vers lesquels vous souhaitez rediriger lorsque vous utilisez ubox dans le cadre de votre implémentation. Si la place sur la liste autorisée n’est pas spécifiée, [!DNL Adobe] ne peut pas vérifier les URL de redirection et se protéger contre les redirections malveillantes potentielles.
>
>La liste autorisée prévaut sur les environnements. Effacez tous les hôtes avant d’utiliser la fonction de place sur la liste autorisée, puis seuls les hôtes autorisés par la liste autorisée apparaissent dans votre liste d’hôtes. Vous pouvez ensuite déplacer les hôtes dans l’environnement de votre choix.

Il arrive parfois que les domaines d’autres sites s’affichent dans vos environnements. A domain appears in the list if the domain calls at.js. Si, par exemple, un utilisateur copie l’une de vos pages web sur son serveur, ce domaine est répertorié dans votre environnement. Les domaines de robots, sites de traduction ou disques durs locaux peuvent également s’afficher.

Dans les cas où `mboxHost` est transmis dans un appel d’API, la conversion est enregistrée pour l’environnement transmis. If no environment is passed, the host in the call defaults to [!UICONTROL Production].

You can also create a denylist that specifies hosts (domains) that cannot send [!DNL Target] requests to [!DNL Target] by adding the desired hosts in the [!UICONTROL Host Does Not Contain] box.

>[!NOTE]
>
>La liste [!UICONTROL Authorized Hosts] est utilisée pour les hôtes [!DNL Target] et les hôtes de redirection par défaut. Ajoutez tous les domaines existants approuvés pour utiliser le SDK JavaScript [!DNL Adobe Target] (at.js) *ET* tous les domaines utilisés dans les URL de redirection par défaut de la boîte d’envoi. Ajoutez de nouveaux domaines similaires à la liste autorisée à l’avenir.

## Suppression d’un hôte {#section_F56355BA4BC54B078A1A8179BC954632}

Vous pouvez supprimer un hôte lorsqu’il n’est plus utile.

1. Dans la liste [!UICONTROL Hosts], cliquez sur l’icône **[!UICONTROL Delete]** .
1. Cliquez sur **[!UICONTROL Delete]** pour confirmer la suppression.

>[!NOTE]
>
>L’hôte est à nouveau répertorié si quelqu’un accède à une page contenant une requête [!DNL Target] sur l’hôte.

## Résolution des problèmes liés aux hôtes {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Suivez les conseils de résolution suivants si vous rencontrez des problèmes avec vos hôtes :

**L’hôte n’apparaît pas dans la liste pour votre compte.**

* Actualisez la page [!UICONTROL Hosts] dans votre navigateur.
* Vérifiez que la requête [!DNL Target] est correcte, y compris la référence at.js.
* Essayez d’accéder à l’une des requêtes [!DNL Target] sur l’hôte. Il est possible qu’aucune requête [!DNL Target] sur l’hôte n’ait jamais été rendue dans un navigateur.

**Les domaines aléatoires ou inconnus apparaissent dans la liste [!UICONTROL Host].**

Un domaine apparaît dans cette liste si une demande de [!DNL Target] est effectuée à partir du domaine. Vous pouvez souvent voir des domaines à partir de moteurs de balayage, de sites de traduction de langue ou d’unités de disque locales. Si le domaine répertorié n’est pas celui que votre équipe utilise, vous pouvez cliquer sur [!UICONTROL Delete] pour le supprimer.

**My [!DNL Target] request returns /&#42; no display - unauthorized mbox host &#42;/.**

If a [!DNL Target] request is made on an unauthorized host, the request responds with /&#42; no display - unauthorized mbox host &#42;/.
