---
keywords: host;hosts;host group;environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist
description: Organisez vos sites et environnements de préproduction pour une gestion simplifiée et une création de rapports distincte.
title: Hôtes
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 32cfa346ae6aa3246d830e1ce153cb45baab8c89
workflow-type: tm+mt
source-wordcount: '1820'
ht-degree: 96%

---


# Hôtes{#hosts}

Organisez vos sites et environnements de préproduction pour une gestion simplifiée et une création de rapports distincte.

La gestion des hôtes vise principalement à garantir qu’aucun contenu inactif ne s’affiche par inadvertance sur les sites web. La gestion des hôtes vous permet de séparer les données de rapport par environnement.

Un hôte est un serveur (ou domaine) web d’où vous diffusez le contenu durant une étape de votre projet. Tout hôte diffusant une mbox est reconnu.

Les hôtes sont regroupés dans des environnements afin d’en faciliter la gestion. Par exemple, dix hôtes peuvent être groupés dans deux ou trois environnements. Les environnements prédéfinis comprennent Production, Test et Développement. Si vous le souhaitez, vous pouvez ajouter de nouveaux environnements et renommer vos environnements.

Un environnement (l’environnement par défaut) est prénommé Production. Il n’est pas possible de supprimer cet environnement, même si vous le renommez. [!DNL Target] considère que c’est là que vous diffuserez les activités et tests finaux et approuvés.

Lorsque de nouveaux sites web ou domaines envoient une requête de mbox, ces nouveaux domaines s’affichent toujours dans l’environnement Production. Il n’est pas possible de modifier les paramètres de cet environnement. Par conséquent, les sites nouveaux ou inconnus peuvent voir uniquement le contenu prêt et actif. Grâce à la gestion des hôtes, vous pouvez facilement garantir la qualité des nouvelles activités et du nouveau contenu dans vos environnements de test et de développement, avant d’activer les activités.

Target ne limite pas un hôte qui peut envoyer et recevoir des mbox. Ainsi, les nouveaux serveurs ou domaines qui s’affichent fonctionnent automatiquement (à moins que vous n’ayez configuré une liste blanche ou une liste noire). Ceci permet également de tester les publicités sur différents domaines que vous ne connaissez pas ou ne pouvez pas anticiper.

Pour gérer les hôtes et les environnements, cliquez sur **[!UICONTROL Configuration]** > **[!UICONTROL Hôtes]**.

![](assets/hosts_list.png)

## Reconnaissance des hôtes {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

Informations sur les conditions nécessaires pour que [!DNL Target] reconnaisse un hôte et l’ajoute à la liste d’hôtes.

Les conditions suivantes doivent être remplies pour reconnaître un hôte :

* Au moins une mbox doit exister sur l’hôte.
* Une page sur l’hôte doit avoir :

   * Une référence [!DNL mbox.js] exacte
   * Une mbox ou un appel de mbox globale généré automatiquement

* La page contenant la mbox doit être consultée dans un navigateur.

Une fois la page consultée, l’hôte est répertorié dans la liste des [!UICONTROL hôtes], ce qui vous permet de le gérer dans un environnement, ainsi que de prévisualiser et de lancer des activités et des tests.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>Cela inclut les serveurs de développement personnel.

Après avoir ajouté un hôte à la liste des [!UICONTROL hôtes], assurez-vous qu’il est reconnu.

1. Cliquez sur **[!UICONTROL Configuration]** > **[!UICONTROL Hôtes]**.
1. Si votre hôte n’apparaît pas dans la liste, actualisez votre navigateur. 
Par défaut, un hôte nouvellement reconnu est placé dans l’environnement Production. Il s’agit de l’environnement le plus sécurisé, car il n’autorise pas l’affichage des activités inactives à partir de ces hôtes.
1. (Conditionnel) Déplacez l’hôte dans l’environnement Développement ou Évaluation.

>[!NOTE]
>
>Il n’est pas possible de supprimer l’environnement Production, même si vous le renommez. On considère que c’est là que vous diffuserez les activités et tests finaux et actifs. L’environnement par défaut n’autorise pas l’affichage des campagnes inactives.

## Gestion des hôtes et des environnements {#concept_90573F5A52E04600A8C3C5897880C10F}

