---
keywords: kit de bienvenue;kit de bienvenue target;présentation;introduction;prise en main
description: Lisez les conseils de notre panel d’experts sur l’utilisation d’Adobe  [!DNL Target]  dans le cadre de vos efforts de test et de personnalisation.
title: Où trouver des conseils et des astuces pour utiliser Target ?
feature: Overview
exl-id: 86437ad1-83ea-4670-b503-6c3c1fff0c16
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '2883'
ht-degree: 72%

---

# Chapitre 4 : Conseils d’utilisation de Target

Notre travail avec de nombreux utilisateurs [!DNL Target] nous a permis découvrir des moyens d’optimiser la valeur de votre solution [!DNL Target]. Nous les avons résumés dans les nombreux conseils que nous avons inclus dans ce chapitre. Conservez cette liste, même si vous n’êtes pas prêt à mettre toutes ces idées en application immédiatement. Plus vous utiliserez la solution, plus votre programme évoluera et plus vous comprendrez comment ces conseils peuvent vous aider à obtenir de meilleurs résultats avec [!DNL Target].

## Conseil 1 : personnalisation plus approfondie en enrichissant le profil du visiteur de données supplémentaires.

Vous pouvez personnaliser des expériences avec des données [!DNL Target] prêtes à l’emploi. Cependant, vous pouvez effectuer une personnalisation de manière plus approfondie en ajoutant vos propres données au processus. Vous pouvez enrichir votre profil avec des données historiques provenant d’[!DNL Adobe Analytics] et des données en temps réel issues d’[!DNL Adobe Audience Manager]. Vous pouvez également utiliser les attributs du client, une fonctionnalité du service principal People dans [!DNL Adobe Experience Cloud], pour importer facilement des données de gestion de la relation client, des données de partenaires secondaires et des données achetées par des tiers dans [!DNL Target].

Par exemple, vous pouvez associer les données d’achat de votre système de point de vente à un profil visiteur. Pour ce faire, il vous suffit de créer un fichier CSV contenant jusqu’à 200 variables hors ligne, puis de le charger directement dans [!DNL Adobe Experience Cloud] par le biais d’un chargement de fichier, ou d’utiliser un FTP pour héberger et programmer la mise à jour régulière de votre fichier. Une fois que les attributs de votre client se trouvent dans [!DNL Adobe Experience Cloud], vous pouvez les mapper à des solutions [!DNL Experience Cloud] comme [!DNL Adobe Analytics] et [!DNL Target], où ils seront disponibles pour analyse, test et personnalisation.

Consultez [Attributs personnalisés](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html?lang=fr) pour obtenir des instructions détaillées.

**Important** : [!DNL Target] étant une plateforme ouverte et indépendante qui fonctionne bien avec différentes technologies, vous pouvez ajouter des données de gestion de la relation client ou achetées de différentes manières. Cela signifie que vous pouvez choisir la méthode qui convient le mieux à votre organisation.

Consultez [Méthodes de transfert de données dans Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=fr){target=_blank} pour plus d’informations.

## Conseil 2 : personnalisation plus approfondie en mélangeant les audiences [!DNL Target] avec d’autres audiences Adobe Experience Cloud.

La combinaison des audiences qui se trouvent dans différentes solutions [!DNL Adobe Experience Cloud] peut vous permettre de mieux comprendre vos clients et d’effectuer une personnalisation plus approfondie. Par exemple, si [!DNL Target] fournit des données d’audience en temps réel, [!DNL Adobe Analytics] fournit des données d’audience historiques. La combinaison des deux peut vous aider à identifier le moment où le comportement d’un client est cohérent et le moment où il peut être possible d’agir sur un nouveau comportement. Il vous suffit de cliquer sur le menu déroulant en regard de « Tous les visiteurs » lors de la création d’une activité. Ensuite, cochez un maximum de vingt cases d’audiences, cliquez sur « Combiner plusieurs audiences », puis sur « Enregistrer ».

