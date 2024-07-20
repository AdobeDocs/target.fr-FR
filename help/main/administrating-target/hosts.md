---
keywords: hôte;hôtes;groupe d’hôtes;résolution des problèmes;bonnes pratiques;boîte de réception;redirections;redirection;liste blanche;liste autorisée;liste noire;liste bloquée
description: Découvrez comment organiser vos sites web et vos environnements de préproduction pour une gestion facile et des rapports distincts dans Adobe Target.
title: Que sont les hôtes et comment les utiliser ?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 17%

---

# Hôtes

Organisez vos sites et environnements de préproduction pour une gestion facile et des rapports distincts dans [!DNL Adobe Target].

La gestion des hôtes vise principalement à garantir qu’aucun contenu inactif ne s’affiche par inadvertance sur les sites web. La gestion des hôtes permet également de séparer les données de rapport par [environnement](/help/main/administrating-target/environments.md).

Un hôte est un domaine à partir duquel une requête [!DNL Target] est effectuée. Sur un site web, il s’agit généralement de la propriété `location.hostname` de l’URL qui effectue la requête [!DNL Target].

Par défaut, [!DNL Target] ne limite pas un hôte qui peut effectuer des requêtes [!DNL Target] et recevoir des réponses [!DNL Target]. Lorsque de nouveaux hôtes effectuent des requêtes, elles fonctionnent automatiquement. Ce processus permet également de tester différents domaines que vous ne connaissez pas ou ne pouvez pas anticiper. Si vous souhaitez remplacer ce comportement par défaut, vous pouvez configurer une liste autorisée ou une liste bloquée pour limiter les hôtes qui fonctionnent avec [!DNL Target].

Pour gérer les hôtes, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

![image hosts_list](assets/hosts_list.png)

## Reconnaissance des hôtes {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Pour reconnaître un hôte et l’ajouter à la liste [!UICONTROL Hosts], les conditions suivantes doivent être remplies :

* Au moins une requête [!DNL Target] doit exister sur l’hôte
* Une page sur l’hôte doit comporter les éléments suivants :

   * Référence exacte d’at.js
   * Une requête [!DNL Target] ou une requête [!DNL Target] globale générée automatiquement

* La page avec la requête [!DNL Target] doit être affichée dans un navigateur.

Une fois la page consultée, l’hôte est répertorié dans la liste [!UICONTROL Hosts], ce qui vous permet de le gérer dans un environnement, de prévisualiser et de lancer des activités et des tests.

>[!NOTE]
>
>Cela inclut les serveurs de développement personnel.

Après avoir ajouté un hôte à la liste [!UICONTROL Host], assurez-vous qu’il est reconnu.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.
1. Si votre hôte n’apparaît pas dans la liste, actualisez votre navigateur.

   Par défaut, un hôte nouvellement reconnu est placé dans l’environnement [!UICONTROL Production]. L’environnement [!UICONTROL Production] est l’environnement le plus sécurisé, car il ne permet pas l’affichage des activités inactives à partir de ces hôtes.

1. (Conditionnel) Cliquez sur l’icône **[!UICONTROL Move]** ( ![icône de déplacement](/help/main/administrating-target/assets/icon-move.png) ) pour déplacer l’hôte dans l’environnement [!UICONTROL Development], [!UICONTROL Staging] ou autre.

>[!NOTE]
>
>L&#39;environnement [!UICONTROL Production] ne peut pas être supprimé, même si vous le renommez. Il est supposé que c’est dans cet environnement que vous diffusez les activités et tests finaux et actifs. L’environnement par défaut n’autorise pas l’affichage des campagnes inactives.

## Tri ou recherche dans la liste des hôtes {#section_068B23C9D8224EB78BC3B7C8580251B0}

Pour trier la liste [!UICONTROL Hosts], cliquez sur l’en-tête d’une colonne ([!UICONTROL Name], [!UICONTROL Environment] ou [!UICONTROL Last Requested]) afin de trier la liste par ordre croissant ou décroissant.

Pour effectuer une recherche dans la liste [!UICONTROL Hosts], saisissez un terme de recherche dans la zone [!UICONTROL Search Hosts].

## Créez des listes autorisées qui spécifient les hôtes autorisés à envoyer des requêtes [!DNL Target] à [!DNL Target]. {#allowlist}

Vous pouvez créer une liste autorisée qui spécifie les hôtes (domaines) autorisés à envoyer des requêtes [!DNL Target] à [!DNL Target]. Tous les autres hôtes générant des requêtes reçoivent une réponse d’erreur d’autorisation commentée. Par défaut, tout hôte qui contient une requête [!DNL Target] est enregistré avec [!DNL Target] dans l’environnement [!UICONTROL Production] et a accès à toutes les activités actives et approuvées. Si cette approche n’est pas souhaitée, vous pouvez utiliser la liste autorisée pour enregistrer les hôtes spécifiques qui peuvent envoyer des demandes [!DNL Target] et recevoir du contenu [!DNL Target]. Tous les hôtes continuent à s’afficher dans la liste [!UICONTROL Hosts] et les environnements peuvent toujours être utilisés pour regrouper ces hôtes et attribuer différents niveaux à chacun d’eux, par exemple si l’hôte peut voir les activités actives et/ou inactives.

