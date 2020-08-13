---
keywords: Target Standard;faq;frequently asked questions;cheat sheet;cheatsheet
description: Liste des questions fréquemment posées à propos des fonctionnalités d’Adobe Target, ainsi que des informations et des liens d’accès à des informations complémentaires.
title: FAQ relative à l’optimisation et la personnalisation de Target
feature: intro
topic: Advanced
uuid: b6052939-6ed4-4c90-b118-77b6fe42b0af
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '2908'
ht-degree: 98%

---


# FAQ relative à l’optimisation et la personnalisation de Target{#target-optimization-and-personalization-faq}

Liste des questions fréquemment posées à propos des fonctionnalités d’Adobe Target, ainsi que des informations et des liens d’accès à des informations complémentaires.

## Informations générales {#section_CE5713B5AAC341C9A75586C107797FA3}

**Comment je peux voir de quelle manière les autres clients ont exploité Adobe Target pour obtenir les meilleurs résultats ?**

Voici quelques [récits de succès de nos clients](https://www.adobe.com/in/marketing-cloud/target/resources.html#x). Découvrez comment des clients tels que vous exploitent Target pour améliorer l’optimisation et la personnalisation et atteindre leurs objectifs de résultat.

Il est à noter que certaines de ces études de cas font appel à des capacités d’Adobe Target Premium.

**Où puis-je en apprendre davantage sur les dernières fonctionnalités de Target ?**

Consultez nos [Notes de mise à jour](../r-release-notes/release-notes.md#reference_8FE40B43A5A34DDF8F26A53D55EE036A) pour prendre connaissance des détails relatifs à la dernière version. Des informations sur toutes nos [versions antérieures](../r-release-notes/release-notes-for-previous-releases.md) sont également disponibles en ligne.

**Existe-t-il une communauté ou un forum qui me permettrait de trouver plus d’informations et de réponses sur Target ?**

Consultez le [forum de la communauté Target](../cmp-resources-and-contact-information.md#concept_9C203A8AED054DFFA9A504811DB6BA42) dans lequel nous aidons nos clients et, ce qui est plus important encore, où nous encourageons les utilisateurs d’Adobe Target à s’entraider. Après tout, le succès d’une communauté et d’un forum repose sur la participation active de ses membres. Devenez membre de la communauté et contribuez à rechercher des réponses à vos questions.

**Quels sont les navigateurs non pris en charge par Target ?**

Veuillez lire notre grille [Navigateurs pris en charge](../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100) pour plus d’informations. Il est à noter que deux aspects doivent être pris en compte : la prise en charge de l’interface de Target Standard/Premium Experience Cloud et la prise en charge du navigateur de l’utilisateur final sur ordinateur de bureau ou les périphériques.

## Bibliothèques JavaScript pour Target (at.js et mbox.js) {#section_C2AC78DFDAD84981A8C84DF20893E340}

**Quel fichier de mise en œuvre de JavaScript dois-je utiliser ; at.js ou mbox.js ?**

at.js représente notre bibliothèque JavaScript la plus récente et la plus complète. mbox.js est notre ancienne version. Reportez-vous à la section [Avantages d’at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) pour comprendre les différences entre les deux bibliothèques. Tous les nouveaux clients sont invités à utiliser at.js.

Tous les clients mbox.js existants sont invités à migrer vers at.js. Découvrez les étapes à suivre pour la [migration de mbox.js vers at.js](../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA) avant d’effectuer la transition.

## Activités {#section_CB95B3BF9934445DB98E8A7E22FC2CF6}

**Puis-je exécuter une activité statistiquement rigoureuse pour trouver une expérience gagnante ou perdante tout en utilisant une expérience témoin ?**

Utilisez le [Test A/B](../c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977) (option de ciblage manuel) en même temps que le [calculateur de taille d’échantillon](../c-activities/t-test-ab/sample-size-determination.md#section_286EB6E671184239BB1552F0387DAEB5) pour obtenir les meilleurs résultats.

**Comment savoir à quel moment arrêter une activité ?**

L’arrêt prématuré d’activités peut déboucher sur des conclusions erronées. Ayez conscience des [écueils communs et assurez-vous de mettre en œuvre les bonnes pratiques pour les éviter](../c-activities/t-test-ab/common-ab-testing-pitfalls.md#section_DF01A97275E44CA5859D825E0DE2F49F). Référez-vous également à [Quelle doit être la durée d’exécution d’un test A/B ?](/help/c-activities/t-test-ab/sample-size-determination.md)

**Comment puis-je exécuter une activité dans une fenêtre temporelle réduite ?**

**Puis-je optimiser mon objectif à mesure que j’exécute le test ?**

Utilisez nos [rapports pour déterminer quelle est l’expérience gagnante](../c-activities/automated-traffic-allocation/determine-winner.md#concept_5741A89ED7224E1285A3BC34B2CCD0F9).

**Puis-je exécuter une activité avec un niveau de personnalisation faisant partie intégrante de l’activité ?**

Consultez l’option [Tests A/B avec le ciblage automatique](../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3).

**Comment savoir quel type d’activité correspond le mieux à mes besoins ?**

Lisez le [Guide des activités Target](../c-activities/target-activities-guide.md#concept_D974B0918EB74B3B8CB07ACD32BF37A1) pour comprendre les situations dans lesquelles chacune des options fournies par Adobe Target s’impose.

Veillez également à tenir compte des [activités de Recommandations](../c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0).

**Comment puis-je découvrir quelles combinaisons d’éléments sur ma page contribuent à son succès et dans quelle mesure chaque élément y contribue ?**

Consultez nos [activités de tests multivariés factoriels complets (MVT)](../c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) avec l’analyse de contribution des éléments pour voir si ces ressources répondent à vos besoins.

Il est à noter que les exigences de trafic augmentent avec les activités MVT.

**Puis-je exécuter une activité s’étendant sur plusieurs pages dont la structure de page est différente ?**

**Puis-je appliquer des offres à différents endroits (par exemple, dans l’entonnoir de passage en caisse) ?**

Testez la fonctionnalité [Activité Multipage](../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), qui vous permet de créer des pages multiples dans les expériences.

**Comment puis-je m’assurer qu’une fois qu’un objectif (principal ou secondaire) a été atteint, un utilisateur n’entre plus jamais dans l’activité, mais qu’il visualise une activité différente à l’avenir ?**

Ce comportement est facile à déclencher grâce à l’option [Paramètres avancés](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_E2FE441AFB324E498793ABB025ED9974) option disponible avec chaque objectif. Vous disposez d’options vous permettant de décider ce qui doit se produire une fois que l’utilisateur a atteint l’objectif, ainsi que la manière dont le comptage doit être incrémenté.

Dans ce cas, vous pouvez sélectionner le paramètre « Incrémenter le décompte, libérer l’utilisateur et autoriser le retour » en même temps que « Par défaut/autre contenu d’activité » pour atteindre l’objectif. Consultez également les autres options disponibles.

**J’ai créé plusieurs objectifs dans mon activité. Puis-je créer une chaîne d’objectifs sous forme d’entonnoir pour les besoins de génération de rapports et d’analyse ?**

**À titre d’exemple, je veux prendre en compte l’objectif B lorsque l’utilisateur a atteint l’objectif A de manière à pouvoir effectuer le suivi numérique d’un entonnoir particulier.**

Target est doté de puissantes fonctions permettant de réaliser cela grâce à notre fonctionnalité de dépendance à plusieurs mesures. Il vous suffit d’[ajouter des dépendances aux autres mesures de succès](../c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B). Vous disposez d’options telles que « Atteint » et « Non atteint », ainsi que de la possibilité de combiner les mesures de plusieurs manières afin de créer n’importe quelle combinaison souhaitée.

**Comment puis-je savoir clairement comment configurer une activité de manière à atteindre mes objectifs ?**

C’est là que les [objectifs](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) entrent en ligne de compte.

Il convient de déterminer dans un premier temps sur quoi vous souhaitez faire porter l’optimisation. Est-ce le chiffre d’affaires, les conversions ou l’engagement ? Chacune de ces options est disponible dans la section des objectifs. Pour chacune d’elles, vous pouvez définir plus précisément quelles mesures un utilisateur doit adopter sur votre site pour déterminer que l’objectif a été atteint.

Cette possibilité est offerte par la sélection du paramètre de l’objectif principal à l’étape 3 du flux de travaux guidé en trois parties. Vous pouvez également ajouter des objectifs supplémentaires afin d’améliorer la génération de rapports.

**Puis-je planifier une activité qui débute et se termine à un moment précis ?**

Appliquez l’étape [fonction de planification dans les objectifs et les paramètres](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) du flux de travaux de l’activité en trois parties en spécifiant les dates de début et de fin.

N’oubliez pas d’activer l’activité. Seules les activités actives respectent la planification spécifiée. Une fois la date de fin atteinte, l’activité passe à l’état Terminé.

**Puis-je apporter une modification uniquement à l’étape de ciblage sans exécuter l’ensemble du flux de travaux guidé en trois étapes pour effectuer l’édition ?**

Vous pouvez facilement le faire en [entrant directement dans l’étape de votre choix à partir de la page d’aperçu de l’activité](../c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0), puis en sortant de cette étape à l’aide de l’option Enregistrer et fermer.

**Puis-je rester sur une étape particulière, continuer à modifier l’activité (le texte de l’offre ou le code personnalisé, par exemple), puis exécuter la vérification QA sous un autre onglet ?**

C’est également possible. Utilisez [simplement l’option Enregistrer pour effectuer des modifications incrémentielles sans quitter l’étape](../c-activities/edit-activity.md#concept_BB064C0D4A194BD1A1AE7CCA1E6BB8F0).

**Comment puis-je prévisualiser et vérifier la qualité d’une activité que je viens de créer ?**

Utilisez notre [puissante fonctionnalité Mode de QA](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) pour exécuter un contrôle qualité. Vous pouvez partager des liens avec votre équipe d’assurance qualité et tester également l’activité de bout en bout, y compris avec la génération de rapports, afin d’être totalement sûr qu’une fois l’activité mise en ligne, elle fonctionnera conformément aux prévisions et aux tests.

**Comment puis-je utiliser le pouvoir décisionnel de Target pour recevoir une expérience ou une offre utilisable dans des applications sur une seule page (SPA) ou des intégrations côté serveur ?**

Utilisez la puissance des [activités d’après les formulaires](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) avec les [offres JSON](../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D) pour atteindre votre objectif.

**J’ai configuré deux activités. Comment puis-je savoir celle qui sera finalement proposée à un visiteur ?**

**Puis-je définir un ordre de priorité entre plusieurs activités ?**

Utilisez le paramètre de priorité disponible à l’étape 3 du flux de travaux guidé en trois parties de Target (sur la page Objectifs et paramètres) pour [définir la priorité des activités](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC).

Il existe deux options :

* Option par défaut, avec trois niveaux (faible, moyen ou élevé)
* Option personnalisée, avec une plage de valeurs de 0 à 999. Pour Personnaliser, activez la fonction Priorités affinées ( Administration > Compositeur visuel d’expérience).

## Audiences {#section_FA6314777ABC46D8B198D6F388051460}

**Puis-je créer un segment d’audience dans une activité spécifique à cette activité ? Je ne crois pas qu’une telle audience devrait être créée dans la bibliothèque d’audiences, puisqu’il n’y a aucun facteur de réutilisation.**

Commencez par utiliser notre [fonction de création d’une audience Activité uniquement](../c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483) pour définir des audiences de niveau local par rapport à l’activité.

**Comment puis-je cibler des utilisateurs d’après leur emplacement ?**

Testez les [audiences Géo](../c-target/c-audiences/c-target-rules/geo.md#concept_5B4D99DE685348FB877929EE0F942670). Consultez la section relative aux niveaux de précision de cette fonctionnalité.

**Puis-je cibler des utilisateurs d’après certains des attributs présents sur la page de session ?**

La meilleure méthode consiste à utiliser les mbox et les [audiences personnalisées](../c-target/c-audiences/c-target-rules/custom-parameters.md#concept_C4C6E00D7C5A4BE9B72D471DB2E3027B) pour offrir une expérience appropriée.

**Puis-je fournir des expériences d’après les attributs des visiteurs au cours de plusieurs visites ?**

**Puis-je répartir le trafic au hasard entre deux lots ?**

Testez la [fonction Scripts de profil](../c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2). Elle offre un puissant moyen de personnaliser les expériences, sous réserve que vous développiez le code correspondant.

**Puis-je commencer une activité avec un moins grand nombre de visiteurs ?**

Utilisez les commandes d’affectation de pourcentages disponibles [à l’étape 2 du flux de travail guidé en trois parties de Target (page de ciblage)](../c-activities/t-test-ab/t-test-create-ab/ab-audience.md#concept_A268236C1224451DB7844BF67F41A087) pour décider comment paramétrer l’activité.

**Je possède également Adobe Analytics et souhaite l’exploiter avec Target. Quelles sont les capacités décisives que j’obtiens en intégrant ces deux solutions ?**

Consultez les aspects suivants du produit :

* [Analytics for Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)
* [Attributs du client](../c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)
* [Audiences](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

## Expériences {#section_5959536B8D6A4BEA8FAA1273338F3451}

**Puis-je exécuter une activité sur plusieurs pages dont la structure est commune ?**

Référez-vous aux [Règles de modèle](../c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) pour inclure de nombreuses pages structurées similaires à l’activité, tout en créant l’expérience sur l’unique adresse URL spécifiée.

**J’en ai assez de voir s’afficher le message « Autoriser votre navigateur à charger les scripts » chaque fois que je tente de charger ma page dans le compositeur d’expérience visuelle (VEC). Comment puis-je éviter cela ?**

La raison est que votre site comporte un contenu mixte, c’est-à-dire qu’il analyse à la fois des ressources HTTP et HTTPS. Demandez à votre équipe IT de passer complètement en mode HTTPS.

Entre-temps, suivez les instructions indiquées dans [Activation du contenu mixte dans votre navigateur](../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/mixed-content.md#concept_46D022D50280468C9EF6D5DF6EFC911C) pour permettre à votre navigateur de charger du contenu mixte. Il s’agit d’une fonctionnalité de sécurité présente sur la plupart des navigateurs récents.

**Puis-je tester le compositeur d’expérience visuelle (VEC) sur mon site même si la bibliothèque at.js de Target n’a pas encore été déployée ?**

Essayez de charger la page avec le [compositeur d’expérience avancé](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D).

**Pourquoi mon site ne se charge-t-il pas dans le compositeur d’expérience visuelle (VEC) ?**

Essayez les [informations de dépannage](../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4) décrites dans notre page d’aide. Contactez l’[assistance technique d’Adobe](../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) si aucune de ces méthodes ne fonctionne.

Nous disposons aussi d’une [approche basée sur les formulaires](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) qui peut permettre de vous débloquer.

Consultez également les explications sur les cas ou les raisons pour lesquelles le [compositeur d’expérience avancé](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) peut être utile. Il se peut que vous deviez contacter votre service informatique pour [allowlist Adobe&#39;s proxy servers](../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#concept_E284B3F704C04406B174D9050A2528A6) as well.

**Mon site est très réactif. Lors de la création d’une activité, comment puis-je m’assurer de prendre en compte les appareils clés ?**

Testez la fonction [Fenêtres d’affichage mobiles](../c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5). Il est à noter que cette fonctionnalité marche uniquement lorsque le compositeur d’expérience avancé est activé.

**J’exploite plusieurs domaines. L’un d’eux nécessite que le compositeur d’expérience avancé soit activé, alors que d’autres ont besoin qu’il soit désactivé. Comment faire ?**

You can always use [Enhanced Experience Composer option at the activity level](../c-experiences/experiences.md#section_34265986611B4AB8A0E4D6ACC25EF91D) to override the default setting ( Administration > Visual Experience Composer).

**Pourquoi aucune option n’est-elle visible pour échanger des images ?**

Contactez Adobe pour [vous assurer que votre compte est configuré pour Scene7](../administrating-target/scene7-settings.md#task_37AD0768EFBA4E588955FE3D5DD670A5). Une fois le provisionnement effectué, vous pourrez permuter aisément les images.

**Je voudrais tester deux expériences différentes, par exemple une remise à plat par rapport à une remise en pourcentage, mais en ciblant les expériences de façon appropriée (en affichant le texte en langue locale ou d’autres devises pour les personnes venant de différents pays). Comment faire ?**

Vous pouvez facilement y parvenir avec notre [fonctionnalité Versions d’expériences multiples](../c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md#task_0138112E283A4A5B9F8AB9AAF2FBC2FF). Veuillez noter les nuances qui caractérisent la livraison lors de ces tests.

**Comment puis-je voir les modifications que j’ai effectuées dans le compositeur d’expérience visuelle (VEC).**

Vos modifications sont toujours affichées dans l’[éditeur de code](../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5) L’onglet Modifications indique le sélecteur CSS ou la mbox que vous avez appliqué(e) à votre offre.

Veuillez noter que le sélecteur CSS est un sélecteur de fichiers Sizzle. Vous pouvez utiliser cette section pour apporter des modifications mineures ou supprimer rapidement certaines offres.

**Je souhaite fournir JavaScript en tant que partie intégrante de l’expérience ou de l’activité afin soit d’apporter des modifications à la volée pour certains éléments dynamiques, soit pour simplement envoyer un appel à une solution tierce. Comment faire ?**

L’une des méthodes consiste à utiliser l’[éditeur de code personnalisé](../c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md#concept_B3A6E9EE3A60406DB640E205EA1745B5). Placez votre option JavaScript dans cette section pour qu’elle soit livrée. Vous avez la possibilité de diffuser ce composant dans l’en-tête ou dans la partie supérieure du corps du message, suivant les besoins.

**Pourquoi ne puis-je pas aller au-delà de la page de connexion dans le compositeur d’expérience visuelle (VEC), ou accéder à une page difficilement accessible et dont je ne connais pas l’adresse URL spécifique ?**

Utilisez les fonctionnalités Composer et Parcourir pour naviguer vers la page de votre choix et commencer à créer votre expérience.

![](assets/vec2.png)

**Comment puis-je accéder à l’expérience de mon choix à l’étape 2 du flux de travaux guidé en trois parties de Target (page de ciblage) ?**

Cliquez sur la miniature qui précède le nom de l’expérience à l’étape 2 pour accéder à l’expérience de votre choix.

![](assets/thumbnail_experiences.png)

**Je suis un ancien utilisateur de Target Classic. Puis-je utiliser mes mbox pour certains cas d’utilisation ?**

Utilisez [l’approche basée sur les formulaires](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) pour créer des activités.

**Puis-je m’assurer que la même expérience est délivrée de façon cohérente sur tous les appareils que possède un utilisateur ?**

Consultez notre programme [Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html), qui vous permet de relier de façon déterministe et probabiliste plusieurs périphériques d’un utilisateur par l’intermédiaire d’une puissante fonction de co-option.

Si vous êtes dans la co-option, un simple indicateur sur la page des objectifs et paramètres suffit à activer la fonctionnalité. La génération de rapports est également modifiée de manière à refléter les personnes au lieu des visiteurs. Adressez-vous à votre interlocuteur Adobe pour plus d’informations sur cette fonctionnalité, car elle n’est pas disponible dans toutes les régions.

**Pourquoi l’offre ou l’expérience que j’ai demandée ne s’affiche-t-elle pas et est-elle remplacée par une autre activité ?**

Utilisez notre [débogueur](../c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA) pour vérifier les [collisions d’activités](../c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E).

## Offres {#section_A547B1EAD0B34FD38D3B87AAF62E3963}

**Je souhaite non pas essayer des changements mineurs, mais plutôt tester une nouvelle page complètement différente.**

**Je veux rediriger les utilisateurs vers une page d’entrée, par exemple un nouveau lancement.**

**Comment faire ?**

Nous proposons une [fonction d’URL de redirection](../c-experiences/c-manage-content/offer-redirect.md#task_33C80CD722564303B687948261484F94) qui vous permet de rediriger les utilisateurs vers la page de votre choix (avec ou sans paramètres de la requête actuelle).

**Pourquoi la diffusion de contenu ne fonctionne-t-elle pas dans mon processus d’AQ ?**

Il est possible que votre site utilise des identifiants dynamiques ou en double, ou des classes dynamiques sur certains éléments. Il se peut que vous deviez évaluer les options de préférences de site au niveau du compte (ou au niveau de l’activité si le problème est spécifique à un domaine ou à une page). Voir [Sélecteurs CSS](/help/administrating-target/visual-experience-composer-set-up.md#css).

**Pourquoi l’offre ou l’expérience que j’ai demandée ne s’affiche-t-elle pas et est-elle remplacée par une autre activité ?**

Utilisez notre [débogueur](../c-activities/c-troubleshooting-activities/content-trouble.md#concept_D2548B486C984B1E97ED7A72075B8EEA) pour vérifier les [collisions d’activités](../c-experiences/c-visual-experience-composer/activity-collisions.md#concept_0BC6B929592744DFA7DA01FF4F91052E).

**Puis-je utiliser le pouvoir décisionnel de Target pour recevoir une expérience ou une offre utilisable dans des applications sur une seule page (SPA) ou des intégrations côté serveur ?**

Utilisez la puissance des [activités d’après les formulaires](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) avec les [offres JSON](../c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D) pour atteindre votre objectif.

## Rapports (y compris Analytics for Target, A4T) {#section_8AECC69BEEB7422E894E7EC44A50BA0A}

**Je possède également Adobe Analytics et souhaite l’exploiter avec Target. Quelles sont les capacités décisives que j’obtiens en intégrant ces deux solutions ?**

Consultez les aspects suivants du produit :

* [Analytics for Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)

* [Attributs du client](../c-target/c-visitor-profile/working-with-customer-attributes.md#concept_16C5C434D32D4EB1AD44A71821F3DEE8)

* [Audiences](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)


**Puis-je répartir très précisément la génération de rapports entre plusieurs segments d’utilisateurs ?**

C’est là qu’entre en jeu la [fonctionnalité d’audiences pour les rapports](../c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_13119392051044FBA6387D9B3B1C43CF), accessible via la page Objectifs et paramètres à l’étape 3 du flux de travaux guidé de l’activité.

Vous avez la possibilité d’ajouter 50 segments de ce type, ainsi que le point d’application (entrée d’activité ou mesure spécifique), afin de disposer d’un moyen puissant d’effectuer cette segmentation ultra-précise.

Il est à noter que Target collecte les données à cette fin dès le moment où vous ajoutez ces audiences. Par conséquent, si vous omettez d’ajouter des segments avant d’exécuter le test, vous n’avez aucune chance d’atteindre votre objectif.

**Je ne parviens pas à définir des audiences avant l’exécution de l’activité. Je trouve que cet aspect des audiences pour les rapports dans les activités de Target est restrictif.**

**Comment puis-je simplifier ce processus ?**

C’est là que [Analytics pour Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) s’avère pratique. Si vous possédez Adobe Analytics, il suffit de choisir Analytics en tant que source pour mettre fin à cette restriction. Vous pouvez alors exécuter des analyses sur n’importe quelle audience et à n’importe quel stade sans avoir besoin de définir les audiences de génération de rapport au préalable.

**Puis-je effectuer des calculs de génération de rapports hors ligne ?**

Utilisez la mbox [Exportation du rapport au format CSV et Exportation des détails des commandes au format CSV](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) sur la page Rapports pour télécharger les données de rapport souhaitées.

**Puis-je modifier l’expérience témoin pour l’évaluation des rapports, ou modifier la méthodologie de comptage des visiteurs par Visites ?**

Pour effectuer ces changements, utilisez [l’engrenage Paramètres sur la page de rapports](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA). Consultez les informations complémentaires sur ces paramètres pour mieux comprendre les raisons pour lesquelles les calculs peuvent varier.

**Comment dois-je interpréter les rapports ?**

Nous avons essayé de rendre les rapports aussi intuitifs que possible avec des fonctions telles que les [barres d’intervalle de confiance, limites de l’effet élévateur, sélections de niveau de pertinence et de confiance et de mesures multiples, vues tabulaires et graphiques, moyennes d’exécution, etc.](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) afin de permettre une analyse de rapports à la fois puissante et simple à utiliser. Vous pouvez évidemment exploiter Analytics si vous utilisez des activités [Analytics pour Target (A4T)](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) afin de réaliser une analyse plus approfondie des audiences.

## Jetons de réponse {#section_C2A7118B4B62482A9D630C2212112A3D}

**Puis-je exécuter une intégration avec un système tiers tel que Google Analytics ou ClickTale pour transmettre les informations d’activité délivrées à un utilisateur final à des fins d’analyse ?**

Nous disposons également d’une solution pour cela, grâce à la [fonctionnalité Jetons de réponse](../administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4).

## Résolution des problèmes {#section_6B8B4DC62AE34066A8C55915E9EC6C19}

**Comment puis-je déterminer le statut de disponibilité d’Adobe Target ?**

Utilisez la page [Adobe État du système](../r-release-notes/system-status-updates.md#concept_5CBDF506BEFA40E483CC7DE0DA915EAD) pour visualiser l’état des produits Adobe et des solutions Experience Cloud, y compris Target. Cette page vous aide à déterminer si les problèmes rencontrés sont liés à des mises à jour du système ou à des tâches de maintenance périodique.

**Fournissez-vous un guide de dépannage ?**

Nous sommes désolés d’apprendre que vous rencontrez des difficultés. Voir [Dépannage de Target](../r-troubleshooting-target/troubleshooting-target.md#reference_A9DB82675D044BD8861F6752A4EE6839) pour obtenir des liens vers les rubriques de résolution des incidents.

## Target pour les applications mobiles {#section_07BA89F2C38747158ECD5B153274AEAF}

**Nous utilisons un SKU mobile. Puis-je créer des activités mobiles ?**

Pour une optimisation et une personnalisation sur mobile, vous devez utiliser des [activités d’après les formulaires](../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) en parallèle du kit [SDK Adobe](../c-target-mobile-app/mobile-enable-target-in-sdk.md#task_FCA99AD0785A44E995468776AE76FE91). Informations complémentaires sur [Target pour les applications mobiles](../c-target-mobile-app/target-mobile-app.md#concept_80126FF457724DE788CE37264A047559).

## API de Target {#section_714E85EFF6E3400389EF2E40D538E1DA}

**Où puis-je en apprendre davantage sur les API de Target ?**

Nous disposons d’une documentation exhaustive sur les API. Consultez la [Documentation sur les API de diffusion, le SDK NodeJS et les API de recommandations](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).