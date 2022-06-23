---
keywords: api, adobe i/o
description: Découvrez comment effectuer une transition à partir de l’Adobe [!DNL Target] API héritées classiques aux nouvelles API sur Adobe I/O.
title: Comment effectuer une transition des API héritées vers l’Adobe I/O ?
feature: Implement Server-side
role: Developer
exl-id: 4b4274a9-b91a-4a79-9b40-8b1909a2d1d1
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 82%

---

# Transition depuis [!DNL Target] API héritées à Adobe I/O

Informations pour vous aider à passer des API héritées de Target vers les nouvelles API d’Adobe I/O.

Avec le déclassement d’Adobe Target Classic, les API connectées à votre compte Target Classic ne sont également plus disponibles. Ce document vous aidera à faire la transition de vos intégrations basées sur des API héritées vers les API Target proposées par Adobe I/O.

Pour plus d’informations sur l’API de documentation Target, voir [API Target et SDK NodeJS](https://developer.adobe.com/target/implement/server-side/).

## Terminologie  {#section_D8286EDAE3B24D208DA432AEF2E88FD9}

| Terme | Description |
|--- |--- |
| API héritée | API associées à votre compte Target Classic. Les appels de ces API sont basés sur une authentification par nom d’utilisateur et mot de passe et utilisent le nom d’hôte `testandtarget.omniture.com`. Si les appels d’API comportent un nom d’utilisateur et un mot de passe dans l’URL de demande, vous devez passer aux API d’Adobe I/O. |
| Adobe I/O | Adobe I/O est la nouvelle passerelle des API Target. Ces API sont connectées à votre compte Target Standard/Premium. Les API Target sur Adobe I/O utilisent une authentification JWT, qui est la norme de l’industrie pour les API d’entreprise sécurisées. |

## Journal {#section_A478EBF637554A2DB5A31661955121ED}

Les API héritées seront mises hors service lorsque Target Classic sera mis hors service :

| Date | Détails |
|--- |--- |
| 17 octobre 2017 | Toutes les méthodes API qui exécutent une opération d’écriture (`saveCampaign`, `copyCampaign`, `saveHTMLOfferContent` et `setCampaignState`) ont été déclassées.<br>Il s’agit de la date à laquelle tous les comptes utilisateur Target Classic ont été définis sur le statut en lecture seule. |
| 14 novembre 2017 | Les API restantes ont été déclassées. Il s’agit de la date à laquelle l’interface utilisateur Target Classic a été déclassée. |

Les API Recommendations Classic ne sont pas affectées par cette chronologie.

## Méthodes équivalentes {#section_DDB42CCC172545B09CB728D794CC466B}

Le tableau suivant répertorie les nouvelles méthodes d’API Target équivalentes aux méthodes d’API héritées. Les nouvelles API renvoient JSON lors de la comparaison à la réponse XML fournie par les API héritées.

Les nouvelles méthodes d’API sont liées à la section correspondante du site de documentation des API. Un exemple est fourni pour chaque méthode d’API. Vous pouvez également utiliser la collection Postman de l’administrateur qui contient des exemples d’appels d’API pour toutes les nouvelles méthodes d’API d’Adobe sur Adobe I/O.

| Groupement | Méthode d’API héritée | Nouvelle méthode d’API | Remarques |
|--- |--- |--- |--- |
| Campagne/Activité | Création d’une campagne | [Création d’une activité AB](https://developers.adobetarget.com/api/#create-ab-activity)<br>[Création d’une activité XT](https://developers.adobetarget.com/api/#create-xt-activity) | Les nouvelles API fournissent des méthodes de création distinctes pour AB et XT. |
|  | Mise à jour d’une campagne | [Mise à jour d’une activité AB](https://developers.adobetarget.com/api/#update-ab-activity)<br>[Mise à jour d’une activité XT](https://developers.adobetarget.com/api/#update-xt-activity) |  |
|  | Copie d’une campagne | S.O. | Utilisez les API de création d’activités. |
|  | Liste des campagnes | [Liste des activités](https://developers.adobetarget.com/api/#list-activities) |  |
|  | État d’une campagne | [Mise à jour de l’état d’une activité](https://developers.adobetarget.com/api/#update-activity-state) |  |
|  | Affichage d’une campagne | [Obtention d’une activité AB par ID](https://developers.adobetarget.com/api/#get-ab-activity-by-id)<br>[Obtention d’une activité XT par ID](https://developers.adobetarget.com/api/#get-xt-activity-by-id) |  |
|  | ID de campagne tiers | S.O. | Si vous utilisez un paramètre thirdpartyID, les méthodes d’activité pertinentes peuvent être utilisées. |
| Offres | Création d’une offre | [Création d’une offre](https://developers.adobetarget.com/api/#create-offer) |  |
|  | Obtention d’une offre | [Obtention d’une offre par ID](https://developers.adobetarget.com/api/#get-offer-by-id) |  |
|  | Liste des offres | [Liste des offres](https://developers.adobetarget.com/api/#list-offers) |  |
|  | Liste des dossiers | S.O. | Les dossiers ne sont pas pris en charge dans Target Standard/Premium. |
| Création de rapports | Rapport sur les performances d’une campagne | [Obtenir un rapport sur les performances AB](https://developers.adobetarget.com/api/#get-ab-performance-report)<br>[Obtenir un rapport sur les performances XT](https://developers.adobetarget.com/api/#get-xt-performance-report) |  |
|  | Rapport d’audit | [Obtention d’un rapport d’audit](https://developers.adobetarget.com/api/#get-audit-report) |  |
|  | Rapport de contenu 1-1 | [Obtenir un rapport sur les performances AP](https://developers.adobetarget.com/api/#get-ap-activity-performance-report) |  |
| Paramètres du compte | Obtention de groupes d’hôtes | [Liste des environnements](https://developers.adobetarget.com/api/#list-environments) |  |

## Exceptions {#section_09CF9A0E289149279783B4801D1B6D4C}

Si vous avez besoin d’une exception, contactez votre gestionnaire de succès client.

## Aide {#section_591F850E2B7A4342B1C233693425415C}

Contactez le service à la clientèle d’Adobe Target (tt-support@adobe.com) si vous avez des questions ou si vous avez besoin d’aide pour passer aux nouvelles API Target sur Adobe I/O.
