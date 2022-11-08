---
keywords: résoudre les problèmes liés à target;résolution des problèmes liés à target;contenu par défaut;test non actif;activité non active;non-fonctionnement du ciblage;affichage de l’expérience précédente;impossible de créer des activités;création d’activités impossible;créer des activités;structure de page changée;structure de page modifiée;message d’erreur;erreur lors de la suppression du script de profil;non-fonctionnement d’ajax
description: Obtenez des suggestions de résolution de problèmes si votre activité Adobe  [!DNL Target]  n’apparaît pas sur votre site.
title: Comment puis-je résoudre les problèmes liés aux activités ?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
source-git-commit: 8890d29a71506095a166321e324a000b5ad862a6
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 50%

---

# Résolution des problèmes liés aux activités

Si l’activité d’[!DNL Adobe Target] n’apparaît pas sur votre site, ces suggestions de dépannage devraient vous aider à trouver la solution.

>[!NOTE]
>
>Outre les informations de dépannage suivantes, reportez-vous à la section [Dépannage de Target](/help/main/r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) pour consulter des liens vers des rubriques de dépannage supplémentaires, des questions fréquentes et d’autres informations utiles sur la résolution des problèmes d’activités et d’autres fonctionnalités dans [!DNL Adobe Target].

Les sections suivantes contiennent des problèmes que vous pouvez rencontrer avec des solutions suggérées.

## J’ai créé une activité à l’aide de l’interface utilisateur de [!DNL Target] et je ne peux pas la mettre à jour via l’API.

Activités créées à l’aide du [!DNL Target] L’interface utilisateur doit être mise à jour à l’aide de la fonction [!DNL Target] Interface utilisateur. Les activités créées via l’API doivent être mises à jour via celle-ci. Si vous créez initialement une activité à l’aide de l’API, par exemple, mais que vous modifiez ensuite l’activité via la fonction [!DNL Target] mais toutes les modifications ne sont pas mises à jour. Toutes les modifications sont stockées sur le serveur principal et peuvent être mises à jour en effectuant un autre appel API.

Il est recommandé de mettre à jour l’activité en utilisant la même méthode (interface utilisateur ou API) que celle utilisée pour créer l’activité initiale.

## Vous voyez le contenu par défaut.

Assurez-vous que votre activité est terminée et a été activée.

## L’activité n’est pas active.

**Valider :** Accédez à [!UICONTROL Présentation] et voir si le test est marqué &quot;inactif&quot; ou &quot;version préliminaire&quot;.

**Options :**

* Activez le test.
* Utilisez les liens d’aperçu pour afficher le test inactif.

## Vous ne remplissez pas les conditions de ciblage d’audience.

**Valider :** vérifiez les conditions de ciblage sur la page d’aperçu.

**Options :**

* Devenez admissible et essayez à nouveau.
* Utilisez les liens d’aperçu pour ignorer les conditions de ciblage.

## La page ne remplit pas les conditions de ciblage de page.

**Valider :** Sur le [!UICONTROL Présentation] , déterminez si la page ne répond pas aux conditions de ciblage.

**Options :**

* Accédez au [!UICONTROL Compositeur d’expérience visuelle], cliquez sur URL > Avancé > page active.

## Une expérience précédente s’affiche au lieu de la nouvelle expérience.

**Valider :** essayez une des options ci-dessous et tentez de visualiser à nouveau l’expérience.

**Options :**

* Effacez le cache et les cookies et essayez à nouveau.
* Essayez un navigateur différent.
* Utilisez le mode « privé/incognito ».

## Vous avez récemment été ajouté à [!DNL Target], mais ne pouvez pas créer d’activités.

**Validez :**[!UICONTROL  cliquez sur Créer l’activité]. Si l’option n’est pas disponible, vous ne disposez probablement pas de droits suffisants pour créer une activité.

**Options :**

