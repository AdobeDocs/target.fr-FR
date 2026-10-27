---
keywords: notes de mise à jour;notes de version préliminaire;améliorations futures;correctifs futurs;fonctionnalités futures;version à venir
description: Consultez une liste des fonctionnalités, améliorations et correctifs inclus dans les versions antérieures d’Adobe Target.
title: Quelles fonctionnalités sont incluses dans les versions précédentes de 2025 ?
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/cjheajZKokzwCNspfQckh6PHh5ecetdj7vZrrq9IqXw'
source-git-commit: 7f111df77c4b368dbe000a699ee19f5ff1ea266f
workflow-type: tm+mt
source-wordcount: '25402'
ht-degree: 5%
---
# Notes de mise à jour pour les versions antérieures

Notes de mise à jour pour les versions antérieures dʼ[!DNL Adobe Target], comprenant des notes de mise à jour de [!DNL Target Standard/Premium], la plateforme [!DNL Target] et la bibliothèque JavaScript [!DNL Target] (at.js).

Les notes de mise à jour sont répertoriées dans l’ordre décroissant de leur date (mois et année) de publication.

>[!NOTE]
>
>Consultez les [Notes de mise à jour Target (actualisées)](/help/main/r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) pour plus d’informations sur les versions de Target du mois en cours (plateforme et Target Standard/Premium).

## Notes de mise à jour - 2025

### [!DNL Target Standard/Premium] 25.11.2 (14 novembre 2025)

**Offres Decisioning**

+++Afficher les détails

* **Les décisions d’offres avec des sélecteurs masqués ou non valides ne sont pas modifiables dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les décisions d’offre liées à des sélecteurs masqués ou non valides ne pouvaient pas être modifiées sauf si l’élément était visible dans le compositeur d’expérience visuelle (VEC). La modification est désormais prise en charge directement à partir du panneau, ce qui permet de restaurer la fonctionnalité disponible dans l’interface utilisateur héritée et de s’assurer que les décisions d’offre peuvent être modifiées quelle que soit la visibilité du sélecteur. (TGT-53899)

+++

**Recommandations**

+++Afficher les détails

* **La modification de critères dans une activité a provoqué le blocage de la page.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel la modification des critères d’activité entraînait le blocage de la page avec des erreurs de console liées à `useCrudActionsCtx`. L’éditeur de critères se charge et fonctionne désormais correctement, ce qui permet de modifier les activités sans interruption. (TGT-53971)
* La colonne **[!UICONTROL Message] n’affichait pas les données du produit par intermittence dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur [!UICONTROL Recommendations] mise à jour en raison duquel la colonne [!UICONTROL Message] de la [!UICONTROL Recherche catalogue] ne pouvait pas afficher par intermittence les données du produit, même si les valeurs étaient présentes dans le flux. La colonne affiche désormais systématiquement les valeurs de message correctes sur tous les produits, ce qui garantit une visibilité fiable sans nécessiter de reconfiguration manuelle des colonnes. (TGT-52777)
* Le bouton **[!UICONTROL Télécharger les données de recommandations] n’apparaît pas après l’enregistrement de l’activité dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où le bouton [!UICONTROL Télécharger les données de recommandations] n’apparaissait pas pour certaines activités enregistrées, même après avoir été à nouveau enregistrées. Le bouton s’affiche désormais de manière cohérente sur toutes les activités, ce qui permet aux utilisateurs d’exporter des données de recommandation de manière fiable sans solution. (TGT-53802)
* **L’ouverture de certains produits d’une collection a renvoyé « La ressource demandée est introuvable » et il n’y avait pas d’option de fermeture dans le modal.** Correction d’un problème dans l’interface utilisateur de Recommendations mise à jour en raison duquel l’ouverture de certains produits d’une collection déclenchait une erreur « La ressource demandée est introuvable » et affichait une boîte de dialogue modale vide sans option de fermeture. La boîte de dialogue modale charge désormais correctement les détails du produit, et une option de fermeture est toujours disponible pour une sortie réussie. (TGT-53986)

+++

## [!DNL Target Standard/Premium] 25.11.1 (10 novembre 2025)


**Analytics for Target (A4T)**

+++Afficher les détails

* Message d’erreur **[!UICONTROL Objectifs et paramètres] lors de l’utilisation de [!DNL Adobe Analytics] comme source de création de rapports dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour [!UICONTROL Présentation] où la section Objectifs affichait l’erreur « Un problème s’est produit. Nous ne pouvons pas traiter votre demande. Veuillez contacter [!DNL Adobe Client Care] si le problème persiste » lorsque [!DNL Adobe Analytics] (A4T) a été sélectionné comme source de création de rapports. Les objectifs s’affichent désormais correctement avec les mesures , ce qui garantit une visibilité cohérente entre les sources de création de rapports. (TGT-54021)

+++

**Audiences**

+++Afficher les détails

* **Impossible de sélectionner plusieurs audiences de création de rapports dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les utilisateurs ne pouvaient pas sélectionner simultanément plusieurs audiences de rapports nouvellement créées lors de la modification d’une activité. Plusieurs audiences peuvent désormais être affectées simultanément, ce qui améliore la flexibilité et l’efficacité de la configuration des rapports. (TGT-53253)

+++

**Offres Decisioning**

+++Afficher les détails

* **Impossible de modifier ou de remplacer les offres de prise de décision dans l’interface utilisateur mise à jour.** Résolution d’un problème dans l’interface utilisateur mise à jour où les offres de prise de décision ne pouvaient pas être modifiées ni remplacées par le panneau [!UICONTROL Modifications] et où les noms d’offre apparaissaient vides. Les offres de prise de décision sont désormais entièrement accessibles et modifiables, ce qui permet de restaurer la parité avec l’interface utilisateur héritée et de s’assurer que les clients peuvent gérer les offres directement dans les activités. (TGT-53884)

+++

**Localisation**

+++Afficher les détails

* **Correction de plusieurs erreurs de localisation dans l’interface utilisateur coréenne et japonaise.** (TGT-54003, TGT-54004, TGT-54006, TGT-54007 ET TGT-54018)

+++

**[!UICONTROL Recommandations]**

+++Afficher les détails

* **Échec du chargement de la clé de recommandation après l’enregistrement de l’activité lors de la promotion par attribut avec correspondance des attributs d’entité.** Correction d’un problème en raison duquel les promotions de type [!UICONTROL Promotion par attribut] avec le type de règle [!UICONTROL Correspondance des attributs d’entité] ne chargeaient pas la clé de recommandation lors de la modification après l’enregistrement d’une activité. Le problème est dû au fait que le `customKeyId` n’est pas demandé via GraphQL. Les clés de recommandation se chargent désormais correctement lors des modifications de promotion. (TGT-53117)
* **La recommandation persiste visuellement lors du passage d’ExpB à ExpA.** Correction d’un problème en raison duquel l’insertion d’une recommandation dans l’expérience B, puis le passage à l’expérience A laissait la zone d’offre de recommandation visible. Il s’agissait uniquement d’une incohérence visuelle ; les modifications s’affichent désormais correctement lors du changement d’expérience, garantissant ainsi un comportement précis de l’interface utilisateur. (TGT-53911)
* **La clé de recommandation ne se charge pas pour [!UICONTROL Promotion par attribut] avec [!UICONTROL Attribut d’entité] Correspondance.** Correction d’un problème où les promotions de type [!UICONTROL Promotion par attribut] avec le type de règle [!UICONTROL Correspondance des attributs d’entité] ne chargeaient pas la clé de recommandation lors de la modification après l’enregistrement d’une activité. La clé de recommandation est désormais correctement récupérée via GraphQL, ce qui garantit que les promotions s’affichent et fonctionnent comme prévu. (TGT-53917)
* **La modification des recommandations sur les éléments HTML masqués ne fonctionne pas dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur [!UICONTROL Nouvelle création] et du VEC en raison duquel les activités de recommandation appliquées aux éléments HTML masqués ne pouvaient pas être modifiées. Cette fonctionnalité fonctionne désormais comme prévu, en rétablissant la parité avec l’interface utilisateur héritée et en s’assurant que les recommandations peuvent être modifiées, quelle que soit la visibilité des éléments. (TGT-53953)
* **Impossible de modifier les activités de recommandation sur les éléments HTML masqués dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les activités de recommandation appliquées aux éléments HTML masqués ne pouvaient pas être modifiées. Cette fonctionnalité fonctionne désormais comme prévu, en rétablissant la parité avec l’interface utilisateur héritée et en s’assurant que les recommandations peuvent être modifiées, quelle que soit la visibilité des éléments. (TGT-53951)
* **Des valeurs d’attribut sont manquantes par intermittence dans le catalogue de recommandations dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur [!UICONTROL Recommendations] mise à jour en raison duquel les listes de recherche de catalogue échouaient par intermittence à afficher certaines valeurs d’attribut (par exemple, message) même lorsqu’elles étaient présentes dans le flux de produits. Les valeurs d’attribut se chargent désormais de manière cohérente dans les résultats de recherche sans nécessiter de reconfiguration des colonnes, ce qui améliore la fiabilité et l’efficacité de la gestion des catalogues. (TGT-52769)
* Le bouton **[!UICONTROL Télécharger les recommandations] est manquant pour les activités [!DNL Recommendations] dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur de [!DNL Recommendations] mise à jour en raison duquel le bouton [!UICONTROL Télécharger les recommandations] n’était pas visible pour les activités A/B utilisant les recommandations. Le bouton s’affiche désormais correctement, ce qui permet aux utilisateurs d’exporter des données de recommandation comme prévu, conformément à la fonctionnalité de l’interface utilisateur héritée. (TGT-53768)
* Le bouton **[!UICONTROL Télécharger les données de recommandation] est manquant dans l’interface utilisateur de présentation mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour [!UICONTROL Aperçu] en raison duquel le bouton [!UICONTROL  Télécharger les données de recommandation] n’était pas visible pour les activités contenant des recommandations. Le bouton s’affiche désormais correctement, ce qui permet aux utilisateurs d’exporter directement les données de recommandations sans avoir à revenir à l’interface utilisateur héritée. (TGT-53772)
* **La modification des critères d’activité entraînait parfois un écran vide dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où le fait de cliquer sur [!UICONTROL  Modifier les critères dans Expériences ] entraînait parfois l’affichage d’un écran vide pour certaines activités. L’éditeur de critères se charge désormais de manière fiable dans toutes les activités, ce qui permet aux utilisateurs de modifier sans interruption. (TGT-53961)
* **Impossible de modifier les critères de séquence dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où la tentative de modification de [!UICONTROL Critères de séquence] entraînait le blocage de la fenêtre contextuelle des critères au chargement, puis l’affichage d’un écran vide. L’éditeur de critères se charge désormais correctement, ce qui permet aux utilisateurs et utilisatrices de modifier et de mettre à jour les critères de séquence sans interruption. (TGT-53985)

+++

**[!UICONTROL Rapports]**

+++Afficher les détails

* Les emplacements **[!UICONTROL Multivariate Test] (MVT) et le problème de création de rapports graphiques ont empêché la génération de rapports.** Correction d’un problème en raison duquel les activités MVT ne généraient pas de rapports [!UICONTROL Contribution de l’emplacement] et graphiques dans l’interface utilisateur de Target, affichant l’erreur « Un problème s’est produit. Nous ne pouvons pas traiter votre demande. » Les rapports se chargent désormais correctement dans l’interface utilisateur, offrant ainsi une visibilité totale. (TGT-53654)
* **Les rapports MVT ne se chargent pas en raison d’une erreur de rapport de contribution [!UICONTROL Élément].** Correction d’un problème en raison duquel le chargement des rapports d’activité MVT échouait dans l’interface utilisateur de Target, affichant l’erreur « Impossible de récupérer le rapport de contribution des éléments ». Les rapports s’affichent désormais correctement, assurant ainsi une visibilité complète des contributions des éléments. (TGT-53691)
* **Exporter les détails de la commande vers un événement CSV pour les activités [!UICONTROL Ciblage d’expérience] (XT)**. Correction d’un problème en raison duquel l’option [!UICONTROL Exporter les détails de la commande au format CSV] s’affichait incorrectement pour les activités XT et renvoyait un fichier vide. L’option s’affiche désormais uniquement pour les activités AP, ce qui garantit une fonctionnalité d’exportation précise et empêche toute confusion. (TGT-53798)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* Le problème du bouton **[!UICONTROL Supprimer la modification] a empêché la suppression des modifications d’activité.** Correction d’un problème en raison duquel le bouton [!UICONTROL Supprimer la modification] de l’interface utilisateur de [!DNL Target] ne fonctionnait pas, empêchant les utilisateurs de supprimer des modifications dans les activités . Le bouton fonctionne désormais comme prévu, ce qui permet de supprimer les modifications de manière fiable et sans délai. (TGT-53728)
* **Les sélecteurs préférés ne sont pas reconnus dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où les sélecteurs préférés, tels que `data-target-component-id`, n’apparaissaient pas dans la liste des sélecteurs CSS dans le VEC. Les utilisateurs peuvent désormais sélectionner de manière fiable les attributs préférés au lieu des noms de classe générés dynamiquement, ce qui garantit un ciblage stable entre les mises à jour de page SPA. (TGT-53908)
* **Incompatibilité d’alignement des emplacements d’activité entre les pages [!UICONTROL Modifier] et [!UICONTROL Aperçu].** Correction d’un problème en raison duquel la numérotation des emplacements d’activités sur la page [!UICONTROL Aperçu] ne correspondait pas aux mises à jour effectuées sur la page [!UICONTROL  Modifier l’expérience]. Les emplacements restent désormais cohérents sur les deux vues, ce qui garantit un alignement précis et empêche les positions manquantes ou mal numérotées. (TGT-53960 et TGT-53954)
* **Impossible de revenir au mode [!UICONTROL Conception] dans le VEC mis à jour.** Correction d’un problème dans l’interface utilisateur du VEC mise à jour en raison duquel les utilisateurs ne pouvaient pas revenir au mode [!UICONTROL Conception] après avoir accédé à une nouvelle page en mode [!UICONTROL Parcourir]. Le bouton (bascule) [!UICONTROL Conception] fonctionne désormais correctement, ce qui permet d’appliquer facilement les modifications sur plusieurs pages. (TGT-53988 et TGT-53993)
* **Paramètre de requête non affiché dans la vue d’ensemble de l’activité.** Correction d’un problème dans l’interface utilisateur mise à jour où les paramètres de requête n’étaient pas affichés dans la page [!UICONTROL Aperçu] pour les activités, ce qui provoquait des incohérences entre les URL [!UICONTROL Aperçu] et de diffusion de page. Les paramètres de requête s’affichent désormais correctement, ce qui garantit que les emplacements des activités sont entièrement représentés et cohérents entre les vues. (TGT-53701)

+++

### [!DNL Target Standard/Premium] 25.10.1 (22 octobre 2025)

Cette version comprend les mises à jour et correctifs suivants :

**Activités**

+++ Afficher les détails
* **Résolution d’un problème d’utilisation dans l’interface utilisateur mise à jour**. [!UICONTROL Les observateurs] peuvent désormais prévisualiser les activités à l’aide de l’option [!UICONTROL Afficher l’activité], comme dans l’interface utilisateur héritée. (TGT-51741)
* **[!UICONTROL Observateur] les utilisateurs peuvent désormais afficher le contenu de l’activité dans l’interface utilisateur mise à jour.** Restauration de la visibilité pour les utilisateurs dotés du rôle d’observateur dans l’interface utilisateur d’Activity mise à jour. Auparavant, les observateurs ne pouvaient pas afficher les modifications, les offres et les changements de contenu, une fonctionnalité disponible dans l’interface utilisateur héritée. (TGT-53785)
* **[!UICONTROL Approbateur] les utilisateurs peuvent désormais modifier les objectifs des activités sans erreur de privilège d’éditeur.** Correction d’un problème d’autorisations dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs au niveau de l’approbateur d’enregistrer les modifications apportées aux paramètres d’objectif avancés. Les utilisateurs concernés ont reçu une erreur `403 Forbidden.Resource` nécessitant des privilèges d’éditeur, alors qu’ils disposaient d’un accès suffisant. (TGT-53819)

+++

**Audiences**

+++Afficher les détails

* **Sélection multi-audience restaurée dans les rapports « Cette activité uniquement ».** Correction d’un problème dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs de sélectionner plusieurs audiences sous la section [!UICONTROL Cette activité uniquement] dans [!UICONTROL Objectifs et paramètres]. (TGT-53283)
* **Les graphiques de création de rapports basés sur les audiences affichent désormais correctement les données de conversion.** Correction d’un problème dans l’onglet [!UICONTROL Rapports] en raison duquel les graphiques échouaient lors de la sélection d’audiences non par défaut. Bien que les données et les mesures de confiance soient disponibles, le graphique visuel ne présente qu’une ligne continue, ce qui rend l’analyse difficile. (TGT-53769)
* **L’interface utilisateur [!UICONTROL Ciblage] indique désormais clairement les règles d’audience exclues.** Correction d’un problème dans la section [!UICONTROL Ciblage] de l’interface utilisateur de création d’activité où les règles d’audience définies sur [!UICONTROL Exclure] n’étaient pas clairement affichées. Cela entraînait une certaine confusion lors de la révision de la logique de ciblage, en particulier pour les audiences excluant des URL spécifiques. (TGT-53809)
* **Les valeurs de définition de l’audience peuvent désormais être sélectionnées et copiées dans l’onglet [!UICONTROL Ciblage].** Correction d’un problème dans l’interface de création d’activité qui empêchait les utilisateurs de sélectionner et de copier les valeurs des règles d’audience dans l’onglet [!UICONTROL Ciblage]. Cette fonctionnalité était disponible dans l’interface utilisateur héritée, mais elle était absente de l’interface utilisateur mise à jour. (TGT-53856)

+++

**Localisation**

+++Afficher les détails

* **Correction d’une erreur de traduction de « quote » dans le contexte de l’éditeur de page zh_CN.** Correction d’une erreur de traduction contextuelle dans le paramètre régional zh_CN où le terme « devis » était incorrectement traduit par « 报价 », ce qui impliquait un devis commercial. Dans la section Typographie > Style de titre > Guillemet-bloc , la signification prévue fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53841)
* **Correction d’une erreur de traduction de « guillemet supprimé » dans le contexte de l’éditeur de page zh_CN.** Correction d’une erreur de traduction dans le paramètre régional zh_CN où le « devis supprimé » était incorrectement rendu comme « 移除了报价 », ce qui impliquait un devis commercial. Dans la section Typographie > Style de titre > Citation, le terme fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53843)
* **Correction d’une erreur de traduction de « devis réarrangé » dans le contexte de l’éditeur de page zh_CN.** Correction d’une erreur de traduction contextuelle dans le paramètre régional zh_CN où « quote rearrangée » était incorrectement traduite en « 重新排列了报价 », ce qui impliquait un devis commercial. Dans la section Typographie > Style de titre > Citation, le terme fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53844)
* **Correction d’une erreur de traduction de « modification de citation » dans le contexte de l’éditeur de page zh_CN.** Correction d’une erreur de traduction dans le paramètre régional zh_CN où le rendu de « cotation modifiée » était incorrect en tant que « 更改了报价 », suggérant une cotation commerciale. Dans la section Typographie > Style de titre > Citation, le terme fait référence à un élément de mise en forme (le bloc de citation), et non à un prix. (TGT-53845)

+++

**Recommandations**

+++Afficher les détails

* **Les modifications apportées au sélecteur CSS pour les recommandations sont désormais correctement enregistrées.** Correction d’un problème dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs de mettre à jour le sélecteur CSS pour les emplacements de recommandations. Annulation des modifications après l’enregistrement, bloquant les mises à jour des conteneurs de ciblage. (TGT-53835)
* **La sélection de l’événement de chargement de page persiste désormais dans les modifications de recommandation.** Correction d’un problème dans l’interface utilisateur de création d’activité qui empêchait les utilisateurs d’enregistrer les modifications lors du changement du type d’événement d’une recommandation de [!UICONTROL Affichage] à [!UICONTROL Chargement de page]. Bien que la sélection semble avoir réussi, elle est rétablie après avoir quitté l’application, bloquant la publication de l’activité. (TGT-53957)

+++

**Rapports**

+++Afficher les détails

* **« [!UICONTROL Exporter les détails de la commande au format CSV] » télécharge désormais les données complètes.** Correction d’un problème dans l’interface utilisateur mise à jour [!UICONTROL Présentation] en raison duquel l’option « [!UICONTROL Exporter les détails de la commande au format CSV] » téléchargeait des fichiers vides, même en présence de données de rapport valides. (TGT-53787)

+++

**Sécurité**

+++Afficher les détails

* **Ajout d’un préfiltre IMS pour protéger les points d’entrée GQL de l’exposition des données entre organisations.** Correction d’une vulnérabilité de sécurité dans l’onglet Admin affectant les points d’entrée GraphQL licenseGroups et targetProperties. Le problème provenait de l’utilisation de l’API JIL avec un jeton client d’administration qui pouvait être exploité pour accéder aux données de produit inter-organisations. (TGT-53837)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails

* **Restauration de la stabilité de la création dans l’interface utilisateur de création d’activité.** Correction d’un problème intermittent dans l’interface utilisateur du compositeur d’expérience visuelle qui entraînait l’échec de la création et rendait inopinément cliquables les liens, redirigeant les utilisateurs et utilisatrices hors de la page. (TGT-53153)
* **Modification restaurée pour les activités enregistrées dans l’interface utilisateur de création d’activité.** Correction d’un problème qui empêchait les utilisateurs de modifier les activités après avoir enregistré les modifications. Les activités affectées sont restées bloquées dans « [!UICONTROL  Application des modifications initiales ] », bloquant les mises à jour supplémentaires et masquant le bouton [!UICONTROL  Annuler ]. (TGT-53631)
* **Le compositeur d’expérience visuelle ne se bloque plus sur « [!UICONTROL  Application des modifications initiales ] »** Correction d’un problème de performances dans le VEC qui provoquait de longs retards lors du chargement d’expériences avec un grand nombre de modifications. Les utilisateurs concernés ont vu l’interface utilisateur bloquée sur « [!UICONTROL  Application des modifications initiales ] » pendant plusieurs minutes, en particulier dans les scénarios de l’expérience B. (TGT-53727)
* **Le compositeur d’expérience visuelle charge désormais les modifications sans éléments racine.**
Correction d’un problème dans le VEC en raison duquel les expériences se bloquaient lors du chargement de modifications sans élément racine clair. Ces modifications provoquaient auparavant un blocage indéfini de l’interface utilisateur sur « Application [!UICONTROL  modifications initiales ] ». (TGT-53799)
* **L’enregistrement des modifications dans les activités fonctionne désormais comme prévu.** Correction d’un problème lié aux autorisations dans la nouvelle interface utilisateur de création qui empêchait les utilisateurs d’enregistrer les modifications lors de la modification des objectifs et des paramètres avancés dans les activités. Un ruban d’erreur rouge et un message « Forbidden.Resource » s’affichaient pour les utilisateurs concernés, bien qu’ils disposaient des droits d’accès appropriés. (TGT-53816)
* **L’interface utilisateur du compositeur d’expérience visuelle conserve désormais les modifications d’expérience dans les vues.** Résolution de plusieurs problèmes dans le VEC mis à jour qui affectaient le développement d’expérience. Les modifications ne persistaient pas correctement, en particulier lors de l’utilisation des offres HTML ou du changement d’affichage. (TGT-53825)
* **Toutes les vues s’affichent désormais correctement lorsqu’une modification couvre plusieurs expériences.** Correction d’un problème dans l’interface utilisateur de création d’activité où une seule vue était affichée lorsqu’une modification était appliquée à plusieurs vues. L’info-bulle de pointage n’a pas permis de répertorier toutes les vues associées, même si la modification a été correctement appliquée. (TGT-53827)
* **Le compositeur d’expérience visuelle ne se bloque plus par intermittence sur « [!UICONTROL  Application des modifications initiales ]. »** Correction d’un problème intermittent dans le VEC où les expériences ne se chargeaient pas et restaient bloquées sur « [!UICONTROL  Application des modifications initiales ] ». Ce comportement était incohérent et déclenchait parfois des boucles de redirection ou nécessitait un effacement manuel du cache. (TGT-53916)
* **Le problème de chargement du compositeur d’expérience visuelle n’a pas pu être reproduit.** Nous avons enquêté sur un problème signalé en raison duquel le compositeur d’expérience visuelle restait bloqué sur « [!UICONTROL  Application des modifications initiales ] » lors de la modification des activités existantes. Le comportement était suspecté d’être lié à un contenu HTML dépourvu d’élément parent. Nous continuerons à surveiller la périodicité et vous recommandons d’utiliser des conteneurs structurés pour les offres HTML afin d’assurer la stabilité. (TGT-53972)
* Le mode **[!UICONTROL Conception] du compositeur d’expérience visuelle ne se comporte plus comme le mode [!UICONTROL Parcourir] par intermittence.** Correction d’un problème dans l’interface utilisateur où le mode [!UICONTROL Conception] se comportait comme le mode [!UICONTROL Parcourir] par intermittence, permettant les liens de `<a>` cliquables et empêchant la sélection d’éléments. Cela entraînait la disparition de la zone de survol et bloquait les workflows de modification. (TGT-53136)
* **Les clics de bouton en mode [!UICONTROL Compositeur] ne déclenchent plus la redirection de page.** Correction d’un problème dans l’interface utilisateur mise à jour du VEC en raison duquel le fait de cliquer sur un bouton en mode [!UICONTROL Compositeur] provoquait une redirection inattendue vers l’URL cible du bouton. Cela empêchait les utilisateurs de modifier les éléments de call-to-action (CTA) et perturbait le workflow de création. (TGT-53137)
* **Les mises à jour du code d’offre dans les activités de personnalisation automatisée sont désormais enregistrées sans erreur.** Correction d’un problème dans la nouvelle interface utilisateur de création qui provoquait une erreur « [!UICONTROL Entrée utilisateur non valide] » lors de la mise à jour du code d’offre dans les activités [!UICONTROL Automated Personalization]. L’erreur a empêché les utilisateurs d’enregistrer les modifications, même si l’entrée était valide. (TGT-53586)
* Le mode **[!UICONTROL Conception] du VEC bloque désormais la navigation des liens pour les composants modifiables.** Résolution d’un problème dans le VEC mis à jour où les éléments cliquables, tels que les boutons et les liens, déclenchaient une redirection de page même en mode [!UICONTROL Conception]. Ce comportement imitait le mode [!UICONTROL Parcourir] et empêchait les utilisateurs et utilisatrices de modifier les composants clés. (TGT-53696)
* **mesure « [!UICONTROL a cliqué sur un élément] » fonctionne désormais sans redirection ni erreur.** Correction d’un problème dans la nouvelle interface utilisateur de création qui entraînait des redirections inattendues et des écrans vides lors de la sélection de la mesure de conversion « [!UICONTROL Clic sur un élément] ». Cliquer sur un bouton pendant la configuration a déclenché la navigation au lieu d’enregistrer l’élément, ce qui a entraîné une erreur « [!UICONTROL  élément introuvable ] ». (TGT-53817)
* **Les activités existantes ne sont plus bloquées dans une boucle de chargement infinie lors de la modification.** Correction d’un problème dans la nouvelle interface utilisateur de création, en raison duquel la modification d’une activité existante dans le VEC entraînait le blocage de la page dans une boucle de chargement infinie. Ce problème n’affectait pas les activités nouvellement créées et a été déclenché par des modifications préexistantes sur la page. (TGT-53913)
* **Les pages d’activité existantes avec des modifications se chargent désormais correctement dans le VEC.** Correction d’un problème dans le VEC mis à jour en raison duquel les pages restaient bloquées en phase de chargement lors de la modification d’une activité existante avec des modifications enregistrées. Nouvelles activités chargées sans problème, mais dont le rendu des activités configurées précédemment a échoué. (TGT-53967)

+++

### [!DNL Target Standard/Premium] 25.9.3 (30 septembre 2025)

Cette version comprend les améliorations et correctifs suivants.

+++[!UICONTROL Audiences]

