---
keywords: résoudre les problèmes liés à target;résolution des problèmes liés à target;contenu par défaut;test non actif;activité non active;non-fonctionnement du ciblage;affichage de l’expérience précédente;impossible de créer des activités;création d’activités impossible;créer des activités;structure de page modifiée;structure de page modifiée;message d’erreur;erreur lors de la suppression du script de profil;non-fonctionnement d’ajax
description: Obtenez des suggestions de résolution de problèmes si votre activité Adobe [!DNL Target] n’apparaît pas sur votre site.
title: Comment puis-je résoudre les problèmes liés aux activités ?
feature: Activities
exl-id: 6aa0486a-9ca3-4545-ae06-9b02e586d777
TQID: 'https://experienceleague.adobe.com/L-011t7q6c3aICs0ZrM01m9pZByH86FKGiLG1A7Rl2s'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9621044454d3e1b47c06cac2ad5d08cba8e482c0
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 7%
---
# Prise en main des activités de dépannage {#troubleshooting-activities}

>[!BEGINSHADEBOX]

**Sur cette page :** Trouvez des solutions aux problèmes courants lorsqu’une activité [!DNL Adobe Target] n’apparaît pas sur votre site ou ne se comporte pas comme prévu.

>[!ENDSHADEBOX]

Plusieurs causes peuvent empêcher l&#39;apparition d&#39;une activité [!DNL Adobe Target] sur votre site. Utilisez les problèmes suivants et les solutions suggérées pour identifier la cause et appliquer le correctif.

>[!NOTE]
>
>Outre les informations de dépannage suivantes, consultez [Dépannage de Target](/help/main/r-troubleshooting-target/troubleshooting-target.md) pour obtenir des liens vers des rubriques de dépannage supplémentaires, des questions fréquentes et d’autres informations utiles sur le dépannage des activités et d’autres fonctionnalités dans [!DNL Adobe Target].

## L’activité ne s’affiche pas comme prévu {#not-displayed}

+++ Le contenu par défaut apparaît

Assurez-vous que votre activité est terminée et qu’elle a été activée.

+++

</br>

+++ Activité non active

**Valider :** Dans l’onglet **[!UICONTROL Aperçu]**, vérifiez si l’activité est marquée comme inactive ou brouillon.

**Options :**

* activer l’activité ;
* Utilisez les liens de prévisualisation pour afficher l’activité inactive.

+++

</br>

+++ Vous ne remplissez pas les conditions de ciblage d’audience

**Valider :** consulter les conditions de ciblage sur la page **[!UICONTROL Aperçu]**.

**Options :**

* Qualifiez-vous pour l’audience, puis réessayez.
* Utilisez des liens de prévisualisation pour contourner les conditions de ciblage.

+++

</br>

+++ La page ne remplit pas les conditions de ciblage de page

**Valider :** sur la page **[!UICONTROL Aperçu]**, déterminez si la page ne répond pas aux conditions de ciblage.

**Options :**

* Accédez au **[!UICONTROL compositeur d’expérience visuelle]**, puis cliquez sur URL > Avancé > page actuelle.

+++

</br>

+++ Une expérience précédente s’affiche plutôt que la nouvelle expérience

**Valider :** Essayez l’une des options suivantes, puis tentez d’afficher à nouveau l’expérience.

**Options :**

* Effacez le cache et les cookies, puis réessayez.
* Essayez un navigateur différent.
* Utilisez le mode privé ou incognito.

+++

</br>

+++ La structure de la page a changé depuis la configuration de l’activité

**Valider :** Accédez au **[!UICONTROL compositeur d’expérience visuelle]** pour l’activité existante et recherchez un message d’avertissement indiquant que les sélecteurs (ou la structure) ont changé.

**Options :**

* Recompilez l’activité.

Pour plus d’informations sur la manière dont les modifications de page affectent la capacité d’affichage du contenu de [!DNL Target], consultez [Scénarios de modification de page](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md).

+++

</br>

+++ La structure de la page est modifiée lors du chargement de la page (au moment de l’exécution)

**Valider :** Demandez à votre développeur.

**Remarque :** Pour que [!DNL Target] reconnaisse où les modifications de l&#39;activité doivent être appliquées, évitez d&#39;insérer dynamiquement un élément avec la même classe ou de modifier dynamiquement la classe d&#39;un frère.

**Options :**

* Mettez à jour le code de page pour identifier de manière unique chaque élément testé à l’aide d’un identifiant.
* Arrêtez de modifier dynamiquement la classe ou les frères comme décrit ci-dessus.