Ces informations vous aident à gérer les hôtes et les environnements (groupes d’hôtes), notamment à définir l’hôte par défaut pour la création de rapports, à créer des listes blanches, à modifier le nom d’un environnement, à déplacer un hôte vers un autre environnement et à supprimer un hôte ou un environnement.


Pour accéder à la liste des [!UICONTROL hôtes], cliquez sur **[!UICONTROL Configuration]** > **[!UICONTROL Hôtes]**.

![](assets/hosts_list.png)

## Filtrage, tri ou recherche dans la liste des hôtes {#section_068B23C9D8224EB78BC3B7C8580251B0}

Pour filtrer la liste des [!UICONTROL hôtes] par environnement, cliquez sur la liste déroulante **[!UICONTROL Tous]**, puis sélectionnez l’environnement désiré (Production, Test, Développement ou un environnement personnalisé que vous avez créé).

Pour trier la liste des [!UICONTROL hôtes], cliquez sur l’en-tête d’une colonne (Nom, Environnement ou Dernière demande) pour trier la liste dans l’ordre croissant ou décroissant.

Pour effectuer une recherche dans la liste des [!UICONTROL hôtes], saisissez un terme de recherche dans le champ Rechercher.

## Sélection de plusieurs hôtes {#section_EF3B458475184B7EA997C3559714397C}

Pour sélectionner plusieurs hôtes, cochez les cases situées en regard de la colonne [!UICONTROL Nom] pour les hôtes souhaités. Vous pouvez ensuite déplacer ou supprimer tous les hôtes sélectionnés.

## Création d’un environnement {#section_32097D0993724DF3A202D164D3F18674}