* **Les règles d’exclusion d’audience étaient incorrectement affichées comme inclusion dans l’interface utilisateur [!DNL Target].** Les audiences configurées avec des règles d’exclusion s’affichaient comme incluses lors de la modification du ciblage dans une activité. Bien que la logique d’exclusion ait été correctement appliquée lors de l’exécution, l’interface utilisateur n’a pas reflété la règle avec précision, omettant le libellé « exclusion ». L’interface utilisateur de [!DNL Target] affiche désormais correctement les règles d’exclusion dans les workflows de configuration et de ciblage des audiences, ce qui garantit la clarté et la cohérence de la configuration des campagnes. (TGT-53808)
* **La section [!UICONTROL Ciblage] n’indiquait pas qu’une règle d’audience était définie sur exclure.** Les audiences configurées avec la logique d’exclusion s’affichaient incorrectement en tant qu’inclusion dans la section [!UICONTROL Ciblage] de l’interface utilisateur de création d’activité. Bien que le serveur principal ait correctement appliqué la règle d’exclusion, l’interface utilisateur n’a pas pu la représenter visuellement, omettant le libellé « Exclure » et provoquant une confusion lors de la configuration de la campagne. La section [!UICONTROL Ciblage] affiche désormais clairement les règles d’exclusion, ce qui garantit la cohérence entre la configuration des audiences et la visualisation de ciblage. (TGT-53809)

+++

+++Localisation

* **Correction d’une incohérence terminologique dans la traduction chinoise simplifiée de « Vue détaillée complète ».**
Auparavant, le terme « Détails » était incorrectement traduit par « 详情 » dans le paramètre régional Chinois simplifié (zh_CN), enfreignant les directives terminologiques établies. Ce paramètre a été corrigé en « 详细信息 » pour assurer la cohérence avec la base terminologique. (TGT-53741)

+++

+++[!UICONTROL Recommandations]

* **Les zones de recommandation étaient difficiles à localiser et à sélectionner dans le compositeur d’expérience visuelle.** Après l’ajout d’une offre de recommandations dans le (VEC), le fait de cliquer sur la modification dans le panneau de gauche ne mettait pas en surbrillance ni n’affichait la zone de recommandation correspondante sur la page. Cela rendait difficile la localisation et la modification de l’offre, en particulier lorsqu’elle était masquée sous les sélecteurs ou mise en forme de manière minimale. Cliquer sur une modification de recommandation met désormais correctement en surbrillance l’élément associé et le fait défiler, ce qui améliore la convivialité et l’efficacité de la modification dans le processus de création d’activité mis à jour. (TGT-52571)
* **Les sélecteurs de recommandation ont été réécrits de manière incorrecte après l’enregistrement d’une activité.** Lors de l’ajout d’une recommandation à un élément dans le VEC, le sélecteur était initialement correct, mais après l’enregistrement et la réouverture de l’activité, il est devenu un sélecteur générique. Les tentatives de restauration manuelle du sélecteur d’origine ont provoqué des erreurs de validation. Les sélecteurs de recommandations persistent désormais avec précision après l’enregistrement, assurant ainsi un ciblage fiable et la modifiabilité dans le processus de création d’activité mis à jour. (TGT-53709)
* **Le contenu des critères n’a pas pu être modifié lors de la modification d’une activité existante.** Lors de la modification d’une activité, la section de contenu [!UICONTROL Critères] s’affichait désactivée, les boutons étaient grisés et ne répondaient pas. Ce problème a été résolu en s’assurant que les configurations [!UICONTROL Critères] sont entièrement modifiables lors des mises à jour des activités. Les clients peuvent désormais modifier le contenu [!UICONTROL Critères] sans avoir à changer de sélection ni à utiliser des solutions de contournement, ce qui améliore la flexibilité et la convivialité du processus de création d’activités mis à jour. (TGT-53812)
* **Les critères n’ont pas pu être modifiés dans une activité.** Les options [!UICONTROL Modifier les critères] et [!UICONTROL Supprimer des critères] ont été désactivées lors de l’accès aux critères depuis une activité. Toutefois, les mêmes critères peuvent être modifiés avec succès via l’onglet [!UICONTROL Recommendations]. Les critères sont désormais entièrement modifiables à partir du workflow de modification d’activité et de l’onglet [!UICONTROL Recommendations], ce qui garantit une expérience de modification cohérente et efficace. (TGT-53814)

+++

+++[!UICONTROL Rapports]

* **La génération d’offres ad hoc dans A[!UICONTROL Automated Personalization] a entraîné des incohérences dans les rapports.** L’utilisation de la fonctionnalité Générer des offres ad hoc dans les activités  (AP) a entraîné des rapports inexacts. Plus précisément, les identifiants d’offre ont été réutilisés entre les emplacements, ce qui a entraîné l’attribution incorrecte ou le remplacement des données de rapport. Les offres ad hoc sont désormais générées avec des identifiants distincts par emplacement, ce qui garantit un suivi et un reporting précis sur toutes les expériences configurées. (TGT-53757)
* **Échec du chargement des rapports d’activité en raison d’une erreur JavaScript.** Les clients ont rencontré un message « Un problème est survenu » lors de l’accès à l’onglet [!UICONTROL Rapports] pour certaines activités. L&#39;erreur est due à une exception JavaScript : impossible de lire les propriétés de l&#39;objet undefined (lecture de &#39;indexOf&#39;), déclenchées lors de l&#39;appel `getAnalyticsReportSummary` de GraphQL. Les rapports se chargent désormais correctement et la gestion des erreurs a été améliorée afin d’éviter des échecs similaires dans le workflow de création d’activité mis à jour. (TGT-53797)
* **Rapports bloqués après interaction avec la barre de défilement.** Lorsque vous cliquez sur la barre de défilement de l’onglet [!UICONTROL Rapports], la page se bloque, accompagnée d’une erreur JavaScript :
  Les rapports `SyntaxError: Failed to execute 'querySelector' on 'Element': '[data-key="a-currentcopy"hiretalent""]' is not a valid selector.` se chargent et défilent désormais correctement sans déclencher d’erreurs ou de blocages. (TGT-53828)
* **Les rapports n’affichaient pas la mesure principale.** La mesure principale, configurée en tant que mesure de conversion à l’aide d’une mbox, était absente des rapports d’activité. La recherche par nom de mesure ou de mbox n’a donné aucun résultat, ce qui empêche de voir les données de performances clés. Les mesures de Principal s’affichent désormais correctement dans l’onglet [!UICONTROL Rapports], ce qui permet d’assurer un suivi et une analyse précis des performances des campagnes. (TGT-53773)
* **L’onglet [!UICONTROL  Rapports] de l’interface utilisateur mise à jour s’est bloqué lors de l’interaction avec la barre de défilement horizontale.** La vue [!UICONTROL Rapports] s’est bloquée par intermittence avec une erreur « Un problème est survenu » lors de l’utilisation de la barre de défilement horizontale pour accéder aux mesures non visibles. La barre de défilement fonctionne désormais de manière fiable, ce qui permet aux clients d’afficher et d’analyser toutes les mesures sans avoir à recourir à des solutions telles que le zoom arrière ou l’utilisation de la touche Maj-Scroll. (TGT-53824)

+++

+++[!UICONTROL Compositeur d’expérience visuelle] (VEC)

* **Le fait de cliquer sur les chemins de navigation dans le VEC n’affichait pas systématiquement le menu de modification.**
Lors de la sélection d’éléments HTML via les chemins de navigation dans le (VEC), le menu d’édition ne s’affiche ou disparaît rapidement par intermittence, ce qui rend la sélection d’éléments peu fiable. Le menu d’édition s’affiche désormais de manière cohérente lorsque vous naviguez à travers les chemins de navigation, ce qui améliore le workflow de sélection d’éléments dans le processus de création d’activité mis à jour. (TGT-52873)
* **Le menu contextuel n’a pas pu apparaître par intermittence dans le VEC.** Le menu contextuel de l’interface utilisateur du compositeur d’expérience visuelle mise à jour n’apparaissait pas de manière cohérente lorsque vous cliquiez sur des éléments, ce qui rendait difficile l’accès aux options de modification. Le menu contextuel s’affiche désormais de manière fiable lors de la sélection d’un élément, ce qui améliore le workflow de modification et la convivialité globale dans le processus de création d’activité mis à jour. (TGT-53015)
* **Le menu contextuel n’a pas pu s’afficher pour certains éléments dans le VEC.** Le menu contextuel ne s’affichait pas lors de la sélection d’éléments spécifiques dans le compositeur d’expérience visuelle mis à jour, ce qui rendait difficile l’application des modifications. Le menu contextuel s’affiche désormais de manière cohérente pour tous les éléments pris en charge, ce qui améliore la fiabilité et la convivialité de l’expérience de modification dans le workflow de création d’activité mis à jour. (TGT-53248)
* **Le menu contextuel disparaissait lors du premier clic lors de l’utilisation de chemins de navigation dans le VEC.** La sélection d’un élément parent via les chemins de navigation dans le compositeur d’expérience visuelle a fait apparaître brièvement le menu contextuel, puis a disparu, ce qui a rendu difficile l’accès aux options de modification. Le menu contextuel reste désormais visible et fonctionnel lors de la navigation dans les éléments à travers les chemins de navigation, ce qui améliore la fiabilité du workflow de sélection d’éléments dans le processus de création d’activités mis à jour. (TGT-53424)
* **Le menu contextuel ne s’affichait pas pour les éléments de niveau supérieur dans le VEC.** La sélection d’éléments de niveau supérieur, tels que des balises `<div>` ou `<main>`, via les chemins de navigation du compositeur d’expérience visuelle, n’a pas déclenché le menu contextuel, empêchant ainsi d’autres actions de modification. Le menu contextuel s’affiche désormais de manière cohérente pour tous les éléments pris en charge, y compris les conteneurs de niveau supérieur, ce qui améliore la flexibilité et la convivialité du workflow de création d’activité. (TGT-53770)
* **Les éléments d’une page spécifique n’étaient pas modifiables dans le VEC.** Certains éléments de la page n’ont pas pu être sélectionnés ou modifiés dans le VEC mis à jour. Ce problème était isolé à cette page et n’affectait pas d’autres pages du même compte. Tous les éléments de la page peuvent désormais être sélectionnés et modifiés comme prévu, ce qui restaure toutes les fonctionnalités du workflow de création d’activité. (TGT-53353)
* **Amélioration du workflow lors de l’affichage d’éléments enfants lors de la sélection d’éléments dans le VEC.** Pour améliorer la convivialité et la précision lors de la création de l’activité, le compositeur d’expérience visuelle affiche désormais les éléments enfants lors du survol ou de la sélection d’un élément HTML parent. Cette amélioration permet aux clients de mieux comprendre la structure de la page et d’apporter des modifications plus précises, ce qui simplifie le workflow de modification dans l’interface utilisateur mise à jour. (TGT-53416)
* **Impossible de modifier les éléments des activités existantes à l’aide de la barre de modification.** Lors de la modification d’activités créées précédemment, la barre de modification ne s’activait pas pour certains éléments de la page, empêchant ainsi les mises à jour. Ce problème a principalement été observé dans les activités modifiées et était difficile à reproduire dans les activités nouvellement créées. La barre de modification s’affiche désormais de manière cohérente et permet de modifier tous les éléments pris en charge, ce qui améliore la fiabilité et la convivialité du workflow de création d’activité mis à jour. (TGT-53013)

+++

+++[!UICONTROL Workspaces]

* **Le clonage d’une activité vers un autre espace de travail a déclenché une erreur « Entrée utilisateur non valide ».** La tentative de clonage d’une activité d’un espace de travail à un autre a entraîné une erreur : « InvalidProperty.Json - Unknown property name &#39;content&#39; ». Ce problème était dû à une gestion incorrecte des métadonnées d’activité pendant le processus de clonage. Les activités peuvent désormais être clonées dans les espaces de travail sans déclencher d’erreurs de validation, ce qui garantit des workflows de déploiement d’activité plus fluides. (TGT-53731 et TGT-53736)

+++

### [!DNL Target Standard/Premium] 25.9.2 (22 septembre 2025)

Cette version comprend les améliorations et correctifs suivants :

**[!UICONTROL Audiences]**

+++Afficher les détails

* **Correction d’un problème en raison duquel les activités ne pouvaient pas être copiées en raison d’identifiants d’audience non valides.** Les clients et clientes qui tentent de copier des activités dans le processus de création d’activités mis à jour ont rencontré une erreur due à des ID d’audience non valides (par exemple, -1752722444307). Ce problème de validation du serveur principal a empêché la duplication des activités dans le même espace de travail. Ce problème a été résolu, et les activités peuvent désormais être copiées sans erreurs liées aux audiences. (TGT-53717)
* **Correction d’un problème en raison duquel des erreurs d’entrée utilisateur non valides s’affichaient pour les audiences d’activité uniquement dans les activités [!UICONTROL Automated Personalization] la modale [!UICONTROL Gérer le contenu].** Les clients ont rencontré des erreurs d’entrée utilisateur non valides lors de la configuration des audiences d’activité uniquement dans la fenêtre modale [!UICONTROL  Gérer le contenu ] pour les activités AP. Ce problème se produisait malgré l’utilisation réussie des audiences précédentes. Les configurations d’audience combinées s’enregistrent désormais correctement sans déclencher d’erreurs de validation. (TGT-53749)

+++

**Documentation**

+++Afficher les détails

