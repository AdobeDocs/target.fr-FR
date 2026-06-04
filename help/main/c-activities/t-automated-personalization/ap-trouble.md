---
kewords: Automated Personalization;ap;troublshoot;troubleshooting;model;lift
description: Explorez les défis potentiels que vous pouvez rencontrer lors de l’utilisation d’activités [!UICONTROL ] (AP) dans Adobe Target, ainsi que les solutions suggérées.
title: Comment résoudre les problèmes liés aux activités [!UICONTROL ] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
TQID: https://experienceleague.adobe.com/1Qevyq-TiutN1dEZnfC1DDmUgXoHIxtBl-3RMPq-m-0
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 764
ht-degree: 30%

---

# Résolution des problèmes liés à 

Il arrive parfois que les activités ne se déroulent pas comme prévu. Voici quelques défis potentiels auxquels vous pourriez être confronté lors de l’utilisation de  (AP), ainsi que quelques solutions suggérées.

## Mon activité  prend trop de temps pour créer des modèles. {#section_20028B204DBB4D77A324BA193434AEE2}

+++Afficher les détails

Plusieurs modifications de la configuration de l’activité peuvent réduire le temps nécessaire à la création des modèles, notamment le nombre d’expériences dans votre activité , le trafic sur votre site et la mesure de succès que vous avez sélectionnée.

**Solution :** passez en revue la configuration de votre activité et vérifiez si vous êtes prêt à apporter des modifications pour accélérer la création des modèles.

* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdez pas de données d’activité si vous modifiez la mesure de succès de RPV à conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les besoins en trafic nécessaires à la compilation des modèles, car un nombre minimum de conversions est requis pour cela.
* Y a-t-il des offres ou des expériences que vous pouvez exclure de votre activité ? La réduction du nombre d’expériences dans une activité accélère la création de modèles.
* Existe-t-il une page à trafic plus élevé où cette activité serait plus réussie ? Plus il y a de trafic et de conversions dans les emplacements de vos activités, plus les modèles sont créés rapidement.

+++

## Mon activité  n’a pas généré d’effet élévateur. {#section_8900BC8968474438B8092F7A94C0C6CF}

+++Afficher les détails

Plusieurs facteurs sont requis pour qu’une activité  génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées à un emplacement qui fait la différence par rapport à l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** le meilleur plan d’action consiste à s’assurer en premier lieu que le contenu et les lieux qui composent les expériences de l’activité créent une réelle différence dans les taux de réponse globaux par le biais d’un simple test A/B non personnalisé. Veillez à calculer les tailles d’échantillon à l’avance. Le calcul de la taille des échantillons à l’avance permet de s’assurer qu’il y a suffisamment de puissance pour voir un effet élévateur raisonnable. Vous pouvez ensuite exécuter le test A/B pendant une durée fixe sans l’arrêter ni apporter de modifications. Si un résultat de test A/B indique une augmentation statistiquement significative sur une ou plusieurs expériences, il est probable qu’une activité personnalisée réussisse. Personalization peut fonctionner même s’il n’existe aucune différence dans les taux de réponse globaux des expériences. En règle générale, le problème provient du fait que les offres ou les emplacements n’ont pas un impact suffisamment important sur l’objectif d’optimisation pour être détectés avec une signification statistique.

+++

## L’URL de mon activité  affiche du contenu d’offre sur des pages incorrectes. {#section_82A224406DBF4107B05204BEFBBE458C}

+++Afficher les détails

Dans , les règles de test d’URL et de modèle sont ajoutées à la contrainte d’entrée de requête [!DNL Target] (par exemple, target-global-mbox), où elles sont évaluées une seule fois. Une fois qu’un utilisateur est qualifié pour une activité, les règles de ciblage au niveau de la requête Target ne sont pas réévaluées. L’audience de ciblage est toutefois ajoutée aux règles de ciblage d’emplacement.

**Solution :** ajoutez les règles de modèle nécessaires en tant qu’entrée-audience de l’activité. L’évaluation de l’audience s’effectue à chaque demande/appel.

+++

## Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties. {#section_076D1F44298C4E4A849AC52F5A33214D}

+++Afficher les détails

Ce comportement est attendu.

Dans une activité , une fois qu’une mesure de conversion (objectif d’optimisation ou objectif de publication) est convertie, le visiteur est libéré de l’expérience et l’activité est redémarrée.

Par exemple, il existe une activité avec une mesure de conversion (C1) et une autre mesure (A1). A1 dépend de C1. Lorsqu’un visiteur entre dans l’activité pour la première fois et que les critères de conversion de A1 et C1 ne sont pas convertis, la mesure A1 n’est pas convertie en raison de la dépendance de la mesure de succès. Si le visiteur convertit C1, puis convertit A1, A1 n’est toujours pas converti, car lorsque C1 est converti, le visiteur est libéré.

+++

## Les URL de mes expériences ne fonctionnent pas comme prévu. {#section_7B08DA1F30AA483E9406336DAF361BA4}

+++Afficher les détails

* Si l’aperçu ne s’affiche pas dans le nouvel onglet (en raison de la mise en cache du navigateur), essayez de l’actualiser deux ou trois fois. Vous pouvez également copier le lien et l’ouvrir dans un nouveau navigateur ou une nouvelle session.
* Régénérez les liens d’URL d’Experience si vous avez modifié des contenus et partagez les nouveaux liens avec les autres membres de votre équipe.

+++