Pour créer une liste autorisée :

1. Dans la liste [!UICONTROL Hosts], cliquez sur **[!UICONTROL Authorize Hosts]**.
1. Activez le bouton bascule **[!UICONTROL Enable Authorized Hosts for content delivery]** .
1. Ajoutez les hôtes souhaités dans la zone **[!UICONTROL Host contains]**, suivant vos besoins.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Ajoutez les hôtes souhaités dans la zone **[!UICONTROL Host does not contains]**, suivant vos besoins.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Cliquez sur **[!UICONTROL Save]**.

Si une requête [!DNL Target] est effectuée sur un hôte non autorisé, l’appel répond avec `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Bonnes pratiques en matière de sécurité** : si vous utilisez la fonctionnalité de boîte de réception de [!DNL Target], cette liste autorisée contrôle également la liste des domaines sur lesquels vos [redirecteurs](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html){target=_blank} peuvent accéder. Veillez à ajouter les domaines vers lesquels vous souhaitez rediriger lorsque vous utilisez la boîte de réception dans le cadre de votre mise en oeuvre. Si la liste autorisée n’est pas spécifiée, [!DNL Adobe] n’est pas en mesure de vérifier les URL de redirection et de se protéger des redirections malveillantes potentielles.
>
>La liste autorisée prévaut sur les environnements. Effacez tous les hôtes avant d’utiliser la fonction de liste autorisée, puis seuls les hôtes autorisés par la liste autorisée apparaissent dans la liste des hôtes. Vous pouvez ensuite déplacer les hôtes dans l’environnement de votre choix.

Il arrive parfois que les domaines d’autres sites s’affichent dans vos environnements. Un domaine s’affiche dans la liste s’il appelle at.js. Si, par exemple, un utilisateur copie l’une de vos pages web sur son serveur, ce domaine est répertorié dans votre environnement. Les domaines de robots, sites de traduction ou disques durs locaux peuvent également s’afficher.

Dans les cas où `mboxHost` est transmis dans un appel d’API, la conversion est enregistrée pour l’environnement transmis. Si aucun environnement n’est transmis, l’hôte de l’appel propose par défaut [!UICONTROL Production].

Vous pouvez également créer une liste bloquée qui spécifie les hôtes (domaines) qui ne peuvent pas envoyer de requêtes [!DNL Target] à [!DNL Target] en ajoutant les hôtes souhaités dans la zone [!UICONTROL Host Does Not Contain].

>[!NOTE]
>
>La liste [!UICONTROL Authorized Hosts] est utilisée pour les hôtes [!DNL Target] et les hôtes de redirection par défaut. Ajoutez tous les domaines existants autorisés à utiliser le [!DNL Adobe Target] SDK JavaScript (at.js) *ET* tous les domaines utilisés dans les URL de redirection par défaut de la boîte de réception. À l’avenir, ajoutez de nouveaux domaines similaires à la liste autorisée .

## Suppression d’un hôte {#section_F56355BA4BC54B078A1A8179BC954632}

Vous pouvez supprimer un hôte lorsqu’il n’est plus utile.

1. Dans la liste [!UICONTROL Hosts], cliquez sur l&#39;icône **[!UICONTROL Delete]**.
1. Cliquez sur **[!UICONTROL Delete]** pour confirmer la suppression.

>[!NOTE]
>
>L’hôte est de nouveau répertorié si un utilisateur accède à une page contenant une requête [!DNL Target] sur l’hôte.

## Résolution des problèmes liés aux hôtes {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Suivez les conseils de résolution suivants si vous rencontrez des problèmes avec vos hôtes :

**L&#39;hôte n&#39;apparaît pas dans la liste de votre compte.**

* Actualisez la page [!UICONTROL Hosts] dans votre navigateur.
* Vérifiez que la requête [!DNL Target] est correcte, y compris la référence at.js.
* Essayez d’accéder à l’une des requêtes [!DNL Target] sur l’hôte. Il est possible qu’aucune requête [!DNL Target] sur l’hôte n’ait jamais été rendue dans un navigateur.

**Des domaines aléatoires ou inconnus apparaissent dans la liste [!UICONTROL Host].**

Un domaine s’affiche dans la liste si une demande vers [!DNL Target] est effectuée à partir du domaine. Vous pouvez souvent voir des domaines à partir de moteurs de balayage, de sites de traduction de langue ou d’unités de disque locales. Si le domaine répertorié n’est pas celui que votre équipe utilise, vous pouvez cliquer sur [!UICONTROL Delete] pour le supprimer.

**Ma requête [!DNL Target] renvoie /&#42; no display - unauthorized mbox host &#42;/.**

Si une requête [!DNL Target] est effectuée sur un hôte non autorisé, la requête répond avec /&#42; no display - unauthorized mbox host &#42;/ (aucun affichage - hôte de mbox non autorisé).