* **Déplacement des pages de documentation de Web SDK spécifiques à Target vers le référentiel Adobe Target.** Dans le cadre de la restructuration de la documentation de Web SDK, le contenu spécifique à [!DNL Target] a été migré de la documentation générale de Web SDK vers le [!DNL Adobe Target] [guide de développement](https://experienceleague.adobe.com/en/docs/target-dev/developer/a4t/overview-a4t?lang=en){target=_blank}. Cette modification améliore la visibilité du contenu et garantit que l’équipe produit appropriée maintient les conseils spécifiques à la solution. (TGT-53374)

+++

**[!UICONTROL Décisions d’offre]**

+++Afficher les détails

* **L’option Décision d’offre est désormais systématiquement visible lors de la création initiale de l’activité.** Correction d’un problème dans l’interface utilisateur mise à jour où l’option [!UICONTROL Décision d’offre] ne s’affichait pas lors du flux de création pour la première fois des activités A/B, en particulier lorsqu’elle était accessible en mode navigation privée sur les clients pour lesquels les décisions d’offre étaient activées. L’option ne s’affichait qu’après avoir accédé à l’étape [!UICONTROL Ciblage] et être revenu à [!UICONTROL Expériences]. Ce correctif garantit que l’option [!UICONTROL Décision d’offre] est immédiatement disponible lors de la configuration initiale, ce qui améliore la convivialité et réduit la confusion. (TGT-51888)

+++

**[!UICONTROL Offres]**

+++Afficher les détails

* **Correction d’un problème en raison duquel les offres de redirection n’incluaient pas de `redirectOptions` dans la payload lors de la `includeContent=true`.** Les clients récupérant des offres de redirection avec `includeContent=true ` ne disposaient pas du champ `redirectOptions` dans la payload de réponse. Cette incohérence affectait les workflows, tels que la copie d’offres et la création d’activités. Les offres de redirection incluent désormais correctement les `redirectOptions` lorsque du contenu est demandé. (TGT-53737)

+++

**[!DNL Recommendations]**

+++Afficher les détails

* **Suivi des clics restauré pour les activités [!UICONTROL Recommendations] créées dans l’interface utilisateur mise à jour.** Correction d’un problème en raison duquel les activités [!UICONTROL Recommendations] créées dans l’interface utilisateur mise à jour n’enregistraient pas le suivi des clics, ce qui entraînait l’absence de conversions signalées. Les activités intégrées à l’interface utilisateur héritée ont correctement suivi les clics et signalé les conversions comme prévu. Ce correctif garantit que les activités Recommendations créées dans l’interface utilisateur mise à jour incluent désormais les attributs de suivi corrects, ce qui restaure les rapports de conversion et l’alignement sur les mesures A4T. (TGT-53287)
* **Suivi des clics restauré pour les activités Recommendations.** Correction d’un problème en raison duquel les activités [!UICONTROL Recommendations] créées dans l’interface utilisateur mise à jour n’enregistraient pas le suivi des clics, ce qui entraînait l’absence de conversions signalées. L’interface utilisateur héritée a correctement appliqué un identifiant de suivi (`at-track-click`) au contenu [!UICONTROL Recommendations], tandis que l’interface utilisateur mise à jour a inséré par erreur un espace réservé (`__recsClickTrackIdPlaceholder__`), empêchant le suivi du serveur principal. Ce correctif garantit que [!DNL Recommendations] contenu inclut désormais l’identifiant de suivi correct, restaurant les rapports de conversion et l’alignement sur les mesures A4T. (TGT-53496)
* **Le blocage de l’éditeur de collections a été résolu dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur [!UICONTROL Compositeur d’expérience visuelle] (VEC) mise à jour en raison duquel l’ouverture d’une collection à partir du panneau de l’éditeur entraînait le blocage de la page avec une erreur TypeError : impossible de lire les propriétés de l’objet non défini (lecture de « customLocale »). Cette erreur s’est produite sur plusieurs types d’activité, y compris les tests [!UICONTROL Recommendations] et A/B. (TGT-53703)
* **Option permettant de supprimer la collection sélectionnée restaurée dans le VEC.** Correction d’un problème dans le VEC en raison duquel les utilisateurs ne pouvaient remplacer qu’une collection sélectionnée dans une activité [!UICONTROL Recommendations], mais ne pouvaient pas la supprimer entièrement. Cette limitation a bloqué les cas d’utilisation nécessitant une suppression nette de la collection sans substitution. Ce correctif introduit une option claire pour supprimer la collection sélectionnée, ce qui permet une plus grande flexibilité dans la configuration de l’activité et l’alignement avec le comportement hérité de l’interface utilisateur. (TGT-53652)
* **Les collections de critères personnalisés s’affichent désormais correctement dans l’interface utilisateur de [!UICONTROL Recommendations].** Correction d’un problème dans l’interface de Recommendations en raison duquel les collections créées à l’aide de critères personnalisés n’affichaient pas les résultats du produit. Bien que les collections standard basées sur les attributs aient fonctionné comme prévu, celles qui utilisent des filtres personnalisés ont renvoyé « Aucun résultat trouvé » malgré des correspondances de catalogue valides. Ce correctif garantit que les collections qui utilisent des attributs personnalisés s’affichent désormais correctement dans l’onglet [!UICONTROL Produit], restaurant ainsi l’intégralité des fonctionnalités des workflows de recommandations personnalisées. (TGT-53653)
* **Correction d’un problème en raison duquel les collections n’affichaient pas les produits lors de la première ouverture de la page [!UICONTROL Products].** Les clients qui accédaient aux collections dans la section [!UICONTROL Recommendations] ont obtenu des résultats de produit vides lors de la première ouverture de la page [!UICONTROL Products]. Ce problème était dû à une erreur de serveur principal dans la requête GraphQL, qui n’a pas réussi à charger les données de produit pour les collections avec des critères personnalisés. Le problème a été résolu et les produits s’affichent désormais correctement sans nécessiter de changement d’environnement. (TGT-53694)
* **Correction d’un problème en raison duquel les collections ne pouvaient pas être supprimées dans les activités basées sur des formulaires [!UICONTROL Recommendations].** Les clients qui créaient des activités [!UICONTROL Recommendations] à l’aide du [!UICONTROL compositeur d’expérience d’après les formulaires] ne pouvaient pas désélectionner une collection choisie précédemment. L’interface utilisateur exigeait qu’une collection soit sélectionnée avant d’enregistrer, ce qui empêche les utilisateurs de revenir à « Toutes les collections ». Ce comportement a été mis à jour pour correspondre à la fonctionnalité du VEC, ce qui permet aux clients d’enregistrer sans sélectionner de collection et de définir par défaut « Toutes les collections » comme prévu. (TGT-53708)
* **Correction d’un problème en raison duquel les promotions ne pouvaient pas être définies par attribut en raison de valeurs de règle de collecte ou de filtrage manquantes.** Les clients configurant des promotions par attribut dans le processus de création d’activité ont rencontré une erreur indiquant qu’il manquait une promotion avec un ID de collection ou des valeurs de règle de filtrage. Ce problème de validation a bloqué la progression même lorsque la configuration semblait terminée. Les promotions peuvent désormais être enregistrées correctement lorsqu’elles sont configurées par attribut . (TGT-53750)
* **Correction d’un problème en raison duquel les activités ne pouvaient pas être enregistrées en raison de noms d’expérience en double.** Les clients ont rencontré une erreur d’entrée utilisateur non valide lors de l’enregistrement d’activités qui incluaient des combinaisons spécifiques de critères et de conceptions. L’erreur a été déclenchée par des noms d’expérience en double, même si la configuration semblait valide. Les activités avec des configurations distinctes peuvent désormais être enregistrées sans conflits de noms. (TGT-53805)
* **Correction d’un problème en raison duquel la validation n’était pas valide pour les promotions configurées par attribut.** Les clients ont rencontré des erreurs de validation persistantes lors de la configuration des promotions par attribut dans le processus de création d’activités, même lorsque tous les champs obligatoires étaient correctement renseignés. Ce problème était dû à une logique de validation incorrecte dans le workflow [!UICONTROL Recommendations]. Les promotions basées sur les attributs sont désormais validées et enregistrées comme prévu. (TGT-53811)
* **Correction d’un problème en raison duquel l’application d’une promotion à une activité [!UICONTROL Recommendations] active déclenchait une erreur.** Les clients ont rencontré l’erreur « Il manque un ID de collection ou des valeurs de règle de filtrage dans une promotion » lors de la tentative d’application d’une promotion front-end à une activité [!UICONTROL Recommendations] active, même après avoir fourni des détails de configuration valides. Les promotions peuvent désormais être appliquées avec succès aux activités actives sans déclencher d’erreurs de validation, ce qui garantit une expérience plus fluide dans l’interface utilisateur de création d’activité mise à jour. (TGT-53738)
* **Correction d’un problème en raison duquel les produits n’étaient pas visibles dans les collections dans l’interface utilisateur de [!UICONTROL Recommendations].** Les clients d’un seul client ont signalé l’échec du chargement des listes de produits lors de l’affichage de certaines collections dans la section [!UICONTROL Recommendations] de la nouvelle interface utilisateur. Le problème a été temporairement résolu en changeant d’environnement, mais cette solution de contournement a entraîné une mauvaise expérience utilisateur. Les entités de produit se chargent désormais de manière cohérente sans basculement d’environnement. (TGT-53783)
* **Correction d’un problème où les critères et les conceptions n’étaient pas affichés sur une ligne dans l’interface utilisateur de création d’activités.** Auparavant, les critères et les conceptions du processus de création d’activités s’affichaient dans un format compressé, ce qui rendait difficile l’affichage et la gestion des éléments individuels pour les clients. Chaque critère et conception apparaît désormais sur sa propre ligne, ce qui améliore la lisibilité et la convivialité dans l’interface utilisateur mise à jour. (TGT-53818)

+++

**Rapports**

+++Afficher les détails

* La mesure **[!UICONTROL Chiffre d’affaires total] est désormais incluse dans les exportations CSV des rapports d’activité.** Correction d’un problème dans l’interface utilisateur mise à jour [!UICONTROL Aperçu] où le chiffre d’affaires total s’affichait correctement dans la vue du rapport d’activité, mais était absent de l’exportation au format CSV, avec un montant de 0 $. Cette incohérence empêchait les utilisateurs de se fier aux données exportées pour l’analyse et la création de rapports hors ligne. (TGT-53325)
* La mesure **[!UICONTROL Ventes totales] est désormais incluse dans les exportations CSV des rapports d’activité.** Correction d’un problème dans l’interface utilisateur mise à jour où la mesure [!UICONTROL Total Sales] s’affichait correctement dans la vue du rapport d’activité, mais était absente de l’exportation au format CSV. Cette incohérence empêchait les utilisateurs d’accéder à des données de performances complètes dans les rapports téléchargés. Ce correctif garantit que les valeurs [!UICONTROL Total Sales] sont désormais incluses avec précision dans les exportations CSV, rétablissant la cohérence entre les rapports in-app et l’analyse hors ligne. (TGT-53330)
* **Amélioration de la messagerie d’erreur pour [!UICONTROL Vue graphique] lorsque les mesures ne sont pas activées.** Correction d’un problème dans le VEC en raison duquel la [!UICONTROL vue graphique] affichait un message générique « Un problème est survenu » lorsqu’une mesure demandée n’était pas activée dans la suite de rapports [!DNL Analytics] associée. Ce problème a été déclenché par une erreur `not_enabled_metric` dans la réponse GraphQL du serveur principal. Ce correctif remplace l’erreur vague par un message plus informatif qui aide les utilisateurs et utilisatrices à identifier les problèmes de configuration dans [!DNL Analytics], ce qui réduit la confusion et les remontées inutiles de l’assistance. (TGT-53577)
* **Correction d’un problème en raison duquel la durée du rapport dépassait la limite prise en charge de 90 jours.** Les clients et clientes qui utilisaient le filtre « [!UICONTROL X derniers jours] » dans la section [!UICONTROL Rapports] ont pu sélectionner des durées supérieures à 90 jours, ce qui pouvait entraîner des problèmes de performances et des données incomplètes. Le filtre a été mis à jour pour appliquer une plage maximale de 90 jours, ce qui garantit la cohérence et la fiabilité des rapports. (TGT-53795)
* **Correction d’un problème où les rapports CSV de performances étaient générés à l’aide de l’environnement par défaut au lieu de l’environnement sélectionné.** Auparavant, lorsque les clients modifiaient l’environnement dans les paramètres du rapport et généraient un rapport de performances, le fichier CSV obtenu contenait des données de l’environnement par défaut plutôt que de l’environnement sélectionné.  L’interface utilisateur transmet désormais correctement le paramètre `environmentId`, en s’assurant que le rapport reflète l’environnement choisi. En outre, la gestion des erreurs a été améliorée. Si des erreurs GraphQL se produisent lors de la génération du fichier CSV, l’interface utilisateur affiche désormais un message d’erreur clair au lieu de produire un fichier CSV vide. (TGT-53064)
* **Correction d’un problème en raison duquel les rapports Analytics for Target (A4T) n’affichaient pas les données dans la [!UICONTROL vue graphique].** Les clients qui utilisaient [!DNL Target] avec l’intégration A4T ont rencontré une erreur « Un problème s’est produit » lors du passage à la vue Graphique dans l’onglet Rapports des activités de test A/B. Bien que la [!UICONTROL vue Tableau] ait été chargée correctement, la [!UICONTROL vue Graphique] n’a pas pu effectuer le rendu des tendances des mesures au cours de la période sélectionnée. La [!UICONTROL vue Graphique] affiche désormais les données de performances attendues pour toutes les mesures prises en charge, ce qui améliore la visibilité et la précision des rapports dans l’interface utilisateur mise à jour. (TGT-53573)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails

* **Les métadonnées d’élément sont désormais visibles au survol dans le menu de chemin de navigation.** Amélioration du menu de chemin de navigation dans le VEC pour afficher des détails d’élément supplémentaires tels que l’identifiant, la classe et le nom lors du survol d’un élément. Cette amélioration permet aux utilisateurs et utilisatrices d’identifier et de différencier plus facilement les éléments lors de la configuration des activités. (TGT-53409)
* **Le survol du chemin de navigation met désormais en surbrillance l’élément correspondant dans le VEC.** Amélioration du [!UICONTROL compositeur d’expérience visuelle] afin de mettre en surbrillance l’élément correspondant dans l’éditeur lorsque vous pointez sur des éléments dans le menu de chemin de navigation. Le type d’élément est également affiché, par exemple conteneur, texte en gras ou bouton. Ce comportement s’applique aux éléments frères et exclut les types non pris en charge tels que SVG, en fonction de la liste de validation. (TGT-53411)
* **Alerte Modifications non enregistrées restaurée dans les workflows de modification du compositeur d’expérience visuelle.** Correction d’un problème dans le VEC en raison duquel les utilisateurs n’étaient plus avertis des modifications non enregistrées des modifications du code personnalisé. Contrairement à l’interface utilisateur héritée, la nouvelle expérience ne comportait pas d’invites lors de la fermeture de l’éditeur de personnalisation, ce qui entraînait une perte accidentelle de la progression. Ce correctif restaure les alertes pour tous les types de modification, y compris le code personnalisé, et garantit que les utilisateurs sont avertis avant de quitter sans enregistrer. (TGT-53435).
* **Les modifications du code personnalisé persistent désormais pendant l’actualisation de la page dans le VEC.** Correction d’un problème dans le VEC en raison duquel les modifications du code personnalisé étaient perdues lors des actualisations du site web. Ce problème se produisait sur les pages comportant plusieurs rechargements, ce qui entraînait la réinitialisation et l’annulation des modifications non enregistrées par l’éditeur. Le correctif garantit que les modifications de code personnalisé restent intactes même si la page se recharge lors de la modification, évitant ainsi toute perte accidentelle de la progression. (TTGT-53501)
* **Problème de connexion résolu pour l’accès au site dans le VEC.** Correction d’un problème en raison duquel les utilisateurs ne pouvaient pas se connecter à leur site lors de l’accès via le VEC. Le flux de connexion a redirigé à plusieurs reprises les utilisateurs vers la page de connexion, empêchant la configuration et la prévisualisation de l’activité. Ce correctif garantit que le compositeur d’expérience visuelle n’interfère plus avec le comportement de connexion et restaure l’accès attendu pour les utilisateurs authentifiés. (TGT-53524)
* **Problème de duplication des cookies résolu dans l’extension d’assistance du VEC.** Correction d’un problème en raison duquel l’extension [!UICONTROL Adobe Experience Cloud Visual Editing Helper] dupliquait le cookie `at_qa_mode` lors de l’assurance qualité via les liens de prévisualisation. Lors du changement manuel d’index d’aperçu, plusieurs cookies ont été créés avec des valeurs en conflit entre les domaines, empêchant les testeurs de changer de variantes de manière fiable. Ce comportement a été observé même en dehors de l’interface utilisateur de Target et a affecté les comptes internes et clients. Ce correctif garantit une gestion cohérente des cookies en empêchant les entrées en double et en alignant la portée du domaine, ce qui permet un changement de variante transparent sans nécessiter de nettoyage manuel des cookies. (TGT-53579)
* **Correction d’un problème en raison duquel cliquer sur des éléments sur une certaine page d’accueil provoquait des fuites de mémoire.** Les clients et clientes créant des activités sur cette page d’accueil ont rencontré des fuites de mémoire lors de leur interaction avec les éléments de page. Le problème était lié à des avertissements excessifs de la console et à l&#39;augmentation de l&#39;utilisation de la mémoire dans les sous-trames, en particulier en ce qui concerne les attributs srcset incorrects. L’utilisation de la mémoire reste désormais stable lors de l’interaction. (TGT-53761)
* **Correction d’un problème en raison duquel le VEC se bloquait et affichait un écran vide lors du chargement de certaines activités.** Les clients d’un client spécifique ont signalé que l’éditeur n’a pas réussi à charger des activités spécifiques. Le compositeur d’expérience visuelle est resté bloqué sur « Application des modifications initiales » avant de se bloquer et d’afficher un écran vide. Le compositeur d’expérience visuelle charge désormais les activités affectées sans erreur dans le processus de création d’activités mis à jour. (TGT-52932)
* **Correction d’un problème en raison duquel le rail [!UICONTROL Gérer le contenu] dans les activités [!UICONTROL Automated Personalization] affichait des libellés d’emplacement incohérents.** Les clients ont signalé que les numéros d’emplacement du rail [!UICONTROL Gérer le contenu] ne correspondaient pas dans les onglets [!UICONTROL Expériences] et [!UICONTROL Offres]. (par exemple, Emplacement 2 et Emplacement 4 dans Expériences, et Emplacement 1 et Emplacement 2 dans Offre) même si seulement deux emplacements ont été configurés. Les libellés d’emplacement sont désormais cohérents et mappés avec précision aux modifications, ce qui améliore la clarté et la convivialité du processus de création d’activités. (TGT-52934)
* **Correction d’un problème en raison duquel les modifications du VEC étaient perdues après l’enregistrement.** Les clients ont signalé qu’après l’enregistrement d’une modification dans le VEC, la page s’actualisait et revenait à sa version précédente. Ce problème entraînait la perte des mises à jour les plus récentes, sauf si l’activité entière était enregistrée immédiatement. Les modifications persistent désormais correctement après l’enregistrement et l’éditeur n’annule plus les modifications de manière inattendue, ce qui garantit une expérience fiable dans le workflow de création d’activité. (TGT-53500)
* **Amélioration de la sélection d’éléments dans le VEC en affichant le type d’élément lors du survol et de la sélection.** Pour améliorer la convivialité lors de la création de l’activité, le compositeur d’expérience visuelle agrémente désormais les éléments HTML avec leur type lorsqu’ils sont survolés ou sélectionnés. Cette amélioration permet aux clients d’identifier et de sélectionner plus facilement les éléments corrects. Les éléments sélectionnés sont mis en surbrillance avec une couleur distincte et les éléments survolés sont entourés en bleu. Le type d’élément s’affiche également, fournissant un contexte plus clair lors de la modification. (TGT-53502)

+++

### Mises à jour des flux de données (19 septembre 2025)

L’identifiant du flux de données et la combinaison de sandbox doivent être uniques pour les connexions de destination [!DNL Adobe Target].

Mise à jour de la logique de validation pour [!DNL Target] connexions de destination afin d’imposer que la combinaison de l’identifiant du flux de données et du nom du sandbox doit être unique au sein d’une organisation IMS. Cela signifie :

* La même paire identifiant de flux de données + nom de sandbox ne peut pas être réutilisée sur plusieurs connexions de destination [!DNL Target].
* Un même identifiant de flux de données peut être utilisé pour différentes connexions uniquement si elles sont configurées dans différents sandbox.
* Cette règle s’applique à toutes les sélections de flux de données, y compris lorsque l’option « Aucun » est sélectionnée.

Cette mise à jour garantit une configuration cohérente et empêche les conflits entre les environnements multi-sandbox. Pour plus d’informations, voir [Connexion ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/personalization/adobe-target-connection){target=_blank} dans le guide *Destinations Experience Platform*.

### [!DNL Target Standard/Premium] 25.9.1 (5 septembre 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Fragments d’expérience]**

+++Afficher les détails

* **Amélioration de l’attribution des utilisateurs pour les offres de [!UICONTROL fragment d’expérience AEM].** Correction d’un problème dans le VEC en raison duquel le champ « [!UICONTROL Dernière mise à jour ] » des offres de [!UICONTROL Fragment d’expérience AEM] (XF) affichait incorrectement un ID de code au lieu du nom d’utilisateur. Cette incohérence s’est produite lors de la sélection des offres dans l’interface utilisateur mise à jour, créant une incohérence avec les offres de l’interface utilisateur et d’HTML héritées, qui affichaient correctement le nom du dernier éditeur. Ce correctif garantit une attribution utilisateur cohérente entre les types d’offres, ce qui améliore la transparence et l’alignement sur le comportement attendu. (TGT-52880 et TGT-52898)

+++

****

+++Afficher les détails

* **L’erreur de décision d’offre a été résolue pour les offres ODE.** Correction d’un problème où les offres du moteur de décision d’offre (ODE) injectées via [!DNL Target] renvoyaient une erreur 400 en raison de métadonnées de format manquantes. Le message d’erreur indiquait que le type MIME était nul, ce qui empêchait le traitement réussi des décisions d’offre. Ce correctif garantit la gestion appropriée des métadonnées de l’offre, la restauration de la fonctionnalité pour la diffusion de contenu personnalisé et la possibilité d’exécuter sans interruption les campagnes marketing. (TGT-53635)
* **Résolution d’un problème de rendu d’offre ODS.** Correction d’un problème où les offres [!DNL Offer Decision Service] (ODS) créées via [!DNL Adobe Journey Optimizer] (AJO) n’étaient pas rendues lorsque les activités étaient créées à l’aide du VEC dans l’interface utilisateur mise à jour. La même configuration fonctionnait correctement dans l’interface utilisateur héritée, ce qui entraînait une confusion et bloquait l’exécution de la campagne. Ce correctif garantit la cohérence de la diffusion des offres dans les deux versions de l’interface utilisateur et restaure le comportement attendu pour la personnalisation pilotée par AJO.

+++

**Rapports**

+++Afficher les détails

* **Option de téléchargement restaurée dans la section Rapports de l’interface utilisateur de présentation des rapports mise à jour.** Correction d’un problème dans la nouvelle interface utilisateur de présentation en raison duquel le bouton [!UICONTROL Télécharger] était absent de la section Rapports, ce qui empêchait les utilisateurs d’exporter les scores d’importance des attributs. Cette mise à jour restaure l’intégralité des fonctionnalités d’exportation, permettant un accès rationalisé aux données téléchargeables pour l’analyse et le reporting. (TGT-53222)
* **[!UICONTROL Télécharger le rapport CSV complet] bouton restauré dans la vue [!UICONTROL Attributs importants].** Correction d’un problème dans l’interface utilisateur de création d’activité mise à jour où le bouton [!UICONTROL Télécharger le rapport CSV complet] était absent de la section [!UICONTROL Attributs importants] dans la vue des rapports. Ce correctif restaure l’accès aux informations téléchargeables, garantissant ainsi des fonctionnalités cohérentes dans les interfaces utilisateur mises à jour et héritées. (TGT-53238)
* **Résolution des problèmes d’interface utilisateur affectant le reporting [!UICONTROL Ciblage automatique] dans l’interface utilisateur de présentation mise à jour.** Correction de plusieurs problèmes d’interface utilisateur dans l’interface d’aperçu mise à jour qui affectaient les rapports d’activité de [!UICONTROL ciblage automatique]. Ces correctifs incluent :

  * Mesures d’effet élévateur et de confiance manquantes dans les rapports de synthèse
  * Indicateur de couleur incorrect pour la case à cocher « modèles créés »
  * Rapport graphique non fonctionnel malgré la variance des données dans [!DNL Analytics]
  * Lien de téléchargement manquant pour les rapports [!UICONTROL  Segments automatisés ] et [!UICONTROL Attributs importants]
  * Affichage du rapport [!UICONTROL Segments automatisés] interrompu

  Ces correctifs restaurent le comportement de création de rapports attendu et améliorent la visibilité sur les performances du [!UICONTROL ciblage automatique] dans l’interface utilisateur mise à jour. (TGT-53484)

+++

**[!UICONTROL Compositeur d’expérience visuelle]**

+++Afficher les détails

* **Validation du formulaire corrigée pour les conditions de présence des paramètres dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour où la sélection de « [!UICONTROL  La valeur du paramètre de mbox personnalisé est présente ] » ou « [!UICONTROL  Le paramètre est présent ] » obligeait incorrectement les clients à saisir une valeur. Ce comportement était en conflit avec la logique prévue, qui vérifie simplement l’existence d’un paramètre quelle que soit sa valeur. Le correctif aligne la validation du formulaire sur le comportement attendu, ce qui permet une configuration plus fluide des activités et une adoption complète de l’interface utilisateur mise à jour. (TGT-53638)
* **Correction de la logique de formulaire pour les règles de présence de paramètres dans la diffusion de page.** Correction d’un problème dans l’interface utilisateur mise à jour où la sélection de règles de diffusion de page telles que « [!UICONTROL Paramètre est présent] », « [!UICONTROL Paramètre n’est pas présent] », « [!UICONTROL Valeur de paramètre est présente] » ou « [!UICONTROL Valeur de paramètre n’est pas présente] » obligeait incorrectement les utilisateurs à saisir une valeur de paramètre supplémentaire. Ce comportement était incompatible avec l’interface utilisateur héritée et contredisait la logique prévue de détection de la présence de paramètres sans spécifier de valeur. Ce correctif restaure le comportement attendu de configuration des règles, rationalisant la configuration des activités et améliorant la convivialité. (TGT-53640)
* **Amélioration de la logique de validation pour le créateur de règles à plusieurs pages dans l’interface utilisateur mise à jour.** Résolution de plusieurs problèmes de validation dans le créateur de règles multi-pages dans l’interface utilisateur mise à jour. Ces correctifs incluent :

  * Empêcher la création de règles lorsque le paramètre mbox est vide
  * Affichage des messages d’erreur appropriés pour les états de règle non valides
  * Correction de la logique de validation pour les opérateurs unaires et basés sur des paramètres qui ne nécessitent pas de valeurs d’opérande
  * Activation des règles de fragment de hachage avec des opérateurs unaires en restaurant la fonctionnalité d’enregistrement

  Ces mises à jour garantissent une configuration des règles précise et améliorent la convivialité sur plusieurs scénarios de diffusion de pages complexes. (TGT-53722)
* **Problème de changement de nom de l’emplacement résolu dans les activités A/B et MVT.** Correction d’un bug dans l’interface utilisateur mise à jour en raison duquel le changement de nom d’un emplacement dans une activité [!UICONTROL Test A/B] ou [!UICONTROL Test multivarié] (MVT) ne persistait pas après la navigation entre la liste d’emplacements, le ciblage et retour. Cette mise à jour garantit que les modifications du nom de l’emplacement sont enregistrées et répercutées de manière cohérente tout au long du workflow d’activité. (TGT-52367)
* **Persistance du nom de l’emplacement corrigée pour les activités MVT et AP dans l’interface utilisateur mise à jour.** Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les noms d’emplacement modifiés dans les activités [!UICONTROL Test multivarié] (MVT) et [!UICONTROL Automated Personalization] (AP) n’étaient pas enregistrés correctement. Après avoir renommé un emplacement, la navigation entre les onglets, tels que [!UICONTROL Ciblage] et [!UICONTROL Expériences], a fait revenir les noms à leur état précédent. Ce correctif garantit la cohérence des noms d’emplacement entre les onglets et améliore la fiabilité lors de la configuration des activités. (TGT-52927)
* **Correction de l’étiquetage de l’emplacement dans le panneau Gérer les expériences pour les activités MVT.** Correction d’un problème dans l’interface utilisateur mise à jour où le panneau [!UICONTROL Gérer les expériences] dans les activités [!UICONTROL Test multivarié] (MVT) affichait une numérotation d’emplacement incohérente. Ce correctif garantit que les libellés d’emplacement sont séquentiels et correctement alignés sur les modifications définies par l’utilisateur, ce qui améliore la clarté et la convivialité lors de la configuration de l’expérience. (TGT-52929)

+++

### [!DNL Target Standard/Premium] 25.8.4 (1er septembre 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Activités]**

+++Afficher les détails

* **Les clients ne pouvaient pas copier les noms d’activité ou de document à partir de la [!UICONTROL Présentation de l’activité]** : auparavant, les clients ne pouvaient pas copier le nom d’une activité ou l’offre/le document associé directement à partir de la [!UICONTROL Présentation de l’activité] dans le processus de création d’activité mis à jour. Cette limitation affectait la convivialité, en particulier sur les écrans plus petits. Les clients peuvent désormais facilement copier les noms des activités et des documents sans solution. (TGT-51850)
* **Ingestion proactive des données client [!DNL Target] traitées lors de la création de l’activité** : amélioration du processus de création d’activité en permettant la collecte proactive de rapports, de contenu et de captures d’écran de clients [!DNL Target]. Cette amélioration corrige les lacunes en matière de données identifiées dans les cas d’utilisation existants et permet d’obtenir des informations plus précises lors de la configuration des activités et des expériences. (TGT-52415)
* **Les activités AP n’ont pas récupéré les données prêtes pour le modèle dans la section [!UICONTROL Rapports]** : les clients qui visualisaient les activités Automated Personalization (AP) dans la section [!UICONTROL Rapports] n’ont pas pu voir les indicateurs prêts pour le modèle au niveau du groupe de rapports et de l’offre. Ce problème se produisait car les données prêtes pour le modèle n’étaient pas correctement récupérées à partir du serveur principal. La fonctionnalité a été restaurée et les données prêtes pour le modèle apparaissent désormais comme prévu. (TGT-53600 et TGT-53601)
* **Les activités planifiées pour le futur affichaient incorrectement un statut « [!UICONTROL En direct] » dans la présentation de [!UICONTROL Activité]** : les clients ont observé que les activités planifiées pour démarrer dans le futur étaient incorrectement marquées comme « [!UICONTROL En direct] » dans la présentation de [!UICONTROL Activité]. Cette incohérence de statut a été résolue et les activités planifiées s’affichent désormais correctement en tant que « [!UICONTROL Planifié] » sans nécessiter d’actualisation de page. (TGT-52835)

+++

**[!UICONTROL Recommandations]**

+++Afficher les détails

* **La liste de produits n’était pas visible dans la boîte de dialogue [!UICONTROL Afficher la collection] :** auparavant, les clients ne pouvaient pas voir la liste de produits lors de l’affichage d’une collection dans l’onglet [!UICONTROL Recommandations]. La boîte de dialogue [!UICONTROL Afficher la collection] affiche désormais correctement les produits associés, ce qui améliore la transparence et la convivialité dans l’interface utilisateur [!UICONTROL Recommendations] mise à jour. (TGT-50531)
* **Correction d’un problème qui provoquait un filtrage sensible à la casse dans la [!UICONTROL Recherche de catalogue de produits] recherche avancée** : le filtrage de recherche avancé dans la page [!UICONTROL Recherche de catalogue de produits] ignore désormais correctement le respect de la casse, en s’alignant sur le comportement des services principaux et GraphQL. Cette mise à jour garantit des résultats de suggestions cohérents et précis pour les clients, quelle que soit la casse du texte. (TGT-53585)
* **La recherche avancée dans l’interface utilisateur [!UICONTROL Recherche de catalogue de produits] mise à jour n’a pas fourni de suggestions** : les clients qui utilisaient la fonctionnalité de recherche avancée dans l’interface utilisateur [!UICONTROL Recherche de catalogue de produits] mise à jour devaient saisir des valeurs exactes avec une orthographe correcte, car aucune suggestion ne s’affichait. Ce problème rendait difficile la localisation efficace des produits. Les suggestions s’affichent désormais comme prévu lors de la saisie de la recherche avancée. (TGT-52008)
* **Certains approbateurs n’ont pas pu afficher les produits dans [!UICONTROL Recherche de catalogue de produits]** : les clients disposant des autorisations [!UICONTROL Approbateur] n’ont pas pu afficher les produits dans [!UICONTROL Recherche de catalogue de produits], malgré l’accès d’autres utilisateurs avec des rôles identiques. Ce problème était dû à une incohérence des autorisations affectant la visibilité du catalogue. Tous les approbateurs peuvent désormais afficher les produits dans la section [!UICONTROL Recommendations] comme prévu. (TGT-53617)

+++ 

**[!UICONTROL Rapports]**

+++Afficher les détails

* **Échec du chargement des rapports pour l’audience de bureau en raison d’une erreur de nom d’audience non valide** : les clients et clientes ont rencontré une erreur GraphQL lors de la tentative d’affichage des rapports pour l’audience du processus de création d’activité. Le système a renvoyé un message « Nom d’audience non valide : XXXXX », empêchant l’accès aux données de rapports. Les rapports se chargent désormais correctement pour l’audience Desktop. (TGT-53371)
* **Le changement d’audience sur la page Rapports provoquait des erreurs dans l’interface utilisateur de Target** : les clients et clientes rencontraient des erreurs lors de la sélection de certaines audiences dans la section [!UICONTROL Rapports]. Ce problème était dû à une gestion des audiences non valide dans les appels GraphQL principaux, ce qui entraînait des erreurs inattendues et des données manquantes. Le problème a été résolu et les audiences de bureau se chargent désormais sans erreurs, même lorsqu’aucune donnée n’est disponible. (TGT-53370)
* **[!UICONTROL Vue graphique] dans la section [!UICONTROL Rapports] n’affichait pas les valeurs de[!DNL Analytics]** : les clients accédant à [!UICONTROL Vue graphique] dans la section  ont rencontré des données manquantes, toutes les valeurs apparaissant comme zéro. Ce problème était dû à une récupération incorrecte des données depuis [!UICONTROL Analytics]. La [!UICONTROL vue Graphique] affiche désormais des valeurs précises comme prévu. (TGT-52792)
+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* **Échec du clic sur « Accepter les cookies » à l’aide du [!UICONTROL Enhanced Experience Composer] (EEC) en raison d’une fonction manquante** : les clients ont signalé que la tentative d’acceptation des cookies via l’EEC entraînait une erreur de console : `handleclickAcceptAllButton is not defined`. La fonctionnalité d’acceptation des cookies fonctionne désormais comme prévu, assurant une expérience plus fluide lors de la création de l’activité dans l’interface utilisateur mise à jour. (TGT-52794)
* **La nouvelle interface utilisateur CEE n’a pas pu charger certaines pages qui étaient auparavant prises en charge dans l’interface utilisateur héritée** : les clients ont signalé que la nouvelle interface n’a pas pu charger certaines pages, qui étaient accessibles dans l’interface utilisateur héritée, malgré le code qui démolissait le iframe présent sur le site. Le processus de création d’activités mis à jour prend désormais en charge le chargement de ces pages, ce qui restaure la compatibilité des workflows de création d’activités. (TGT-53061)
* **Le compositeur d’expérience visuelle affichait un écran blanc vierge lors de la modification d’expériences** : les clients d’un certain client ont signalé que l’écran du compositeur d’expérience visuelle était vide lors de la tentative de modification d’expériences dans le compositeur d’expérience visuelle mis à jour. Ce problème affectait les activités nouvellement créées et les activités plus anciennes, empêchant la continuité du workflow. Le compositeur d’expérience visuelle se charge désormais correctement, ce qui permet aux clients de modifier les expériences sans interruption. (TGT-53547)
* **Le compositeur d’expérience visuelle s’est bloqué et a affiché un écran vide lors du chargement de certaines activités** : les clients d’un certain client ont signalé que le compositeur d’expérience visuelle n’a pas pu charger des activités spécifiques. L’éditeur d’expérience est resté bloqué sur « Application des modifications initiales » avant de se bloquer et d’afficher un écran vide. Les erreurs de console indiquent une échec de lecture des propriétés non définies. L’éditeur charge désormais les activités affectées sans erreur dans le VEC mis à jour. (TGT-53548)
* **L’effacement de toutes les valeurs de date à l’aide de la touche Retour arrière a provoqué le blocage de la page** : les clients et clientes qui planifiaient des activités dans la section [!UICONTROL Objectifs et paramètres] ont subi un blocage lors de l’utilisation de la touche Retour arrière pour effacer toutes les valeurs des champs « [!UICONTROL Date et heure spécifiées] ». Ce problème était dû à une erreur de référence nulle dans la logique de gestion des dates. La page gère désormais correctement les entrées de date vides sans blocage. (TGT-53624)
* **Aucun produit ne s’est affiché dans [!UICONTROL Recherche de catalogue de produits] en raison d’une payload non valide** : les clients accédant à la section [!UICONTROL Recommendations] dans [!UICONTROL Recherche de catalogue de produits] ont rencontré des résultats vides en raison d’une payload GraphQL non valide. Cette erreur du serveur principal a empêché le chargement correct des données du produit. Les produits s’affichent désormais comme prévu dans l’interface utilisateur mise à jour. (TGT-53630)
* **[!DNL Scene7]images ont été enregistrées avec une résolution inférieure dans le VEC mis à jour** : les clients qui modifiaient les expériences dans le VEC mis à jour ont remarqué que les URL d’image [!UICONTROL Scene7] étaient enregistrées sans paramètres de résolution, ce qui entraînait la diffusion d’images de qualité inférieure (400 × 400 au lieu des 800 × prévus). Les URL des images conservent désormais les paramètres appropriés pour garantir une résolution correcte. (TGT-52631)
* **les activités actives pouvaient toujours être modifiées dans le VEC** : les clients et clientes pouvaient accéder aux options de modification des activités actives dans le VEC mis à jour, ce qui pouvait entraîner des modifications imprévues. Ce problème a été résolu en désactivant la fonctionnalité de modification pour les activités dynamiques. Les boutons Modifier sont désormais masqués dans la liste des activités et la vue d’ensemble pour les éditeurs, tandis que les approbateurs et les autres rôles ne sont pas affectés. (TGT-53055)
* **Mise hors service de la section [!UICONTROL Échec] et [!UICONTROL Brouillon] des activités dans le VEC mis à jour** : les options [!UICONTROL Échec] et [!UICONTROL Brouillon] des activités ont été supprimées du VEC mis à jour. La nouvelle interface utilisateur ne prend plus en charge les états de brouillon. Les campagnes en échec ne sont pas stockées dans le serveur principal. Ces options ne sont plus pertinentes. Les filtres associés et les champs du serveur principal (par exemple, `uiSyncFailed`, `errorMessage`) ont également été supprimés afin de rationaliser la gestion des activités. (TGT-53150)
* **Impossible de se connecter au VEC pour une activité** : les clients et clientes qui tentaient de se connecter à leur site par le VEC ont été redirigés à plusieurs reprises vers la page de connexion, empêchant l’accès à la modification d’activité. Ce problème n’était pas reproductible en interne et pouvait être lié à la gestion des sessions côté site. Le flux de connexion a été stabilisé et les clients et clientes peuvent désormais accéder au VEC sans erreurs de redirection. (TGT-53524)
* **Lorsque vous avez appuyé deux fois sur le bouton Précédent en mode [!UICONTROL Parcourir], le compositeur d’expérience visuelle a subi un blocage** : les clients et clientes qui naviguaient en mode [!UICONTROL Parcourir] dans le compositeur d’expérience visuelle ont subi des blocages lorsqu’ils ont appuyé deux fois sur le bouton Précédent du navigateur. Ce problème entraînait le blocage de l’éditeur et nécessitait une actualisation de la page. L’éditeur gère désormais la navigation arrière de manière fiable sans blocage. (GT-53568)
* **Les activités n’ont pas pu être modifiées en raison de mappages d’emplacement non définis** : les clients ont rencontré une erreur lors de la tentative de modification des activités, due à des ID d’emplacement non définis dans la logique de `LocationMapping.behaviorTargetedActivity`. Ce problème entraînait une erreur 400 et bloquait les mises à jour d’activité. Les activités peuvent désormais être modifiées sans erreurs de validation liées à l’emplacement. (TGT-53607)
* **L’enregistrement des activités a déclenché une erreur d’entrée utilisateur non valide** : les clients et clientes ont rencontré une erreur d’entrée utilisateur non valide lors de la tentative d’enregistrement des activités après avoir apporté des modifications mineures au VEC mis à jour. L’erreur est due à des mappages d’emplacement incohérents dans la logique de validation du serveur principal. Les activités peuvent désormais être enregistrées sans déclencher d’erreurs liées à l’emplacement. (TGT-53603)

+++

### [!DNL Target Standard/Premium] 25.8.3 (21 août 2025)

Cette version comprend les mises à jour et correctifs suivants :

**[!UICONTROL Activités]**

+++Afficher les détails

* **Correction d’un problème où l’enregistrement des activités déclenchait une erreur d’entrée utilisateur non valide en raison de données de propriété incorrectes** : les clients et clientes rencontraient une erreur critique lors de la tentative d’enregistrement des activités existantes. Le message d’erreur indiquait une entrée utilisateur non valide, faisant spécifiquement référence à un contenu de nom de propriété non reconnu dans la payload JSON. Notamment, les nouvelles activités utilisant la même propriété ont été enregistrées avec succès, ce qui suggère que le problème a été isolé des données d’activité héritées. Le processus de création d’activités gère désormais correctement les configurations de propriété héritées, ce qui évite les erreurs d’entrée non valides et garantit un comportement d’enregistrement cohérent entre les activités nouvelles et existantes. (TGT-53507)
* **Correction d’un problème qui empêchait les clients d’enregistrer une activité en raison d’une erreur InvalidProperty.Json** : les clients rencontraient une erreur lorsqu’ils tentaient d’enregistrer une activité dans l’interface utilisateur mise à jour, même sans apporter de modifications. Le message d’erreur indique une structure JSON non valide : « JSON non valide. Nom de propriété « content » non reconnu. Emplacement : ligne - 1, colonne - 432. » Ce problème était dû à une propriété non reconnue dans la payload de requête et a été résolu. Les clients peuvent enregistrer les activités sans rencontrer cette erreur. (TGT-53513)
* **Correction d’un problème en raison duquel les activités planifiées affichaient incorrectement un statut [!UICONTROL Actif] jusqu’à l’actualisation de la page** : les clients ont observé que lors de la planification d’une activité pour une activation à une date et une heure futures, le statut s’affichait immédiatement comme [!UICONTROL  Actif] au lieu de [!UICONTROL Planifié]. Cela a semé la confusion, même si le message de confirmation indiquait correctement que l’activité était planifiée. Actualiser la page a corrigé l’affichage du statut. Ce problème a été résolu et les activités planifiées affichent correctement le statut Planifié sans qu’une actualisation soit nécessaire. (TGT-52937)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Afficher les détails

* **Correction d’un problème en raison duquel les clients ne pouvaient pas saisir les noms des suites de rapports pendant le processus de création d’activités** : les clients qui utilisaient [!DNL Adobe Analytics] comme source de création de rapports pendant le processus de création d’activités ne pouvaient pas saisir de noms dans la liste déroulante [!UICONTROL Suite de rapports] pour rechercher des suites de rapports spécifiques. Cela affectait les workflows pour les organisations ayant un grand nombre de suites de rapports, où le défilement manuel retardait considérablement la configuration. La liste déroulante n’était pas triée par ordre alphabétique et ne répondait pas de manière cohérente aux entrées saisies, ce qui rendait difficile la localisation de suites de rapports telles que « Office + Store - Web - Prod ». Ce problème a été résolu et les clients peuvent désormais effectuer une recherche efficace en saisissant les noms des suites de rapports. (TGT-53345)

+++

**[!UICONTROL Audiences]**

+++Afficher les détails

* **Correction d’un problème en raison duquel les audiences « Time Frame » expirées bloquaient l’enregistrement de l’activité même après la suppression** : les clients ne pouvaient pas enregistrer les activités dans l’interface utilisateur mise à jour en raison d’une erreur liée aux audiences « Time Frame » expirées. Même après la suppression de l’audience affectée, le message d’erreur persistait : « L’activité contient une audience avec une période non valide ». Ce problème se produisait car le système continuait à valider l’audience d’activité seule, même lorsqu’elle n’était plus utilisée. Le comportement était encore compliqué par des écarts de fuseau horaire. La logique de validation a été corrigée et les clients peuvent désormais enregistrer les activités sans rencontrer cette erreur. (TGT-53517)

+++

**[!UICONTROL Fragment d]expérience**

+++Afficher les détails

* **Correction d’un problème qui empêchait les clients et clientes d’insérer des fragments d’expérience à l’aide des options [!UICONTROL Insérer avant] ou [!UICONTROL Insérer après] dans l’interface utilisateur** les clients et clientes rencontraient une erreur lors de la tentative d’insertion de [!UICONTROL fragments d’expérience] dans une activité à l’aide des options « Insérer avant » ou « Insérer après » dans l’interface utilisateur mise à jour. Le message d’erreur affiché était le suivant : « Le contenu de l’offre doit contenir exactement un élément HTML ». Ce problème était spécifique à l’interface utilisateur mise à jour et ne se produisait pas dans la version précédente. Ce problème a maintenant été résolu et les clients peuvent insérer [!UICONTROL Fragments d’expérience] sans rencontrer cette erreur. (TGT-53442)

+++

**[!UICONTROL Décisions d’offre]**

+++Afficher les détails

* **Correction d’un problème qui empêchait les clients de modifier les offres de décision et de sélectionner des éléments de page spécifiques dans l’interface utilisateur mise à jour** : dans le processus de création d’activité mis à jour, les clients ne pouvaient pas modifier les offres de décision existantes ni sélectionner des éléments de page spécifiques dans le compositeur d’expérience visuelle (VEC). Les offres de décision s’affichaient incorrectement en tant qu’offres HTML et les modifications apportées lors de la modification n’ont pas été enregistrées. En outre, certaines URL régionales, telles que le site du Japon, n’ont pas pu se charger correctement dans le VEC, ce qui a bloqué la création et les mises à jour d’activités. Les offres de décision s’affichent désormais correctement, les éléments de page peuvent être sélectionnés comme prévu et les URL régionales se chargent correctement dans le VEC, ce qui restaure l’ensemble des fonctionnalités de modification. (TGT-53425)
* **Correction d’un problème en raison duquel les sélecteurs [!UICONTROL Décision d’offre] ne pouvaient pas être modifiés et changés de manière inattendue après l’enregistrement** : dans le processus de création d’activité mis à jour, les clients et clientes ne pouvaient pas modifier le sélecteur [!UICONTROL Décision d’offre] comme prévu. Les tentatives de modification du sélecteur ont échoué, et le sélecteur est revenu à une valeur incorrecte après l’enregistrement. Ce comportement a entraîné la disparition de l’offre de décision du Compositeur d’expérience visuelle (VEC), bloquant d’autres modifications. Les modifications apportées au sélecteur sont désormais correctement conservées et les offres de décision restent visibles et modifiables dans le VEC après l’enregistrement. (TGT-53433)
* **Correction d’un problème en raison duquel [!UICONTROL Décisions d’offre] disparaissait de l’activité après l’enregistrement** : [!UICONTROL Les décisions d’offre] ajoutées pendant le processus de création d’activité n’étaient pas conservées après l’enregistrement et la réouverture de l’activité. Ce problème se produisait lors de la modification de contenu dynamique et de l’insertion de [!UICONTROL Décisions d’offre]avec des sélecteurs et des propriétés spécifiques. Les [!UICONTROL décisions d’offres] persistent désormais correctement après l’enregistrement et les sélecteurs restent intacts, ce qui garantit un comportement cohérent de ciblage et de modification. (TGT-53434)

+++

**[!DNL Recommendations]**

+++Afficher les détails

* **Correction d’un problème dans [!DNL Recommendations]’interface utilisateur en raison duquel le téléchargement d’un CSV de critères personnalisés renvoyait une erreur 404** : correction d’un problème en raison duquel les clients et clientes ne pouvaient pas télécharger le CSV de critères personnalisés dans le processus de création d’activités. Le lien de téléchargement fonctionne désormais correctement, ce qui permet aux clients d’exporter des critères personnalisés comme prévu. (TGT-51966)
* **Correction d’un chargement incohérent des images dans [!UICONTROL Recherche catalogue]** : correction d’un problème en raison duquel les miniatures et les images dans [!UICONTROL  Recherche catalogue] ne se chargeaient pas de manière cohérente dans le processus de création d’activités. Les images ne s’affichaient pas, sauf si la colonne « URL de la miniature » était visible et que certaines images de produit étaient partiellement chargées ou pas du tout après des actions de navigation ou de recherche. Le comportement de chargement des images est stabilisé et les miniatures s’affichent désormais de manière fiable, quelle que soit la visibilité des colonnes ou les actions de navigation. (TGT-52778)
* **Correction d’un problème en raison duquel la modification d’une recommandation dans une expérience dupliquée avait un impact sur l’expérience d’origine** : les clients ont signalé que la modification d’une recommandation dans une expérience dupliquée modifiait involontairement l’expérience d’origine. Plus précisément, après avoir dupliqué l’expérience B dans le processus de création d’activité et modifié sa conception ou ses critères, les mêmes modifications ont été répercutées dans l’expérience B d’origine, bien qu’il s’agisse d’entités distinctes. Les expériences dupliquées conservent désormais des configurations distinctes, ce qui garantit que les modifications apportées à une expérience n’affectent pas l’expérience d’origine. (TGT-53369)
* **Correction d’un problème en raison duquel les modifications apportées à une expérience dupliquée affectaient involontairement l’expérience originale dans une activité** : les clients et clientes signalaient que lors de la duplication d’une expérience au sein d’une activité et de l’affectation d’une nouvelle audience, toute modification apportée à la conception ou aux critères de l’expérience dupliquée était également répercutée dans l’expérience originale. Ce problème se produisait même si aucune modification n’était apportée directement à la version d’origine, ce qui affectait la possibilité de créer des variations indépendantes au sein de la même activité. Le processus de création d’activités isole désormais correctement les expériences dupliquées, en veillant à ce que les modifications apportées à une expérience n’affectent pas l’expérience originale. (TGT-53361)
* **Correction d’un problème en raison duquel le [!UICONTROL Catalogue de recommandations] n’affichait pas les données complètes d’attributs de produit par intermittence** : dans l’interface utilisateur de [!DNL Recommendations] mise à jour, les clients et clientes rencontraient un problème en raison duquel certains attributs de produit, tels que le message, n’étaient pas affichés de manière cohérente dans les résultats de la [!UICONTROL Recherche catalogue], même si les données existaient dans le flux. Pour résoudre ce problème, les clients devaient reconfigurer manuellement la visibilité de la colonne pour récupérer les valeurs manquantes. La [!UICONTROL recherche catalogue] affiche désormais de manière fiable tous les attributs configurés, rendant ainsi inutile la réinitialisation manuelle des colonnes. (TGT-52769)
* **Correction d’un problème en raison duquel une [!UICONTROL Promotion front] ne pouvait pas être désactivée dans une activité active** : les tentatives de désactivation d’une [!UICONTROL Promotion front] dans une activité active n’étaient pas enregistrées. Après avoir sélectionné [!UICONTROL Modifier la promotion] et l’avoir désactivée, la promotion est restée active lors de la modification de l’activité, empêchant la mise à jour des configurations de recommandation. Les paramètres de promotion s’enregistrent désormais correctement, ce qui permet aux clients de désactiver ou de modifier les promotions dans les activités dynamiques comme prévu. (TGT-53231)
* **Correction d’un problème en raison duquel l’activation d’une [!DNL Recommendations] [!UICONTROL Promotion] sans données déclenchait un message d’erreur flou** : l’activation d’une [!UICONTROL Promotion avant] ou [!UICONTROL Promotion arrière] dans une activité [!DNL Recommendations] sans spécifier les valeurs requises générait un message générique « Erreur d’entrée non valide ». Le problème sous-jacent était l’absence d’un champ de configuration , mais le message d’erreur n’indiquait pas clairement la cause, ce qui rendait le dépannage difficile. Le processus de création d’activités génère désormais un message d’erreur clair et exploitable lorsque des champs obligatoires, tels que des `collectionId` ou des règles, sont manquants, ce qui permet aux clients d’identifier et de résoudre rapidement les problèmes de configuration. (TGT-52616)
* **Correction d’un problème qui empêchait l’affichage de la liste [!UICONTROL Product] dans la fenêtre modale [!UICONTROL Modifier] de l’onglet [!UICONTROL Recommendations]** : les clients ne pouvaient pas afficher la liste de produits filtrée lors de la modification d’une [!UICONTROL collection] ou [!UICONTROL exclusion] dans l’onglet [!UICONTROL Recommendations]. La liste devait être mise à jour en temps réel en fonction des règles appliquées, mais elle n’apparaissait pas comme prévu. Ce problème a été résolu, et la liste des produits s’affiche désormais correctement et se met à jour dynamiquement à mesure que les règles sont modifiées. (TGT-53481)
* **Correction d’un problème lié à la disposition de la boîte de dialogue Afficher les détails dans l’interface utilisateur mise à jour** : la disposition de la boîte de dialogue modale Afficher les détails dans l’interface utilisateur mise à jour a été modifiée pour améliorer la clarté et la convivialité. La boîte de dialogue comprend désormais deux onglets :
  * Onglet [!UICONTROL Détails] : affiche toutes les informations pertinentes pour l’élément sélectionné.
  * Onglet [!UICONTROL Inventaire] : affiche tous les produits filtrés par les règles de collecte et d&#39;exclusion actuelles.

  Cette amélioration permet aux clients de parcourir et de comprendre plus facilement les données spécifiques à un article et le contexte de l’inventaire dans le processus de création d’activités. (TGT-53503)

  * **Correction d’un problème en raison duquel les promotions supprimées dans les activités de recommandation réapparaissaient après l’enregistrement** : les clients signalaient que lorsque les promotions [!UICONTROL front] ou [!UICONTROL back] étaient supprimées des activités de [!DNL Recommendations] et que l’activité était enregistrée, les promotions continuaient à apparaître lors de la réouverture. Ce problème se produisait dans les environnements d’évaluation et de production et affectait le processus de création d’activité mis à jour. Le problème a été résolu. Les promotions supprimées d’une activité persistent désormais correctement après l’enregistrement. (TGT-53490)

+++

**Rapports**

+++Afficher les détails

* **Correction d’un problème en raison duquel le rapport [!UICONTROL Segments automatisés] affichait des valeurs d’audience nulles** : les clients ont signalé que les [!UICONTROL Segments automatisés] des rapports d’activité affichaient une valeur nulle pour les données d’audience, ce qui empêchait une analyse précise des performances du segment. Ce problème se produisait lors de l’accès à la section [!UICONTROL Rapports] et de la sélection de [!UICONTROL Segments automatisés], même si des données d’audience valides étaient attendues. [!UICONTROL Segments automatisés] affiche désormais correctement les valeurs d’audience, garantissant ainsi des rapports et des informations de segmentation fiables. (TGT-52793)

+++

**Applications monopages (SPA)**

+++Afficher les détails

* **Correction d’un problème en raison duquel le changement entre les modes [!UICONTROL Parcourir] et [!UICONTROL Conception] réinitialisait l’état de la SPA dans l’interface utilisateur mise à jour** : les clients ont signalé que le changement entre les modes [!UICONTROL Parcourir] et [!UICONTROL Conception] dans l’interface utilisateur mise à jour entraînait le rechargement de l’éditeur web, la réinitialisation de l’état des SPA. Ce problème interrompait les workflows et obligeait les clients à saisir à nouveau les informations. Le problème a été résolu. L’état de la SPA est désormais préservé lors du basculement entre les modes, ce qui garantit une expérience plus fluide et plus cohérente lors de la création de l’activité. (TGT-53074)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* **Correction d’un problème dans le processus de création d’activités qui bloquait la progression vers l’étape [!UICONTROL Ciblage] dans les activités AP** : correction d’un problème dans le processus de création d’activités en raison duquel les clients ne pouvaient pas passer à l’étape [!UICONTROL Ciblage] dans les activités [!UICONTROL Automated Personalization] (AP) à moins que deux emplacements ne soient ajoutés. Ce comportement différait de l’expérience précédente, où un seul emplacement avec plusieurs offres était suffisant. Cette exigence a été corrigée, ce qui permet aux clients de continuer à utiliser des configurations à emplacement unique dans le cadre de leurs workflows AP. (TGT-53426)
* **Correction d’un problème en raison duquel le nouveau processus de création d’activités ne définissait pas le paramètre fmt=png-alpha pour les images transparentes** : dans l’interface utilisateur mise à jour, les images insérées pendant le processus de création d’activités n’incluaient plus le paramètre `fmt=png-alpha` par défaut, ce qui entraînait une perte de transparence. Ce comportement était différent de celui de l’interface utilisateur précédente, qui ajoutait automatiquement le paramètre aux URL des images, préservant ainsi les arrière-plans transparents. Le processus de création d’activités applique désormais correctement le paramètre `fmt=png-alpha` aux URL d’images lorsque la transparence est requise, garantissant ainsi un rendu cohérent des ressources transparentes. (TGT-52615)
* **Correction d’un problème qui empêchait les clients et clientes de rechercher des suites de rapports dans l’interface utilisateur mise à jour** : dans l’interface utilisateur mise à jour, la liste déroulante [!UICONTROL Suites de rapports] de la section [!UICONTROL Objectifs et paramètres] ne permettait pas aux clients et clientes de saisir et de rechercher des suites de rapports spécifiques, ce qui rendait difficile leur localisation, en particulier pour les clientes et clients avec un grand nombre d’entrées. Contrairement à l’interface utilisateur précédente, la liste n’était pas triée et ne comportait pas de filtrage basé sur les entrées. Ce problème a été résolu. Les clients peuvent désormais saisir du texte pour rechercher et filtrer des suites de rapports, restaurant ainsi la fonctionnalité disponible dans l’interface utilisateur héritée. (TGT-53514)

+++

**[!UICONTROL Workspaces]**

+++Afficher les détails

* **Correction d’un problème en raison duquel un client limité à un seul espace de travail pouvait afficher les activités d’autres espaces de travail** : les clients dont l’accès était limité à un espace de travail pouvaient de manière inattendue afficher les activités de tous les espaces de travail lors de la sélection de [!UICONTROL Tous les espaces de travail] dans le processus de création d’activités. Cette visibilité entraînait un risque de modifications involontaires des activités en direct dans d’autres espaces de travail, ce qui pouvait avoir un impact sur les performances du site web. Les contrôles d’accès de Workspace ont été renforcés pour s’assurer que les clients peuvent afficher et interagir uniquement avec les activités dans l’espace de travail qui leur est affecté. (TGT-53101)
* **Correction d’un problème en raison duquel un client pouvait afficher les activités à partir du [!UICONTROL Workspace par défaut] sans y avoir accès :** un client avec un accès limité à l’espace de travail d’évaluation pouvait afficher les activités à partir du [!UICONTROL Workspace par défaut] via le processus de création d’activités. Ce comportement s’est produit malgré une configuration de serveur principal et des droits d’accès corrects. Les contrôles d’accès de Workspace ont été renforcés afin que les clients puissent afficher les activités uniquement dans l’espace de travail qui leur est affecté. (TGT-53297)

+++

### [!DNL Target Standard/Premium] 25.8.2 (14 août 2025)

Cette version comprend les correctifs et mises à jour suivants :

**[!UICONTROL Activités]**

+++Afficher les détails

* **Correction d’un problème de chargement d’activité dans l’interface utilisateur de [!DNL Target] mise à jour**: correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour où certaines activités ne se chargeaient pas lors de la tentative de modification. Ce problème entraînait le départ des clients dans un écran de chargement indéfini. Ce problème affectait plusieurs activités et il était signalé de manière incohérente parmi les clients. Grâce à ce correctif, les activités affectées se chargent désormais correctement, ce qui permet une modification transparente et réduit l’interruption des workflows d’activité. (TGT-53209)
* **Correction d’une erreur d’enregistrement dans le processus de création d’activités en raison de la validation du `optionLocalId`** : correction d’un problème dans le processus de création d’activités qui empêchait les clients d’enregistrer les modifications en raison d’une erreur de validation du serveur principal : `OptionLocalIdReferentialIntegrity.ABActivity - Invalid optionLocalIds:` ce problème se produisait lors de la modification d’éléments spécifiques dans une activité, ce qui entraînait l’échec de l’opération d’enregistrement. Le correctif garantit que les références `optionLocalId` sont désormais correctement validées, ce qui permet aux clients d’enregistrer les activités sans rencontrer cette erreur. (TGT-53293)
* **Correction du blocage dans le processus de création d’activités en raison de références d’option non valides lors du changement de page** : correction d’un problème dans le processus de création d’activités en raison duquel l’interface utilisateur se bloquait après avoir changé de page trois fois lors de la modification. Le crash a été déclenché par des références d&#39;option non valides, entraînant des erreurs de console telles que « Option avec localId &#39;7&#39; introuvable. » Grâce à cette mise à jour, les clients peuvent désormais basculer entre les pages et appliquer des modifications sans rencontrer de défaillances ou d’interruptions du système. (TGT-53295)
* **Correction d’une erreur d’enregistrement dans le processus de création d’activités due à une entrée utilisateur non valide lors de la modification d’expériences** : correction d’un problème dans le processus de création d’activités en raison duquel les clients et clientes ne pouvaient pas enregistrer les modifications apportées à une activité en raison d’une erreur d’entrée utilisateur non valide. L’erreur s’est produite lors de la modification d’expériences dans l’interface utilisateur mise à jour, empêchant la validation des mises à jour. L’activité peut désormais être enregistrée avec succès, ce qui permet aux clients de la modifier et de la publier sans interruption. (TGT-53267)
* **Correction d’un problème de chargement dans le processus de création d’activités qui bloquait la modification dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités en raison duquel les clients ne pouvaient pas modifier les activités dans l’interface utilisateur mise à jour en raison d’un écran de chargement continu. Les clients peuvent désormais ouvrir et modifier des activités sans rencontrer d’échecs de chargement. (TGT-53415)
* **Correction d’un problème d’exigence d’expérience dans le processus de création d’activités pour les activités AP dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités où les activités [!UICONTROL Automated Personalization] (AP) nécessitaient deux emplacements au lieu de deux expériences dans l’interface utilisateur mise à jour. Ce comportement bloque les cas d’utilisation où les clients configurent un emplacement unique avec plusieurs offres, qui était auparavant pris en charge. L’exigence a été corrigée pour correspondre à la fonctionnalité d’origine, ce qui permet aux clients de poursuivre les activités AP à l’aide de deux expériences, quel que soit le nombre d’emplacements. (TGT-53429)
* **Correction du comportement des champs d’élément suivis en mode Clic sur le suivi pour empêcher l’enregistrement d’une entrée et améliorer la clarté** : correction d’un problème dans le processus de création d’activité en raison duquel le champ [!UICONTROL Élément suivi] en mode [!DNL Click Track] était modifiable, mais ne conservait pas le nom saisi, ce qui entraînait une confusion chez les clients. Le champ est maintenant désactivé pour empêcher toute entrée non enregistrée et le nom des éléments sélectionnés a été clarifié pour améliorer la configuration des objectifs et la précision du suivi.** (TGT-53458)
* **Correction d’un problème dans le processus de création d’activités qui bloquait l’attribution de noms aux composants suivis dans [!UICONTROL Suivi des clics] mode** : correction d’un problème dans le processus de création d’activités en raison duquel les clients ne pouvaient pas nommer les composants suivis dans [!UICONTROL Suivi des clics] mode. Après avoir saisi un nom, le champ semblait modifiable, mais ne conservait pas l’entrée. Par défaut, les libellés génériques tels que « MON OBJECTIF DE PRINCIPAL 0 » étaient utilisés en mode d’édition. Le champ Élément suivi est maintenant désactivé et le comportement de dénomination a été clarifié afin d’améliorer la configuration des objectifs et la précision du suivi. (TGT-51396)

+++

**Fragments d’expérience (XF)**

+++Afficher les détails

* **Correction d’un problème dans le processus de création d’activités qui autorisait la modification involontaire par HTML des fragments exportés par AEM** : correction d’un problème dans le processus de création d’activités qui permettait aux clients de modifier l’HTML des [!DNL Experience Fragments] (XF) exportés depuis [!DNL Adobe Experience Manager] (AEM) dans [!DNL Target]. Ce comportement n’était pas prévu, car les fichiers XF doivent rester verrouillés pour modification une fois publiés à partir d’AEM. Le correctif garantit que l’option « Modifier HTML » n’est plus disponible pour les fragments exportés par AEM, préservant ainsi l’intégrité du contenu et la gouvernance attendue. (TGT-53286)
* **Correction d’un problème d’aperçu intermittent du contenu XF dans le processus de création d’activités dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités où le rendu du contenu XF échouait par intermittence en mode d’aperçu dans l’interface utilisateur mise à jour. Bien que le contenu ait été correctement diffusé, l’aperçu ne s’affichait pas de manière cohérente, ce qui rendait difficile la validation de la configuration de l’offre pour les clients. Les aperçus XF se chargent désormais de manière fiable, améliorant la confiance et l’efficacité lors de la configuration des activités. (TGT-53318)

+++

**Mode assurance qualité**

+++Afficher les détails

* **Correction d’un problème dans le processus de création d’activités en raison duquel les espaces de début dans les URL provoquaient des liens d’assurance qualité rompus** : correction d’un problème dans le processus de création d’activités en raison duquel les espaces de début dans l’URL de l’activité n’étaient pas correctement supprimés lors de l’enregistrement. Cela entraînait des liens d’assurance qualité non valides et un formatage incorrect dans le serveur principal. Après la mise à jour, les URL sont désormais enregistrées proprement, ce qui empêche les liens rompus et améliore la fiabilité des workflows d’assurance qualité pour les clients et les clientes. (TGT-53427)

+++

**[!UICONTROL Recommandations]**

+++Afficher les détails

* **Correction d’un problème dans l’interface utilisateur de recherche catalogue en raison duquel la recherche avancée ne pouvait pas fournir de suggestions** : correction d’un problème dans la nouvelle interface utilisateur [!UICONTROL Recherche catalogue] en raison duquel la fonctionnalité [!UICONTROL Recherche avancée] ne pouvait pas fournir de suggestions. Les utilisateurs devaient saisir des valeurs exactes avec une orthographe précise, ce qui rendait la recherche difficile et susceptible de contenir des erreurs. Grâce à ce correctif, la [!UICONTROL recherche avancée] offre désormais des suggestions pertinentes au fur et à mesure que les utilisateurs saisissent, améliorant ainsi la convivialité et réduisant le frottement lors de la localisation des produits. (TGT-52008)
* **Résolution de plusieurs problèmes d’interface utilisateur et de filtrage pour améliorer la réactivité et l’interaction des entités** : résolution de plusieurs problèmes, notamment la faible réactivité des détails des critères sur les appareils à petit écran, l’absence de résultats lors de la sélection de « Tous les groupes d’hôtes » dans le filtre Environnement et l’impossibilité d’interagir avec des entités sans nom. Ces correctifs améliorent la convivialité sur toutes les tailles d’écran, assurent un filtrage précis et permettent une interaction complète avec toutes les entités de produit, améliorant ainsi l’expérience globale pour les utilisateurs. (TGT-52992)
* **Correction d’ID de produit manquants dans la vue détaillée Recommendations lors de la création de l’activité** : correction d’un problème dans le processus de création d’activité [!DNL Recommendations] en raison duquel les ID de produit étaient manquants dans l’écran des détails du produit, ce qui rendait difficile pour les clients de copier ou de référencer les ID de produit pendant les workflows. Les identifiants de produit apparaissent désormais clairement dans la vue détaillée, ce qui améliore la visibilité et permet une gestion plus efficace des produits pour les clients. (TGT-51964)
* **Correction d’un problème dans le processus de création d’activités en raison duquel les messages de produit ne s’affichaient pas dans la vue de recommandations**: correction d’un problème dans le processus de création d’activités en raison duquel la colonne [!UICONTROL Message] de la vue de [!DNL Recommendations] n’affichait pas les données de produit, même si des messages étaient présents. Les clients devaient supprimer et ajouter à nouveau manuellement la colonne pour afficher temporairement le contenu, qui disparaissait souvent à nouveau lors du défilement ou de la recherche. Cette mise à jour restaure une visibilité cohérente des messages de produit, améliorant la navigation dans le catalogue et les workflows de révision. (TGT-52777)
* **Correction d’un problème dans le processus de création d’activités, en raison duquel la sélection de « Tous les groupes d’hôtes » n’avait renvoyé aucun résultat dans la vue de recommandations** : correction d’un problème dans le processus de création d’activités, en raison duquel la sélection de l’environnement « Tous les groupes d’hôtes » dans la vue de [!DNL Recommendations] n’avait renvoyé aucun résultat. Les clients peuvent désormais afficher comme prévu les données de produit sur tous les groupes d’hôtes, ce qui améliore la visibilité et la précision du filtrage lors de la configuration des activités. (TGT-53006)
* **Correction d’un problème dans le processus de création d’activités en raison duquel le bouton de promotion front ne persistait pas après l’enregistrement** : correction d’un problème dans le processus de création d’activités en raison duquel la désactivation du bouton de promotion front dans les paramètres d’activité ne persistait pas après l’enregistrement. Les clients qui tentaient de supprimer la promotion principale ont trouvé que le bouton (bascule) était réactivé lors de leur visite de l’activité, empêchant une personnalisation correcte. Cette mise à jour permet d’enregistrer les modifications de manière fiable, ce qui donne aux clients un contrôle total sur les paramètres de promotion. (TGT-53215)
* **Correction d’un tri incohérent par la colonne [!UICONTROL Dernière mise à jour] :** correction d’un problème dans le processus de création d’activités en raison duquel le tri du catalogue par la colonne [!UICONTROL Dernière mise à jour] générait des résultats incohérents. Les clients ne pouvaient pas organiser de manière fiable les données de produit en fonction des horodatages de mise à jour, ce qui rendait la révision et la gestion du catalogue plus difficiles. Le tri fonctionne désormais comme prévu, ce qui améliore la précision et la convivialité dans l’interface utilisateur mise à jour. (TGT-53116)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails

* **Correction des problèmes de chargement des activités et de bouton [!UICONTROL Annuler] dans le processus de création d’activités** : correction d’un problème dans le processus de création d’activités où le chargement de certaines activités échouait, empêchant les clients d’accéder aux modifications. En outre, le bouton [!UICONTROL Annuler] ne répondait pas, ce qui empêchait les clients d’arrêter le processus de chargement ou de quitter la vue d’édition. Ce correctif garantit que les activités se chargent désormais de manière fiable et que le bouton [!UICONTROL Annuler] fonctionne comme prévu, améliorant ainsi la stabilité globale et l’expérience utilisateur dans le compositeur d’expérience visuelle. (VEC)(TGT-53218)
* **Correction d’un problème de changement d’expérience dans l’interface utilisateur du VEC mise à jour qui bloquait la modification et désactivait le bouton [!UICONTROL Annuler]** : correction d’un problème dans l’interface utilisateur du VEC mise à jour où les modifications ne se chargeaient pas lors du changement d’expérience dans une activité de ciblage d’expérience (XT). Les clients ne pouvaient pas modifier les expériences au-delà de celle qu’ils avaient saisie initialement et le bouton [!UICONTROL Annuler] était manquant ou ne répondait pas. Ce correctif garantit que les modifications se chargent désormais correctement sur toutes les expériences et que le bouton [!UICONTROL Annuler] fonctionne de manière fiable, même sans l’extension d’assistance, améliorant les workflows de modification et réduisant la frustration. (TGT-53256)
* **Correction d’un problème d’écran blanc lors du changement entre plusieurs expériences dans le processus de création d’activités** : correction d’un problème en raison duquel le changement entre plusieurs expériences provoquait un écran blanc. Correction également d’un problème dans le processus de création d’activités en raison duquel les clients et clientes rencontraient un écran blanc lorsqu’ils tentaient de modifier plusieurs expériences au sein d’une activité. Ce problème se produisait après l’application des modifications à deux expériences, puis la sélection d’une troisième expérience, ce qui empêchait d’autres modifications. La mise à jour assure des transitions fluides entre les expériences, ce qui permet aux clients d’apporter des modifications sans interruption. (TGT-53266)
* **Correction d’un problème dans le VEC en raison duquel les modifications de code personnalisé n’étaient pas enregistrées de manière fiable dans les sessions de modification** : correction d’un problème en raison duquel les modifications de code personnalisé effectuées dans le compositeur d’expérience visuelle (VEC) n’étaient pas enregistrées de manière fiable en une seule tentative. Les clients ont signalé que des modifications, telles que des mises à jour de style ou des modifications d’HTML, manquaient par intermittence sur le site web et dans les URL d’assurance qualité, même après avoir utilisé les boutons [!UICONTROL  Modifier le contenu ] et [!UICONTROL Enregistrer] finaux. Cette régression a été résolue, en veillant à ce que toutes les modifications du code personnalisé persistent comme prévu entre les sessions de modification.** (TGT-53418)
* **Correction d’un `triggerViews` manquant dans l’interface utilisateur mise à jour lors de la création de l’activité** : correction d’un problème dans le processus de création d’activités où les `triggerViews` n’apparaissaient pas dans l’interface utilisateur mise à jour, même si elles étaient correctement implémentées sur la page. Cela affectait plusieurs clients et rendait difficile la validation des déclencheurs basés sur les vues lors de la configuration de l’activité. Les `TriggerViews` s’affichent désormais comme prévu, ce qui permet aux clients de terminer et de tester leurs configurations de manière fiable. (TGT-53239)
* **Correction d’un problème de chargement des vues dans le processus de création d’activités pour des pages web spécifiques dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités en raison duquel les vues ne se chargeaient pas dans l’interface utilisateur mise à jour pour des pages web spécifiques, bien qu’elles aient été correctement implémentées et visibles dans les appels de diffusion ou d’interaction. Cela affectait plusieurs clients et clientes et rendait difficile la validation du ciblage basé sur les vues. Les vues sont désormais renseignées de manière cohérente sur les pages prises en charge, ce qui améliore la fiabilité lors de la configuration des activités. (TGT-53246)
* **Correction d’un problème de chargement des vues intermittentes dans le processus de création d’activités dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités où les vues ne s’affichaient pas par intermittence dans l’interface utilisateur mise à jour lors de la modification des activités. Bien que le nom d’affichage correct était présent dans la payload du réseau, il n’était pas reconnu de manière cohérente dans l’interface, ce qui affectait la capacité des clients à configurer la personnalisation basée sur les vues. Les vues apparaissent désormais de manière fiable, ce qui facilite la configuration et les workflows de validation. (TGT-53223)
* **Correction d’un problème dans le processus de création d’activités, en raison duquel les noms des actions suivies n’étaient pas enregistrés dans l’interface utilisateur mise à jour** : correction d’un problème dans le processus de création d’activités, en raison duquel les mesures des actions suivies ne pouvaient pas être enregistrées dans l’interface utilisateur mise à jour. Après avoir nommé un élément suivi et enregistré l’activité, le nom est réinitialisé à un libellé par défaut lors de la réouverture, ce qui entraîne une confusion et perturbe la configuration des objectifs. Les actions suivies conservent désormais leurs noms attribués, ce qui permet aux clients de définir et de gérer avec précision les mesures de conversion. (TGT-53453)

+++

### [!DNL Target Standard/Premium] 25.8.1 (7 août 2025)

Cette version comprend les améliorations et correctifs suivants :

**Activités**

+++Afficher les détails

* Correction de plusieurs problèmes liés à l’interface utilisateur mise à jour, notamment des erreurs lors de la suppression de types de page en raison de l’espacement des valeurs d’entrée, d’une copie d’activité non fiable entre les espaces de travail et d’un dysfonctionnement des règles de diffusion de page dans les environnements d’assurance qualité. (TGT-52703)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les utilisateurs dotés du rôle [!UICONTROL Éditeur] pouvaient accéder aux activités en direct et tenter de les modifier, ce qui devait être limité. Les écrans de liste et d’aperçu des activités n’affichaient pas correctement les options de modification des activités en direct, ce qui entraînait des modifications involontaires potentielles. (TGT-53055)
* Correction d’un problème dans l’interface utilisateur [!UICONTROL Recherche avancée] en raison duquel la sélection des opérateurs « la valeur est présente » ou « la valeur n’est pas présente » invitait les utilisateurs à saisir un opérande, qui ne devrait pas être obligatoire pour ces conditions. (TGT-51961)
* Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les tentatives de copie des activités de l’espace de travail d’évaluation vers l’espace de travail de production échouaient systématiquement, même dans les environnements sandbox. Les clients ont rencontré divers messages d’erreur, notamment « Audience anonyme déjà utilisée par l’activité » et « Identifiant d’audience non valide », même s’ils utilisaient des configurations valides et disposaient des autorisations d’espace de travail appropriées. (TGT-52394)

+++

**Fragments d’expérience (XF)**

+++Afficher les détails

* Correction d’un problème en raison duquel le rendu du contenu du fragment d’expérience (XF) échouait dans l’aperçu du [!UICONTROL compositeur d’expérience visuelle] (VEC), bien que le contenu fonctionne correctement dans la diffusion de contenu. (TGT-53318)

+++

**Localisation**

+++Afficher les détails

* Correction d’un problème de localisation en raison duquel le bouton « Ajouter une promotion » de la section « Promotions » apparaissait non localisé dans plusieurs environnements linguistiques dans le client d’assurance qualité. (TGT-53263)

+++

**Offres**

+++Afficher les détails

* Correction d’un problème en raison duquel la modification d’une offre HTML existante via le Compositeur d’expérience visuelle (VEC) entraînait la suppression de toutes les modifications de la diffusion de contenu. Les modifications apparaissent grisées dans l’onglet de modification et ne sont pas répercutées dans les aperçus de l’assurance qualité, bien qu’elles aient été correctement appliquées dans l’interface utilisateur héritée. (TGT-52863)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les modifications d’offres HTML effectuées dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) ne persistaient pas après avoir repassé de l’onglet [!UICONTROL Ciblage] à [!UICONTROL Expériences]. (TGT-52874)
* Correction d’un problème dans l’interface utilisateur [!DNL Target] mise à jour en raison duquel l’insertion d’une offre HTML avant et d’une autre après le même sélecteur provoquait une génération d’emplacement incorrecte. Lorsque les clients sont revenus de l’onglet [!UICONTROL Ciblage] à l’onglet [!UICONTROL Expérience], un seul sélecteur a été conservé, ce qui a entraîné la perte des modifications et l’interruption de la diffusion de contenu. Ce comportement était différent de celui de l’interface utilisateur héritée, qui conservait correctement les deux modifications avec des identifiants d’emplacement distincts. (TGT-52891)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel le fait de cliquer sur une offre ajoutée dans le rail [!UICONTROL Modifications] entraînait l’affichage et la disparition intermittents du panneau [!UICONTROL Configuration] de droite, ce qui rendait difficile l’interaction avec les paramètres de l’offre. (TGT-53288)
* Correction d’un problème où les offres d’HTML ajoutées à des variations spécifiques à l’audience dans une activité n’étaient pas systématiquement enregistrées ou affichées dans la section de modification. Après avoir basculé entre les audiences lors de la modification, les offres précédemment appliquées disparaissaient parfois ou ne s’affichaient pas, ce qui perturbait la validation et retardait la préparation de l’activité. (TGT-53440)
* Correction d’un problème en raison duquel la copie d’une activité qui incluait des offres entraînait la création d’offres en double dans la nouvelle activité. Ce comportement entraînait un encombrement et une confusion inutiles, en particulier lors du déplacement d’activités entre les espaces de travail. Le correctif garantit que [!DNL Target] offres sont désormais correctement copiées dans l’espace de travail de destination sans duplication, ce qui permet de rationaliser la gestion des activités et d’améliorer l’efficacité des workflows. (TGT-53454)

