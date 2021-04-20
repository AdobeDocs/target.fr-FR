---
keywords: hôte ; hôtes ; groupe d’hôtes ; résolution des problèmes ; bonnes pratiques ; ubox ; redirections ; redirection ; liste autorisée ; liste autorisée ; liste bloquée ; liste bloquée
description: Découvrez comment organiser vos sites Web et vos environnements de préproduction pour une gestion aisée et des rapports séparés à Adobe Target.
title: Que sont les hôtes et comment les utiliser ?
feature: Administration & Configuration
role: Administrator
translation-type: tm+mt
source-git-commit: 86102ed5b49d102660ed38fe0a71612cefcd2caf
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 22%

---


# Hôtes

Organisez vos sites et environnements de préproduction pour une gestion aisée et des rapports séparés dans [!DNL Adobe Target].

La gestion des hôtes vise principalement à garantir qu’aucun contenu inactif ne s’affiche par inadvertance sur les sites web. La gestion des hôtes vous permet également de séparer les données de rapport par [environnement](/help/administrating-target/environments.md).

Un hôte est tout domaine à partir duquel une demande [!DNL Target] est effectuée. Sur un site Web, il s’agit généralement de la propriété `location.hostname` de l’URL qui effectue la demande [!DNL Target].

Par défaut, [!DNL Target] ne limite pas un hôte qui peut faire des demandes [!DNL Target] et recevoir des réponses [!DNL Target]. Lorsque de nouveaux hôtes effectuent des requêtes, elles fonctionnent automatiquement. Ce processus permet également de tester différents domaines que vous ne connaissez pas ou ne pouvez pas anticiper. Si vous souhaitez remplacer ce comportement par défaut, vous pouvez configurer une liste autorisée ou une liste bloquée pour limiter les hôtes qui fonctionnent avec [!DNL Target].

Pour gérer les hôtes, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hôtes]**.

![](assets/hosts_list.png)

## Reconnaissance des hôtes {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Pour reconnaître un hôte et l&#39;ajouter à la liste [!UICONTROL Hôtes], les conditions suivantes doivent être remplies :

* Au moins une requête [!DNL Target] doit exister sur l&#39;hôte
* Une page sur l’hôte doit avoir :

   * Référence exacte à at.js
   * Une requête [!DNL Target] ou une requête globale [!DNL Target] générée automatiquement

* La page contenant la requête [!DNL Target] doit être affichée dans un navigateur.

Une fois la page consultée, l’hôte est répertorié dans la liste [!UICONTROL Hôtes], ce qui vous permet de le gérer dans un environnement, ainsi que de prévisualisation et de lancement d’activités et de tests.

>[!NOTE]
>
>Cela inclut les serveurs de développement personnel.

Après avoir ajouté un hôte à la liste des [!UICONTROL hôtes], assurez-vous qu’il est reconnu.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hôtes]**.
1. Si votre hôte n’apparaît pas dans la liste, actualisez votre navigateur. 


   Par défaut, un hôte nouvellement reconnu est placé dans l’environnement [!UICONTROL Production]. L&#39;environnement [!UICONTROL Production] est l&#39;environnement le plus sûr, car il ne permet pas l&#39;affichage des activités inactives à partir de ces hôtes.

1. (Conditionnel) Cliquez sur l’icône **[!UICONTROL Déplacer]** ( ![icône de déplacement](/help/administrating-target/assets/icon-move.png) ) pour déplacer l’hôte dans [!UICONTROL Développement], [!UICONTROL Évaluation] ou un autre environnement.

>[!NOTE]
>
>L&#39;environnement [!UICONTROL Production] ne peut pas être supprimé, même si vous le renommez. On suppose que c&#39;est dans cet environnement que vous diffusez les activités et tests finaux et principaux. L’environnement par défaut n’autorise pas l’affichage des campagnes inactives.

## Tri ou recherche de la liste Hôtes {#section_068B23C9D8224EB78BC3B7C8580251B0}

Pour trier la liste [!UICONTROL Hôtes], cliquez sur un en-tête de colonne ([!UICONTROL Nom], [!UICONTROL Environnement] ou [!UICONTROL Dernière demande]) afin de trier la liste par ordre croissant ou décroissant.

Pour rechercher la liste [!UICONTROL Hôtes], entrez un terme de recherche dans la zone [!UICONTROL Hôtes de recherche].

## Créez des listes autorisées qui spécifient les hôtes autorisés à envoyer des demandes de Cible à la Cible. {#allowlist}

Vous pouvez créer une liste autorisée qui spécifie les hôtes (domaines) autorisés à envoyer des demandes [!DNL Target] à [!DNL Target]. Tous les autres hôtes générant des requêtes reçoivent une réponse d’erreur d’autorisation commentée. Par défaut, tout hôte qui contient une requête [!DNL Target] est enregistré avec [!DNL Target] dans l&#39;environnement [!UICONTROL Production] et a accès à toutes les activités principales et approuvées. Si cette approche n&#39;est pas souhaitée, vous pouvez utiliser la liste autorisée pour enregistrer les hôtes spécifiques qui peuvent faire des demandes [!DNL Target] et recevoir du contenu [!DNL Target]. Tous les hôtes continuent à s&#39;afficher dans la liste [!UICONTROL Hôtes] et les environnements peuvent toujours être utilisés pour regrouper ces hôtes et attribuer différents niveaux à chacun d&#39;eux, par exemple si l&#39;hôte peut voir les activités principales et/ou inactives.

