---
keywords: hôte;hôtes;groupe d’hôtes;résolution des problèmes;bonnes pratiques;boîte de réception;redirections;redirection;liste autorisée;liste autorisée;liste bloquée;liste bloquée
description: Découvrez comment organiser vos sites web et vos environnements de préproduction pour une gestion facile et des rapports distincts dans Adobe Target.
title: Que sont les hôtes et comment les utiliser ?
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 22%

---

# Hôtes

Organisez vos sites et environnements de préproduction pour une gestion facile et des rapports distincts dans [!DNL Adobe Target].

La gestion des hôtes vise principalement à garantir qu’aucun contenu inactif ne s’affiche par inadvertance sur les sites web. La gestion des hôtes permet également de séparer les données de rapport par [environnement](/help/main/administrating-target/environments.md).

Un hôte est un domaine à partir duquel un [!DNL Target] est effectuée. Sur un site web, il s’agit généralement de la variable `location.hostname` de l’URL qui crée la propriété [!DNL Target] requête.

Par défaut, [!DNL Target] ne limite pas un hôte qui peut créer [!DNL Target] requêtes et réception [!DNL Target] réponses. Lorsque de nouveaux hôtes effectuent des requêtes, elles fonctionnent automatiquement. Ce processus permet également de tester différents domaines que vous ne connaissez pas ou ne pouvez pas anticiper. Si vous souhaitez remplacer ce comportement par défaut, vous pouvez configurer une liste autorisée ou une liste bloquée pour limiter les hôtes qui fonctionnent avec . [!DNL Target].

Pour gérer les hôtes, cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hôtes]**.

![image hosts_list](assets/hosts_list.png)

## Reconnaissance des hôtes {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Pour reconnaître un hôte et l’ajouter au [!UICONTROL Hôtes] , les conditions suivantes doivent être remplies :

* Au moins un [!DNL Target] La requête doit exister sur l’hôte
* Une page sur l’hôte doit avoir :

   * Référence exacte d’at.js
   * A [!DNL Target] ou une requête globale générée automatiquement [!DNL Target] requête

* La page avec [!DNL Target] doit être affichée dans un navigateur.

Une fois la page affichée, l’hôte est répertorié dans la variable [!UICONTROL Hôtes] de la liste, ce qui vous permet de la gérer dans un environnement, de prévisualiser et de lancer des activités et des tests.

>[!NOTE]
>
>Cela inclut les serveurs de développement personnel.

Après avoir ajouté un hôte à la liste des [!UICONTROL hôtes], assurez-vous qu’il est reconnu.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Hôtes]**.
1. Si votre hôte n’apparaît pas dans la liste, actualisez votre navigateur. 


   Par défaut, un hôte nouvellement reconnu est placé dans la variable [!UICONTROL Production] environnement. Le [!UICONTROL Production] est l’environnement le plus sécurisé, car il ne permet pas l’affichage des activités inactives à partir de ces hôtes.

1. (Conditionnel) Cliquez sur le bouton **[!UICONTROL Déplacer]** Icône ( ![icône de déplacement](/help/main/administrating-target/assets/icon-move.png) ) pour déplacer l’hôte dans le [!UICONTROL Développement], [!UICONTROL Évaluation]ou tout autre environnement.

>[!NOTE]
>
>Le [!UICONTROL Production] ne peut pas être supprimé, même si vous le renommez. Il est supposé que c’est dans cet environnement que vous diffusez les activités et tests finaux et principaux. L’environnement par défaut n’autorise pas l’affichage des campagnes inactives.

## Tri ou recherche dans la liste des hôtes {#section_068B23C9D8224EB78BC3B7C8580251B0}

Pour trier les [!UICONTROL Hôtes] Cliquez sur l’en-tête d’une colonne ([!UICONTROL Nom], [!UICONTROL Environnement]ou [!UICONTROL Dernière demande]) pour trier la liste par ordre croissant ou décroissant.

Pour rechercher la variable [!UICONTROL Hôtes] , saisissez un terme de recherche dans la liste [!UICONTROL Rechercher des hôtes] de la boîte.

## Créer des listes autorisées qui spécifient les hôtes autorisés à envoyer [!DNL Target] de [!DNL Target]. {#allowlist}

Vous pouvez créer une liste autorisée qui spécifie les hôtes (domaines) autorisés à envoyer [!DNL Target] de [!DNL Target]. Tous les autres hôtes générant des requêtes reçoivent une réponse d’erreur d’autorisation commentée. Par défaut, tout hôte contenant un [!DNL Target] demande d’enregistrement avec [!DNL Target] dans le [!UICONTROL Production] et a accès à toutes les activités principales et approuvées. Si cette approche n’est pas souhaitée, vous pouvez utiliser la liste autorisée pour enregistrer les hôtes spécifiques pouvant effectuer des [!DNL Target] requêtes et réception [!DNL Target] contenu. Tous les hôtes continuent à s’afficher dans la variable [!UICONTROL Hôtes] Les environnements list et peuvent toujours être utilisés pour regrouper ces hôtes et attribuer différents niveaux à chacun d’eux, par exemple si l’hôte peut voir les activités principales et/ou inactives.