+++

**Applications monopages (SPA)**

+++Afficher les détails

* Correction d’un problème dans le VEC mis à jour qui empêchait les clients et clientes d’appliquer des modifications aux vues [!UICONTROL  Application d’une seule page ] (SPA). Bien que les activités créées dans l’ancienne interface utilisateur prenaient en charge le ciblage spécifique des vues, la nouvelle interface utilisateur n’a pas réussi à détecter ou à autoriser les modifications de ces vues, et les commandes de changement de vue sont apparues désactivées. (TGT-52556)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails

* Correction d’un problème en raison duquel les modifications apportées aux expériences dans le [!UICONTROL compositeur d’expérience visuelle] n’étaient pas visibles ou s’affichaient de manière incohérente dans l’interface utilisateur. (TGT-TGT-53381)
* Correction d’un problème dans le VEC mis à jour en raison duquel la section [!UICONTROL Gérer le contenu] n’affichait pas de texte secondaire pour les miniatures d’expérience. Ce problème rendait difficile l’identification des documents pour les utilisateurs et les utilisatrices, en particulier lorsque les noms de fichier étaient longs ou tronqués. (TGT-52291)
* Correction d’une erreur en raison de laquelle les clients rencontraient des erreurs de validation incorrectes lors de la configuration des règles [!UICONTROL diffusion de page] dans les activités du VEC. En particulier, les opérateurs tels que « est égal à n’importe lequel » et « n’est égal à aucun de » déclenchent une « entrée non valide pour le type d’opérateur » lors de la saisie de valeurs de texte, même si le texte doit être pris en charge. (TGT-52629)
* Correction de plusieurs problèmes qui provoquaient un comportement incohérent dans le panneau [!UICONTROL Modifications] de l’interface utilisateur mise à jour lors de la sélection des offres à l’aide du bouton « Sélectionner une offre ». Au lieu de remplacer l’offre existante, l’interface utilisateur a ajouté un doublon et a tenté d’interagir avec l’une ou l’autre des offres, ce qui a entraîné des erreurs de console, telles que `selectorNotFound`. De plus, certaines offres n’affichent pas le bouton « Sélectionner une offre », affichant uniquement les propriétés modifiables. (TGT-53321)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les modifications de code HTML effectuées lors de la configuration de l’activité ne persistaient pas sur les pages de variation, même si elles étaient correctement enregistrées pour les populations témoins. Malgré plusieurs tentatives et la recréation de tests sans regroupements de pages, les pages de variation ne conservaient jamais les modifications, ce qui affectait la diffusion du contenu et la validation de l’assurance qualité. (TGT-53436)
* Correction d’un problème dans le VEC mis à jour en raison duquel l’opérateur « égal à n’importe lequel » dans les règles de diffusion de page n’acceptait pas les valeurs d’entrée. Lors de la configuration des paramètres client dans toutes les mbox, la sélection de cet opérateur entraînait une erreur « Entrée non valide », empêchant la création de la règle. (TGT-52623)

