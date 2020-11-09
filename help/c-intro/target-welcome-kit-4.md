---
keywords: welcome kit;target welcome kit;intro;introduction;getting started
description: Kit de bienvenue Adobe Target - Chapitre 4 - Conseils pour l’utilisation de la Cible
title: Kit de bienvenue Adobe Target - Chapitre 4 - Conseils pour l’utilisation de la Cible
feature: intro
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '2880'
ht-degree: 0%

---


# Chapitre 4 : Conseils relatifs à l’utilisation de la Cible

Sur la base de notre travail avec de nombreux [!DNL Target] utilisateurs, nous avons observé comment vous pouvez obtenir plus de valeur de votre [!DNL Target] solution. Nous les avons résumées dans les nombreux conseils que nous avons inclus dans ce chapitre. Bien que vous ne soyez pas prêt à utiliser toutes ces idées tout de suite, tenez-vous à cette liste. Plus vous avez d’expérience avec la solution et plus votre programme est mûr, plus vous verrez comment ces conseils peuvent vous aider à accomplir davantage avec [!DNL Target].

## Conseil 1 : Approfondir la personnalisation en enrichissant le profil visiteur de données supplémentaires.

Vous pouvez personnaliser des expériences avec [!DNL Target] des données prêtes à l’emploi. Mais personnalisez plus profondément en ajoutant vos propres données dans le mélange. Vous pouvez augmenter votre profil avec des données historiques issues [!DNL Adobe Analytics] et des données en temps réel provenant de [!DNL Adobe Audience Manager]. Vous pouvez également utiliser les attributs du client, une fonctionnalité du service principal Personnes dans [!DNL Adobe Experience Cloud], pour importer facilement des données de gestion de la relation client, des données de partenaires tiers et des données achetées par des tiers dans [!DNL Target].

Par exemple, vous pouvez associer les données d’achat de votre système de point de vente à un profil visiteur. Pour ce faire, il vous suffit de créer un fichier CSV contenant jusqu’à 200 variables hors ligne, puis de le télécharger directement dans [!DNL Adobe Experience Cloud] un fichier par le biais d’un transfert de fichier, ou d’utiliser le protocole FTP pour héberger et programmer la mise à jour régulière de votre fichier. Une fois les attributs du client présents dans [!DNL Adobe Experience Cloud]votre site, vous pouvez les mapper à [!DNL Experience Cloud] des solutions telles que [!DNL Adobe Analytics] et [!DNL Target] où ils seront disponibles pour l’analyse, les tests et la personnalisation.

Voir Attributs [](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) personnalisés pour obtenir des instructions détaillées.

**A savoir**: Comme [!DNL Target] est une plate-forme ouverte et indépendante qui fonctionne bien avec différentes technologies, vous pouvez ajouter des fonctions de gestion de la relation client ou acheter des données de différentes manières. Cela signifie que vous pouvez choisir une méthode qui fonctionne le mieux pour votre entreprise.

Pour plus d’informations, voir [Méthodes permettant d’intégrer des données dans la Cible](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md) .

## Conseil 2 : Personnalisez plus profondément en mélangeant les audiences Cibles avec d&#39;autres audiences Adobe Experience Cloud.

Le mélange d’audiences qui vivent dans différentes [!DNL Adobe Experience Cloud] solutions peut vous permettre de mieux comprendre vos clients, ainsi que de mieux personnaliser vos produits. Par exemple, bien que [!DNL Target] fournisse des données d’audience en temps réel, [!DNL Adobe Analytics] fournit des données d’audience historiques. La combinaison des deux peut vous aider à déterminer quand le comportement d’un client est cohérent et quand il peut y avoir une opportunité d’agir sur un nouveau comportement. Il vous suffit de cliquer sur le menu déroulant en regard de &quot;Tous les Visiteurs&quot; lors de la création d’une activité. Ensuite, cochez les cases jusqu’à vingt audiences, cliquez sur &quot;Combiner plusieurs Audiences&quot;, puis sur &quot;Enregistrer&quot;.

Voir [Combinaison de plusieurs audiences](/help/c-target/combining-multiple-audiences.md) pour obtenir des instructions détaillées.

