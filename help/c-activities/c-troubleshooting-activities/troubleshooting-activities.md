---
keywords: résoudre les problèmes liés à target;résolution des problèmes liés à target;contenu par défaut;test non actif;activité non active;non-fonctionnement du ciblage;affichage de l’expérience précédente;impossible de créer des activités;création d’activités impossible;créer des activités;structure de page changée;structure de page modifiée;message d’erreur;erreur lors de la suppression du script de profil;non-fonctionnement d’ajax
description: Obtenez des suggestions de résolution de problèmes si votre activité Adobe  [!DNL Target]  n’apparaît pas sur votre site.
title: Comment puis-je résoudre les problèmes liés aux activités ?
feature: Activités
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
translation-type: ht
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: ht
source-wordcount: '834'
ht-degree: 100%

---

# Résolution des problèmes liés aux activités

Si l’activité d’[!DNL Adobe Target] n’apparaît pas sur votre site, ces suggestions de dépannage devraient vous aider à trouver la solution.

>[!NOTE]
>
>Outre les informations de dépannage suivantes, reportez-vous à la section [Dépannage de Target](/help/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) pour consulter des liens vers des rubriques de dépannage supplémentaires, des questions fréquentes et d’autres informations utiles sur la résolution des problèmes d’activités et d’autres fonctionnalités dans [!DNL Adobe Target].

Les sections suivantes contiennent des problèmes que vous pourriez rencontrer avec des solutions suggérées.

## J’ai créé une activité à l’aide de l’interface utilisateur de [!DNL Target] et je ne peux pas la mettre à jour via l’API.

Les activités créées à l’aide de l’interface utilisateur de Target doivent être mises à jour via celle-ci. Les activités créées via l’API doivent être mises à jour via celle-ci. Si, par exemple, vous créez une activité à l’aide de l’API, puis que vous la modifiez plus tard via l’interface utilisateur de Target, toutes les modifications ne sont pas mises à jour. Toutes les modifications sont stockées sur le serveur principal et peuvent être mises à jour en effectuant un autre appel API.

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

## Vous avez récemment été ajouté à [!DNL Target], mais ne pouvez pas créer d’activités.

**Validez :** cliquez sur Créer l’activité. Si l’option n’est pas disponible, vous ne disposez probablement pas de droits suffisants pour créer une activité.

**Options :**

Une fois que vous avez été ajouté en tant qu’utilisateur dans Target, vous devez disposer du rôle d’approbateur pour être en mesure de créer des activités.

* Demandez à l’administrateur de votre compte de vous attribuer le rôle d’approbateur.
* Si vous êtes l’administrateur, attribuez-vous le rôle d’approbateur dans **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** dans Target.

   Voir [Attribution à vous-même du rôle d’approbateur](/help/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La structure de la page a changé depuis la configuration de l’activité.

**Valider :** accédez au compositeur d’expérience visuelle correspondant à l’activité existante. Recherchez un message d’avertissement indiquant que les sélecteurs (ou la structure) ont changé.

**Options :**

* Recompilez l’activité.

Pour plus d’informations sur la façon dont les modifications de pages affectent la capacité d’affichage de Target, voir  [Scénarios de modification d’une page](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La structure de la page est modifiée au cours du chargement de la page (au moment de l’exécution).

**Valider :** demandez au développeur.

**Remarque :** Afin que Target reconnaisse l’emplacement où des modifications d’activités doivent être appliquées, évitez d’insérer dynamiquement des éléments de la même classe ou de modifier dynamiquement la classe des frères.

**Options :**

* Mettez à jour le code de la page afin d’identifier de manière unique chaque élément qui sera testé (à l’aide d’un identifiant (ID)).
* Arrêtez de modifier dynamiquement la classe ou les frères, comme décrit ci-dessus.

Pour plus d’informations sur la façon dont les modifications de pages affectent la capacité d’affichage de Target, voir  [Scénarios de modification d’une page](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## Mbox.js extrait tout le code consécutif de l’en-tête et le place dans le corps.

**Valider :** affichez la source afin de déterminer si une déclaration suit le fichier mbox.js avant la balise  `</body>` de fermeture.

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
* Patientez environ 10 minutes que l’importateur de Target Standard/Premium s’exécute. L’importateur met à jour la liste des scripts de profil.

## Certains appels [!DNL Target] ajax ne fonctionnent pas.

**Remarque :** plusieurs appels [!DNL Target] ajax avec le même nom mais avec des paramètres différents ne fonctionnent pas sur une même page. Seul le premier appel est effectué.

## Vous avez activé une activité à l’aide de l’API [!DNL Target], mais son statut indique [!UICONTROL Inactif] dans l’interface utilisateur de [!DNL Target].

Lorsque vous réalisez certaines actions, par exemple lorsque vous activez une activité hors de l’interface utilisateur à l’aide des méthodes de l’API, la mise à jour peut prendre jusqu’à dix minutes pour se propager jusqu’à l’interface utilisateur.