+++

**Workspaces**

+++Afficher les détails

* Amélioration du workflow lors de la copie d’activités entre les espaces de travail. Les activités de copie entre les espaces de travail entraînaient précédemment des erreurs de synchronisation en raison d’audiences manquantes et de propriétés non attribuées. Cette mise à jour introduit un workflow plus intelligent et plus intuitif qui garantit que les activités copiées sont correctement configurées et prêtes à être publiées. (TGT-47094)
* Correction d’un problème en raison duquel les clients ne pouvaient pas copier d’activités entre les espaces de travail en raison d’un échec de la mutation `copyActivityBatchOperations`. Les tentatives de duplication d’activités ont entraîné une erreur de serveur (500) et une payload de réponse nulle. (TGT-52405)
* Correction d’un problème en raison duquel les activités ne se synchronisaient pas lorsque les offres référencées dans la configuration n’étaient pas accessibles dans l’espace de travail sélectionné. Cela provoquait des erreurs de publication et laissait les activités dans un état d’échec. (TGT-52535)
* Correction de plusieurs problèmes lors de la copie d’activités entre des espaces de travail dans l’interface utilisateur [!DNL Target] mise à jour. Les clients rencontrent des erreurs liées à l’accès à l’audience, en particulier avec les activités en direct, et une validation de privilèges incorrecte, même lorsque l’utilisateur disposait de rôles « [!UICONTROL Approbateur] » dans les espaces de travail source et de destination. (TGT-53002)
* Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel la copie d’activités dans le même espace de travail dupliquait inutilement les offres et audiences associées. (TGT-53457)
* Correction d’un problème en raison duquel les audiences ad hoc (anonymes) n’étaient pas correctement copiées entre les espaces de travail non par défaut ou entre les espaces de travail non par défaut et les espaces de travail par défaut. Alors que les mises à jour précédentes assuraient une duplication appropriée pour les scénarios par défaut et d’espace de travail identique, cette amélioration se concentrait sur la conservation des configurations d’audience combinées qui s’étendent sur plusieurs espaces de travail. Le correctif garantit un comportement d’audience cohérent et un ciblage précis sur toutes les transitions d’espace de travail. (TGT-53268)

+++

### [!DNL Target Standard/Premium] 25.7.4 (1er août 2025)

Cette version résout les problèmes récents, principalement causés par des personnalisations client complexes, et comprend les correctifs et améliorations suivants :

**Activités**

+++Afficher les détails

* Correction d’un problème en raison duquel un client rencontrait une erreur « Entrée utilisateur non valide » lors de la tentative d’enregistrement d’une activité dynamique, même sans apporter de modifications. La réponse GraphQL indique un problème de doublon de LocalId. (TGT-53329 ET TGT-53373 ET TGT-53195)
* Correction d’un problème qui empêchait la création d’une expérience de redirection dans le VEC mis à jour. L’URL de redirection a été ignorée et la page d’origine a été affichée à la place. (TGT-53306)

+++

**Localisation**

+++Afficher les détails

* Correction d’un problème de localisation dans la fenêtre modale [!UICONTROL Créer des critères], lors de la sélection de l’option « entre les valeurs suivantes » dans la liste déroulante [!UICONTROL Choisir une règle de prix], la chaîne « vers » était délocalisée dans la section [!UICONTROL Règles d’inclusion]. (TGT-49754)
* Correction d’un problème de localisation entraînant la localisation incorrecte de la chaîne « [!UICONTROL Tous les groupes d’hôtes] » dans la liste déroulante [!UICONTROL Environnement] de l’assistant Création de flux. (TGT-46737)

+++

**QA**

+++Afficher les détails

* Correction d’un problème en raison duquel l’environnement d’assurance qualité ne chargeait pas les données sur plusieurs onglets, ce qui rendait l’interface inutilisable. (TGT-53377)
* Correction d’un problème qui empêchait la création d’une activité dans l’environnement d’assurance qualité. Le processus a été redirigé vers la page [!UICONTROL Activités] au lieu d’être terminé avec succès. (TGT-53328)

+++

**Recommandations**

+++Afficher les détails

* Correction d’un problème en raison duquel le survol de l’opérande « deep-learning » lors de la création d’une collection dans [!DNL Recommendations] entraînait le blocage de la page. (TGT-53305)
* Correction d’un problème en raison duquel les suggestions de filtre dans [!UICONTROL Recherche catalogue] dans l’interface utilisateur mise à jour étaient inexactes. (TGT-52007)
* Correction d’un problème dans l’interface utilisateur de [!DNL Recommendations] en raison duquel le filtre Opérandes s’affichait lors de l’utilisation des opérateurs « valeur présente » ou « valeur non présente », bien qu’il doive être masqué. (TGT-53012)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails

* Correction d’un problème en raison duquel un utilisateur cliquait sur [!UICONTROL Gérer le contenu] puis sur [!UICONTROL Terminé] lors de la modification d’une activité Automated Personalization (AP), la page devenait vierge et ne répondait plus. (TGT-53047 et TGT-52993)
* Correction d’un problème en raison duquel la page se bloquait en sélectionnant la mesure de conversion [!UICONTROL Affichage d’une mbox] sous [!UICONTROL Objectifs et paramètres]. (TGT-53346, TGT-53343, et TGT-53348)
* Correction d’un problème en raison duquel la fonction [!UICONTROL Rediriger vers l’URL] ne fonctionnait pas comme prévu, aucune redirection ne se produisant même avec des URL valides. (TGT-53307)

+++

**Workspaces**

+++Afficher les détails

* Correction d’un problème lors de la copie d’activités entre les espaces de travail provoquant des entrées « Copie d’audience » en double et des conflits d’ID. Les audiences sont désormais copiées avec des ID uniques, un contexte d’espace de travail et une gestion récursive pour les audiences combinées (jusqu’à 5 niveaux). (TGT-53081)
* Correction d’un problème en raison duquel l’espace de travail est défini sur « [!UICONTROL Tous les espaces de travail] ». La copie d’une activité qui existe déjà dans l’espace de travail par défaut entraîne une erreur incorrecte :

  « Au moins une propriété doit être incluse pour les espaces de travail non par défaut. »

  Comme la copie se trouve dans l’espace de travail par défaut, aucune propriété ne doit être requise. Toute tentative d’ajout d’une propriété et d’enregistrement entraîne une seconde erreur :

  « Entrée Utilisateur Non Valide »

+++

### [!DNL Target Standard/Premium] 25.7.3 (vendredi 24 juillet 2025)

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, cette version comprend les correctifs et mises à jour suivants :

**Activités**

+++Afficher les détails

* Correction d’un problème en raison duquel la méthode `buildViews` de la classe builder définissait incorrectement le `viewMaxLocalId` sur le nombre total de vues, plutôt que sur la `viewLocalId` la plus élevée attribuée. (TGT-53207)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les offres supprimées dans les activités [!UICONTROL Automated Personalization] (AP) s’affichaient sous la forme `Deleted option with ID: X` au lieu de leurs noms d’origine (par exemple, `Offer Name [Deleted]` comme indiqué dans l’interface utilisateur héritée). Ce correctif restaure l’étiquetage significatif pour les offres supprimées, améliorant ainsi la clarté et rendant les rapports plus précis et plus conviviaux. (TGT-52921)
* Correction d’un problème en raison duquel certaines activités migrées du serveur frontal [!DNL Target] vers [!DNL Target] Central présentaient des configurations de mesures incohérentes en raison d’un bug de synchronisation précédemment corrigé. Plus précisément, les activités qui utilisaient à l’origine une mesure de conversion et qui ont ensuite été mises à jour vers une mesure basée sur les analyses conservaient des valeurs obsolètes dans les champs `primaryMetricType` et `successCriteria`. (TGT-52643)
* Correction d’un problème où l’intégralité du contenu d’une page d’aperçu de l’assurance qualité devenait modifiable en raison de l’inclusion involontaire de l’attribut `contentEditable` dans les modifications d’HTML. Cela permettait aux utilisateurs de cliquer et de modifier n’importe quel texte de la page, ce qui pouvait entraîner des problèmes de mise en page et une confusion lors de l’assurance qualité. (TGT-53247)
* Correction d’un problème en raison duquel le déplacement d’une modification de [!DNL Page Load] vers une [!UICONTROL Vue] entraînait la duplication de la modification, le maintien dans [!UICONTROL Chargement de page] tout en apparaissant également dans la [!UICONTROL Vue]. En outre, la suppression de la modification de la [!UICONTROL Vue] la supprimerait incorrectement de la [!UICONTROL Chargement de la page]. (TGT-53270)

+++

**API**

+++Afficher les détails

* Correction d’un problème dans la couche de persistance du serveur principal en raison duquel les options supprimées étaient correctement stockées, mais non accessibles via les points d’entrée de l’API existants. Par conséquent, les applications frontales n’ont pas pu récupérer de noms significatifs pour les options supprimées, ce qui a eu un impact sur les vues de rapports historiques. Ce correctif garantit que les données des options supprimées conservées peuvent désormais être correctement affichées dans l’interface utilisateur. (TGT-52973)
* Mise en œuvre d’un nouveau point d’entrée de migration pour prendre en charge le transfert des options d’activité supprimées des activités basées sur JCR vers [!DNL Target] Central. Cette fonctionnalité permet un suivi et des rapports cohérents entre les systèmes. Cette fonctionnalité garantit que les options supprimées sont préservées et synchronisées sur le serveur frontal et le serveur principal [!DNL Target], ce qui améliore les rapports historiques et l’intégrité des données. (TGT-53217)
* Ajout d’un nouveau point d’entrée d’API qui permet aux utilisateurs de restaurer des options d’activité supprimées précédemment d’une base de données secondaire. Cette fonctionnalité tire parti de l’infrastructure existante fournie par les classes `RemovedCampaignElements` et `RemovedOptionInfo`, assurant ainsi une réintégration transparente des options supprimées dans les activités actives. (TGT-52903)
* Correction d’un problème en raison duquel les activités [!DNL Recommendations] contenant des noms de mesures de plus de 25 caractères ne pouvaient pas être ouvertes ni modifiées en raison des limitations de l’API. Ce correctif garantit la compatibilité avec les noms de mesures dépassant la limite de caractères et restaure un accès complet aux activités affectées. (TGT-52839)

+++

**Compositeur d’expérience d’après les formulaires**

+++Afficher les détails

* Correction d’un problème dans le [!UICONTROL compositeur d’expérience d’après les formulaires] en raison duquel l’éditeur se bloquait après avoir cliqué sur l’icône **[!UICONTROL Gérer le contenu]** ( ![icône Gérer le contenu](/help/main/assets/icons/Experience.svg) ) lors de la création ou de la modification d’une activité [!UICONTROL Automated Personalization] (AP). (TGT-53047)

+++

**Recommandations**

+++Afficher les détails

* Correction d’un problème qui empêchait [!UICONTROL Recherche catalogue] de charger des résultats supplémentaires lors du défilement vers le bas de la liste, restaurant ainsi un comportement cohérent avec l’interface utilisateur héritée. (TGT-53088)
* Correction d’un problème qui bloquait la suppression d’éléments de la boîte de dialogue [!UICONTROL Détails des critères]. (TGT-53245)
* Correction d’un problème qui empêchait l’ouverture ou l’interaction avec des produits sans nom. Ce problème se produisait lors de la sélection d’environnements qui renvoyaient des résultats sans nom, empêchant l’accès aux détails du produit. (TGT-53007)
* Correction d’un problème en raison duquel la page [!UICONTROL Recherche catalogue] se bloquait et affichait un écran vide lors de la sélection de certains produits. (TGT-53087)
* Correction d’un problème en raison duquel les utilisateurs ne pouvaient pas modifier l’activité de [!DNL Recommendation] site_cart_z1 dans l’interface utilisateur de [!DNL Target]. La tentative d’ouverture de l’activité a déclenché une erreur sur la page [!UICONTROL Aperçu], bloquant l’accès à l’éditeur. (TGT-53221)

+++

**Création de rapports**

+++Afficher les détails

* Correction d’un problème en raison duquel le champ sandbox de la base de données des activités n’était pas effacé lors du changement de la source de création de rapports de [!DNL Customer Journey Analytics] ou [!DNL Analytics] à [!DNL Target]. Auparavant, l’interface utilisateur envoyait correctement la sandbox : null, mais le serveur principal ignorait cette valeur, laissant en place des données de sandbox obsolètes. Le serveur principal efface désormais correctement le champ sandbox lorsque la valeur null est reçue. (TGT-52798)
* Nouvelle implémentation de la couche de persistance des options supprimées dans le serveur principal de Target pour prendre en charge les rapports historiques précis dans les activités  (AP). Auparavant, lorsqu’une option était supprimée, son nom était perdu, ce qui rendait difficile l’interprétation des données de performances antérieures.

  **Améliorations clés** :

  * Les options supprimées sont désormais suivies à l’aide des infrastructures `RemovedCampaignElements` et `RemovedOptionInfo` existantes.
  * Lorsqu’une option est supprimée d’une activité AP, ses métadonnées (par exemple, l’identifiant et le nom) sont conservées.
  * L’interface utilisateur de création de rapports peut désormais afficher le nom de l’option d’origine (par exemple, `Option Name [Deleted]`) avec les mesures historiques, ce qui améliore la clarté et la convivialité.

  Cette mise à jour garantit la cohérence et la pertinence des rapports, même après la suppression d’options d’une activité. (TGT-52986)

+++

**Compositeur d’expérience visuelle**

+++Afficher les détails

* Correction d’un problème dans le VEC en raison duquel l’application d’une modification à une vue provoquait une duplication et déclenchait une erreur « Entrée utilisateur non valide ». (TGT-52886)
* Correction d’un problème lié à la fonctionnalité [!UICONTROL Annuler] des options [!UICONTROL Insérer avant] et [!UICONTROL Insérer après] lors de la configuration des offres d’images dans le compositeur d’expérience visuelle.

  Auparavant, l’annulation d’une action [!UICONTROL Insérer avant] ou [!UICONTROL Insérer après] sur des offres d’image entraînait un comportement incohérent ou un échec à annuler correctement la modification, en particulier dans les activités créées dans l’interface utilisateur de [!DNL Target] héritée. Ce problème a été résolu afin de garantir que les actions d’annulation fonctionnent désormais de manière fiable pour ces modifications. (TGT-52809)

* Correction d’un problème en raison duquel l’attribut `contentEditable` était involontairement défini sur true et conservé dans le contenu HTML enregistré. Cette mise à jour garantit une sortie HTML plus épurée et attendue, sans comportement de modification involontaire. (TGT-52319)
* Pour éviter la perte permanente d’options supprimées et garantir un comportement cohérent entre les services, la fonctionnalité de suppression réversible a été mise en œuvre pour les options de l’interface utilisateur et les microservices associés.

  **Modifications clés** :

  * Les options ne sont plus supprimées définitivement. Au lieu de cela, ils sont marqués d’un nouvel indicateur deleted : true dans l’objet XML des paramètres.
  * Cet indicateur est utilisé uniquement par l’interface utilisateur [!DNL Target] mise à jour pour exclure les options supprimées du rendu et empêcher leur envoi aux services Edge.
  * Les options supprimées restent une partie de la payload de l’activité lors des modifications, ce qui permet d’assurer la traçabilité tout en évitant la diffusion d’options inexistantes aux clients.

  Cette mise à jour améliore l’intégrité des données et s’aligne sur les bonnes pratiques de gestion des suppressions dans les systèmes distribués. (TGT-52726)

+++

**Workspaces**

+++Afficher les détails

* Correction d’un problème lors de la copie d’une activité d’un espace de travail non par défaut vers un espace de travail par défaut ou entre des espaces de travail non par défaut. Les offres sont désormais dupliquées avec un suivi et un nommage améliorés afin d’éviter les conflits.

  **Améliorations clés** :
  * Les offres sont recréées dans l’espace de travail de destination avec des identifiants et des métadonnées mis à jour.
  * Les offres copiées sont renommées au format : « Copie du nom de l’offre » plus un nombre aléatoire ou un horodatage pour garantir l’unicité.
  * Le système met à jour les états des offres et des activités pour refléter les nouveaux identifiants.
  * Cette fonctionnalité empêche les erreurs dues à plusieurs noms de « Copie d’offre » identiques lors d’actions de copie répétées.
  * Les offres peuvent ne pas apparaître immédiatement dans la liste des offres de l’espace de travail de destination, mais sont traitées et affichées de manière appropriée.

  Cette mise à jour améliore la fiabilité et la traçabilité lors de la gestion des offres sur plusieurs espaces de travail. (TGT-53080)

