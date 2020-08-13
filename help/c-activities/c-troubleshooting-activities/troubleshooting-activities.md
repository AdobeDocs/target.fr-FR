---
keywords: troubleshoot target;troubleshooting target;default content;test not live;activity not live;targeting not working;previous experience displays;cannot create activities;can't create activities;create activities;page structure changed;page structure modified;error message;error delete profile script;ajax not working
description: Si l’activité n’apparaît pas sur votre site, ces suggestions de dépannage devraient vous aider à trouver la solution.
title: Résolution des problèmes liés aux activités
feature: activities
topic: Advanced,Standard,Classic
uuid: 5b22c369-0efc-48c0-a0dc-0179b18536fe
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 81%

---


# Résolution des problèmes liés aux activités{#troubleshoot-activities}

Si l’activité n’apparaît pas sur votre site, ces suggestions de dépannage devraient vous aider à trouver la solution.

>[!NOTE]
>
>Outre les informations de dépannage suivantes, reportez-vous à la section [Dépannage de Target](../../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) pour consulter des liens vers des rubriques de dépannage supplémentaires, des questions fréquentes et d’autres informations utiles sur la résolution des problèmes d’activités et d’autres fonctionnalités dans [!DNL Adobe Target].

Les sections suivantes contiennent des problèmes que vous pourriez rencontrer avec des solutions suggérées.

## J’ai créé une activité à l’aide de l’interface utilisateur de la Cible et je ne peux pas la mettre à jour via l’API.

Les Activités créées à l’aide de l’interface utilisateur de la Cible doivent être mises à jour via l’interface utilisateur de la Cible. Les Activités créées via l’API doivent être mises à jour via l’API. Si, par exemple, vous créez une activité à l’aide de l’API, puis que vous modifiez ultérieurement l’activité via l’interface utilisateur de la Cible, toutes les modifications ne sont pas mises à jour. Toutes les modifications sont stockées sur le serveur principal et peuvent être mises à jour en effectuant un autre appel d&#39;API.

Il est recommandé de mettre à jour l’activité en utilisant la même méthode (interface utilisateur ou API) que celle utilisée pour créer l’activité initiale.

## Vous voyez le contenu par défaut.

Assurez-vous que votre activité est terminée et a été activée.

## L’activité n’est pas active.

**Valider :** sélectionnez l’onglet d’aperçu et vérifiez si le test est marqué « inactif » ou « version préliminaire ».

**Options :**

* Activez le test.
* Utilisez les liens d’aperçu pour afficher le test inactif.

## Vous ne remplissez pas les conditions de ciblage de l’audience.

**Valider :** vérifiez les conditions de ciblage sur la page d’aperçu.

**Options :**

* Devenez admissible et essayez à nouveau.
* Utilisez les liens d’aperçu pour ignorer les conditions de ciblage.

## La page ne remplit pas les conditions de ciblage de pages.

**Valider :** sur la page d’aperçu, déterminez si la page ne répond pas aux conditions de ciblage.

**Options :**

* Accédez au compositeur d’expérience visuelle, cliquez sur URL > Avancé > page actuelle.

## Une expérience précédente s’affiche au lieu de la nouvelle expérience.

**Valider :** essayez une des options ci-dessous et tentez de visualiser à nouveau l’expérience.

**Options :**

* Effacez le cache et les cookies et essayez à nouveau.

* Essayez un navigateur différent.
* Utilisez le mode « privé/incognito ».

## Vous avez récemment été ajouté à Target mais ne pouvez créer d’activités.

**Validez :** cliquez sur Créer l’activité. Si l’option n’est pas disponible, vous ne disposez probablement pas de droits suffisants pour créer une activité.

**Options :**

Une fois que vous avez été ajouté en tant qu’utilisateur dans Target, vous devez disposer du rôle d’approbateur pour être en mesure de créer des activités.

* Demandez à l’administrateur de votre compte de vous attribuer le rôle d’approbateur.
* If you are the Admin, give yourself the Approver role from **[!UICONTROL Administration]** > **[!UICONTROL Users]** in Target.

   Voir [Attribution à vous-même du rôle d’approbateur](../../administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La structure de la page a changé depuis la configuration de l’activité.

**Valider :** accédez au compositeur d’expérience visuelle correspondant à l’activité existante. Recherchez un message d’avertissement indiquant que les sélecteurs (ou la structure) ont changé.

**Options :**

* Recompilez l’activité.

Pour plus d’informations sur la façon dont les modifications de pages affectent la capacité d’affichage de Target, voir [Scénarios de modification d’une page](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La structure de la page est modifiée au cours du chargement de la page (au moment de l’exécution).

**Valider :** demandez au développeur.

**Remarque :** Afin que Target reconnaisse l’emplacement où des modifications d’activités doivent être appliquées, évitez d’insérer dynamiquement des éléments de la même classe ou de modifier dynamiquement la classe des frères.

**Options :**

* Mettez à jour le code de la page afin d’identifier de manière unique chaque élément qui sera testé (à l’aide d’un identifiant (ID)).
* Arrêtez de modifier dynamiquement la classe ou les frères, comme décrit ci-dessus.

Pour plus d’informations sur la façon dont les modifications de pages affectent la capacité d’affichage de Target, voir [Scénarios de modification d’une page](../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Mbox.js extrait tout le code consécutif de l’en-tête et le place dans le corps.

**Valider :** affichez la source afin de déterminer si une déclaration suit le fichier mbox.js avant </body> Balise.

**Options :**

* Placez mbox.js en tant que dernier élément de la section `<head>` de votre page.
* Utilisez des balises div uniques pour les éléments de niveau supérieur dans le corps.

## D’autres activités sont en cours d’exécution sur la même page.

**Valider :** utilisez l’onglet Collisions pour voir si d’autres activités sont en cours d’exécution.

**Remarque :** L’onglet Collisions ne fonctionne pas avec le module de test de modèles.

**Options :**

* Augmentez la priorité de cette activité.
* Diminuez la priorité des autres activités.
* Désactivez les autres activités.

## Un message d’erreur apparaît lorsque vous supprimez un script de profil.

**Validation :** la suppression d’un script de profil de Target Standard/Premium engendre le message d’erreur « Impossible de supprimer le script de profil ».

**Options :**

Effectuez l’une des opérations suivantes :

* Supprimez à nouveau. Le message de confirmation apparaît.
* Patientez environ 10 minutes que l’importateur s’exécute. L’importateur met à jour la liste des scripts de profil.

## Some ajax [!DNL Target] calls are not working.

**Remarque :**[!DNL Target] Plusieurs appels de ajax avec le même nom de et des paramètres différents ne fonctionnent pas sur une même page. Seul le premier appel est effectué.

## You activated an activity using the Target API, but the activity shows a status of [!UICONTROL Inactive] in the Target UI.

Lorsque vous réalisez certaines actions, par exemple lorsque vous activez une activité hors de l’interface utilisateur à l’aide des méthodes de l’API, la mise à jour peut prendre jusqu’à dix minutes pour se propager jusqu’à l’interface utilisateur.