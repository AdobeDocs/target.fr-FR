---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: Organisez vos sites et environnements de préproduction pour une gestion simplifiée et une création de rapports distincte.
title: Hôtes
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 1dc6fc4a9ad582cb4ace5394c5b9834aa8cd3f58
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 57%

---


# Hôtes{#hosts}

Organisez vos sites et environnements de préproduction pour une gestion simplifiée et une création de rapports distincte.

La gestion des hôtes vise principalement à garantir qu’aucun contenu inactif ne s’affiche par inadvertance sur les sites web. Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

Un hôte est un serveur (ou domaine) web d’où vous diffusez le contenu durant une étape de votre projet. Tout hôte diffusant une mbox est reconnu.

Les hôtes sont regroupés dans des environnements afin d’en faciliter la gestion. Par exemple, dix hôtes peuvent être groupés dans deux ou trois environnements. The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. Si vous le souhaitez, vous pouvez ajouter de nouveaux environnements et renommer vos environnements.

One environment, the default environment, is pre-named [!UICONTROL Production]. Il n’est pas possible de supprimer cet environnement, même si vous le renommez. [!DNL Target] considère que c’est là que vous diffuserez les activités et tests finaux et approuvés.

When an mbox request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. The [!UICONTROL Production] environment cannot have its settings changed, so unknown or new sites are guaranteed to see only content that is active and ready. Grâce à la gestion des hôtes, vous pouvez facilement garantir la qualité des nouvelles activités et du nouveau contenu dans vos environnements de test et de développement, avant d’activer les activités.

[!DNL Target] ne limite pas un hôte qui peut envoyer et recevoir des mbox. Ainsi, lorsque de nouveaux serveurs ou domaines apparaissent, ils fonctionnent automatiquement (à moins que vous n’ayez configuré une liste d’autorisations ou de blocs). Ceci permet également de tester les publicités sur différents domaines que vous ne connaissez pas ou ne pouvez pas anticiper.

Pour gérer les hôtes, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hôtes]**.

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Pour reconnaître un hôte et l’ajouter à la liste [!UICONTROL Hôtes] , les conditions suivantes doivent être remplies :

* Au moins une mbox doit exister sur l’hôte.
* Une page sur l’hôte doit avoir :

   * Référence exacte à at.js ou mbox.js
   * Une mbox ou un appel de mbox globale généré automatiquement

* La page contenant la mbox doit être consultée dans un navigateur.

Une fois la page consultée, l’hôte est répertorié dans la liste des [!UICONTROL hôtes], ce qui vous permet de le gérer dans un environnement, ainsi que de prévisualiser et de lancer des activités et des tests.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Cela inclut les serveurs de développement personnel.

Après avoir ajouté un hôte à la liste des [!UICONTROL hôtes], assurez-vous qu’il est reconnu.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hôtes]**.
1. Si votre hôte n’apparaît pas dans la liste, actualisez votre navigateur. 


   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. Il s’agit de l’environnement le plus sécurisé, car il n’autorise pas l’affichage des activités inactives à partir de ces hôtes.

1. (Conditionnel) Cliquez sur l’icône Déplacer ( icône ![](/help/administrating-target/assets/icon-move.png) Déplacer ) pour déplacer l’hôte dans le [!UICONTROL environnement Développement], [!UICONTROL Évaluation]ou autre.

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. On considère que c’est là que vous diffuserez les activités et tests finaux et actifs. L’environnement par défaut n’autorise pas l’affichage des campagnes inactives.

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send mbox calls to Target. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send mbox calls to [!DNL Target]. Tous les autres hôtes générant des appels obtiendront une réponse d’erreur d’autorisation commentée. Par défaut, tout hôte qui contient un appel de mbox est enregistré avec [!DNL Target] dans l’environnement Production et a accès à toutes les activités actives et approuvées. If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make mbox calls and receive [!DNL Target] content. Tous les hôtes continueront à apparaître dans la liste des [!UICONTROL hôtes] et les environnements pourront continuer à être utilisés pour grouper ces hôtes et attribuer différents niveaux à chacun d’eux, par exemple si l’hôte peut voir les campagnes actives et/ou inactives.

Pour créer une liste d&#39;autorisations :