Pour plus d’informations sur la manière dont les modifications de page affectent la capacité d’affichage du contenu de [!DNL Target], consultez [Scénarios de modification de page](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-scenarios.md).

+++

</br>

+++ D’autres activités sont exécutées sur la même page

**Valider :** Utilisez l’onglet **[!UICONTROL Collisions]** pour voir si d’autres activités sont en cours d’exécution.

**Remarque :** L’onglet **[!UICONTROL Collisions]** ne fonctionne pas avec le module de test des modèles.

**Options :**

* Augmentez la priorité de cette activité.
* Réduire la priorité des autres activités.
* Désactivez les autres activités.

+++

## Utilisateurs, API et interface utilisateur {#users-api-ui}

+++ J’ai créé une activité à l’aide de l’interface utilisateur [!DNL Target] et je ne peux pas la mettre à jour via l’API

Les activités créées à l’aide de l’IU [!DNL Target] doivent être mises à jour via l’IU [!DNL Target]. Les activités créées via l’API doivent être mises à jour via celle-ci. Par exemple, si vous créez une activité à l’aide de l’API, mais que vous la modifiez ultérieurement via l’interface utilisateur [!DNL Target], toutes les modifications ne sont pas mises à jour. Toutes les modifications sont stockées sur le serveur principal et peuvent être mises à jour en effectuant un autre appel API.

Il est recommandé de mettre à jour l’activité en utilisant la même méthode (interface utilisateur ou API) que celle utilisée pour la créer.

+++

</br>

+++ Vous avez récemment été ajouté à [!DNL Target], mais ne pouvez pas créer d’activités

**Valider :** Cliquez Sur **[!UICONTROL Créer Une Activité]**. Si l’option n’est pas disponible, vous ne disposez probablement pas de droits suffisants pour créer une activité.

**Options :**

Après avoir été ajouté en tant qu’utilisateur dans [!DNL Target], vous avez besoin du rôle **[!UICONTROL Approbateur]** pour créer des activités.

* Demandez à l’administrateur de votre compte de vous faire approuver.
* Si vous êtes l’administrateur, attribuez-vous le rôle **[!UICONTROL Approbateur]** de **[!UICONTROL Administration]** > **[!UICONTROL Utilisateurs]** dans [!DNL Target]. Voir [Affecter le rôle d&#39;approbateur](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

+++

</br>

+++ Vous avez activé une activité à l’aide de l’API [!DNL Target], mais son statut indique [!UICONTROL Inactif] dans l’interface utilisateur [!DNL Target]

Lorsque vous effectuez certaines actions, telles que l’activation d’une activité en dehors de l’interface utilisateur à l’aide de l’API [!DNL Target], la mise à jour peut prendre jusqu’à dix minutes pour se propager vers l’interface utilisateur.

+++

</br>

+++ Un message d’erreur apparaît lorsque vous supprimez un script de profil

**Valider :** La suppression d’un script de profil de [!DNL Target] affiche le message d’erreur « Échec de la suppression du script de profil ».

**Options :**

Effectuez l’une des opérations suivantes :

* Supprimez à nouveau le script de profil. Le message de confirmation apparaît.
* Patientez environ 10 minutes pour que l’importateur [!DNL Target] s’exécute. L’importateur met à jour la liste des scripts de profil.

+++

## Appels et conversion {#calls-and-conversion}

+++ Certains appels [!DNL Target] ajax ne fonctionnent pas

**Remarque :** plusieurs appels [!DNL Target] ajax avec le même nom mais avec des paramètres différents ne fonctionnent pas sur la même page. Seul le premier appel est effectué.

+++

</br>

+++ Après la conversion de l’activité, le visiteur n’a aucune expérience

Dans de rares cas, si la mesure de conversion de l’activité qui qualifie un visiteur pour une expérience est envoyée dans la même requête que la qualification de l’activité, il se peut que le visiteur ne se trouve dans aucune expérience une fois la requête envoyée. Dans ce cas, le contenu par défaut s’affiche et l’ID d’expérience capturé via les jetons est -1. [!DNL Adobe] ne recommande pas la qualification et la conversion de l’activité d’envoi dans la même requête [!DNL Target].

Si vous souhaitez envoyer les deux mesures dans la même requête, vous pouvez utiliser les **[!UICONTROL Paramètres avancés]** pour spécifier que le visiteur reste dans la même expérience après la conversion.

+++