Consultez [Combinaison de plusieurs audiences](/help/main/c-target/combining-multiple-audiences.md) pour obtenir des instructions détaillées.

**Important** : les audiences [!DNL Adobe Audience Manager] sont automatiquement disponibles dans [!DNL Target]. Cependant, le partage d’audiences [!DNL Adobe Analytics] nécessite un minimum de configuration manuelle. Il vous suffit de cocher la case intitulée « La transformer en audience Experience Cloud » lors du processus de création d’audiences en [!DNL Analytics]. Ensuite, dans [!DNL Target], cliquez sur Importer des audiences Experience Cloud.

## Conseil 3 : exportation de données issues de [!DNL Target] pour les utiliser avec des outils tiers.

Grâce aux jetons de réponse, les administrateurs peuvent facilement extraire des données de [!DNL Target] et les intégrer à des outils tiers. Cela peut s’avérer utile lorsque vous souhaitez ajouter vos données aux données collectées dans un outil de sondage. Par exemple, si une enquête révèle qu’un échantillon de la population a attribué la note « 9 » à une expérience et qu’un autre a attribué la note « 4 » à une autre expérience, vous pouvez utiliser vos données pour déterminer qui a vu l’expérience A et qui a vu l’expérience B. Vous pouvez également utiliser des jetons de réponse pour exporter des données [!DNL Target] vers votre entrepôt de données interne. Il vous suffit de cliquer sur « Administration », puis d’activer le bouton en regard du jeton de réponse souhaité. Ensuite, créez une activité. Les données sont alors prêtes à être transférées au fournisseur tiers. Vous pouvez vérifier que [!DNL Target] exporte les données à l’aide d’outils de débogage.

Consultez [Jetons de réponse](/help/main/administrating-target/response-tokens.md) pour obtenir des instructions détaillées.

**Conseil utile** : avant qu’un administrateur puisse activer un jeton de réponse associé à un tiers, un développeur doit établir un partenariat avec cette société tierce.

Consultez [Jetons de réponse](/help/main/administrating-target/response-tokens.md) pour obtenir des instructions détaillées.

**Instructions préalables** : assurez-vous d’utiliser la version 1.1 ou ultérieure d’at.js. Si vous utilisez une version précédente, les jetons de réponse s’affichent, mais at.js ne pourra pas les utiliser.

## Conseil 4 : création d’audiences à partir de ces variables clés pour augmenter la valeur de votre activité.

Lors de la création d’audiences pour le ciblage ou le test de promotions et d’offres, tenez d’abord compte des variables suivantes :

* Comportemental. Modèles de visites sur site et schémas d’achat
* Référent. Sites et campagnes de référence
* Temporel. Horaires, jours de la semaine et facteurs saisonniers
* Hors ligne. Modèles de visites et d’achats dans les magasins physiques
* Environnement. Pays d’origine, système d’exploitation, type de navigateur

## Conseil 5 : attribution aux utilisateurs du niveau d’accès nécessaire pour travailler.

Simplifiez l’utilisation des données de votre organisation tout en assurant leur sécurité. [!DNL Target Premium] permet aux administrateurs de contrôler le niveau d’accès donné aux différentes équipes internes et externes.

Consultez [Autorisations des utilisateurs d’Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) pour plus d’informations.

**Conseil utile** : lors de l’ajout d’utilisateurs, si le nom d’un membre de l’équipe n’a pas été précédemment ajouté à votre organisation, comme cela pourrait être le cas pour un employé d’une agence tierce, la saisie de son adresse e-mail et de son mot de passe déclenche une invitation par e-mail à rejoindre l’espace de travail d’une équipe.

Vous utilisez Target Standard ? Vous pouvez toujours [attribuer trois niveaux d’accès](/help/main/administrating-target/c-user-management/c-user-management/user-management.md) à vos utilisateurs avec des rôles en lecture seule, d’éditeur et d’approbateur.