**A savoir**: [!DNL Adobe Audience Manager] Les audiences sont disponibles [!DNL Target] automatiquement. Mais le partage des [!DNL Adobe Analytics] audiences nécessite un peu de configuration manuelle. Cochez simplement la case intitulée &quot;Faire de cette audience un Experience Cloud&quot; lors du processus de création d’audiences dans [!DNL Analytics]. Ensuite, à partir de [!DNL Target], cliquez sur &quot;Importer des audiences Experience Cloud&quot;.

## Conseil 3 : Exportez les données de la Cible pour les utiliser avec des outils tiers.

Grâce aux jetons de réponse, les administrateurs peuvent facilement extraire des données de [!DNL Target] et les intégrer à des outils tiers. Cela peut s’avérer utile lorsque vous souhaitez ajouter vos données aux données collectées dans un outil de questionnaire. Par exemple, si un questionnaire montre un échantillon d’une population a marqué une expérience a &quot;9&quot; et qu’un autre a marqué une expérience a &quot;4&quot;, vous pouvez utiliser vos données pour déterminer qui a vu l’expérience A et qui a vu l’expérience B. Vous pouvez également utiliser des jetons de réponse pour exporter [!DNL Target] des données vers votre entrepôt de données interne. Il vous suffit de cliquer sur &quot;Administration&quot;, puis de basculer le commutateur en regard du jeton de réponse souhaité en position Activé. Créez ensuite une activité. Les données sont alors prêtes à être transférées au fournisseur tiers. Vous pouvez vérifier que [!DNL Target] les données sont exportées à l’aide des outils de débogage.

Voir Jetons [de](/help/administrating-target/response-tokens.md) réponse pour obtenir des instructions détaillées.

**Conseil** utile : Avant qu’un administrateur puisse activer un jeton de réponse associé à un tiers, un développeur doit configurer un partenariat avec cette société tierce.

Voir Jetons [de](/help/administrating-target/response-tokens.md) réponse pour obtenir des instructions détaillées.

**Procédez d&#39;abord**: Assurez-vous d’utiliser at.js version 1.1 ou ultérieure. Si vous utilisez une version précédente, vous verrez les jetons de réponse, mais at.js ne pourra pas les utiliser.

## Conseil 4 : Créez des audiences à partir de ces variables clés pour augmenter la valeur de votre activité.

Lors de la création d’audiences pour le ciblage ou le test de promotions et d’offres, tenez d’abord compte des variables suivantes :

* Comportement. Modèles de visites sur site et schémas d’achat
* Référent. Sites et campagnes référents
* Temporel. Horaires, jours de la semaine et facteurs saisonniers
* Hors ligne. Modèles de visite et d’achat dans les magasins physiques
* Environnement. Pays d’origine, système d’exploitation, type de navigateur

## Conseil 5 : Donnez aux utilisateurs le niveau d’accès dont ils ont besoin pour faire leur travail.

Simplifiez l&#39;utilisation des données de votre entreprise tout en les préservant. [!DNL Target Premium] permet aux administrateurs de contrôler le niveau d&#39;accès donné aux différentes équipes internes et externes.

Pour plus d’informations, voir Autorisations [des utilisateurs de l’](/help/administrating-target/c-user-management/property-channel/property-channel.md) entreprise.

**Conseil** utile : Lors de l’ajout d’utilisateurs, si le nom d’un membre de l’équipe n’a pas été précédemment ajouté à votre organisation, par exemple avec un employé d’une agence tierce, la saisie de son adresse électronique et de son mot de passe déclenche une invitation par courrier électronique à rejoindre l’espace de travail d’une équipe.

Utilisation de Target Standard ? Vous pouvez toujours [attribuer trois niveaux d’accès](/help/administrating-target/c-user-management/c-user-management/user-management.md) à vos utilisateurs avec des rôles en lecture seule, d’éditeur et d’approbateur !

## Conseil 6 : Découvrez comment une offre effectue un parcours client en le testant sur chaque page du parcours.