+++

### [!DNL Target Standard/Premium] 25.7.2 (samedi 18 juillet 2025)

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, cette version comprend les correctifs et mises à jour suivants :

**Activités**

+++Afficher les détails

* Ajout d’un avertissement de confirmation supplémentaire lors de l’annulation des modifications d’activité avec des modifications non enregistrées : « Voulez-vous vraiment enregistrer cette activité ? Si vous n’enregistrez pas, toutes vos modifications seront perdues. » Ce message permet d’éviter les pertes de données accidentelles. (TGT-52865)
* Restauration de la fonctionnalité héritée du curseur [!UICONTROL  Priorité ] dans [!UICONTROL  Objectifs et paramètres ], ce qui permet aux clients de saisir directement une valeur numérique, comme pris en charge dans l’interface utilisateur héritée. (TGT-53185 et TGT-53219)

+++

**Audiences**

+++Afficher les détails

* Correction d’un problème qui empêchait l’enregistrement ou la modification des activités contenant des audiences personnalisées. Les clients ont rencontré le message d’erreur « Nous ne pouvons pas traiter votre demande. Contactez [!DNL Adobe Client Care] si le problème persiste. » lorsque vous tentez d’enregistrer les modifications apportées à certaines activités , ou même de les enregistrer sans modification. (TGT-53189)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Afficher les détails

* Correction d’un problème en raison duquel les clients affichaient les rapports d’activités spécifiques sur la page [!UICONTROL Objectifs et paramètres], le lien [!UICONTROL Afficher dans Analytics] pointait incorrectement vers l’environnement d’assurance qualité plutôt que vers l’environnement de production. (TGT-53163)

+++

**[!UICONTROL Expériences] et [!UICONTROL Offres]**

+++Afficher les détails

* Correction d’un problème où l’appel de `triggerView` via du code personnalisé provoquait une boucle infinie. (TGT-52885)
* Correction d’un problème qui entraînait des incohérences entre les `LocalIds` définis pour les activités et ceux `LocalIds` dans les définitions des expériences. (TGT-52669)
* Correction d’un problème en raison duquel les noms des mesures étaient manquants sur la page [!UICONTROL Aperçu] de l’activité, qui affichait uniquement « Offre » au lieu du nom correct de la mesure. (TGT-53054)

+++

**Compositeur d’expérience d’après les formulaires**

+++Afficher les détails

* Correction d’un problème dans le [!UICONTROL Compositeur d’expérience d’après les formulaires] qui empêchait l’enregistrement des activités et déclenchait le message d’erreur : « Impossible de lire les propriétés de l’objet non défini (lecture d’un « mappage ») ». (TGT-53145)

+++

**Recommandations**

+++Afficher les détails

* Correction d’un problème en raison duquel un clic sur un produit dans la [!UICONTROL Recherche catalogue] affichait l’erreur « Échec de la récupération des détails du produit » et ouvrait une boîte de dialogue modale sans option de fermeture. (TGT-53082)
* Correction d’un problème en raison duquel les [recommandations en tant qu’offres](/help/main/c-recommendations/recommendations-as-an-offer.md) dans les activités [!UICONTROL Test A/B] n’étaient pas correctement mises à jour lors de la modification de collections ou de promotions. (TGT-52884)
* Correction d’un problème dans l’environnement de production en raison duquel le fait de cliquer sur une entité dans l’interface utilisateur mise à jour affichait l’erreur : « Échec de la récupération des détails du produit. Contactez [!DNL Adobe Client Care] si ce problème persiste. » (TGT-53071)

+++

**Rapports**

+++Afficher les détails

* Correction d’un problème en raison duquel l’enregistrement des détails de commande dans un fichier CSV générait un fichier vide. (TGT-52225)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* Correction d’un problème sur la page [!UICONTROL Objectifs et paramètres] où les sélecteurs utilisés dans plusieurs expériences n’étaient pas systématiquement mis en surbrillance comme sélectionnés. (TGT-53062)
* Correction d’un problème qui empêchait la modification des activités et déclenchait le message d’erreur : « Impossible de lire les propriétés de l’objet non défini (lecture d’un « mappage ») ». (TGT-53161)

+++

**Workspaces**

+++Afficher les détails

* Amélioration de la gestion des offres ad hoc lors du changement d’espace de travail.
  * Lorsque vous passez de l’espace de travail par défaut à un espace de travail non par défaut (ou entre des espaces de travail non par défaut), les offres ad hoc sont désormais correctement copiées. Lors de l’initialisation, le contexte de l’espace de travail est mis à jour et un nouvel identifiant est attribué à l’offre afin d’en assurer l’unicité.
  * Aucune modification ne se produit lorsque vous restez dans le même espace de travail. (TGT-53079)
* Correction d’un problème qui empêchait les clients de [copier des activités entre différents espaces de travail](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6). (TGT-52753 et TGT-47094)
* Correction d’un problème lors de la modification des propriétés entre les espaces de travail.
  * Lorsque vous passez de l’espace de travail par défaut à un espace de travail autre que celui par défaut, si la propriété actuelle existe dans l’espace de travail de destination, la propriété est conservée.
  * Si la liste [!UICONTROL Propriétés] affiche un avertissement (susceptible d’indiquer que certaines propriétés peuvent ne pas être compatibles) et que le client clique sur [!UICONTROL Ajouter] ou [!UICONTROL Supprimer] puis sur [!UICONTROL Enregistrer], toutes les propriétés qui ne se trouvent pas dans l’espace de travail de destination sont supprimées. Si le client clique sur [!UICONTROL Annuler], toutes les propriétés restent, même si elles n’existent pas dans l’espace de travail de destination. (TGT-47094)
  * Si vous restez dans le même espace de travail ou passez d’un espace de travail non par défaut à l’espace par défaut ou à un autre espace de travail, tout reste tel quel. (TGT-53078)
* Mise à jour de la logique de validation des entités pour respecter le contexte d’espace de travail original de l’activité. Les entités telles que [!UICONTROL Fragments d’expérience] (XF) sont désormais validées en fonction de l’espace de travail dans lequel l’activité a été créée à l’origine. Par exemple, si un fichier XF existe dans l’espace de travail par défaut et que l’activité est copiée de l’espace de travail X vers l’espace de travail Y, la validation est toujours effectuée tant que le fichier XF est valide dans l’espace de travail d’origine (par défaut). (TGT-53196)
* Amélioration de la prise en charge de la copie d’audiences ad hoc lors de la duplication des activités.
  * Les audiences ad hoc, y compris les mesures, les rapports, les pages et les types d’activités uniquement, sont désormais automatiquement copiées dans les scénarios suivants :
    * Lors de la copie d’une activité de l’espace de travail par défaut vers un espace de travail non par défaut.
    * Lors de la copie d’une activité dans le même espace de travail. (TGT-53197)

+++

### [!DNL Target Standard/Premium] 25.7.1 (samedi 11 juillet 2025)

En raison de problèmes récents identifiés, principalement liés à des personnalisations client complexes, cette version comprend les correctifs et mises à jour suivants :

**Activités**

+++Afficher les détails

* Correction d’un problème où l’URL [!UICONTROL AQ d’activité] incluait un paramètre de requête inutile : `at_preview_evaluate_as_true_audience_ids`. (TGT-52907)
* Correction d’un problème en raison duquel les URL de prévisualisation incluaient incorrectement des audiences supplémentaires au-delà de celle explicitement saisie par l’utilisateur. Ce comportement a été corrigé afin de garantir que seule l’audience spécifiée est appliquée lors de la génération d’un lien d’assurance qualité ou de prévisualisation. (TGT-52912)
* Correction d’un problème qui empêchait les utilisateurs de créer des activités [!UICONTROL Ciblage automatique] (AT) si l’option [!UICONTROL  Affectation automatique] (AA) était sélectionnée en premier lors de la configuration de l’affectation du trafic. Ce problème entraînait une erreur de validation du serveur principal et empêchait l’enregistrement de l’activité. (TGT-53096)

+++

**Audiences**

+++Afficher les détails

* Correction d’un problème en raison duquel les utilisateurs dotés du rôle [!UICONTROL Approbateur] ne pouvaient pas ajouter ou enregistrer les améliorations d’audience d’activité uniquement. Toute tentative de ce type a provoqué une erreur 403 Interdit, indiquant que le privilège « [editor] » était requis, même si l’utilisateur disposait des autorisations suffisantes pour approuver et gérer les activités. (TGT-52984)
* Correction d’un problème en raison duquel une audience spécifique à une activité était supprimée à l’aide de l’option [!UICONTROL Supprimer l’affinement d’audience], l’audience n’apparaissait plus dans la liste des audiences pour être resélectionnée au sein de la même activité. Ce comportement empêchait les utilisateurs d’ajouter à nouveau la même audience, sauf si elle était recréée à partir de zéro. (TGT-52979)
* Correction d’un problème en raison duquel les améliorations d’audience d’activité unique disparaissaient de l’interface utilisateur immédiatement après avoir été supprimées d’un emplacement, avant même que l’activité ne soit enregistrée. Ce comportement est en contradiction avec la fonctionnalité attendue et le guide d’info-bulle, qui indique : « Toutes les audiences inutilisées de cette bibliothèque seront supprimées une fois l’activité enregistrée ». (TGT-52982)
* Correction d’un problème lors de la tentative d’affectation d’une audience autre que [!UICONTROL Tous les visiteurs] à une activité. Lors de l’enregistrement, le message d’erreur suivant s’affichait : « Nous ne pouvons pas terminer votre demande. Contactez l’[!UICONTROL Assistance clientèle ] si le problème persiste. » (TGT-53008)
* Correction d’un problème qui empêchait l’enregistrement d’une activité après la création et l’affectation d’une nouvelle audience dans l’éditeur d’activités. Le message d’erreur affiché était le suivant : « Nous ne pouvons pas traiter votre demande. Contactez l’[!UICONTROL Assistance clientèle ] si le problème persiste. » (TGT-52977)

+++

**[!UICONTROL Analytics for Target] (A4T)**

+++Afficher les détails

* Correction d’un problème en raison duquel la copie d’une activité existante et la modification de la source de création de rapports en [!DNL Adobe Analytics] (A4T) entraînaient une erreur « Entrée utilisateur non valide ». L’erreur a été déclenchée lorsque certaines actions de mesures incompatibles avec les rapports [!DNL Analytics], telles que `restart_same_experience`, `restart_random_experience` et `restart_new_experience`, ont été conservées dans l’activité d’origine. (TGT-52900)
* Correction d’un problème qui empêchait les clients de créer ou d’enregistrer une activité lors de la sélection de [!DNL Adobe Analytics] (A4T) comme source de création de rapports dans l’étape [!UICONTROL Objectifs et paramètres]. Le problème s’est produit spécifiquement lors de la sélection d’une mesure [!UICONTROL Événement personnalisé] (par exemple, « Événement personnalisé 16 »), ce qui a entraîné l’erreur suivante : « Entrée utilisateur non valide ». (TGT-52910)
* Correction d’un problème en raison duquel le fait de cliquer sur le lien « [!UICONTROL  Afficher dans Analytics ] » redirigeait les utilisateurs vers la page d’accueil plutôt que vers le tableau de bord [!DNL Analytics] prévu. (TGT-53092 et TGT-53093)
  <!-- * Fixed an issue when cloning an existing activity and changing the reporting source from [!DNL Target] to [!DNL Adobe Analytics], users encounter a "400 - Invalid User Input" error, preventing the activity from being saved. (TGT-52875)-->
* Correction d’un problème lors de l’affichage d’une activité de [!DNL Recommendations] dans l’interface utilisateur mise à jour [!UICONTROL Présentation]. La section [!UICONTROL Objectifs et paramètres] ne se charge pas lorsque [!DNL Adobe Analytics] (A4T) est sélectionné comme source de création de rapports. Le message d’erreur suivant s’affichait : « Un problème est survenu. Nous ne pouvons pas traiter votre demande. Si le problème persiste, contactez l’assistance clientèle Adobe. » (TGT-52999)

+++

**[!UICONTROL Expériences] et [!UICONTROL Offres]**

+++Afficher les détails
<!-- * Fixed an issue where using the [!UICONTROL Manage Content] feature in [!UICONTROL Automated Personalization] (AP) activities caused the page to crash and remain blank. This issue occurred after clicking [!UICONTROL Done] in the content manager, particularly in activities created or edited in the updated UI. (TGT-53047)-->
* Correction d’un problème en raison duquel la fonction [!UICONTROL Gérer le contenu] ne validait pas correctement l’état d’un emplacement après la suppression de toutes les options de contenu. Ce problème peut entraîner un comportement incohérent ou des erreurs lors de la tentative d’enregistrement ou de poursuite de la configuration de l’activité. (TGT-52801)
* Correction d’un problème en raison duquel les utilisateurs rencontraient une erreur « Entrée non valide » lors de l’ajout d’une nouvelle page et de la suppression d’éléments spécifiques dans différentes expériences. L’erreur est déclenchée par la génération de `LocalIds` en double lors de la manipulation des éléments, en particulier lors du passage d’une expérience à l’autre et de la modification des structures de page partagées. (TGT-52720)
* Correction d’un problème en raison duquel l’utilisation de la fonctionnalité [!UICONTROL Générer une offre ad hoc] entraînait l’affichage d’emplacements indéfinis dans le panneau [!UICONTROL Gérer le contenu]. (TGT-53076 et TGT-53070)
* Clarification du comportement vis-à-vis du client selon lequel les modifications apportées à l’aide d’une offre HTML peuvent sembler manquantes lors de la navigation entre l’étape [!UICONTROL Ciblage] et [!UICONTROL Expériences]. Pour ce client ou cette cliente, le site web affecté a généré dynamiquement plusieurs sélecteurs DOM qui ont changé à chaque chargement de page. Par conséquent, le sélecteur utilisé à l’origine pour la modification est introuvable lorsque l’éditeur est rouvert, ce qui fait que la modification semble manquante ou non valide. Ce scénario fonctionne comme prévu. Pour que les modifications soient conservées visuellement dans l’éditeur, il est recommandé aux clients d’utiliser des sélecteurs stables et cohérents, qui ne changent pas lors des rechargements de page. (TGT-52874)
* Correction d’un problème où la tentative de suppression ou de désactivation d’une offre qui faisait partie d’une expérience exclue déclenchait une erreur « Entrée utilisateur non valide ». Ce problème se produisait même si l’offre n’était pas activement utilisée dans les expériences incluses. (TGT-52917)

+++

**Compositeur d’expérience d’après les formulaires**

+++Afficher les détails

* Correction d’un problème dans les activités basées sur des formulaires où la duplication d’une expérience et la modification du code personnalisé dans l’une des expériences dupliquées appliquaient involontairement ces modifications à toutes les expériences dupliquées. Chaque expérience conserve désormais son propre code personnalisé indépendamment après duplication. (TGT-51600)

+++

**Localisation**

+++Afficher les détails

* Mise à jour des chaînes de localisation dans la nouvelle interface utilisateur pour le français (fr_FR), l’allemand (de_DE), l’italien (it_IT), le coréen (ko_KO) et le chinois simplifié (zh_CN).

+++

**[!DNL Recommendations]**

+++Afficher les détails

* Ajout d’un nouveau flux de [!DNL Recommendations] [statut](/help/main/c-recommendations/c-products/feeds.md#status) : [!UICONTROL Échec de l’importation partielle]. (KB-2215)
* Correction d’un problème affectant le workflow de création d’activité lors de l’ajout de [!DNL Recommendations] avec des [!UICONTROL promotions]. Lorsque l’utilisateur sélectionne « [!UICONTROL Promouvoir par attribut] » et ajoute une règle de filtrage (par exemple, [!UICONTROL Correspondance de paramètres]), le type de règle et les valeurs d’opérande sélectionnés ne sont pas conservés après l’enregistrement et la modification de l’activité. Lors de la réouverture, le type de règle de filtrage change de manière inattendue et les valeurs d’opérande sont manquantes. (TGT-53059)
* Correction d’un problème dans l’interface utilisateur de [!DNL Recommendations] en raison duquel toute promotion créée avec une seule règle était incorrectement interprétée et affichée comme un type de promotion « Liste d’éléments », quelle que soit la logique de la règle. (TGT-53063)
* Correction d’un problème lors de l’utilisation de l’interface utilisateur [!UICONTROL Aperçu]mise à jour, le bouton « [!UICONTROL Télécharger les données de recommandations] » était manquant pour les activités [!UICONTROL Ciblage d’expérience] (XT) qui incluent des [!DNL Recommendations]. (TGT-52730 et TGT-52756)
* Auparavant, l’interface utilisateur de Recommendations affichait uniquement le nombre d’entités importées à partir d’un flux. Cependant, le format du message principal inclut à la fois le nombre d’entités importées et le nombre total d’entités au format : `# of entities imported / # of total entities`. En raison de cette incohérence, les utilisateurs ne voyaient que la première valeur (nombre importé) dans l’interface utilisateur, ce qui entraînait une confusion. L’interface utilisateur affiche désormais les deux nombres. (TGT-53073)
* Correction d’un problème en raison duquel les clients ne pouvaient pas enregistrer de règle de filtrage lors de la configuration d’une promotion « [!UICONTROL Promouvoir par attribut] » dans une activité A/B basée sur des formulaires avec des recommandations. Après avoir enregistré et rouvert l’activité, la règle de filtrage était manquante et l’activité n’a pas pu être enregistrée correctement. (TGT-53057)

  +++

**Rapports**

+++Afficher les détails

* Correction d’un problème en raison duquel la sélection de « [!UICONTROL Exporter les détails de la commande au format CSV] » dans la page [!UICONTROL Rapports] entraînait le téléchargement d’un fichier vide. Ce problème se produisait même lorsque des données de commande valides étaient présentes dans l’activité. (TGT-52225)
* Correction d’un problème lors de la tentative d’enregistrement d’une activité après la création et l’affectation d’une nouvelle audience de rapport. Le message d’erreur renvoyé était le suivant : « Accès refusé. Pour effectuer cette opération, tous les privilèges suivants sont requis : [éditeur]. » Ce problème se produisait malgré l’accès de l’utilisateur au niveau de l’approbateur. (TGT-53103)

+++

**[!UICONTROL Compositeur d’expérience visuelle] (VEC)**

+++Afficher les détails

* Correction d’un problème où l’application d’une modification à une vue entraînait la duplication de la vue et le renvoi d’une erreur « Entrée utilisateur non valide » par l’activité. Ce correctif garantit que les modifications d’affichage sont appliquées correctement sans déclencher de duplication ou d’erreurs de validation. (TGT-52886)
* Correction d’un problème en raison duquel les modifications du code personnalisé s’affichaient incorrectement pour une expérience incorrecte. Plus précisément, les modifications destinées à une expérience ont été présentées dans une expérience différente, ce qui a entraîné une confusion et une mauvaise configuration potentielle des activités en direct. (TGT-52776)
* Correction d’un problème qui empêchait la modification ou l’enregistrement des modifications de code personnalisé dans la nouvelle interface utilisateur du VEC. Plus précisément :

  * Après modification d’un bloc de code personnalisé et enregistrement, les modifications n’étaient pas répercutées dans l’interface utilisateur ou dans l’aperçu de l’assurance qualité.
  * Dans certains cas, les modifications ne pouvaient pas être supprimées à moins que l’activité ne soit fermée et rouverte.
  * Pour pallier ce problème, les utilisateurs devaient copier le code, supprimer la modification et le recréer manuellement avec le contenu mis à jour. (TGT-53072)

* Correction d’un problème en raison duquel la modification et l’enregistrement du code personnalisé provoquaient l’absence de réponse du panneau [!UICONTROL Modifications]. (TGT-53075)
* Correction d’un problème en raison duquel les modifications apportées au code personnalisé dans les variantes d’expériences étaient involontairement répercutées dans l’expérience [!UICONTROL Contrôle]. Cela a provoqué des changements inattendus dans le comportement de la diffusion. L’expérience [!UICONTROL Control] reste désormais isolée des modifications de code personnalisé apportées à d’autres expériences. (TGT-52413)
* Correction d’un problème où les modifications apportées à une expérience (par exemple, l’expérience B) étaient involontairement dupliquées vers une autre expérience (expérience A) si l’utilisateur cliquait sur la deuxième expérience avant que l’éditeur ne soit complètement chargé. Ce comportement peut également entraîner la perte des modifications si l’expérience sélectionnée initialement n’a pas été modifiée. (TGT-52597)
* Correction d’un problème en raison duquel les modifications apportées à l’étape [!UICONTROL Modifications] de création de l’activité n’étaient pas enregistrées de manière cohérente. Dans certains cas, une fois toutes les étapes effectuées et que vous avez cliqué sur [!UICONTROL Enregistrer], le script personnalisé ajouté à la section [!UICONTROL Modifications] n’est pas reflété sur le site actif, bien qu’aucune erreur visible n’ait été rencontrée pendant le processus d’enregistrement. (TGT-52661)
* Correction d’un problème en raison duquel les modifications du code personnalisé n’étaient pas enregistrées correctement et étaient involontairement mises en miroir sur plusieurs expériences au sein de la même activité. En outre, les utilisateurs rencontraient des problèmes d’accès lors de l’ouverture ou de l’actualisation de certaines activités, ce qui entraînait des écrans vierges. Ces problèmes ont été résolus afin d’assurer une modification d’activité stable et une isolation d’expérience précise. (TGT-52594)
* Correction d’un problème en raison duquel les utilisateurs ne pouvaient pas accéder à une autre URL en [!UICONTROL mode de navigation]. Cela empêchait les testeurs et les éditeurs de valider ou de prévisualiser d’autres pages dans la même session d’activité. (TGT-53052)
* Correction d’un problème où plusieurs instances [!UICONTROL Compositeur d’expérience visuelle] (VEC) s’ouvraient simultanément lors de la création de l’activité. Ce problème se produisait lorsque les utilisateurs désactivaient le [!UICONTROL Enhanced Experience Composer] (EEC) et supprimaient la barre oblique de fin de l’URL du site web à l’étape [!UICONTROL Diffusion de page]. (TGT-52782)
* Correction d’un problème en raison duquel la liste déroulante de la mesure [!UICONTROL Chiffre d’affaires] de l’étape [!UICONTROL Objectifs et paramètres] était incorrectement définie par défaut sur [!UICONTROL Chiffre d’affaires par visite] (RPVISIT), même après la sélection d’une autre mesure par l’utilisateur.  Le problème s’est produit lors de la réduction et du développement du panneau de configuration des mesures, entraînant la réinitialisation de la valeur sélectionnée précédemment. (TGT-52811 et TGT-52878)
* Correction de plusieurs problèmes dans le workflow de création d’activités liés à la dénomination des offres et à la traduction de contenu dans les activités  (AP) et [!UICONTROL Multivariate Testing] (MVT) :

  Principales questions abordées :

  * La création de plusieurs offres HTML portant le même nom (par exemple, « Expérience ») a déclenché une erreur « Les noms d’offres en double ne sont pas autorisés », mais l’interface utilisateur n’indiquait pas clairement quelles offres étaient à l’origine du conflit.
  * Le changement de nom des offres par le biais du panneau de droite a mis à jour le nom dans l’interface utilisateur, mais la modification n’a pas été répercutée dans les onglets [!UICONTROL Gérer le contenu] ou [!UICONTROL Offres], ce qui entraîne des erreurs de validation persistantes.
  * Dans les activités MVT, bien que l’erreur de nom en double n’ait pas persisté après le changement de nom, l’interface utilisateur ne reflétait toujours pas les noms d’offre mis à jour de manière cohérente dans les onglets. (TGT-52933)

  +++

### [!DNL Target Standard/Premium] 25.6.4 (samedi 27 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Ajout de l’option [!UICONTROL Réorganiser] à l’interface utilisateur [!UICONTROL Compositeur d’expérience visuelle] (VEC) mise à jour afin de s’aligner sur les fonctionnalités disponibles dans l’ancien VEC. (TGT-46957 et TGT-52876)
* Correction d’un problème en raison duquel les modifications apportées aux variantes d’expériences (par exemple, l’expérience B) dans une activité [!UICONTROL Test A/B] n’étaient pas conservées. Après avoir basculé entre les expériences, les modifications apportées à la variante disparaissaient. Ce problème n’a pas affecté l’expérience de contrôle. (TGT-52664)
* Correction d’un problème en raison duquel certains clients ne pouvaient pas créer ou enregistrer d’activités, tandis que d’autres pouvaient effectuer les mêmes actions sans problème. Le problème était incohérent entre les comptes.(TGT-52842)
* Correction d’un problème en raison duquel, dans le VEC mis à jour, les utilisateurs ne pouvaient pas déplacer les modifications vers l’[!UICONTROL événement de chargement de page], une fonctionnalité qui existait dans l’interface utilisateur héritée. (TGT-52617)
* Correction d’un problème dans l’interface utilisateur mise à jour en raison duquel les événements [!UICONTROL chargement de page] n’étaient pas visibles dans les [!DNL Target] lors de la création de modifications ; les mises à jour étaient appliquées uniquement aux vues. (TGT-52604)
* Correction d’un problème qui empêchait l’affichage correct de certaines modifications d’activité dans le VEC mis à jour. (TGT-52818)
* Correction d’une exception de pointeur nul qui se produisait lors de la récupération des données de rapport pour les activités  (AP). (TGT-52362)
* Correction d’un problème qui empêchait l’affichage des détails au niveau de l’offre dans le fichier .CSV pour les activités  (AP). (TGT-52675)
* Correction d’un problème lors de l’application de modifications dans le VEC mis à jour, les modifications apparaissent initialement correctement, y compris le [!UICONTROL fragment d’expérience] attendu. Cependant, lors du changement d’expérience ou de la réalisation de modifications supplémentaires, certaines modifications ne s’appliquent pas en raison de problèmes de sélecteur. (TGT-52679)
* Correction d’un problème en raison duquel, lorsqu’une nouvelle activité était créée en clonant une activité existante, les liens d’assurance qualité de l’activité clonée conservaient incorrectement les URL de page de l’activité d’origine. (TGT-52775)
* Correction d’un problème qui empêchait involontairement [!UICONTROL la prise de décision sur l’appareil] d’être disponible dans le VEC mis à jour. (TGT-52371)
* Correction d’un problème qui empêchait la modification d’une activité de [!DNL Recommendations] de produit. Lors de la tentative d’accès au VEC via l’interface utilisateur de Target, une erreur s’est produite sur la page [!UICONTROL Aperçu], empêchant toute modification. (TGT-52823)
* Correction d’un problème qui empêchait l’enregistrement d’une activité [!DNL Recommendations] lorsque les noms d’expérience dépassaient 50 caractères. (TGT-52619)
* Correction d’un problème en raison duquel les clients et clientes ne pouvaient pas enregistrer une activité Recommendations après avoir modifié les critères dans la nouvelle interface utilisateur. Le problème semble être lié aux autorisations et n’affecte pas tous les utilisateurs ayant des rôles similaires. (TGT-52816)
* Correction d’un problème en raison duquel les utilisateurs dotés du rôle [!UICONTROL Éditeur] ne pouvaient pas modifier une activité [!DNL Recommendations]. Toute tentative de modification de la conception et d’enregistrement de l’activité a provoqué une erreur 403 Interdit, indiquant que le privilège « [editor] » était requis, même si l’utilisateur jouait déjà ce rôle dans l’espace de travail approprié. (TGT-52836)

### [!DNL Target Standard/Premium] 25.6.3 (samedi 20 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel la copie d’une activité d’un espace de travail à un autre déclenchait des erreurs telles que « ne doit pas être nul » ou « Un problème est survenu ». (TGT-52474)
* Correction d’un problème en raison duquel les rapports [!UICONTROL Segments automatisés] et [!UICONTROL Attributs importants] n’étaient pas générés pour certaines activités. (TGT-52904)
* Correction d’un problème dans le VEC mis à jour en raison duquel la gestion de contenu par défaut dans les activités  (AP) ne correspondait pas à l’interface utilisateur héritée. Le système ajoute désormais automatiquement un `optionGroup` par défaut nommé « Contenu par défaut » avec des `optionGroupLocalId = 0` lorsqu’aucun groupe n’est explicitement ajouté. Ce groupe comprend l’option par défaut (par exemple, `optionLocalId: 0`). Si le contenu par défaut est supprimé, le groupe d&#39;options correspondant est également supprimé. (TGT-52651)
* Correction d’un problème dans les activités [!UICONTROL Test multivarié] (MVT) en raison duquel la réutilisation d’un `experienceLocalId` provenant d’expériences supprimées précédemment était incorrectement interdite. (TGT-52672)
* Correction d’un problème qui empêchait la copie ou la modification des activités contenant un fragment d’expérience. Cela a déclenché l’erreur : `Enum "AemOfferType" cannot represent value: "html"`. (TGT-52635)
* Correction d’un problème en raison duquel les URL des emplacements d’activité n’affichaient pas les paramètres de requête en raison de caractères non valides, tels que des barres obliques (/). (TNT52845)
* Amélioration du message d’erreur de validation pour les mises à jour d’activité [!DNL A/B Test] via l’API principale. Lorsque des noms d’emplacement en double sont présents, le message indique désormais clairement : « Les noms en double ne sont pas autorisés » pour `locations.selectors`. (TGT-52589)
* Correction d’une erreur qui se produisait lors de la mise à jour d’une activité active [!UICONTROL Recommendations] en raison d’une propriété non reconnue dans la payload de la requête. Le système gère désormais correctement le fichier JSON « non valide ». Erreur « Nom de propriété non reconnu ». (TGT-52723)
* Correction d’un problème qui empêchait la création d’une conception [!DNL Recommendations]. Cliquer sur [!UICONTROL Créer] a déclenché le message : « Au moins 1 variable d’entité doit être utilisée dans le script. » (TGT-52395 et TGT-52899)
* Correction d’un problème en raison duquel le réenregistrement d’une conception [!DNL Recommendations] sans modifications était bloqué. (TGT-52879)
* Correction d’une erreur de validation du serveur principal qui provoquait une erreur « 400 Bad Request » lors de l’enregistrement d’une activité [!UICONTROL Recommendations]. (TGT-52716)
* Correction d’un problème dans le [!UICONTROL Compositeur d’expérience d’après les formulaires] en raison duquel le survol d’une mbox avec des caractères spéciaux dans la liste déroulante [!UICONTROL Emplacement] entraînait le vidage de l’éditeur et le déclenchement d’un événement « Échec de l’exécution de la requête querySelector » sur « Élément ». s’affiche. (TGT-52717)
* Amélioration de la précision de l’état du flux avec un nouvel indicateur « PARTIALLY_IMPORTED ». Auparavant, les flux étaient marqués comme « succès » même lorsque toutes les lignes d’un fichier n’étaient pas importées, ce qui était trompeur. (TGT-52892)
* Correction d’une erreur en raison de laquelle, après la migration vers AP V2, certains appels API à `/admin/rest/ui/v1/campaigns` renvoyaient des erreurs côté client (HTTP 4xx). (TGT-52721)

### [!DNL Target Standard/Premium] 25.6.2 (vendredi 12 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Ajout d’un [nouvel article FAQ](/help/main/c-intro/updated-ui-faq.md) pour répondre aux questions courantes sur l’interface utilisateur [!DNL Target] mise à jour et le [!UICONTROL compositeur d’expérience visuelle] (VEC).
* Correction d’un problème en raison duquel la règle « [!UICONTROL URL - ne contient pas] » dans [!UICONTROL Diffusion de page] ne fonctionnait pas, ce qui permettait l’affichage de contenu même lorsqu’il aurait dû être bloqué. (TGT-52754)
* Correction d’un problème en raison duquel [!UICONTROL Diffusion de page] affichait incorrectement le message d’erreur : « Les URL de page en double ne sont pas autorisées. (TGT-52765)
* Correction d’un problème où les audiences pour les URL [!UICONTROL Diffusion de page] contenant des fragments d’expérience étaient créées avec le signe # ajouté par erreur. (TGT-52786)
* Correction d’un problème en raison duquel la copie d’une activité et la modification des paramètres sur la page [!UICONTROL Objectifs et paramètres] provoquaient une défaillance de l’interface utilisateur de [!DNL Target]. (TGT-52797)
* Correction d’un problème dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour qui autorisait incorrectement la redirection d’une page supplémentaire dans une activité [!UICONTROL Test A/B] vers la même URL. (TGT-51838)
* Correction d’un problème en raison duquel les modifications apportées aux mesures sur la page [!UICONTROL Objectifs et paramètres] n’étaient pas enregistrées lors de la modification d’une activité. (TGT-52799)
* Correction d’un problème en raison duquel l’ajout d’une nouvelle expérience alors que l’éditeur web était toujours en cours de chargement entraînait la duplication du contenu de la nouvelle expérience depuis l’expérience précédente. (TGT-51397)
* Restauration de la possibilité d’utiliser du code personnalisé en dehors de la balise `<head>`, une fonctionnalité auparavant disponible dans l’ancienne interface utilisateur de Target. (TGT-52304 et TGT-52300)
* Suppression de la validation inutile lors de la sélection de l’espace de travail par défaut lors de la création de l’activité. La validation obligatoire des propriétés ne s’applique plus à l’espace de travail par défaut, mais reste en place pour les espaces de travail non par défaut. (TGT-52449)
* Correction d’un problème dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour en raison duquel les appels `triggerView()` n’étaient pas détectés. (TGT-52575)
* Correction d’un problème dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour qui empêchait les utilisateurs d’ajouter des modifications aux vues [!UICONTROL application d’une seule page] (SPA). (TGT-52556)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour qui empêchait les clients d’afficher les détails de l’offre. (TGT-52607)
* Correction d’un problème en raison duquel les mises à jour apportées aux offres dans la [!UICONTROL bibliothèque des offres] n’étaient pas reflétées dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour. (TGT-52637)
* Correction d’un problème qui empêchait l’affichage correct de la section Offres lors de la création d’une activité. (TGT-52773)
* Ajout d’une validation pour s’assurer que toutes les `optionLocalIds` référencées dans `optionGroups` existent dans le tableau d’options. Les références non valides sont automatiquement supprimées lors de la création de l’activité. (TGT-52687)
* Correction d’un problème où les groupes de génération de rapports et les exclusions n’étaient pas conservés après l’ajout d’une nouvelle offre. (TGT-52728)
* Correction d’un problème en raison duquel les activités sans bouton [!UICONTROL AQ d’activité] affichaient un sélecteur d’options vide. (TGT-52733)
* Correction d’un problème en raison duquel les liens d’assurance qualité ne rendaient pas correctement le contenu. (TGT-52718)
* Correction d’un problème en raison duquel le remplacement d’un élément par un fragment d’expérience ne reflétait pas correctement les modifications dans l’environnement d’assurance qualité. (TGT-52762)
* Correction d’un problème dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour qui provoquait une erreur « Entrée non valide » lorsque les utilisateurs tentaient d’ajouter des fragments d’expérience. (TGT-52701)
* Correction d’un problème en raison duquel la boîte de dialogue modale « Modifier l’audience » apparaissait vide lors de la modification du ciblage des audiences dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC) mis à jour. (TGT-52749)
* Ajout d&#39;un message pour informer les utilisateurs qu&#39;une entité n&#39;est pas accessible dans l&#39;espace de travail sélectionné. (TGT-52767)
* Correction d’un problème en raison duquel l’interface utilisateur ne permettait pas l’affectation manuelle d’un identifiant d’environnement à un critère. Il s’agit plutôt de l’ID par défaut pour le groupe d’hôtes [!UICONTROL Recherche catalogue de produits]. Ce correctif garantit que les modifications des critères sont désormais appliquées à tous les environnements, et pas seulement à la valeur par défaut. (TGT-52817)
* Correction d’un problème en raison duquel l’option « [!UICONTROL Télécharger les données de recommandations] » était manquante pour les activités [!UICONTROL Ciblage d’expérience] (XT) avec des recommandations. (TGT-52730 et TGT-52756)