## Conseil 6 : découverte des performances d’une offre dans un parcours client en la testant sur chaque page du parcours.

Découvrez les performances d’une offre, telle que la livraison gratuite, pendant un parcours client qui se déroule sur plusieurs pages de votre site web.

Consultez [Activité multipage](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md) pour obtenir des instructions détaillées.

**Conseil utile** : la modification de l’URL après avoir spécifié une plage de pages réinitialise l’expérience. Cela signifie que les variations que vous avez spécifiées n’apparaîtront plus. Si vous devez modifier l’URL, pensez à redéfinir l’expérience.

## Conseil 7 : test d’une offre avec différentes audiences pour déterminer si les audiences ont des préférences différentes.

Les versions d’expérience vous permettent d’exécuter un test avec des variations pour autant d’audiences que vous le souhaitez. Par exemple, vous pouvez créer une bannière publicitaire offrant la livraison gratuite (avec des images et des variations de devises pour les clients aux États-Unis, au Royaume-Uni et aux Émirats arabes unis), sans avoir à exécuter de tests pour trois audiences différentes.

Consultez [Audiences d’expériences multiples dans un test A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) pour obtenir des instructions détaillées.

## Conseil 8 : gain de temps en répliquant des expériences d’activité sur des pages similaires.

Créez une variation sur une page web, telle qu’une nouvelle couleur de bouton, et appliquez-la automatiquement à toutes les pages qui partagent le même modèle. Vous pouvez spécifier des pages ou appliquer les variations à toutes les pages similaires sur votre site web.

Consultez [Inclure la même expérience sur des pages similaires](/help/main/c-experiences/c-visual-experience-composer/temtest.md) pour obtenir des instructions détaillées.

## Conseil 9 : réduction de l’encombrement de votre bibliothèque d’audiences en créant des audiences à usage unique.

Si vous ciblez un segment que vous ne ciblerez pas à nouveau (par exemple, les clients affectés par un événement météorologique inattendu), la création d’une audience à usage unique peut vous aider à réaliser votre travail sans encombrer votre bibliothèque d’audiences. Cela permet de retrouver plus facilement les audiences que vous utilisez régulièrement.

Consultez [Création d’une audience d’activité unique](/help/main/c-target/creating-activity-only-audience.md) pour obtenir des instructions détaillées.

**Fonctionnalité très demandée** : nos clients nous ont demandé de faire en sorte que les audiences à usage unique ne soient pas automatiquement enregistrées dans la bibliothèque d’audiences. Désormais, ils ne doivent plus supprimer manuellement les audiences pour que leurs bibliothèques soient organisées.

## Conseil 10 : exécution plus rapide de tests simples en évitant de les soumettre au processus standard d’assurance qualité.

Rien n’est pire que de disposer d’une activité prête à être lancée et d’attendre pendant des semaines qu’elle passe par le processus standard d’assurance qualité. Vous pouvez contrôler la qualité de la plupart des activités en transmettant simplement quelques liens d’assurance qualité à vos collègues pour qu’ils les testent sur différents navigateurs. Il est probable que vous souhaitiez effectuer davantage de tests d’assurance qualité pour les efforts qui changent radicalement la fonction du site, mais en réalité, ces activités sont beaucoup plus rares que les activités de base. L’ajout de contrôles des droits plus efficaces, afin que moins de personnes puissent activer du contenu, permet également de fixer des limites judicieuses et d’atteindre les objectifs requis sans sacrifier la rapidité et l’efficacité. Une autre option consiste à désigner une ressource informatique chargée de superviser le processus d’assurance qualité dans le délai imparti.

Consultez [Assurance qualité des activités](/help/main/c-activities/c-activity-qa/activity-qa.md) pour obtenir des instructions détaillées.

## Conseil 11 : exécution des tests sur les pages à trafic élevé afin d’obtenir une signification statistique plus rapidement.

