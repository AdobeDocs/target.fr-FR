---
keywords: implémentation ; bibliothèque javascript ; js ; atjs ; prise de décision sur périphérique ; prise de décision sur périphérique ; fonctionnalités prises en charge
description: Découvrez les fonctionnalités prises en charge pour la prise de décision sur périphérique.
title: Quelles fonctionnalités sont prises en charge dans la prise de décision sur le périphérique ?
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
translation-type: tm+mt
source-git-commit: 62a3b387445977a1bdcd2cf45306c8ff032fca50
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 11%

---

# Fonctionnalités prises en charge pour la prise de décision sur périphérique

Le [!DNL Adobe Target] SDK JS offre aux clients la possibilité de choisir entre les performances et la fraîcheur des données pour les décisions. En d’autres termes, si la diffusion du contenu personnalisé le plus pertinent et attrayant par le biais de l’apprentissage automatique est la plus importante pour vous, un appel au serveur en direct doit être effectué. Mais lorsque les performances sont plus critiques, une décision sur périphérique et en mémoire doit être prise. Pour que la prise de décision sur périphérique fonctionne, reportez-vous aux sections suivantes qui liste les fonctionnalités prises en charge.

## Types d’activité pris en charge

Le tableau suivant indique les [types d’activité](/help/c-activities/target-activities-guide.md) créés par le compositeur d’expérience d’après les formulaires [ou le compositeur d’expérience visuelle](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (compositeur d’expérience visuelle) pris en charge ou non pour la prise de décision sur le périphérique.](/help/c-experiences/form-experience-composer.md)[

| Type d&#39;activité | Pris en charge ? |
| --- | --- |
| [Test A/B](/help/c-activities/t-test-ab/test-ab.md) | Oui |
| [affectation automatique](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Non |
| [ciblage automatique](/help/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/assets/premium.png) | Non |
| [Test multivarié](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Non |
| [Ciblage](/help/c-activities/t-experience-target/experience-target.md)  d’expérience (XT) | Oui |
| [](/help/c-activities/t-automated-personalization/automated-personalization.md) ![Personnalisation automatisée Premium](/help/assets/premium.png) | Non |
| [](/help/c-recommendations/recommendations.md) ![RecommendationsPremium](/help/assets/premium.png) | Non |
| [Activités utilisant Analytics pour Cible](/help/c-integrating-target-with-mac/a4t/a4t.md)  (A4T) | Oui |

## Ciblage des Audiences

Le tableau suivant indique les règles d’audience prises en charge ou non pour la prise de décision sur le périphérique.

| Règle d&#39;Audience | Pris en charge ? |
| --- | --- |
| [Géo](/help/c-target/c-audiences/c-target-rules/geo.md) | Oui |
| [Réseau](/help/c-target/c-audiences/c-target-rules/network.md) | Non |
| [Mobile](/help/c-target/c-audiences/c-target-rules/mobile.md) | Non |
| [Paramètres personnalisés](/help/c-target/c-audiences/c-target-rules/custom-parameters.md) | Oui |
| [Système d’exploitation](/help/c-target/c-audiences/c-target-rules/operating-system.md) | Oui |
| [Pages du site](/help/c-target/c-audiences/c-target-rules/site-pages.md) | Oui |
| [Navigateur](/help/c-target/c-audiences/c-target-rules/browser.md) | Oui |
| [Profil du visiteur](/help/c-target/c-audiences/c-target-rules/visitor-profile.md) | Non |
| [Sources de trafic](/help/c-target/c-audiences/c-target-rules/traffic-sources.md) | Non |
| [Période](/help/c-target/c-audiences/c-target-rules/time-frame.md) | Oui |
| audiences Adobe Experience Cloud<br>(Audiences de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] et [!DNL Adobe Experience Manager] | Non |

### Ciblage géographique pour la prise de décision sur le périphérique

Pour maintenir une latence minimale pour les activités de prise de décision sur périphérique avec des audiences basées sur la géolocalisation, Adobe vous recommande de fournir les valeurs de géolocalisation vous-même dans l&#39;appel à [getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md). Définissez l’objet Geo dans le contexte de la demande. Cela signifie à partir du navigateur, une façon de déterminer l’emplacement de chaque visiteur. Par exemple, vous pouvez effectuer une recherche IP/géo à l’aide d’un service que vous configurez. Certains fournisseurs d’hébergement, tels que Google Cloud, fournissent cette fonctionnalité par le biais d’en-têtes personnalisés dans chacun des `HttpServletRequest`.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				city: "SAN FRANCISCO", 
				countryCode: "US", 
				stateCode: "CA", 
				latitude: 37.75, 
				longitude: -122.4 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

Cependant, si vous ne pouvez pas effectuer de recherches IP-géo sur votre serveur, mais que vous souhaitez toujours prendre une décision sur le périphérique pour les demandes [getOffers](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) qui contiennent des audiences basées sur la géographie, ceci est également pris en charge. L&#39;inconvénient de cette approche est qu&#39;elle utilise une recherche IP/géo distante, ce qui ajoute de la latence à chaque appel `getOffers`. Cette latence doit être inférieure à un appel `getOffers` avec prise de décision côté serveur, car elle atteint un CDN situé près de votre serveur. Fournissez uniquement le champ &quot;ipAddress&quot; dans l’objet Geo dans le contexte de votre demande pour que le SDK récupère l’emplacement géographique de l’adresse IP de votre visiteur. Si un autre champ en plus de &quot;ipAddress&quot; est fourni, le SDK [!DNL Target] ne récupère pas les métadonnées de géolocalisation pour résolution.

```javascript
window.adobe.target.getOffers({ 
	decisioningMethod: "on-device", 
	request: { 
		context: { 
			geo: { 
				ipAddress: "127.0.0.1" 
			} 
		}, 
		execute: { 
			pageLoad: {} 
		} 
	} 
})
```

### Méthode d’allocation

Le tableau suivant indique les méthodes d’attribution prises en charge ou non pour la prise de décision sur le périphérique.

| Méthode d’allocation | Pris en charge ? |
| --- | --- |
| Manuel | Oui |
| [Affectation automatique à la meilleure expérience](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Non |
| [Cible automatique pour les expériences personnalisées](/help/c-activities/auto-target/auto-target-to-optimize.md) | Non |