### [!DNL Target Standard/Premium] 25.6.1 (samedi 6 juin 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel les liens d’assurance qualité ne fournissaient pas l’expérience appropriée pour l’activité associée. (TGT-52163 et TGT-52790)
* Correction d’un problème en raison duquel les liens d’assurance qualité ne comportaient pas l’identifiant d’audience associé. (TGT-52722)
* Correction d’un problème pour s’assurer que les expériences ne sont diffusées que lorsque les conditions de l’URL de diffusion de page configurées sont précisément remplies. (TGT-52696)
* Correction d’un problème qui empêchait les clients de créer un modèle de conception [!DNL Recommendations]. La tentative de création d’un modèle a déclenché l’erreur : « Au moins 1 variable d’entité doit être utilisée dans le script. » (TGT-52395)
* Correction d’un problème qui empêchait l’enregistrement des conceptions [!DNL Recommendations] à l’aide de tableaux Velocity. Le message d’erreur « Il doit y avoir au moins 1 variable d’entité utilisée dans le script » a été déclenché de manière incorrecte. (TGT-52734)
* Correction d’un problème en raison duquel les modifications n’étaient pas accessibles dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) lorsque le chargement de la page échouait pour les pages web internes. (TGT-52488 ET TGT-52470)
* Correction d’un problème en raison duquel le panneau [!UICONTROL Modifications] n’était pas visible sur les plus petites tailles d’écran dans le VEC. (TGT-52470)
* Correction d’un problème dans le VEC mis à jour en raison duquel le passage du mode [!UICONTROL Parcourir] au mode [!UICONTROL Conception] provoquait une erreur de console et empêchait toute autre interaction. (TGT-52532)
* Correction d’un problème dans le VEC en raison duquel cliquer sur certains éléments développait involontairement leur taille. (TGT-52497)
* Correction d’un problème en raison duquel certains éléments de page ne se chargeaient pas ou n’étaient pas reconnus dans le VEC, ce qui empêchait des interactions telles que la sélection de boutons ou de bannières et perturbait le suivi précis des événements dans les activités. (TGT-52663)
* Correction d’un problème qui empêchait les clients de supprimer des offres dans les activités  (AP). (TGT-52690)
* Correction d’un problème qui provoquait un comportement incohérent de qualification des activités dans les activités multi-pages. (TGT-52694)
* Correction d’un problème en raison duquel la page [!UICONTROL Aperçu] de l’activité affichait une URL non valide pour l’[!UICONTROL Emplacement de l’activité]. (TGT-52695)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour qui entraînait l’affichage de doublons pour les emplacements d’activités. (TGT-52693)
* Correction d’un problème qui déclenchait une erreur `getAudiencesV3`, empêchant les clients de modifier ou de copier des activités. (TGT-52709)
* Correction d’un problème qui provoquait une erreur de payload non valide lors de l’ajout d’offres [!UICONTROL Fragments d’expérience] ou HTML à une activité. (TGT-52779 et TGT-52773)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les fragments ’expérience ne s’affichaient pas correctement en raison d’une erreur d’entrée non valide. (TGT-52701)
* Correction d’un problème qui empêchait les clients et clientes de modifier les activités dans le [!UICONTROL Compositeur d’expérience d’après les formulaires] en raison d’une erreur utilisateur non valide. (TGT-52470)
* Correction d’un problème de localisation en langue coréenne en raison duquel les traductions précédentes utilisaient des caractères en dehors du plan multilingue de base. La traduction mise à jour utilise des caractères appropriés qui transmettent précisément la signification prévue. (TGT-52508 et TGT-52509)
* Correction d’un problème de localisation en coréen en raison duquel la traduction de la « date » était incohérente lors de la sélection des dates de début et de fin d’une activité. (TGT-52510)

### [!DNL Target Standard/Premium] 25.5.4 (29 mai 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème qui empêchait l’ajout ou la modification d’URL en mode AQ. (TGT-51941)
* Ajout d’un paramètre de trafic en mode QA sous [!UICONTROL Rapports] > [!UICONTROL Paramètres des rapports] ( ![icône Paramètres des rapports](/help/main/assets/icons/Setting.svg) ) pour s’aligner sur les fonctionnalités de l’ancienne interface utilisateur de [!DNL Target]. (TGT-52228 et TGT-52329)
* Correction d’un problème en raison duquel l’activité basée sur les formulaires générait des liens d’assurance qualité incorrects. L’URL/emplacement de l’activité incluait un « 1 » involontaire à la fin, qui a maintenant été supprimé pour garantir une liaison précise. (TGT-52355 et TGT-52358)
* Correction d’un problème en raison duquel l’activité basée sur les formulaires générait des liens d’assurance qualité incorrects. L’URL d’activité incluait une `http://pid-ppc` involontaire au début de l’URL, qui a été supprimée pour garantir une liaison précise. (TGT-52557)
* Correction d’un problème en raison duquel [!DNL Target] générait des liens d’assurance qualité non valides pour les activités basées sur des formulaires. (TGT-52528 et TGT-52603)
* Correction d’un problème en raison duquel l’enregistrement d’une activité modifiée semblait être en cours de traitement, mais n’était jamais terminé, et aucun message d’erreur ne s’affichait dans [!DNL Target]. (TGT-52461)
* Correction d’un problème en raison duquel le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour ne détectait pas automatiquement la valeur `at_property`. (TGT-52347)
* Correction d’un problème en raison duquel deux modifications étaient enregistrées alors qu’une seule était attendue après le changement entre les modes [!UICONTROL Parcourir] et [!UICONTROL Conception] dans le VEC lors de l’interaction avec un élément de formulaire. (TGT-52455)
* Correction d’un problème qui empêchait la sélection du paramètre [!UICONTROL Clic sur un élément] dans le VEC mis à jour en raison d’une erreur indiquant que le sélecteur n’était pas valide, était déjà utilisé ou n’était pas visible. (TGT-52467)
* Correction d’un problème en raison duquel l’ajout d’une zone [!UICONTROL Offre de recommandation] dans le VEC mis à jour entraînait l’affichage de zones en double (fantômes). Le passage entre les expériences A et B a permis d’ajouter plusieurs zones fantômes. (TGT-52505 et TGT-52519)
* Correction d’un problème dans l’interface utilisateur de [!DNL Target] mise à jour en raison duquel les modifications apportées à une offre HTML via le menu [!UICONTROL Offre] n’étaient pas reflétées dans l’activité associée, et vice versa. Ce comportement correspond désormais à l’interface utilisateur héritée, où les mises à jour se synchronisent correctement entre le menu [!UICONTROL Offre] et l’activité. (TGT-52540 et TGT-52541)
* Correction d’un problème en raison duquel les mises à jour récentes d’[!UICONTROL Fragments d’expérience] dans la [!UICONTROL bibliothèque des offres] n’étaient pas prises en compte lors de leur utilisation dans une activité. (TGT-52659)
* Correction d’un problème de localisation dans la traduction chinoise simplifiée d’un message de confirmation. La version précédente ne comportait pas de guillemets autour du nom de l’emplacement et utilisait un langage informel, contrairement au guide de style du client. La traduction mise à jour utilise désormais une ponctuation correcte et un ton formel. (TGT-52364)

### [!DNL Target Standard/Premium] 25.5.3 (22 mai 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel la fonction de recherche par nom de la liste [!UICONTROL Activités] ne fonctionnait pas correctement avec les requêtes à plusieurs mots. (TGT-52529)
* Correction d’un problème qui empêchait l’exclusion d’expériences des activités  (AP). (TGT-52383)
* Correction d’un problème en raison duquel l’option « [!UICONTROL Contient] » était absente des [!UICONTROL Règles de filtrage] lors de la gestion du contenu dans les activités AP. (TGT-52384)
* Correction d’une incohérence dans les rapports des activités  (AP), spécifiquement liée à la manière dont les offres par défaut sont suivies et signalées à l’aide de valeurs `optionLocalId` du système interne de [!DNL Target].
* Correction d’un problème en raison duquel les liens d’assurance qualité ne fournissaient pas l’expérience d’activité prévue. (TGT-52163)
* Correction d’un problème en raison duquel les utilisateurs disposant d’autorisations [!UICONTROL Approbateur] étaient incorrectement bloqués lors de la modification des activités dynamiques, et recevaient un message d’erreur « Accès refusé ». (TGT-52416)
* Correction d’un problème en raison duquel les ajustements d’audience ne s’affichaient pas pour certaines activités dans l’interface utilisateur de [!DNL Target] mise à jour. (TGT-52057)
* Correction d’un problème en raison duquel les affinements d’audience et les audiences d’activité étaient inversés dans l’interface utilisateur mise à jour. (TGT-52158)
* Correction d’un problème en raison duquel la génération d’offres ad hoc entraînait des offres en double. (TGT-51938)
* Correction d’un problème qui bloquait les mises à jour d’offre et affichait incorrectement une erreur « Utilisateur non valide ». (TGT-52361)
* Correction d’un problème qui empêchait l’enregistrement des activités existantes et déclenchait une erreur « Entrée utilisateur non valide ». (TGT-52422)
* Correction d’un problème qui bloquait la modification des offres HTML existantes et déclenchait une erreur « Entrée utilisateur non valide » lors de l’enregistrement, même si aucune modification de code n’était apportée. (TGT-52351)
* Correction d’un problème qui empêchait [!DNL Target] de reconnaître le caractère « # » dans l’URL d’un site web. (TGT-52093)
* Correction d’un problème qui empêchait la modification des activités [!DNL Recommendations] pour ajouter ou mettre à jour des promotions, ce qui provoquait des échecs d’enregistrement et des promotions en double. (TGT-52343)
* Correction d’un problème qui empêchait les modifications apportées aux critères ou aux conceptions dans les activités [!DNL Recommendations], ce qui entraînait une erreur « JSON non valide : nom de propriété non reconnu ». (TGT-52375)
* Correction d’un problème en raison duquel les critères de séquence ne s’affichaient pas correctement dans le [!UICONTROL Compositeur d’expérience visuelle] (VEC) pour les activités [!DNL Recommendations]. (TGT-52435)
* Correction d’un problème en raison duquel les vues n’étaient pas correctement identifiées sur les pages SPA lors de l’utilisation du [!DNL Adobe Experience Platform Web SDK] . (TGT-52106)
* Correction d’un problème en raison duquel les détails d’ODS (On-Device Decisioning) n’étaient pas enregistrés correctement, bien qu’ils aient été inclus dans la payload de l’opération par lots. (TGT-52406)
* Ajout d’un champ `audienceMetadata` aux activités, permettant sa lecture et sa mise à jour lors de la modification. (TGT-51004)
* Ajout d’un message d’erreur pour alerter les utilisateurs lorsqu’une période d’audience n’est pas valide. (TGT52522)
* Mise à jour de la structure des activités pour prendre en charge les audiences en double de différents types. (TGT-51200)

<!--
### [!DNL Adobe Target] [!DNL AI Assistant] release (May 16, 2025)

We are thrilled to announce the launch of the [!DNL AI Assistant] in [!DNL Adobe Target]! This powerful user interface feature is designed to help you navigate and understand [!DNL Target] concepts with ease. Available across multiple products in [!DNL Adobe Experience Cloud], including [!DNL Target], [!DNL AI Assistant] is here to revolutionize your experience.

[!DNL AI Assistant] in [!UICONTROL Target] is a conversational tool that you can use to accelerate your workflows with [!DNL Experience Platform] applications and services. Use [!DNL AI Assistant] to boost your overall productivity and amplify your understanding of product knowledge

In [!DNL Target], the first phase of [!DNL AI Assistant] provides invaluable product knowledge grounded in [!DNL Experience League] documentation. Whether you are setting up a profile script, troubleshooting errors, or considering an upgrade to the AEP Web SDK, [!DNL AI Assistant] has you covered.

For more information, see [Coworker skills for Adobe Target](/help/main/c-intro/coworker-skills.md).
-->

### [!DNL Target Standard/Premium] 25.5.2 (8 mai 2025)

Cette version comprend les correctifs et mises à jour suivants :