De nombreux professionnels du marketing lancent des programmes d’optimisation pour la segmentation et le ciblage d’audience sans vérifier si les niveaux de trafic et d’audience représentés produiront des résultats significatifs au cours de la période de test pour leurs objectifs d’optimisation et de conversion. Pour éviter cette erreur courante, répondez préalablement à ces questions :

* Combien de visiteurs uniques par jour la page reçoit-elle ?
* Quel est le taux de conversion de la page ?
* Pendant combien de temps estimez-vous devoir effectuer le test avant de pouvoir le considérer comme terminé ?

**Conseil utile** : utilisez le [!DNL Adobe Target] [Calculateur de taille d’échantillon](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) pour déterminer la taille d’échantillon nécessaire à la réussite du test.

## Conseil 12 : conception de tests plus simples pour s’assurer de pouvoir les créer et les implémenter

Une fois que vous avez examiné tous les aspects de la conception d’un test, le plan peut devenir très complexe. En fonction de l’état d’avancement de votre entreprise en matière de tests, et de la capacité de votre groupe à concevoir, coder, exécuter et analyser les résultats, déterminez si le test semble trop ambitieux. Si tel est le cas, soyez prêt à en réduire la portée et la complexité. Mieux vaut agir progressivement que de ne pas réaliser de test. Vous ne pouvez pas fournir d’effet élévateur efficace si vous ne lancez jamais le test. Il est important d&#39;équilibrer les aspirations de l&#39;équipe avec les réalités de vos ressources et de vos capacités.

## Conseil 13 : division des tests complexes en activités de test plus modestes et donc réalisables.

Au lieu de développer un test important avec plusieurs variables et un développement complexe, développez une série de tests moins complexes avec un minimum de variables. Cela permet de mieux comprendre les performances des tests en fonction de variables spécifiques. Cela réduit également les éventuels problèmes techniques liés au développement de projets plus importants.

![Illustration de la division des tests complexes](/help/main/c-intro/assets/break-complex-tasks.png)

## Conseil 14 : optimisation de l’impact de votre test en effectuant des tests vers la fin de l’entonnoir de conversion.

Les tests effectués aussi près que possible de la page sur laquelle les visiteurs cliquent sur Effectuer l’achat, Soumettre la demande ou Effectuer une conversion donnent généralement les résultats les plus probants. Les visiteurs qui atteignent la fin de l’entonnoir sont plus qualifiés, ont investi plus de temps et sont prêts à passer à l’achat. Par conséquent, tester les informations sur leurs préférences et leurs actions peut vous aider à apporter des changements rentables. Les pages du parcours d’achat étant essentielles pour les taux de conversion, les tests effectués sur ces pages doivent être communiqués aux principales parties prenantes avant d’être déployés.

![Illustration de l’entonnoir de conversion](/help/main/c-intro/assets/conversion-funnel.png)

## Conseil 15 : mise à jour constante de vos tests pour apporter des améliorations itératives.

Si votre hypothèse ne se vérifie pas, réfléchissez aux moyens d’améliorer votre test. N’oubliez pas que même si aucune des expériences testées n’a donné de meilleurs résultats, votre expérience n’a pas été une perte de temps. Un test réussi ne signifie pas toujours une augmentation du chiffre d’affaires ou des conversions. Si le test a vraiment confirmé votre hypothèse, vous êtes sur la bonne voie pour développer une théorie générale. Mais même lorsque vous obtenez un résultat nettement gagnant, ne vous arrêtez pas là. Les professionnels du marketing commettent trop souvent l’erreur de réaliser un seul test, puis de miser sur les résultats obtenus sans vraiment comprendre la raison de cette réussite. Au contraire, envisagez de reproduire ces résultats pour déterminer la clé de la réussite. Ainsi, les informations obtenues seront plus précises et vous pourrez les utiliser dans vos futures campagnes.

## Conseil 16 : comparaison des activités de tests et de personnalisation pour obtenir des idées permettant d’améliorer le ciblage.