Une fois que vous avez été ajouté en tant qu’utilisateur dans [!DNL Target], vous devez disposer de la variable [!UICONTROL Approbateur] pour créer des activités.

* Demandez à l’administrateur de votre compte de vous désigner comme approbateur.
* Si vous êtes l’administrateur, attribuez-vous la variable [!UICONTROL Approbateur] rôle de **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** in [!DNL Target].

   Voir [Attribution à vous-même du rôle d’approbateur](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## La structure de la page a changé depuis la configuration de l’activité.

**Valider :**[!UICONTROL  accédez au compositeur d’expérience visuelle correspondant à l’activité existante. ] Recherchez un message d’avertissement indiquant que les sélecteurs (ou la structure) ont changé.

**Options :**

* Recompilez l’activité.

Pour plus d’informations sur l’impact des modifications de page [!DNL Target]la capacité d’affichage, voir [Scénarios de modification d’une page](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## La structure de la page est modifiée au cours du chargement de la page (au moment de l’exécution).

**Valider :** demandez au développeur.

**Remarque :** Pour [!DNL Target] pour déterminer où des modifications d’activité doivent être appliquées, évitez d’insérer dynamiquement un élément avec la même classe ou de modifier dynamiquement la classe de n’importe quel parent.

**Options :**

* Mettez à jour le code de page afin d’identifier de manière unique chaque élément testé (à l’aide d’un identifiant).
* Arrêtez de modifier dynamiquement la classe ou les frères, comme décrit ci-dessus.

Pour plus d’informations sur l’impact des modifications de page [!DNL Target]la capacité d’affichage, voir [Scénarios de modification d’une page](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md#concept_A458A95F65B4401588016683FB1694DB).

## D’autres activités sont en cours d’exécution sur la même page.

**Valider :** Utilisez la variable [!UICONTROL Collisions] pour voir si d’autres activités sont en cours d’exécution.

**Remarque :**[!UICONTROL  L’onglet Collisions ne fonctionne pas avec le module de test de modèles.]

**Options :**

* Augmentez la priorité de cette activité.
* Diminuez la priorité des autres activités.
* Désactivez les autres activités.

## Un message d’erreur apparaît lorsque vous supprimez un script de profil.

**Validation :**[!DNL Target] la suppression d’un script de profil de engendre le message d’erreur « Impossible de supprimer le script de profil ».

**Options :**

Effectuez l’une des opérations suivantes :

* Supprimez à nouveau le script de profil. Le message de confirmation apparaît.
* Patientez environ 10 minutes pour la variable [!DNL Target] importateur à exécuter. L’importateur met à jour la liste des scripts de profil.

## Certains appels [!DNL Target] ajax ne fonctionnent pas.

**Remarque :** Plusieurs ajax [!DNL Target] les appels portant le même nom, mais différents paramètres ne fonctionnent pas sur la même page. Seul le premier appel est effectué.

## Vous avez activé une activité à l’aide de l’API [!DNL Target], mais son statut indique [!UICONTROL Inactif] dans l’interface utilisateur de [!DNL Target].

Lorsque vous effectuez certaines actions, comme l’activation d’une activité en dehors de l’interface utilisateur à l’aide de la fonction [!DNL Target] API, la mise à jour peut prendre jusqu’à dix minutes pour se propager à l’interface utilisateur.

## Après la conversion de l’activité, le visiteur ne fait partie d’aucune expérience.

Si la mesure de conversion de l’activité pour être admissible pour une expérience est envoyée dans la même [!DNL Target] demande en tant que qualification d’activité, le visiteur peut ne pas être dans une expérience après l’envoi de la demande. Dans ce cas, le visiteur voit le contenu par défaut. [!DNL Adobe] recommande de ne pas envoyer de conversion et de qualification d’activité dans la même requête.

Si vous souhaitez envoyer les deux paramètres dans la même requête, vous pouvez utiliser [!UICONTROL Paramètres avancés] pour indiquer que le visiteur reste dans la même expérience après la conversion.