* [!DNL Target] utilisateurs disposant de droits [!UICONTROL Administrateur de produit] et [!UICONTROL Administrateur système] peuvent désormais modifier tous les paramètres des pages [!UICONTROL Administration], quel que soit leur rôle dans [!DNL Target]. Les utilisateurs ne disposant pas de ces autorisations ont accès en lecture seule à ces paramètres. Cette mise à jour garantit un contrôle d’accès plus strict sur les [paramètres d’administration](/help/main/administrating-target/administrating-target.md). (TGT-48179)
* Correction d’un problème de mise en cache qui empêchait l’enregistrement de l’activité [Préférences du site](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings). (TGT-52213)
* Correction d’un problème en raison duquel les clients ne pouvaient pas activer la sélection par ID et classe dans la section [!UICONTROL Préférences du site] après le chargement du site dans le VEC. Le paramètre [!UICONTROL Préférences du site] est automatiquement rétabli à désactivé même après activation. (TGT-52207)
* Correction d’un problème en raison duquel le [!UICONTROL compositeur d’expérience visuelle] (VEC) n’affichait pas la page correcte lorsque les URL [diffusion de page](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#settings) se terminaient par une barre oblique (/). (TGT-52237)
* Correction d’un problème qui empêchait la suppression des modifications de code personnalisé lors du changement d’expériences. (TGT-52240)
* Correction d’un problème en raison duquel les modifications d’HTML dans le VEC recouvraient des éléments de page existants. (TGT-52265)
* Correction d’un problème qui empêchait la modification du code personnalisé dans le VEC mis à jour en raison du fait que le code personnalisé existant n’était pas visible dans l’éditeur. (TGT-52272)
* Correction d’un problème entraînant l’affichage d’un message d’erreur « Les noms en double ne sont pas autorisés » lors de l’enregistrement d’une activité Recommendations. (TGT-52318)
* Correction d’un problème dans le VEC mis à jour qui empêchait les clients et clientes de modifier des éléments de texte ou de supprimer des objets conteneur. (TGT-52348)
* Correction d’un problème qui empêchait l’affichage correct des [!DNL Customer Journey Analytics] sur une page d’activité [!UICONTROL Aperçu]. (TGT-52359)
* Correction d’un problème qui empêchait les groupes de génération de rapports de persister dans les activités  (AP). (TGT-52368)
* Correction d’un problème qui empêchait l’enregistrement des activités qui incluaient Offer Decisioning. (TGT-52390)
* Correction d’un problème où l’offre par défaut était sélectionnée, mais où le contenu d’autres offres était affiché dans les activités  (AP) et [!UICONTROL Test multivarié] (MVT). (TGT-52372)
* Correction de la logique des autorisations GET pour vérifier avec OU entre l’accès complet à l’organisation et l’accès spécifique organisation + utilisateur. (TGT-52374)
* Correction d’un problème en raison duquel les noms d’audience ne s’affichaient pas après la sélection d’une audience pour [!UICONTROL Contenu géré] et [!UICONTROL Audiences du reporting], même si l’option [!UICONTROL Afficher uniquement la sélection] était activée. (TGT-52393)

### [!DNL Target Standard/Premium] 25.5.1 (5 mai 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème qui empêchait l’affichage d’ajustements d’audience pour certaines activités dans l’interface utilisateur mise à jour. (TGT-52057)
* Correction d’un problème qui empêchait l’utilisation d’audiences combinées dans les activités . (TGT-52346)
* Correction d’un problème qui empêchait la création d’une activité dans un espace de travail autre que celui par défaut à l’aide d’une audience d’activité unique du même espace de travail. (TGE-52349)
* Correction d’un problème en raison duquel les audiences d’activité uniquement disparaissaient de l’interface utilisateur mise à jour après la création et la sélection d’une nouvelle audience. (TGT=52091)
* Correction d’un problème qui empêchait l’utilisation d’audiences en double dans les activités . (TGT-51200 et TGT-52057)
* Correction d’un problème en raison duquel les affinements d’audience et les audiences d’activité étaient inversés dans l’interface utilisateur mise à jour. (TGT-52158)
* Correction d’un problème qui empêchait la création d’une nouvelle activité en raison de l’erreur de saisie utilisateur : « Espace de travail non par défaut non autorisé pour cet utilisateur ». (TGT-52267)
* Correction d’un problème qui empêchait l’affichage des offres dans l’interface utilisateur mise à jour pour les espaces de travail par défaut et non par défaut. [!DNL Target] affiche désormais les offres des deux espaces de travail. (TGT-52339)
* Correction d’un problème en raison duquel [!DNL Target] n’avertissait pas les clients lors de la modification d’une activité et d’un élément de site web modifié. (TGT-52100)
* Correction d’un problème en raison duquel la modification d’une offre avec des offres ad hoc créait une nouvelle offre au lieu de mettre à jour l’offre existante. (TGT-52135)
* Correction d’un problème qui provoquait une erreur de payload non valide lors du déplacement d’offres vers des dossiers. (TGT-52325)
* Correction d’un problème qui provoquait une erreur de saisie de l’utilisateur lors du déplacement d’offres vers des dossiers. (TGT-52296)
* Ajout d’un champ `audienceMetadata` pour chaque activité et vérification de sa lecture et de sa mise à jour lors de sa modification. (TGT-51004)

### [!DNL Target Standard/Premium] 25.4.5 (25 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème qui entraînait des incohérences dans les listes d’audience entre la page des paramètres [!UICONTROL Activité] et la page d’aperçu [!UICONTROL Rapports]. (TGT-52203)
* Correction d’un problème qui empêchait l’ajout d’une nouvelle page à une activité en raison d’une erreur d’entrée utilisateur non valide. (TGT-52263)
* Correction d’un problème en raison duquel les `OptionLocalIDs` étaient incorrectement incrémentées lorsque l’option restait inchangée. (TGT-52187)
* Correction d’un problème en raison duquel `location` et `OptionLocalIDs` s’incrémentaient incorrectement lorsque l’option restait inchangée. (TGT-52188)
* Correction d’un problème en raison duquel l’emplacement sur la page [!UICONTROL Aperçu] de l’activité était incorrect. (TGT-52182)
* Correction d’un problème où un avertissement de sélecteur non valide ne s’affichait pas pour un emplacement non valide. (TGT-52110)
* Correction d’un problème en raison duquel les fichiers de création de rapports téléchargés affichaient correctement les données présentes dans l’interface utilisateur de création de rapports. (TGT-52068)
* Correction d’un problème en raison duquel les opérations par lots n’échouaient pas après l’ajout de règles de diffusion de page. (TGT-52097)
* Correction d’un problème en raison duquel [!DNL Target] supprimait tous les paramètres de requête de l’URL du site web. (TGT-52100)
* Correction d’une erreur de console qui empêchait les clients de créer des activités dans l’interface utilisateur de [!DNL Target] héritée et mise à jour. (TGT-52181)
* Correction d’un problème qui empêchait les clients et clientes d’ajouter de nouvelles pages, provoquant une erreur d’entrée utilisateur non valide. (TGT-52258)
* Correction d’un problème en raison duquel les modifications disparaissaient après l’ajout de pages supplémentaires, puis en revenant à l’onglet [!UICONTROL Expériences]. (TGT-52264)
* Correction d’un problème qui empêchait les clients et clientes de modifier l’audience dans une activité [!UICONTROL Ciblage d’expérience] (XT). (TGT-52191)
* Correction d’une erreur qui empêchait la modification d’une activité XT en raison d’une règle d’IU non prise en charge. (TGT-52273)
* Correction d’un problème dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour en raison duquel les chemins de navigation n’étaient pas toujours affichés en bas de l’éditeur, ce qui entraînait des difficultés pour sélectionner précisément les éléments. (TGT-52169)
* Correction d’un problème en raison duquel la liste déroulante [!UICONTROL Audience] n’affichait pas toutes les audiences en raison de la pagination. (TGT-52204)
* Correction d’un problème qui entraînait un message d’entrée utilisateur non valide lors de l’ajout de nouvelles offres dans les activités  (AP). (TGT-52210)
* Correction d’un problème en raison duquel [!UICONTROL Analytics for Target] (A4T) était incorrectement sélectionné comme source de création de rapports, même si le client n’avait pas accès à A4T. (TGT-52226)
* Correction d’un problème qui empêchait l’enregistrement d’une activité avec la mesure d’URL [!UICONTROL Afficher une page]. (TGT-52260)
* Correction d’un problème qui empêchait les clients de sélectionner des espaces de travail lors de la création d’offres dans une activité. (TGT-52289)
* Correction d’un problème qui empêchait les clients de créer des activités dans tous les espaces de travail. (Tgt-52218)
* Correction d’un problème où les modifications d’une expérience s’affichaient incorrectement lors du passage à une autre expérience. (TGT-52184)
* Correction d’un problème en raison duquel l’offre par défaut s’affichait incorrectement dans l’interface utilisateur de [!DNL Target] lors de l’ouverture de l’activité. (TGT-52198)

### Mise à jour des autorisations Target (22 avril 2025)

Cette future mise à jour améliore le contrôle organisationnel sur les configurations d’instance de [!DNL Target], empêchant les mises à jour accidentelles qui pourraient affecter la diffusion des activités entre différentes équipes de test et de personnalisation.

À compter du 22 avril 2025, seuls les administrateurs [!UICONTROL Produit] et [!UICONTROL Solutions] pourront mettre à jour les paramètres des sections [!UICONTROL Administration], quels que soient leurs rôles dans les espaces de travail [!DNL Target]. Les utilisateurs ne disposant pas de cette autorisation auront un accès en lecture seule aux sections [!UICONTROL Administration].

Pour plus d’informations, voir [ Administration de Target ](/help/main/administrating-target/start-target.md).

### [!DNL Target Standard/Premium] 25.4.4 (17 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Ajout d’un message d’erreur pour guider les utilisateurs et utilisatrices dans la résolution des options en double dans une activité. (TGT-51927)
* Correction d’un problème en raison duquel les sélecteurs `ClickTrack` n’étaient pas supprimés lors de la suppression de pages ou d’expériences avec des offres de redirection. (TGT-51952)
* Correction d’un problème lié à l’autorisation de sélecteurs de `ClickTrack` vides. [!DNL Target] nécessite désormais que le champ de sélecteur ne soit pas vide. (TGT-52107)
* Correction d’un problème qui autorisait incorrectement les mesures avec des noms en double. Les mesures nécessitent désormais des noms uniques. (TGT-52201)
* Correction d’un problème en raison duquel les définitions d’audience n’étaient pas visibles lors de la modification du ciblage au niveau de l’offre dans les activités  (AP). (TGT-52148)
* Correction d’un problème qui empêchait les clients disposant des droits [!UICONTROL Éditeur] d’enregistrer les activités. (TGT-52227)
* `OptionLocalIDs` n’incrémente plus incorrectement lorsque l’option reste inchangée. (TGT-52139)
* Correction d’un problème qui provoquait un message « `optionLocalIds` non valide » lors de la création d’une activité. (TGT-52154)
* Des écarts ont été corrigés entre les `OptionLocalIDs` définis pour une activité et ceux utilisés pour définir les expériences. (TGT-52215)
* Correction d’un problème qui provoquait un échec de validation lors de la tentative de création d’une activité A/B. (TGT-51923)

### [!DNL Target Standard/Premium] 25.4.3 (11 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’une erreur qui empêchait les clients et clientes d’ouvrir le pop-up d’informations sur l’audience pour certaines activités [!UICONTROL  Ciblage d’expérience ] (XT). (TGT-52049)
* Correction d’un problème en raison duquel le paramètre d’audience revenait à « [!UICONTROL Tous les visiteurs] » suite aux modifications apportées au [!UICONTROL Compositeur d’expérience visuelle] (VEC). (TGT-52132)
* Correction d’un problème où les ajustements d’audience n’étaient pas affichés pour des activités spécifiques (TGT-52057)
* Correction d’un problème qui empêchait les clients d’insérer un [!UICONTROL fragment d’expérience] dans l’espace de travail par défaut. (TGT-52073)
* Correction d’un problème en raison duquel une offre affichait « Contenu introuvable » et ne s’affichait pas sur la page [!UICONTROL Offres] pour une activité [!UICONTROL Automated Personalization] (AP). (TGT-52150)
* Ajout de la possibilité d’autoriser les audiences en double dans une activité. (TGT-51200)
* Correction d’un problème en raison duquel un nom de mbox incorrect s’affichait sur la page [!UICONTROL Objectifs et paramètres] pour une activité XT après modification. (TGT-52026)
* Correction d’un problème en raison duquel les `defaultContent` s’affichaient dans les options alors qu’elles n’étaient pas dans les `experiences/optionLocations`. (TGT-52036)
* Correction d’un problème pour s’assurer que les chaînes vides ne sont pas converties en valeurs nulles. (TGT-52037)
* Correction d’un problème en raison duquel les clients devaient reconfigurer l’[!UICONTROL Objectif d’optimisation] dans [!UICONTROL Paramètres de création de rapports] sur la page [!UICONTROL Objectifs et paramètres] après les modifications. (TGT-52071)
* Correction d’un problème en raison duquel une activité sans règles de diffusion de page affichait plusieurs règles sur la page [!UICONTROL Aperçu]. (TGT-52084)
* Ajout d’un message d’erreur pour les utilisateurs qui tentent d’enregistrer une offre avec des caractères en dehors du plan multilingue de base, tels que des émoticônes. (TGT-52105)
* Correction d’un problème en raison duquel l’ouverture d’une activité déclenchait le message d’erreur : « Cette activité utilise une ou plusieurs audiences supprimées à la source ». (TGT-52120)
* Correction d’un problème en raison duquel les mesures ClickTrack n’étaient pas affichées dans le [!UICONTROL compositeur d’expérience visuelle] (VEC) mis à jour lors de la modification. (TGT-52152)
* Correction d’un problème en raison duquel une URL avec un paramètre de requête comme emplacement de l’activité n’affichait pas le paramètre de requête sur la page [!UICONTROL Aperçu] de l’activité. (TGT-51635)
* Correction d’un problème qui empêchait l’affichage de l’URL d’expérience entière dans [!UICONTROL le mode de navigation] dans le [!UICONTROL compositeur d’expérience visuelle] (VEC). (TGT-52101)
* Correction d’un problème en raison duquel la modification d’une activité entraînait l’ajout d’un caractère « / » à la fin de l’URL par la diffusion de la page, la rendant non valide. (TGT-52114)
* Correction d’un problème en raison duquel le lien [!UICONTROL AQ d’activité] du [!UICONTROL Compositeur d’expérience d’après les formulaires] était incorrectement redirigé vers la page d’accueil de [!DNL Adobe Experience Cloud]. (TGT-52055)
* Correction d’un problème en raison duquel les pages supplémentaires ajoutées à l’activité [!UICONTROL Test A/B] n’étaient pas conservées après l’enregistrement et la réouverture. (TGT-51994)
* Correction d’un problème qui empêchait les clients de supprimer des styles dans la section Style intégré . (TGT-52070)
* Restauration de l’accès aux [cartes de définition d’audience](/help/main/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) dans la boîte de dialogue [!UICONTROL AQ d’activité], comme dans l’interface utilisateur héritée. (TGT-52056)
* L’interface utilisateur mise à jour n’a pas enregistré de pages ou d’audiences sans modifications. Si les clients ajoutaient de nouvelles pages ou audiences à une activité mais ne leur apportaient aucune modification, [!DNL Target] ignoraient les audiences non modifiées lors de l’enregistrement. Des notifications ont été ajoutées aux endroits appropriés pour informer les utilisateurs de ce comportement. (TGT-52104)

### [!DNL Target Standard/Premium] 25.4.1 (2 avril 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel les audiences d’expérience disparaissaient des activités . (TGT-52003)
* Correction d’un problème qui provoquait des éléments inattendus lors de la diffusion. (TGT-52011)
* Correction d’un problème qui empêchait les clients et clientes d’afficher l’audience dans le graphique de ciblage sur la page D[!UICONTROL affichage ] et lors de la modification de l’activité. (TGT-52050)
* Correction d’un problème qui empêchait les clients de réorganiser les expériences par ordre de priorité dans les activités [!UICONTROL  Ciblage d’expérience ] (XT). (TGT-52054)
* Correction d’un problème qui provoquait un rendu incorrect lors de l’annulation de modifications de style de texte. (TGT-51876)
* Correction d’un problème en raison duquel, lors de la modification d’une offre de redirection, [!DNL Target] supprime également tous les sélecteurs [!UICONTROL ClickTrack] associés à cette offre. (TGT-51936)
* Correction d’un problème en raison duquel [!DNL Target] enregistrait incorrectement le sélecteur lors de l’annulation de [!UICONTROL ClickTrack]. (TGT-51937)
* Correction d’un problème qui déclenchait une erreur de nom non valide après l’ouverture et la fermeture du sélecteur de mbox sur la page [!UICONTROL  Objectifs et paramètres ] sans apporter de modifications. (TGT-51983)
* Correction d’un problème qui bloquait la modification des offres ad hoc créées dans l’interface utilisateur de [!DNL Target] héritée. (TGT-51984)
* Correction d’un problème qui bloquait les activités de modification comportant des offres ad hoc contenant du code personnalisé. (TGT-51995)
* Correction d’un problème en raison duquel les règles d’exclusion s’affichaient en tant que règles d’inclusion lors de la modification des définitions d’audience combinées. (TGT-51999)
* Correction d’un problème qui empêchait l’affichage correct du code personnalisé lors de l’édition de l’expérience. (TGT-52005)
* Correction d’un problème qui rendait l’option [!UICONTROL Insérer avant] indisponible pour insérer du contenu avant la barre de navigation. (TGT-52031)
* Correction d’un problème qui empêchait la mise en surbrillance correcte de l’expérience par défaut dans les rapports. (TGT-51716)
* Correction d’un problème qui déclenchait un message `default message [Invalid optionLocalIds: xx]]` lors de la création d’une activité. (TGT-52038)

### at.js version 2.11.8 (31 mars 2025)

* Résolution d’une vulnérabilité identifiée par CodeQL dans la validation du suffixe de chaîne pour empêcher les cas Edge lors des opérations de redimensionnement et de déplacement. (TNT-51516)

### [!DNL Target Standard/Premium] 25.3.8 (28 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel la page [!UICONTROL Activités] se chargeait lentement. (TGT-51151)

### [!DNL Target Standard/Premium] 25.3.7 (26 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème qui bloquait l’enregistrement des activités multi-pages si une page était supprimée après des modifications. (TGT-51988)
* Correction d&#39;une erreur qui se produisait lors de la modification d&#39;une activité : `default message [Invalid optionLocalIds: xx]]`. (TGT-51985)
* Correction d’un problème en raison duquel l’ajout de nouvelles modifications à une activité supprimait les modifications existantes. (TGT-51981)
* Correction d’un problème en raison duquel le remplacement d’une audience par « [!UICONTROL Tous les visiteurs] » lors de la création ou de la modification d’une activité provoquait une erreur « Les audiences en double ne sont pas autorisées ». (TGT-51978)
* Correction d’un problème qui provoquait une erreur « Entrée utilisateur non valide » lors de l’enregistrement d’une activité [!UICONTROL  Test A/B ]. (TGT-51976)
* Correction d’un problème qui empêchait l’affichage correct des mesures calculées sur la page [!UICONTROL Objectifs et paramètres]. (TGT-51975)
* Correction d’un problème qui empêchait la correspondance des `companyName` et des `reportSuite` dans la configuration [!DNL Analytics] pour la mesure `pageviews`. (TGT-51965)
* Correction d’un problème en raison duquel le changement d’expérience dans une activité supprimait les modifications. (TGT-51945)
* Correction d’un problème où la suppression d’une audience de page supprimait également les sélecteurs [!UICONTROL ClickTrack]. (TGT-51935)
* Correction d’un problème qui rendait une activité non modifiable après l’ouverture de sa page [!UICONTROL Aperçu]. (TGT-51931)
* Correction d’un problème qui provoquait une erreur `[Unused optionLocalIds: 0]]` lors de la création de l’activité. (TGT-51920)
* Correction d’un problème en raison duquel certaines modifications n’étaient pas correctement traduites après la suppression des modifications de style de texte. (TGT-51876)
* Correction d’un problème qui empêchait les audiences ciblées de se mettre à jour correctement dans le [!UICONTROL Compositeur d’expérience d’après les formulaires]. (TGT-51845)
* Correction d’un problème en raison duquel l’URL du [!UICONTROL compositeur d’expérience visuelle] n’était pas correctement mise à jour lors de la navigation dans les activités. (TGT-51832)
* Correction d’un problème qui empêchait l’affichage des offres dans l’interface utilisateur [!UICONTROL Offres], même si elles s’affichaient correctement lors de la création d’une activité et de l’ajout d’offres. (TGT-51805)
* Correction d’un problème en raison duquel certaines activités ne disposaient pas d’écran de secours pour afficher le contenu par défaut lorsque le contenu personnalisé ou ciblé ne pouvait pas être diffusé. (TGT-51638)
* Correction d’un problème qui empêchait l’affichage correct des offres en direct et de certains dossiers dans l’interface utilisateur de [!UICONTROL Offres]. (TGT-51628)
* Correction d’un problème qui empêchait la localisation correcte de certaines chaînes d’URL et de certaines goURL. (TGT-35741)
* Correction d’un problème qui empêchait la localisation correcte des rôles ([!UICONTROL Approbateur], [!UICONTROL Éditeur] et [!UICONTROL Observateur]) dans l’interface utilisateur de [!DNL Target]. (TGT-29925)

### [!DNL Target Standard/Premium] 25.3.6 (14 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Résolution de l’erreur « Entrée utilisateur non valide » dans les activités [!UICONTROL Compositeur d’expérience visuelle] (VEC) avec l’option [!UICONTROL Suivi des clics] activée lorsque le même sélecteur [!UICONTROL ClickTrack] est utilisé plusieurs fois. (TGT-51921)
* Correction de l’erreur « Entrée utilisateur non valide » dans les activités du compositeur d’expérience visuelle avec des emplacements partagés (par exemple, le sélecteur HEAD) et des offres identiques. (TGT-51879)
* Correction d’un problème en raison duquel les modifications d’expérience étaient partagées entre les audiences. (TGT-51815)
* Résolution des erreurs de validation lors de la création d’activités en raison de conflits d’identifiants de segment. Les erreurs se produisaient lorsque [!DNL Target] détectait des activités existantes à l’aide de segments anonymes. (TGT-51784)
* Résolution d’un problème qui empêchait [!DNL Target] d’enregistrer les activités avec des règles d’exclusion dans une audience. (TGT-51581)
* Correction d’un problème qui empêchait les clients de créer, supprimer ou déplacer des dossiers sans accéder à l’espace de travail par défaut. (TGT-51499)
* Correction d’un problème en raison duquel les requêtes GET échouaient lors de la récupération de [!DNL Analytics] liste de mesures. (TGT-51106)

### [!DNL Target Standard/Premium] 25.3.5 (11 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème qui empêchait les utilisateurs de modifier les offres dans le panneau [!UICONTROL Modifications]. (TGT-51800)
* Correction d’un problème où les actions s’affichaient incorrectement dans le panneau de gauche pour les expériences et les audiences, y compris en mode [!UICONTROL ClickTrack]. (TGT-51895)
* Correction d’un problème où les sélecteurs [!UICONTROL ClickTrack] n’étaient pas appliqués à la bonne page d’audience. (TGT-51871)

### [!DNL Target Standard/Premium] 25.3.4 (7 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème où les audiences d’activité unique n’étaient pas visibles dans le panneau [!UICONTROL Audiences], empêchant leur modification ou leur réutilisation. (TGT-51860)
* Correction d’un problème qui empêchait les clients [!DNL Target Standard] de créer des activités à l’aide des rapports [!UICONTROL Analytics for Target] (A4T). (TGT-51854)
* Correction d’un problème qui excluait les compteurs d’identifiants locaux de la payload lors des opérations de création et de modification par lots. (TGT-51867)

### [!DNL Target Standard/Premium] 25.3.2 (6 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Correction d’un problème en raison duquel la copie d’une activité avec une audience d’activité unique ne permettait pas de créer une activité, utilisant par erreur l’audience de l’activité originale à la place. (TGT-51855)
* Correction d’un problème qui empêchait la modification des activités [!UICONTROL Ciblage d’expérience] (XT) avec des audiences d’activité uniquement. (TGT-51846)
* Correction d’un problème en raison duquel le [!UICONTROL compositeur d’expérience visuelle] (VEC) ne pouvait pas appliquer correctement les modifications à une expérience lors de la première modification. (TGT-51843)
* Correction d’un problème qui déclenchait une erreur « ID » lors d’un clic sur certains éléments dans le VEC. (TGT-51814)
* Mise à jour de la gestion des erreurs dans le VEC lors de la création de l’activité. (TGT-51759)
* Correction d’un problème en raison duquel une vue manquante dans le panneau [!UICONTROL Modifications] provoquait une erreur « entrée utilisateur non valide » lors de l’enregistrement de l’activité. (TGT-51827)
* Correction d’un problème qui empêchait la création de critères de recommandation. (TGT-51834)
* Ajout d’un message de confirmation avant la redirection vers une autre URL. (TGT-51703)
* Correction de problèmes liés aux tests d’intégration de GraphQL dans les offres et les dossiers. (TGT-51839)

### [!DNL Target Standard/Premium] 25.3.1 (3 mars 2025)

Cette version comprend les correctifs et mises à jour suivants :

* Une audience combinée peut inclure des sous-groupes, chacun contenant plusieurs audiences. Cette version a corrigé un problème qui empêchait l’affichage des audiences de sous-groupe dans la boîte de dialogue [!UICONTROL Règles]. (TGT-51813)
* Correction d’un problème en raison duquel certaines audiences d’expérience étaient remplacées par [!UICONTROL Tous les visiteurs] lors de l’ouverture d’anciennes activités. (TGT-51812)
* Correction d’un problème qui empêchait la modification des activités avec des audiences d’activité uniquement. (TGT-51807)
* Correction d’un problème qui empêchait la modification des modifications d’en-tête de page dans l’interface utilisateur [!DNL Target] mise à jour. (TGT-51797)
* Correction d’une erreur « null » qui se produisait lors de la duplication d’une expérience, de la suppression d’une autre expérience, puis de la tentative d’enregistrement de l’activité. (TGT-51796)
* Correction d’un problème qui empêchait l’affichage des règles d’exclusion d’audience dans le panneau d’informations de l’audience lors de l’étape [!UICONTROL Ciblage] de création des activités. (TGT-51579)
* Mise à jour des messages d&#39;erreur en coréen. (TGT-51701 et TGT-51699)

### [!DNL Target Standard/Premium] 25.2.3 (26 février 2025)

Cette version comprend les mises à jour suivantes :

* Correction d’un problème qui empêchait les mises à jour des activités après [!DNL Target] version 25.2.1 pour certaines activités. (TGT-51781)
* Correction d’un problème où toutes les modifications de l’audience dans l’état étaient supprimées lors de l’annulation du processus de création de l’activité (en sélectionnant [!UICONTROL Annuler] au lieu de [!UICONTROL Ajouter une audience]). (TGT-51769 et TGT-51770)
* Correction d’un problème en raison duquel le chargement du [!UICONTROL compositeur d’expérience visuelle] (VEC) échouait pour certaines activités, en particulier lorsque du code personnalisé était utilisé.  En raison d’un problème, le VEC affichait un écran vide ou l’interface utilisateur de [!DNL Target] revenait à son ancienne version. (TGT-51758)
* Correction d’un problème où les modifications étaient ignorées après la modification de la diffusion de page pour les audiences. (TGT-51756)
* Correction d’un problème où toutes les audiences non métriques (audiences de page et d’expérience) étaient supprimées des activités lors de la modification d’un type de mesure sur la page [!UICONTROL  Objectifs et paramètres ]. (TGT-51753)
* Correction d’un problème en raison duquel, en cliquant sur [!UICONTROL Annuler] lors de la modification d’une activité, l’interface utilisateur de Target accédait à la [!UICONTROL Liste des activités] au lieu de la page [!UICONTROL Détails de l’activité]. (TGT-51731)
* Correction d’un problème qui empêchait les clients et clientes de télécharger des rapports via l’option [!UICONTROL  Exporter les rapports au format CSV ]. (TGT-51708)
* Correction d’un problème dans le compositeur d’expérience d’après les formulaires en raison duquel [!DNL Target Standard] clients s’affichaient incorrectement comme utilisant [!UICONTROL Propriétés], une fonctionnalité [!DNL Target Premium]. (TGT-51678)
* Correction d’un problème qui empêchait l’affichage des attributs [!DNL Adobe Experience Platform] lors de la création de nouvelles offres. (TGT-51665)
* Déplacement de tous les filtres actifs pour [!DNL Recommendations] inventaire vers la recherche rapide, en alignant l’interface utilisateur avec [!UICONTROL  Recherche catalogue ] au lieu du rail [!UICONTROL  Filtre ]. (TGT-50723)

### at.js version 2.11.7 (26 février 2025)

Cette version comprend la mise à jour suivante :

* Correction de la journalisation de la télémétrie lorsque `localStorage` n’est pas disponible. La télémétrie provoquait un problème pour certains clients qui avaient `localStorage` désactivés dans leurs navigateurs.

Pour plus d’informations à ce sujet et sur les versions précédentes d’at.js, voir [Informations détaillées sur les versions du fichier at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions){target=_blank}.

### Target Standard/Premium 25.2.1 (mardi 17 février 2025) {#ui-update-2}

Cette version comprend les mises à jour suivantes :

* [!UICONTROL Activités] mise à jour de l’interface utilisateur
* Mise à jour de l’interface utilisateur d’[!DNL Recommendations]

#### [!UICONTROL Activités] mise à jour de l’interface utilisateur

Alors que les efforts de modernisation de l’interface utilisateur de [!DNL Adobe Target] se poursuivent, nous sommes heureux d’annoncer la disponibilité générale de l’interface utilisateur [!UICONTROL Activités] mise à jour.

>[!NOTE]
>
>À compter du 17 février, les clients auront progressivement accès à la nouvelle interface utilisateur [!UICONTROL Activités]. Pour garantir un déploiement transparent pour tous les clients, cette version sera déployée par étapes contrôlées. La première étape consiste à mettre à niveau le groupe initial de clients [!DNL Target] vers la nouvelle interface utilisateur [!UICONTROL Activités]. Les étapes suivantes mettront à niveau les clients restants.

>[!IMPORTANT]
>
>Pour obtenir des informations importantes sur le plan de fin de vie du bouton (bascule) de version de l’interface utilisateur [!DNL Target], voir [[!DNL Target] Obsolescence du bouton (bascule) de version de l’interface utilisateur](/help/main/r-release-notes/release-notes.md#toggle).

En fonction du dernier système de conception [!DNL Adobe Spectrum], la mise à jour normalise les modèles de conception précédemment incohérents, tout en ajoutant de nouvelles améliorations, telles que :

* [Redéfinition des rapports](/help/main/administrating-target/reporting.md) pour une meilleure compréhension des résultats des activités.
* [[!UICONTROL  Mise à jour de la page Journal des modifications ]](/help/main/c-activities/change-log.md), qui récupère désormais les informations du [[!DNL Audit Query API]](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/audit-logs/audit-api/overview){target=_blank} pour obtenir des informations en temps réel.
* [Vues Liste personnalisables](/help/main/c-activities/activities.md) pour une meilleure flexibilité en fonction des besoins des différentes équipes.
* [Amélioration des écrans d’informations rapides et détaillées](/help/main/c-activities/activities.md) pour un accès plus facile aux informations.
* [Options de recherche et de filtrage persistantes dans la session](/help/main/c-activities/activities.md).
* Complètement [reconstruit [!UICONTROL compositeur d’édition visuelle]](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) avec prise en charge des dernières mises à jour de sécurité des fournisseurs de navigateur et une interface utilisateur moderne.

  Pour plus d’informations sur les différences entre le VEC mis à jour et la version précédente, voir :

  * [Modifications du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)
  * [Options du compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)

* [Mise à jour [!DNL Chrome] extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) prise en charge de Manifest V3 pour une sécurité accrue et une meilleure prise en charge des cookies propriétaires.

![Actualisation des activités](/help/main/r-release-notes/assets/activities-refresh.png)

#### Mise à jour de l’interface utilisateur d’[!DNL Recommendations]

Alors que les efforts de modernisation de l’interface utilisateur de [!DNL Adobe Target] se poursuivent, nous sommes heureux d’annoncer la disponibilité générale de l’interface utilisateur de [!DNL Recommendations] mise à jour.

>[!NOTE]
>
>À compter du 17 février, les clients auront progressivement accès à la nouvelle interface utilisateur [!UICONTROL Recommendations]. Pour garantir un déploiement transparent pour tous les clients, cette version sera déployée par étapes contrôlées. La première étape consiste à mettre à niveau le groupe initial de clients [!DNL Target] vers la nouvelle interface utilisateur [!UICONTROL Activités]. Les étapes suivantes mettront à niveau les clients restants.

En fonction du dernier système de conception [!DNL Adobe Spectrum], la mise à jour normalise les modèles de conception précédemment incohérents, tout en ajoutant de nouvelles améliorations, telles que :

* La [recherche catalogue de produits](/help/main/c-recommendations/c-products/catalog-search.md) comprend désormais une base de données mise à jour permettant une synchronisation en temps réel des produits.
* [!UICONTROL Recommendations] les objets ([!UICONTROL Critères], [!UICONTROL Conceptions], [!UICONTROL Collections] et [!UICONTROL Exclusions]) [créés via l’API sont désormais disponibles dans l’IU](/help/main/c-recommendations/c-recommendations-faq/recommendations-faq.md).
* Les [paramètres Recommendations](/help/main/administrating-target/recommendations-settings.md) ont été consolidés dans la section [!UICONTROL Administration].
* Vues Liste personnalisables pour une meilleure flexibilité en fonction des besoins des différentes équipes.
* Actualisation des éditeurs de code HTML et JSON avec [mise en surbrillance de la syntaxe et numérotation des lignes](/help/main/c-experiences/c-manage-content/create-json-offer.md).
* Amélioration des fenêtres d’informations rapides et détaillées pour un accès plus facile aux informations.
* Options de recherche et de filtrage persistantes dans la session.

![Actualisation de l’interface utilisateur de Recommendations](/help/main/r-release-notes/assets/recs-ui-refresh.png)

### Target Standard/Premium 25.1.1 (vendredi 9 janvier 2025) {#ui-update-1}

Cette version comprend les mises à jour suivantes :

#### [!UICONTROL Bibliothèque des offres] mise à jour de l&#39;interface utilisateur

Afin d&#39;améliorer l&#39;expérience utilisateur des utilisateurs [!DNL Adobe Target], cette version met à jour l&#39;interface utilisateur de la [!UICONTROL  Bibliothèque des offres ].

>[!NOTE]
>
>Pour garantir un déploiement transparent pour tous les clients, cette version sera déployée par étapes contrôlées. La première étape a mis à niveau le groupe initial de clients Target vers la nouvelle interface utilisateur d’offres. Les étapes suivantes mettront à niveau les clients restants.

>[!IMPORTANT]
>
>Pour obtenir des informations importantes sur le plan de fin de vie du bouton (bascule) de version de l’interface utilisateur [!DNL Target], voir [[!DNL Target] Obsolescence du bouton (bascule) de version de l’interface utilisateur](/help/main/r-release-notes/release-notes.md#toggle).

En utilisant le dernier système de conception [!DNL Adobe Spectrum], cette mise à jour normalise les modèles de conception incohérents et introduit de nouvelles améliorations, notamment les suivantes :

* **Gestion des offres en masse** : sélectionnez et supprimez ou déplacez plusieurs offres simultanément.

* **[!UICONTROL Éditeur de code] mises à niveau** : actualisation des éditeurs HTML et JSON avec mise en surbrillance de la syntaxe et numérotation des lignes.

* **Cartes d’offres améliorées** : cartes d’informations rapides et détaillées améliorées pour un accès plus facile aux informations.

* **Recherche et filtres persistants** : ajoute des options de recherche et de filtrage persistantes dans la session.

Pour plus d’informations, consultez [Offres](/help/main/c-experiences/c-manage-content/manage-content.md) et les sous-articles de cette section. Tous les articles Offres de cette section ont été mis à jour pour prendre en compte ces modifications de l’interface utilisateur.

Regardez cette courte vidéo pour découvrir les modifications apportées à cette version :

![Vidéo d’actualisation de l’interface utilisateur des offres](/help/main/r-release-notes/assets/offers-video-v2.gif)