La comparaison des performances de conversion de différentes audiences dans le cadre de différents tests effectués à différents emplacements peut aider à cibler et à affiner la stratégie d’optimisation d’une entreprise. Utilisez des comparaisons de tests pour identifier les audiences les plus intéressantes à tester, celles qui devraient recevoir des expériences ciblées et les types d’expériences les plus susceptibles de susciter une réponse.

Par exemple, un client des services financiers a lancé une campagne promotionnelle pour une carte de crédit qui comportait des incentives pour des événements sportifs professionnels. Grâce à des tests multivariés factoriels partiels de ses pages de destination, le client a pu équilibrer de façon optimale les messages sur les avantages des cartes de crédit et les incentives sportifs pour cibler différentes audiences de sa base de clients. Cette approche a permis à la société de tirer parti de la conversion et de l’optimiser lors d’une période critique entourant un événement sportif majeur.

## Conseil 17 : lancement des tests uniquement si l’exploitation des données est possible pour en garantir l’utilité.

Un test est inutile si vous n’êtes pas sûr de la manière dont vous allez agir sur les données. Il s’agit notamment de connaître votre principale mesure de succès, les éléments indispensables au succès, la manière dont vous assurerez le suivi des résultats des tests et les mesures que vous prendrez concernant les informations relatives à l’audience. Pour un test rapide et réussi, il est essentiel que chaque groupe impliqué dans le test (développeurs, talents créatifs, spécialistes des tests, etc.) soit conscient de son rôle avant le lancement du test.

## Conseil 18 : avant le lancement d’un test, il est important de s’assurer que la société est prête à contribuer à la réussite.

Les organisations d’optimisation performantes adhèrent au concept des tests et comprennent que leurs opinions professionnelles, indiquant que le test de l’expérience se révélera concluant, ne se vérifient pas toujours. Ils déterminent l’expérience gagnante sur la base de données solides et sont impatients et disposés à activer l’expérience gagnante une fois les résultats connus, même si elle n’est pas conforme à leurs attentes ou semble contre-intuitive.

Par exemple, un client des services de santé Adobe a récemment prouvé l’utilité des tests en démontrant comment une bannière à forte identification, que l’équipe avait considérée comme un coup de maître, avait en réalité eu un impact négatif sur la conversion. Si votre entreprise n’a pas encore entièrement adopté les tests, il est préférable de commencer par des tests plus simples et de moindre envergure, afin de pouvoir apporter des modifications progressives à partir des résultats des tests.

## Conseil 19 : l’annonce du lancement d’un test permet d’éviter toute inquiétude lors de la modification du site.

L’un des avantages de la configuration de vos activités pour l’utilisation des paramètres d’assurance qualité est que vous pouvez partager ces liens avec tous les membres de votre équipe. Vous informez davantage de personnes sur l’activité et vous vous assurez qu’elles ne supposent pas que le site ne fonctionne pas correctement lorsqu’elles accèdent à une variante de test.

Une fois vos tests terminés, la communication des lancements de campagne, des résultats des tests et, en particulier, des enseignements tirés vous permet d’accroître la sensibilisation et l’intérêt pour les résultats des tests. Le partage des résultats avec tous les membres de l’organisation permet également d’éviter de tester à nouveau une hypothèse, d’éduquer chaque personne sur les méthodes qui fonctionnent et de les aider à fondamentalement remettre en question leurs propres idées sur les méthodes qui fonctionnent, sur la base de vos découvertes. Il est recommandé de préparer un modèle à utiliser à chaque fois que vous partagez vos résultats et vos enseignements clés.
Envisagez ensuite la création d’un livre ou d’une présentation Microsoft PowerPoint à partager reprenant l’ensemble de ces enseignements.

## Conseil 20 : exploitation des fonctionnalités mobiles pour créer des activités mobiles plus innovantes.