1. Dans la liste [!UICONTROL Hôtes] , cliquez sur **[!UICONTROL Autoriser les hôtes]**.
1. Activez la bascule **[!UICONTROL Activer les hôtes autorisés pour la diffusion]** de contenu.
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Si un appel de mbox a lieu sur un hôte non autorisé, l’appel renvoie `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Meilleures pratiques** en matière de sécurité : Si vous utilisez la fonctionnalité de boîte de réception de [!DNL Target], notez que cette liste d’autorisations contrôle également la liste des domaines sur lesquels vos [redirecteurs](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) peuvent naviguer. Assurez-vous d’ajouter les domaines vers lesquels vous souhaitez rediriger lorsque vous utilisez ubox dans le cadre de votre mise en oeuvre. Si la liste d’autorisations n’est pas spécifiée, Adobe ne pourra pas vérifier les URL de redirection et se protéger des redirections malveillantes potentielles.
>
>La liste d’autorisations prévaut sur les environnements. Vous devez effacer tous les hôtes avant d&#39;utiliser la fonction allowlist, puis seuls les hôtes autorisés par cette fonction apparaissent dans la liste hosts. Vous pouvez ensuite déplacer les hôtes dans l’environnement de votre choix.

Il arrive parfois que les domaines d’autres sites s’affichent dans vos environnements. Un domaine s’affiche dans la liste si le domaine appelle at.js ou mbox.js. Si, par exemple, un utilisateur copie l’une de vos pages web sur son serveur, ce domaine est répertorié dans votre environnement. Les domaines de robots, sites de traduction ou disques durs locaux peuvent également s’afficher.

Dans les cas où `mboxHost` est transmis dans un appel d’API, la conversion est enregistrée pour l’environnement transmis. If no environment is passed, the host in the call defaults to [!UICONTROL Production].

Vous pouvez également créer une liste noire qui spécifie les hôtes (domaines) qui ne peuvent pas envoyer d’appels de mbox à [!DNL Target] en ajoutant les hôtes souhaités dans la zone [!UICONTROL L’hôte ne contient pas].

>[!NOTE]
>
>La liste Hôtes autorisés étant utilisée à la fois pour les hôtes de mbox et les hôtes de redirection par défaut, vous devez ajouter tous les domaines existants approuvés pour utiliser le SDK JavaScript de la Cible Adobe (at.js) ** ET tous les domaines utilisés dans les URL de redirection par défaut de la boîte de réception. Vous devez également ajouter à l’avenir de nouveaux domaines similaires à la liste des domaines autorisés.

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

Vous pouvez supprimer un hôte lorsqu’il n’est plus utile.

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. Cliquez sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

>[!NOTE]
>
>L’hôte sera de nouveau répertorié si un utilisateur accède à une page contenant une mbox sur l’hôte.

## Résolution des problèmes liés aux hôtes {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Bonnes pratiques pour la gestion et la résolution des problèmes liés aux hôtes dans [!DNL Adobe Target].

Suivez les conseils de résolution suivants si vous rencontrez des problèmes avec vos hôtes :

**L’hôte ne s’affiche pas dans la liste des mbox associées à votre compte.**

* Actualisez la page [!UICONTROL Hôtes] dans votre navigateur.
* Vérifiez que le code mbox est correct, y compris la référence at.js ou mbox.js.
* Accédez à l’une des mbox sur l’hôte. Il est possible qu’aucune mbox sur l’hôte n’ait jamais été traitée dans un navigateur.

**Des domaines aléatoires ou inconnus s’affichent dans la liste des[!UICONTROL hôtes].**

Un domaine s’affiche dans la liste si un appel à [!DNL Target] a été lancé à partir du domaine. Vous pouvez souvent voir des domaines à partir de moteurs de balayage, de sites de traduction de langue ou d’unités de disque locales. Si le domaine recensé n’est pas utilisé par votre équipe, vous pouvez cliquer sur [!UICONTROL Supprimer] pour le supprimer.

**L’appel de mbox renvoie /* no display - unauthorized mbox host */ (aucun affichage - hôte de mbox non autorisé).**

Si un appel de mbox a lieu sur un hôte non autorisé, l’appel renvoie /* no display - unauthorized mbox host */ (aucun affichage - hôte de mbox non autorisé).