Pour créer une liste autorisée :

1. Dans la liste [!UICONTROL Hôtes], cliquez sur **[!UICONTROL Autoriser les hôtes]**.
1. Activez l’option **[!UICONTROL Activer les hôtes autorisés pour la diffusion de contenu]**.
1. Ajoutez les hôtes de votre choix dans la zone **[!UICONTROL L&#39;hôte contient]**, selon vos besoins.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Ajoutez les hôtes souhaités dans la zone **[!UICONTROL L&#39;hôte ne contient pas]**, comme vous le souhaitez.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Si une requête [!DNL Target] est envoyée sur un hôte non autorisé, l&#39;appel répond par `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Meilleures pratiques** en matière de sécurité : Si vous utilisez la fonctionnalité de boîte de réception de  [!DNL Target], cette liste autorisée contrôle également la liste des domaines dans lesquels vos  [](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) redirections peuvent naviguer. Assurez-vous d’ajouter les domaines vers lesquels vous souhaitez rediriger lorsque vous utilisez ubox dans le cadre de votre mise en oeuvre. Si la liste autorisée n’est pas spécifiée, [!DNL Adobe] ne peut pas vérifier les URL de redirection et les protéger des redirections malveillantes potentielles.
>
>La liste autorisée prévaut sur les environnements. Supprimez tous les hôtes avant d&#39;utiliser la fonction de liste autorisée, puis seuls les hôtes autorisés par la liste autorisée apparaissent dans la liste des hôtes. Vous pouvez ensuite déplacer les hôtes dans l’environnement de votre choix.

Il arrive parfois que les domaines d’autres sites s’affichent dans vos environnements. Un domaine s’affiche dans la liste si le domaine appelle at.js. Si, par exemple, un utilisateur copie l’une de vos pages web sur son serveur, ce domaine est répertorié dans votre environnement. Les domaines de robots, sites de traduction ou disques durs locaux peuvent également s’afficher.

Dans les cas où `mboxHost` est transmis dans un appel d’API, la conversion est enregistrée pour l’environnement transmis. Si aucun environnement n’est transmis, l’hôte de l’appel prend par défaut la valeur [!UICONTROL Production].

Vous pouvez également créer une liste bloquée qui spécifie les hôtes (domaines) qui ne peuvent pas envoyer de requêtes [!DNL Target] à [!DNL Target] en ajoutant les hôtes souhaités dans la zone [!UICONTROL L&#39;hôte ne contient pas].

>[!NOTE]
>
>La liste [!UICONTROL Hôtes autorisés] est utilisée pour les hôtes [!DNL Target] et les hôtes de redirection par défaut. Ajoutez tous les domaines existants approuvés pour utiliser le [!DNL Adobe Target] SDK JavaScript (at.js) *ET* tous les domaines utilisés dans les URL de redirection par défaut de la boîte de réception. Ajoutez à l’avenir de nouveaux domaines similaires à la liste autorisée.

## Supprimer un hôte {#section_F56355BA4BC54B078A1A8179BC954632}

Vous pouvez supprimer un hôte lorsqu’il n’est plus utile.

1. Dans la liste [!UICONTROL Hôtes], cliquez sur l&#39;icône **[!UICONTROL Supprimer]**.
1. Cliquez sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

>[!NOTE]
>
>L’hôte est de nouveau répertorié si un utilisateur accède à une page contenant une requête [!DNL Target] sur l’hôte.

## Résolution des problèmes liés aux hôtes {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Suivez les conseils de résolution suivants si vous rencontrez des problèmes avec vos hôtes :

**L’hôte n’apparaît pas dans la liste de votre compte.**

* Actualisez la page [!UICONTROL Hôtes] dans votre navigateur.
* Vérifiez que la requête [!DNL Target] est correcte, y compris la référence at.js.
* Essayez d&#39;accéder à l&#39;une des requêtes [!DNL Target] sur l&#39;hôte. Il est possible qu’aucune requête [!DNL Target] sur l’hôte n’ait jamais été rendue dans un navigateur.

**Des domaines aléatoires ou inconnus s’affichent dans la liste des [!UICONTROL hôtes].**

Un domaine s’affiche dans cette liste si une requête à [!DNL Target] est effectuée à partir du domaine. Vous pouvez souvent voir des domaines à partir de moteurs de balayage, de sites de traduction de langue ou d’unités de disque locales. Si le domaine recensé n’est pas utilisé par votre équipe, vous pouvez cliquer sur [!UICONTROL Supprimer] pour le supprimer.

**Ma  [!DNL Target] requête renvoie /* no display - non autorisé mbox host */.**

Si une requête [!DNL Target] est envoyée sur un hôte non autorisé, la requête répond par /* no display - non autorisé mbox host */.