Découvrez comment une offre, telle que l’expédition gratuite, se comporte pendant le voyage d’un client qui se déroule sur plusieurs pages de votre site Web.

Voir activité [](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) multi-page pour obtenir des instructions détaillées.

**Conseil** utile : La modification de l’URL après avoir spécifié une plage de pages réinitialise l’expérience. Cela signifie que les variations que vous avez spécifiées n’apparaîtront plus. Si vous devez modifier l’URL, n’oubliez pas de redéfinir l’expérience.

## Conseil 7 : Testez une offre avec différentes audiences pour déterminer si les audiences ont des préférences différentes.

Avec les versions d’expérience, vous pouvez exécuter un test avec des variations pour autant d’audiences que vous le souhaitez. Par exemple, vous pouvez créer une bannière publicitaire offrant un envoi gratuit (avec des images et des variations de devises pour les clients aux États-Unis, au Royaume-Uni et aux États-Unis), sans avoir à exécuter des tests pour trois audiences différentes.

Pour obtenir des instructions détaillées, reportez-vous à la section relative à [plusieurs audiences d’expérience dans un test](/help/c-activities/t-test-ab/t-test-create-ab/target-experience-to-multiple-audiences.md) A/B et aux versions d’ [expérience dans Adobe Target](https://helpx.adobe.com/target/how-to/experience-versions.html?playlist=/ccx/v1/collection/product/target/seg-%20ment/business-practitioners/explevel/beginner-adls/applaunch/how-to-2/collection.ccx.js?ref=helpx.adobe.com) .

## Conseil 8 : Gagnez du temps en répliquant des expériences d’activité sur des pages similaires.

Créez une variante sur une page Web, telle qu’une nouvelle couleur de bouton, et appliquez-la automatiquement à toutes les pages qui partagent le même modèle. Vous pouvez spécifier des pages ou appliquer les variations à toutes les pages similaires sur votre site Web.

Voir [Inclure la même expérience sur des pages](/help/c-experiences/c-visual-experience-composer/temtest.md) similaires pour obtenir des instructions détaillées.

## Conseil 9 : Réduisez l&#39;encombrement de votre bibliothèque d&#39;Audiences en créant des audiences ponctuelles.

Si vous ciblez un segment dont vous savez qu’il ne se cible plus (par exemple, les clients affectés par un événement météorologique inattendu), la création d’une audience à usage unique peut vous aider à faire le travail sans ajouter de problème à votre bibliothèque d’Audiences. Cela facilite la recherche d&#39;audiences que vous utilisez encore et encore.

Voir [Création d’une audience](/help/c-target/creating-activity-only-audience.md) réservée aux activités pour obtenir des instructions détaillées.

**Capacité** très demandée : Nos clients nous ont demandé de faire en sorte que les audiences à usage unique ne soient pas automatiquement enregistrées dans la bibliothèque d&#39;Audiences. Désormais, ils n&#39;ont plus à supprimer manuellement les audiences pour que leurs bibliothèques soient organisées.

## Conseil 10 : Exécutez des tests simples plus rapidement en ne les mettant pas en conformité avec le processus d&#39;assurance qualité standard.

Il n&#39;y a rien de pire que d&#39;avoir une activité prête à partir et d&#39;attendre des semaines pour qu&#39;elle termine le processus d&#39;assurance qualité standard. Vous pouvez contrôler la plupart des activités en transmettant simplement quelques liens d’assurance qualité à des collègues pour les tester sur différents navigateurs. Il est probable que vous souhaitiez effectuer davantage de tests d’assurance qualité pour les efforts qui modifient considérablement la fonction du site, mais en réalité, vous devriez avoir moins de ces activités et beaucoup plus d’activités de base. Ajouter de meilleurs contrôles des droits pour que moins de personnes puissent pousser les choses pleinement en vie ajoute également des limites significatives et vous permet d&#39;accomplir ce dont vous avez besoin sans sacrifier la vitesse et l&#39;efficacité. Une autre option consiste à disposer d&#39;une ressource informatique désignée pour assurer une surveillance opportune du processus d&#39;AQ.

Pour obtenir des instructions détaillées, reportez-vous à la section Contrôle qualité [des](/help/c-activities/c-activity-qa/activity-qa.md) Activités.

## Conseil 11 : Exécutez des tests sur les pages à fort trafic afin qu’elles atteignent une signification statistique plus rapidement.

De nombreux spécialistes du marketing lancent des programmes d’optimisation pour la segmentation et le ciblage des audiences sans vérifier si les niveaux de trafic et les audiences représentés produiront des résultats significatifs au cours de la période de test pour leurs objectifs d’optimisation et de conversion. Pour éviter cette erreur commune, répondez à ces questions à l&#39;avance :

* Combien de visiteurs uniques par jour la page compte-t-elle ?
* Quel est le taux de conversion de la page ?
* Combien de temps pensez-vous devoir exécuter le test avant de pouvoir l’appeler en toute confiance ?

**Conseil** utile : Utilisez le calculateur [de taille d’](https://docs.adobe.com/content/target-microsite/testcalculator.html) échantillon de la Cible pour déterminer la taille d’échantillon requise pour un test réussi.

## Conseil 12 : Concevez des tests plus simples pour vous assurer que vous pouvez les créer et les mettre en oeuvre.

Après avoir examiné tous les aspects de la conception d&#39;un test, un plan peut devenir très complexe. En fonction de l’emplacement de votre entreprise dans le cadre des tests et de la capacité de votre groupe à concevoir, coder, exécuter et analyser les résultats, déterminez si le test semble trop ambitieux. Si tel est le cas, soyez prêts à en réduire la portée et la complexité. Mieux vaut début petit que pas du tout effectuer le test. Vous ne pouvez pas fournir un effet élévateur impactable si vous ne lancez jamais le test. Il est important d’équilibrer les aspirations de l’équipe avec les réalités de vos ressources et de vos capacités.

## Conseil 13 : Réduisez des tests complexes en activités de test plus petites pour les rendre réalisables.

Au lieu de développer un test volumineux avec plusieurs variables et un développement complexe, développez une série de tests moins complexes avec des variables minimales. Cela permet de mieux comprendre les performances des tests en fonction de variables spécifiques. Il réduit également les problèmes techniques qui peuvent découler du développement de projets plus vastes.

![Illustration de la rupture de tests complexes](/help/c-intro/assets/break-complex-tasks.png)

## Conseil 14 : Optimisez l&#39;impact de votre test en le testant plus près de la fin de l&#39;entonnoir de conversion.

Les tests effectués à proximité de la page sur laquelle les visiteurs cliquent sur Acheter terminé, Soumettre la demande ou effectuer une autre conversion tendent à avoir le plus d’impact. Les visiteurs qui atteignent la fin de l&#39;entonnoir sont plus qualifiés, ont investi plus de temps et sont prêts à acheter, de sorte que tester les connaissances sur leurs préférences et actions peut vous aider à effectuer des changements rentables. Les pages du chemin d&#39;achat étant essentielles pour les taux de conversion, les tests effectués sur ces pages doivent être socialisés avec les principaux intervenants avant de les déployer.

![Illustration de l&#39;entonnoir de conversion](/help/c-intro/assets/conversion-funnel.png)

## Conseil 15 : Mettez constamment à jour vos tests pour apporter des améliorations itératives.

Si votre hypothèse ne s&#39;est pas avérée vraie, réfléchissez aux moyens d&#39;améliorer votre test. Rappelez-vous que même si aucune des expériences testées n’a été meilleure, votre expérience n’a pas été une perte de temps. Un test réussi ne signifie pas toujours une augmentation des recettes ou des conversions. Si le test a vraiment soutenu votre hypothèse, alors vous êtes en train de développer une théorie générale. Mais même si vous obtenez un résultat net, ne vous arrêtez pas là. Trop souvent, les spécialistes du marketing commettent l&#39;erreur de tester une fois puis de miser sur ces résultats sans vraiment comprendre ce qui a conduit au succès. Au lieu de cela, prévoyez d&#39;itérer sur ces résultats pour comprendre pourquoi le favori était en avance. Vous obtiendrez ainsi des informations plus précises que vous pourrez utiliser dans les campagnes futures.

## Conseil 16 : Comparez les tests et les activités de personnalisation pour trouver des idées pour améliorer le ciblage.

La comparaison des performances de conversion de différentes audiences dans différents tests à différents emplacements peut aider à cibler et à affiner la stratégie d&#39;optimisation d&#39;une société. Utilisez les comparaisons de tests pour identifier les audiences qui présentent le plus de valeur à tester, celles qui doivent recevoir des expériences ciblées et les types d’expériences qui sont le plus susceptibles de générer une réponse.

Par exemple, un client de services financiers a lancé une campagne promotionnelle pour une carte de crédit qui comportait des incitations au événement sportif professionnel. Grâce à des tests factoriels multivariés partiels de ses landings page, le client a été en mesure d&#39;équilibrer de façon optimale les messages sur les avantages des cartes de crédit avec des incitations sportives pour cible d&#39;audiences distinctes de sa base de clients. Cette approche a permis à la société de tirer parti et d&#39;optimiser la conversion lors d&#39;une fenêtre sensible au temps entourant un événement sportif majeur.

## Conseil 17 : Rendez les tests utiles en les lançant uniquement si vous savez que vous pouvez agir sur les données.

Un test est inutile si vous n’êtes pas clair sur la façon dont vous allez agir sur les données. Il s’agit notamment de connaître votre mesure de réussite clé, de savoir ce qui doit se passer pour pousser un gagnant, de savoir comment vous allez suivre les résultats des tests et de savoir ce que vous allez faire avec les informations sur l’audience. Pour un test rapide et réussi, il est essentiel que tous les groupes impliqués dans le test (développeurs, créatifs, spécialistes de test, etc.) soient conscients de son rôle avant le lancement du test.

## Conseil 18 : Avant de lancer un test, assurez-vous que l’entreprise prend en charge la promotion du gagnant.

Les organisations d&#39;optimisation qui réussissent croient au concept de test et comprennent que leurs opinions professionnelles sur ce qui va gagner le test ne se vérifient pas toujours. Ils déterminent le gagnant sur la base de données solides et sont désireux et désireux de diffuser l’expérience gagnante une fois les résultats atteints, même si elle n’est pas conforme à leurs attentes ou semble contre-intuitive.

Par exemple, un client des services de santé Adobe a récemment démontré l&#39;utilité de tester en montrant comment une bannière à forte identification que l&#39;équipe avait considérée comme un &quot;slam dunk&quot; a effectivement eu un impact négatif sur la conversion. Si votre entreprise n’a pas encore entièrement adopté les tests, il est préférable d’effectuer d’abord des tests plus simples et de portée plus petite afin que les modifications des résultats des tests puissent être effectuées progressivement.

## Conseil 19 : Indiquez à tout le monde que vous avez lancé un test afin d’éviter toute inquiétude lorsque le site change.

L’un des avantages de la configuration de vos activités pour l’utilisation des paramètres d’assurance qualité est que vous pouvez partager ces liens avec tous les membres de votre équipe. Vous sensibilisez davantage de personnes à l’activité et vous assurez qu’elles ne supposent pas que le site ne fonctionne pas correctement lorsqu’elles atteignent une variante de test.

Une fois les tests terminés, la communication des lancements de campagne, des résultats des tests et, en particulier, des leçons apprises vous aide à sensibiliser et à vous intéresser aux résultats des tests. Le partage des résultats avec tous les membres de l&#39;organisation évite également de tester une hypothèse, éduque tout le monde sur ce qui fonctionne et les aide à remettre en question fondamentalement leurs propres idées sur ce qui fonctionne en fonction de ce que vous avez trouvé. Il est recommandé de préparer un modèle que vous utilisez à chaque fois pour partager vos conclusions et vos enseignements clés.
Envisagez ensuite la création d&#39;un livre partagé ou d&#39;un jeu de cartes Microsoft PowerPoint qui capture cumulativement ces enseignements.

## Conseil 20 : Tirez parti de la fonctionnalité mobile pour créer des activités mobiles plus innovantes.

Les utilisateurs de tablette et de smartphone doivent se concentrer sur les commandes tactiles comme Principale interaction visiteur plutôt que sur les clics de la souris et les commandes du clavier. Tirez parti des commandes d&#39;affichage mobiles, notamment le glissement des doigts, le toucher, la glissement, la pincement et le zoom. Utilisez des boutons simples et volumineux pour désigner les interactions et la navigation, tels qu’un grand panier ou un bouton de lecture vidéo. Si vous concevez pour la vente au détail mobile, incorporez une visualisation de produit enrichi optimisée pour le type de périphérique. Cherchez toujours des opportunités pour que l’utilisateur se concentre sur des visionneuses incorporées de grande taille ou sur un panoramique et un zoom interactifs plein écran, une rotation à 360 degrés et des fonctionnalités vidéo améliorées.

## Conseil 21 : Aidez les visiteurs mobiles à trouver ce qu&#39;ils veulent en optimisant la recherche mobile.

Les utilisateurs de mobiles ont un haut niveau d&#39;intention. La majorité d&#39;entre eux utilisent la recherche avant de faire quoi que ce soit d&#39;autre sur les sites de commerce électronique, ce qui rend l&#39;optimisation de la recherche sur les sites mobiles cruciale. Pour améliorer l&#39;optimisation de votre moteur de recherche (optimisation du référencement) pour les dispositifs portables, utilisez des repères de navigation explicites pour faciliter la navigation. En outre, implémentez des suggestions automatiques et des corrections automatiques dans les zones d’entrée de recherche pour résoudre les problèmes de saisie mobile. Fournissez des résultats de recherche pertinents et convaincants, optimisés pour la taille et l’emplacement de l’écran.

## Conseil 22 : Mieux cibler les audiences mobiles en utilisant le ciblage temporel de la journée pour les campagnes MMR mobiles.

Comprenez comment et quand atteindre votre audience et comment mieux gérer vos dépenses publicitaires quotidiennes en &quot;divisant&quot; vos campagnes mobiles en plusieurs segments tout au long de la journée.

De nombreux spécialistes du marketing ont commis l&#39;erreur de ne pas allouer suffisamment de budget pour capturer cette part de voix dans les heures où l&#39;utilisation de certains appareils est la plus lourde, laissant ainsi beaucoup de recettes et de pistes sur la table.

Par exemple, l&#39;utilisation des tablettes augmente généralement le soir et de nombreux utilisateurs naviguent en regardant la télévision. En revanche, les utilisateurs de smartphone accèdent généralement au contenu en déplacement. Les temps de conversion de pointe varient également selon le secteur d’activité. Il est donc important de déterminer à quel moment vos clients sont les plus susceptibles d’agir.

## Gardez à l’esprit

Examinons les idées suivantes avant de passer au chapitre suivant : &quot;Inspiration pour les activités de test et de personnalisation.&quot;

### Lorsque vous créez vos tests, ne décorez pas, soyez intentionnels.

* Contrôlez le flux avec des chemins d’oeil intentionnels axés sur les points de conversion.
* Veillez à utiliser votre bien immobilier à votre avantage.
* Tirez parti de la mise au point des images pour vous assurer que les images ne sont pas décoratives, mais qu’elles fonctionnent pour vous.
* Réduisez l&#39;encombrement, la friction et le flou grâce à la fonction de copie simplifiée.
* Assurez-vous d’avoir des appels à l’action efficaces lorsque vous avez besoin que l’utilisateur agisse.
* Ajoutez la crédibilité par le biais du contenu généré par l’utilisateur lorsque cela est possible.

### Simplifiez votre site Web.

* Ne &quot;faites pas lire&quot; les clients. Ils ne le feront pas.
* Facilite la numérisation.
* Utilisez des blocs de copie à puces.
* Assurez-vous que votre copie suit un processus de pensée clair et séquentiel.

### Utiliser des appels à l&#39;action efficaces (DEC)

* Mettez-vous à la place du client.
* Utiliser un langage orienté vers l&#39;action.
* Considérons la motivation de la conversion.
* Adresse le résultat de la conversion.
* Assurez-vous que les DEC sont visibles !