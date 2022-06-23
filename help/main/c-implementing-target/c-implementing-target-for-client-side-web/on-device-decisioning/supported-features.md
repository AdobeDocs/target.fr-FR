---
keywords: implémentation;bibliothèque javascript;js;atjs;prise de décision sur les appareils;prise de décision sur les appareils;fonctionnalités prises en charge
description: Découvrez les fonctionnalités prises en charge pour la prise de décision sur l’appareil.
title: Quelles fonctionnalités sont prises en charge dans la prise de décision sur les périphériques ?
feature: at.js
role: Developer
exl-id: 3531ff55-c3db-44c1-8d0a-d7ec2ccb6505
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 13%

---

# Fonctionnalités prises en charge pour la prise de décision sur l’appareil

Le [!DNL Adobe Target] Le SDK JS offre aux clients la possibilité de choisir entre les performances et l’actualisation des données pour les décisions. En d’autres termes, si la diffusion de contenu personnalisé le plus pertinent et attrayant par le biais de l’apprentissage automatique est la plus importante pour vous, un appel au serveur en direct doit être effectué. Mais lorsque les performances sont plus critiques, une décision doit être prise sur l’appareil et en mémoire. Pour que la prise de décision sur appareil fonctionne, reportez-vous aux sections suivantes qui répertorient les fonctionnalités prises en charge.

## Types d’activité pris en charge

Le tableau suivant indique laquelle [types d’activités](/help/main/c-activities/target-activities-guide.md) créé par la fonction [Compositeur d’expérience d’après les formulaires](/help/main/c-experiences/form-experience-composer.md) ou [Compositeur d’expérience visuelle](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) sont pris en charge ou non pour la prise de décision sur l’appareil.

| Type d’activité | Pris en charge ? |
| --- | --- |
| [Test A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Oui |
| [affectation automatique](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Non |
| [ciblage automatique](/help/main/c-activities/auto-target/auto-target-to-optimize.md) ![Premium](/help/main/assets/premium.png) | Non |
| [Test multivarié](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Non |
| [Ciblage d’expérience](/help/main/c-activities/t-experience-target/experience-target.md) (XT) | Oui |
| [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) ![Premium](/help/main/assets/premium.png) | Non |
| [Recommendations](/help/main/c-recommendations/recommendations.md) ![Premium](/help/main/assets/premium.png) | Non |
| [Activités utilisant Analytics pour Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Oui |

## Ciblage de l’audience

Le tableau suivant indique les règles d’audience prises en charge ou non pour la prise de décision sur les appareils.

| Règle d’audience | Pris en charge ? |
| --- | --- |
| [Géo](/help/main/c-target/c-audiences/c-target-rules/geo.md) | Oui |
| [Réseau](/help/main/c-target/c-audiences/c-target-rules/network.md) | Non |
| [Mobile](/help/main/c-target/c-audiences/c-target-rules/mobile.md) | Non |
| [Paramètres personnalisés](/help/main/c-target/c-audiences/c-target-rules/custom-parameters.md) | Oui |
| [Système d’exploitation](/help/main/c-target/c-audiences/c-target-rules/operating-system.md) | Oui |
| [Pages du site](/help/main/c-target/c-audiences/c-target-rules/site-pages.md) | Oui |
| [Navigateur](/help/main/c-target/c-audiences/c-target-rules/browser.md) | Oui |
| [Profil du visiteur](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md) | Non |
| [Sources de trafic](/help/main/c-target/c-audiences/c-target-rules/traffic-sources.md) | Non |
| [Période](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | Oui |
| Audiences Adobe Experience Cloud<br>(Audiences de [!DNL Adobe Analytics], [!DNL Adobe Audience Manager], et [!DNL Adobe Experience Manager] | Non |

### Ciblage géographique pour la prise de décision sur les appareils

Pour maintenir une latence minimale pour les activités de prise de décision sur les appareils avec les audiences basées sur la géolocalisation, Adobe vous recommande de fournir les valeurs géographiques vous-même dans l’appel à [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/). Définissez l’objet Geo dans le contexte de la requête. Cela signifie, à partir du navigateur, un moyen de déterminer l’emplacement de chaque visiteur. Par exemple, vous pouvez effectuer une recherche IP/géo à l’aide d’un service que vous configurez. Certains fournisseurs d’hébergement, tels que Google Cloud, fournissent cette fonctionnalité par le biais d’en-têtes personnalisés dans chaque `HttpServletRequest`.

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

Cependant, si vous ne parvenez pas à effectuer des recherches IP vers géo sur votre serveur, mais que vous souhaitez tout de même effectuer des prises de décision sur l’appareil pour [getOffers](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/)Les demandes {target=_blank} qui contiennent des audiences basées sur la géolocalisation, cela est également pris en charge. L’inconvénient de cette approche est qu’elle utilise une recherche distante IP/géo, ce qui ajoute une latence à chaque `getOffers` appelez . Cette latence doit être inférieure à une `getOffers` appel avec prise de décision côté serveur, car il atteint un réseau de diffusion de contenu situé près de votre serveur. Indiquez uniquement le champ &quot;ipAddress&quot; dans l’objet Geo dans le contexte de votre requête pour que le SDK récupère la géolocalisation de l’adresse IP de votre visiteur. Si un autre champ en plus de &quot;ipAddress&quot; est fourni, la variable [!DNL Target] Le SDK ne récupère pas les métadonnées de géolocalisation pour la résolution.

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

### Méthode d’affectation

Le tableau suivant indique les méthodes d’attribution prises en charge ou non pour la prise de décision sur l’appareil.

| Méthode d’affectation | Pris en charge ? |
| --- | --- |
| Manuel | Oui |
| [Auto affecter à la meilleure expérience](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Non |
| [Ciblage automatique pour les expériences personnalisées](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Non |