1. Dans la liste des [!UICONTROL hôtes], cliquez sur l’onglet **[!UICONTROL Environnements]**.
1. Cliquez sur **[!UICONTROL Créer un environnement]**.
1. Attribuez un nom explicite à l’environnement.
1. Spécifiez le mode actif souhaité pour l’environnement : [!UICONTROL Activités actives] ou [!UICONTROL Activités actives et inactives].
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Définition de l’hôte par défaut pour la création de rapports {#section_4F8539B07C0C45E886E8525C344D5FB0}

Vous pouvez sélectionner l’environnement à utiliser par défaut pour tous les rapports d’activités.

Si vous utilisez Production comme environnement par défaut, tous les hôtes inconnus y sont automatiquement ajoutés et les données de rapport sont incluses dans l’affichage des rapports par défaut. La création d’un environnement « propre » garantit que seuls vos sites/domaines principaux sont inclus.

Procédez comme suit pour définir l’environnement par défaut pour la création de rapports :

1. Dans la liste des [!UICONTROL hôtes], cliquez sur l’onglet **[!UICONTROL Paramètres]**.
1. Sélectionnez l’hôte par défaut dans la liste déroulante **[!UICONTROL Paramètres d’environnement]**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>
>Les utilisateurs [!DNL Recommendations] doivent reconstruire leur base de données de comportement et leur base de données de produits si les hôtes changent de groupes d’hôtes.

## Création de listes blanches qui spécifient les hôtes autorisés à envoyer des appels de mbox à Target{#section_0AF7F56C386A42C381AF704DEF08D5CC}

Vous pouvez créer une liste blanche qui spécifie les hôtes (domaines) autorisés à envoyer des appels de mbox à [!DNL Target]. Tous les autres hôtes générant des appels obtiendront une réponse d’erreur d’autorisation commentée. Par défaut, tout hôte qui contient un appel de mbox est enregistré avec [!DNL Target] dans l’environnement Production et a accès à toutes les activités actives et approuvées. S’il ne s’agit pas de l’approche souhaitée, utilisez la liste blanche pour inscrire les hôtes spécifiques qui peuvent envoyer des appels de mbox et recevoir du contenu [!DNL Target]. Tous les hôtes continueront à apparaître dans la liste des [!UICONTROL hôtes] et les environnements pourront continuer à être utilisés pour grouper ces hôtes et attribuer différents niveaux à chacun d’eux, par exemple si l’hôte peut voir les campagnes actives et/ou inactives.

Procédez comme suit pour créer une liste blanche :

1. Dans la liste des [!UICONTROL hôtes], cliquez sur l’onglet **[!UICONTROL Paramètres]**.
1. Cochez la case **[!UICONTROL Activer les hôtes autorisés pour la diffusion de contenu]**.
1. Ajoutez les hôtes souhaités dans la zone **[!UICONTROL L’hôte contient]**.

   Plusieurs hôtes peuvent être répertoriés, chacun sur sa propre ligne.

1. Cliquez sur **[!UICONTROL Enregistrer]**.

Si un appel de mbox a lieu sur un hôte non autorisé, l’appel renvoie `/* no display - unauthorized mbox host */`.

Si vous utilisez la fonctionnalité de boîte aux lettres de [!DNL Target], notez que cette liste blanche contrôle également la liste des domaines sur lesquels vos [redirecteurs](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) peuvent naviguer. Assurez-vous d’ajouter les domaines vers lesquels vous souhaitez rediriger lorsque vous utilisez ubox dans le cadre de votre mise en oeuvre. Si la liste blanche n’est pas spécifiée, Adobe ne pourra pas vérifier les URL de redirection et se protéger des redirections malveillantes potentielles.

La liste blanche a priorité sur les environnements. Pensez à effacer tous les hôtes avant d’utiliser la liste blanche, afin que seuls les hôtes autorisés par la liste blanche soient répertoriés dans la liste des hôtes. Vous pouvez ensuite déplacer les hôtes dans l’environnement de votre choix.

Il arrive parfois que les domaines d’autres sites s’affichent dans vos environnements. Un domaine s’affiche dans la liste s’il appelle la fonction mbox.js. Si, par exemple, un utilisateur copie l’une de vos pages web sur son serveur, ce domaine est répertorié dans votre environnement. Les domaines de robots, sites de traduction ou disques durs locaux peuvent également s’afficher.

Dans les cas où `mboxHost` est transmis dans un appel d’API, la conversion est enregistrée pour l’environnement transmis. Si aucun environnement n’est transmis, l’hôte de l’appel propose Production par défaut.

Vous pouvez également créer une liste noire qui spécifie les hôtes (domaines) qui ne peuvent pas envoyer d’appels de mbox à [!DNL Target] en ajoutant les hôtes souhaités dans la zone [!UICONTROL L’hôte ne contient pas].

## Modification du nom d’un environnement {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. Dans la liste des [!UICONTROL hôtes], cliquez sur l’onglet **[!UICONTROL Environnements]**.
1. Passez votre curseur sur l’environnement souhaité, puis cliquez sur l’icône **[!UICONTROL Modifier.]**
1. Modifiez le nom de l’environnement.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

## Déplacement d’un hôte vers un autre environnement {#section_9F52549958BD485EB74FE78C32773D2A}

1. Dans la liste des [!UICONTROL hôtes], passez votre curseur sur l’hôte que vous souhaitez déplacer.
1. Cliquez sur l’icône **[!UICONTROL Déplacer.]**
1. Sélectionnez l’environnement souhaité dans la liste déroulante, puis cliquez sur l’icône représentant une coche.

## Suppression d’un hôte {#section_F56355BA4BC54B078A1A8179BC954632}

Vous pouvez supprimer un hôte lorsqu’il n’est plus utile.

1. Dans la liste des [!UICONTROL hôtes], passez votre curseur sur l’hôte que vous souhaitez supprimer.
1. Cliquez sur l’icône **[!UICONTROL Supprimer.]**
1. Cliquez sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

>[!NOTE]
>
>L’hôte sera de nouveau répertorié si un utilisateur accède à une page contenant une mbox sur l’hôte.

## Suppression d’un environnement {#section_737F8869612047868D03FC755B1223D3}

Vous pouvez supprimer un environnement lorsqu’il n’est plus utile.

1. Dans la liste des [!UICONTROL hôtes], cliquez sur l’onglet **[!UICONTROL Environnements]**.
1. Passez votre curseur sur l’environnement que vous souhaitez supprimer.
1. Cliquez sur l’icône **[!UICONTROL Supprimer.]**
1. Cliquez sur **[!UICONTROL Supprimer]** pour confirmer la suppression.

>[!NOTE]
>
>Vous ne pouvez pas supprimer l’environnement de production, mais vous pouvez le renommer.

## Résolution des problèmes liés aux hôtes {#concept_B3D7583FA4BB480382CC7453529FE1B7}

Bonnes pratiques pour la gestion et la résolution des problèmes liés aux hôtes dans [!DNL Adobe Target].

Suivez les conseils de résolution suivants si vous rencontrez des problèmes avec vos hôtes :

**L’hôte ne s’affiche pas dans la liste des mbox associées à votre compte.**

* Actualisez la page [!UICONTROL Hôtes] dans votre navigateur.
* Vérifiez que le code mbox est correct, y compris la référence [!DNL mbox.js].
* Accédez à l’une des mbox sur l’hôte. Il est possible qu’aucune mbox sur l’hôte n’ait jamais été traitée dans un navigateur.

**Des domaines aléatoires ou inconnus s’affichent dans la liste des[!UICONTROL hôtes].**

Un domaine s’affiche dans la liste si un appel à [!DNL Target] a été lancé à partir du domaine. Vous pouvez souvent voir des domaines à partir de moteurs de balayage, de sites de traduction de langue ou d’unités de disque locales. Si le domaine recensé n’est pas utilisé par votre équipe, vous pouvez cliquer sur [!UICONTROL Supprimer] pour le supprimer.

**L’appel de mbox renvoie /* no display - unauthorized mbox host */ (aucun affichage - hôte de mbox non autorisé).**

Si un appel de mbox a lieu sur un hôte non autorisé, l’appel renvoie /* no display - unauthorized mbox host */ (aucun affichage - hôte de mbox non autorisé).

## Recommandations : filtrer les collections et exclusions par environnement (groupe d’hôtes)

![Badge Premium](/help/assets/premium.png)

Vous pouvez prévisualiser le contenu des collections et des exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

>[!NOTE]
>Les activités de Recommandations sont disponibles dans le cadre de la solution Target Premium. Elles ne sont pas disponibles dans Target Standard sans une licence Target Premium.

Le groupe d’hôtes peut servir à séparer les éléments disponibles dans votre catalogue pour différents usages. Par exemple, vous pouvez utiliser des groupes d’hôtes pour les environnements de développement et de production, des marques différentes ou plusieurs zones géographiques. Par défaut, les résultats d’aperçu dans la recherche de catalogue, les collections et les exclusions sont basés sur le groupe d’hôtes par défaut. (Vous pouvez également sélectionner un autre groupe d’hôtes pour prévisualiser les résultats à l’aide du filtre Environnement.) Par défaut, les éléments nouvellement ajoutés sont disponibles dans tous les groupes d’hôtes, sauf si un identifiant d’environnement est spécifié lors de la création ou de la mise à jour de l’élément. Les recommandations fournies dépendent du groupe d’hôtes spécifié dans la requête.

Si vos produits ne sont pas répertoriés, vérifiez que vous utilisez le groupe d’hôtes approprié. Si, par exemple, vous configurez votre recommandation pour utiliser un environnement d’évaluation et que vous définissez votre groupe d’hôtes sur Évaluation, il se peut que vous deviez recréer vos collections dans l’environnement d’évaluation pour les produits à afficher. Pour voir quels produits sont disponibles dans chaque environnement, utilisez la recherche catalogue pour chaque environnement. Vous pouvez également prévisualiser le contenu des collections et exclusions de recommandations pour un environnement sélectionné (groupe d’hôtes).

>[!NOTE]
>Après avoir modifié l’environnement sélectionné, vous devez cliquer sur Rechercher pour mettre à jour les résultats renvoyés.

Le filtre Environment est disponible à partir des emplacements suivants dans l’interface utilisateur de Target :

* Recherche catalogue ([!UICONTROL Recommandations > Recherche catalogue])
* Boîte de dialogue Créer une collection ([!UICONTROL Recommandations > Collections > Créer nouveau])
* Boîte de dialogue Mettre à jour la collection ([!UICONTROL Recommandations > Collections > Modifier])
* Boîte de dialogue Créer une exclusion ([!UICONTROL Recommandations > Exclusions > Créer nouveau])
* Boîte de dialogue Mettre à jour l’exclusion ([!UICONTROL Recommandations > Exclusions > Modifier])
