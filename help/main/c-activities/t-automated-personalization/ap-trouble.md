---
keywords: Automated Personalization;ap;dépannage;dépannage;modèle;effet élévateur
description: Explorez les défis potentiels que vous pouvez rencontrer lors de l’utilisation des activités [!UICONTROL Automated Personalization] (AP) dans Adobe Target, ainsi que les solutions suggérées.
title: Comment résoudre les problèmes liés aux activités [!UICONTROL Automated Personalization] ?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Voir ce qui est inclus dans Target Premium."
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
TQID: 'https://experienceleague.adobe.com/1Qevyq-TiutN1dEZnfC1DDmUgXoHIxtBl-3RMPq-m-0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 7%
---
# Dépannage D’[!UICONTROL Automated Personalization] {#ap-troubleshooting}

>[!BEGINSHADEBOX]

**Sur cette page :** Trouvez des solutions aux problèmes courants liés aux activités **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

Les activités ne se déroulent pas toujours comme prévu. Utilisez la liste suivante pour identifier la cause des problèmes courants dans les activités [!UICONTROL Automated Personalization] (AP) et pour appliquer la solution suggérée.

## Modèles et ascenseur {#models-and-lift}

+++ Mon activité [!UICONTROL Automated Personalization] prend trop de temps pour créer des modèles

Plusieurs choix de configuration d’activité affectent le temps nécessaire à la création des modèles, notamment le nombre d’expériences dans votre activité **[!UICONTROL Automated Personalization]**, le trafic sur votre site et votre mesure de succès sélectionnée.

**Solution :** Vérifiez la configuration de votre activité et vérifiez si vous pouvez apporter des modifications pour accélérer la création des modèles.

* Si votre mesure de succès est définie sur la valeur RPV, pouvez-vous la changer en conversion ? Les activités de conversion tendent à exiger moins de trafic pour compiler des modèles. Vous ne perdez pas de données d’activité si vous modifiez la mesure de succès de RPV à conversion.
* Votre mesure de succès est-elle située loin en arrière dans l’entonnoir de vente par rapport aux expériences de votre activité ? Un taux de conversion d’activité plus faible augmente les exigences de trafic pour la création des modèles, car un nombre minimum de conversions est requis.
* Existe-t-il des offres ou des expériences que vous pouvez exclure de votre activité ? La réduction du nombre d’expériences dans une activité accélère la création de modèles.
* Existe-t-il une page à trafic plus élevé où cette activité serait plus réussie ? Plus il y a de trafic et de conversions dans les emplacements de vos activités, plus les modèles sont créés rapidement.

+++

+++ Mon activité [!UICONTROL Automated Personalization] n’a pas généré d’effet élévateur

Plusieurs facteurs sont requis pour qu’une activité **[!UICONTROL Automated Personalization]** génère un effet élévateur :

* Les offres doivent être suffisamment différentes pour influencer les visiteurs.
* Les offres doivent être situées à un emplacement qui fait la différence par rapport à l’objectif d’optimisation.
* Le trafic et la « puissance » statistique de l’activité doivent être suffisants dans le test pour permettre de détecter l’effet élévateur.
* L’algorithme de personnalisation doit fonctionner correctement.

**Solution :** La meilleure solution consiste d’abord à s’assurer que le contenu et les emplacements qui constituent les expériences de l’activité font réellement la différence sur les taux de réponse globaux, en utilisant un test A/B simple et non personnalisé. Calculez les tailles d&#39;échantillon à l&#39;avance pour vous assurer qu&#39;il y a suffisamment d&#39;énergie pour voir une élévation raisonnable, puis exécutez le test A/B pendant une durée fixe sans l&#39;arrêter ni apporter de modifications. Si les résultats des tests A/B montrent une augmentation statistiquement significative sur une ou plusieurs expériences, une activité personnalisée est susceptible de réussir. Personalization peut fonctionner même s’il n’existe aucune différence dans les taux de réponse globaux des expériences. En règle générale, le problème provient du fait que les offres ou les emplacements n’ont pas un impact suffisamment important sur l’objectif d’optimisation pour être détectés avec une signification statistique.

+++

## Configuration et reporting des activités {#setup-and-reporting}

+++ L’URL de mon activité [!UICONTROL Automated Personalization] affiche le contenu de l’offre sur des pages incorrectes

**Cause :** Dans **[!UICONTROL Automated Personalization]**, les règles de test d’URL et de modèle sont ajoutées à la contrainte d’entrée de requête [!DNL Target] (par exemple, target-global-mbox), où elles sont évaluées une seule fois. Une fois qu’un visiteur se qualifie pour une activité, les règles de ciblage au niveau de la requête [!DNL Target] ne sont pas réévaluées, tandis que l’audience de ciblage est ajoutée aux règles de ciblage de l’emplacement.

**Solution :** Ajoutez les règles de modèle nécessaires en tant qu’audience d’entrée de l’activité. L’évaluation de l’audience se produit à chaque demande (appel).

+++

+++ Les mesures qui dépendent d’une mesure de conversion ne sont jamais converties

Ce comportement est attendu.

Dans une activité **[!UICONTROL Automated Personalization]**, une fois qu’une mesure de conversion (qu’il s’agisse d’un objectif d’optimisation ou d’un objectif de publication) est convertie, le visiteur est libéré de l’expérience et l’activité est redémarrée.

Par exemple, une activité comporte une mesure de conversion (C1) et une mesure supplémentaire (A1) qui dépend de C1. Lorsqu’un visiteur accède à l’activité pour la première fois et n’a converti ni C1 ni A1, A1 n’est pas converti en raison de la dépendance aux mesures de succès. Si le visiteur convertit C1, puis convertit A1, A1 n’est toujours pas converti, car le visiteur est libéré lorsque C1 est converti.

+++

+++ Les URL de mon expérience ne fonctionnent pas comme prévu

**Solution :** Utilisez les actions suivantes :

* Si l’aperçu ne s’affiche pas dans le nouvel onglet (en raison de la mise en cache du navigateur), essayez de l’actualiser deux ou trois fois. Vous pouvez également copier le lien et l’ouvrir dans un nouveau navigateur ou dans une nouvelle session.
* Si vous avez modifié du contenu, régénérez les liens URL d’expérience et partagez les nouveaux liens avec vos coéquipiers.

+++