Les expériences des utilisateurs de tablettes et de smartphones doivent être axées sur les commandes tactiles comme principale interaction avec les visiteurs, plutôt que sur les clics de souris et les commandes au clavier. Tirez parti des commandes de l’affichage mobile, notamment le glissement des doigts, le toucher, l’action faire glisser, le pincement et le zoom. Utilisez des boutons simples et imposants pour indiquer les interactions et la navigation, comme un grand panier d’achats ou un bouton de lecture vidéo. Si vous concevez une expérience de vente mobile, intégrez une visualisation riche des produits optimisée pour le type d’appareil. Cherchez toujours des occasions de déplacer l’expérience utilisateur vers des fonctionnalités interactives de zoom et panoramique intégrées, pour les grandes visionneuses ou en plein écran, de rotation à 360° degrés et de vidéo améliorée.

## Conseil 21 : optimisation de la recherche mobile pour aider les visiteurs à trouver ce qu’ils cherchent.

Les utilisateurs mobiles ont un haut niveau d’intention. La majorité d’entre eux utilisent la recherche avant de faire quoi que ce soit d’autre sur les sites de commerce mobile, ce qui rend l’optimisation de la recherche sur les sites mobiles cruciale. Utilisez des repères de navigation explicites pour faciliter la navigation afin d’améliorer l’optimisation du moteur de recherche (SEO) pour les appareils mobiles. En outre, implémentez des suggestions automatiques et des corrections automatiques dans les champs de recherche pour résoudre les problèmes de saisie mobile. Offrez des résultats de recherche pertinents et attractifs, optimisés pour la taille et l’emplacement de l’écran.

## Conseil 22 : ciblage plus pertinent des audiences mobiles grâce au ciblage par tranche horaire pour les campagnes de marketing de moteur de recherche mobiles.

Découvrez comment et quand cibler votre audience et comment mieux gérer vos dépenses publicitaires quotidiennes en répartissant vos campagnes mobiles en différents segments de tranches horaires tout au long de la journée.

De nombreux professionnels du marketing commettent l’erreur de ne pas attribuer suffisamment de budget pour conquérir cette part de voix aux heures où l’utilisation de certains appareils est la plus forte, laissant ainsi s’échapper un chiffre d’affaires et des prospects importants.

Par exemple, le pic d’utilisation des tablettes a généralement lieu le soir et de nombreux utilisateurs naviguent en regardant la télévision. En revanche, les utilisateurs de smartphones accèdent généralement au contenu en déplacement. Les temps de conversion de pointe varient également selon le secteur. Il est donc important de comprendre à quel moment vos clients uniques sont les plus susceptibles d’agir.

## Remarque

Songez aux idées suivantes avant de passer au chapitre suivant : « Inspiration pour les activités de test et de personnalisation ».

### Lorsque vous créez vos tests, n’ajoutez pas de fioritures et allez droit au but.

* Contrôlez le flux grâce à des parcours visuels intentionnels axés sur les points de conversion.
* Veillez à utiliser vos biens immobiliers de manière avantageuse.
* Tirez parti de la mise au point des images pour vous assurer qu’elles ne sont pas une simple décoration, mais qu’elles contribuent à votre succès.
* Réduisez l’encombrement, la friction et le flou grâce à la fonction de texte simplifié.
* Assurez-vous de disposer d’appels à l’action efficaces lorsque vous souhaitez que l’utilisateur agisse.
* Ajoutez de la crédibilité par le biais du contenu généré par l’utilisateur lorsque cela est possible.

### Simplifiez votre site web.

* Ne « forcez » pas les clients à lire. Ils ne le feront pas.
* Rendez le contenu simple à parcourir.
* Utilisez des blocs de texte à puces.
* Assurez-vous que votre texte suit un processus de pensée clair et séquentiel.

### Utilisez des appels à l’action efficaces.

* Mettez-vous à la place du client.
* Utilisez un langage orienté vers l’action.
* Tenez compte de la motivation de la conversion.
* Utilisez le résultat de la conversion.
* Assurez-vous que les appels à l’action sont visibles.