Pour créer une liste autorisée :

1. Dans la [!UICONTROL Hôtes] liste, cliquez sur **[!UICONTROL Autorisation des hôtes]**.
1. Activez la variable **[!UICONTROL Activation des hôtes autorisés pour la diffusion de contenu]** bascule.
1. Ajoutez les hôtes de votre choix dans le **[!UICONTROL L’hôte contient]** , selon vos besoins.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Ajoutez les hôtes de votre choix dans le **[!UICONTROL L’hôte ne contient pas]** , selon vos besoins.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Si une [!DNL Target] La demande est effectuée sur un hôte non autorisé, l’appel répond par `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**Bonnes pratiques relatives à la sécurité**: Si vous utilisez la fonctionnalité de boîte de réception de [!DNL Target], cette liste autorisée contrôle également la liste des domaines auxquels votre [redirecteurs](https://developer.adobe.com/target/implement/email/working-with-redirectors/){target=_blank} peut naviguer. Veillez à ajouter les domaines vers lesquels vous souhaitez rediriger lorsque vous utilisez la boîte de réception dans le cadre de votre mise en oeuvre. Si la liste autorisée n’est pas spécifiée, [!DNL Adobe] ne peut pas vérifier les URL de redirection et se protéger des redirections malveillantes potentielles.
>
>La liste autorisée prévaut sur les environnements. Effacez tous les hôtes avant d’utiliser la fonction de liste autorisée, puis seuls les hôtes autorisés par la liste autorisée apparaissent dans la liste des hôtes. Vous pouvez ensuite déplacer les hôtes dans l’environnement de votre choix.

Il arrive parfois que les domaines d’autres sites s’affichent dans vos environnements. Un domaine s’affiche dans la liste s’il appelle at.js. Si, par exemple, un utilisateur copie l’une de vos pages web sur son serveur, ce domaine est répertorié dans votre environnement. Les domaines de robots, sites de traduction ou disques durs locaux peuvent également s’afficher.

Dans les cas où `mboxHost` est transmis dans un appel d’API, la conversion est enregistrée pour l’environnement transmis. Si aucun environnement n’est transmis, l’hôte de l’appel utilise par défaut la valeur [!UICONTROL Production].

Vous pouvez également créer une liste bloquée qui spécifie les hôtes (domaines) qui ne peuvent pas envoyer [!DNL Target] de [!DNL Target] en ajoutant les hôtes souhaités dans la variable [!UICONTROL L’hôte ne contient pas] de la boîte.

>[!NOTE]
>
>Le [!UICONTROL Hôtes autorisés] list est utilisé pour les deux [!DNL Target] hosts et hôtes de redirection par défaut. Ajoutez tous les domaines existants autorisés à utiliser la variable [!DNL Adobe Target] SDK JavaScript (at.js) *ET* tous les domaines utilisés dans les URL de redirection par défaut de la boîte de réception. À l’avenir, ajoutez de nouveaux domaines similaires à la liste autorisée .

## Suppression d’un hôte {#section_F56355BA4BC54B078A1A8179BC954632}

Vous pouvez supprimer un hôte lorsqu’il n’est plus utile.

1. Dans la [!UICONTROL Hôtes] , cliquez sur **[!UICONTROL Supprimer]** icône .
1. Cliquez sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

>[!NOTE]
>
>L’hôte est de nouveau répertorié si un utilisateur accède à une page qui contient une [!DNL Target] sur l’hôte.

## Résolution des problèmes liés aux hôtes {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Suivez les conseils de résolution suivants si vous rencontrez des problèmes avec vos hôtes :

**L’hôte n’apparaît pas dans la liste de votre compte.**

* Actualisez la page [!UICONTROL Hôtes] dans votre navigateur.
* Confirmez que la variable [!DNL Target] est correcte, y compris la référence at.js.
* Essayez d’accéder à l’une des [!DNL Target] requêtes sur l’hôte. Il est possible que non [!DNL Target] sur l’hôte a jamais été rendue dans un navigateur.

**Des domaines aléatoires ou inconnus s’affichent dans la liste des [!UICONTROL hôtes].**

Un domaine s’affiche dans cette liste si une demande pour [!DNL Target] est créé à partir du domaine . Vous pouvez souvent voir des domaines à partir de moteurs de balayage, de sites de traduction de langue ou d’unités de disque locales. Si le domaine recensé n’est pas utilisé par votre équipe, vous pouvez cliquer sur [!UICONTROL Supprimer] pour le supprimer.

**My [!DNL Target] retours de requête /&#42; no display - unauthorized mbox host &#42;/.**

Si une [!DNL Target] La requête est effectuée sur un hôte non autorisé, la requête répond par /&#42; no display - unauthorized mbox host &#42;/.
