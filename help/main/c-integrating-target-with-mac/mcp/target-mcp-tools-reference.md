---
solution: Target
product: target
title: Référence sur les outils du serveur MCP Adobe Target
description: Référence complète des paramètres pour les 39 outils publics exposés par le serveur MCP Adobe Target.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
hide: true
source-git-commit: d24958d17ff62e957a8d3d6602abfcc8dfd67e46
workflow-type: tm+mt
source-wordcount: '2688'
ht-degree: 15%

---

# Référence des outils du serveur [!DNL Adobe Target] MCP {#target-mcp-tools-reference}

>[!BEGINSHADEBOX]

Table des matières :

* [Utiliser les clients MCP](target-mcp.md)
* **[Référence des outils du serveur MCP](target-mcp-tools-reference.md)**
* [Auto-hébergement du serveur MCP](target-mcp-self-hosted.md)

>[!ENDSHADEBOX]

Cette page est une référence complète pour tous les outils publics exposés par le serveur MCP [!DNL Adobe Target]. Pour chaque outil, vous trouverez une description, les détails des paramètres, la valeur renvoyée et un exemple d’invite en langage naturel. Pour obtenir des instructions de configuration et des cas pratiques, voir [Utilisation de clients MCP](target-mcp.md).

>[!NOTE]
>
>Seuls les outils publics sont documentés ici. Les outils internes et réservés aux agents sont exclus. Les outils de lecture sont disponibles pour tous les utilisateurs connectés ayant un rôle **Observateur** ou supérieur ; les outils d’écriture nécessitent un rôle **Éditeur** ou **Approbateur**.

## Outils d’activité {#tools-activities}

+++list_target_activities

Liste [!DNL Adobe Target] activités avec filtrage et tri côté serveur.

Récupère une liste paginée d’activités. Tous les filtres sont appliqués côté serveur par l’API [!DNL Target] Admin. Le serveur renvoie au maximum 200 activités par page.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `limit` | Entier | Non | Nombre maximum d’activités à retourner (serveur max : 200) |
| `offset` | Entier | Non | Nombre d’activités à ignorer pour la pagination |
| `sort_by` | string | Non | Champ par lequel trier. Préfixe avec `-` pour l’ordre décroissant (par exemple, `-modifiedAt`). Options : `id`, `name`, `state`, `priority`, `startsAt`, `endsAt`, `lifetimeStart`, `lifetimeEnd`, `createdAt`, `createdBy`, `modifiedAt`, `modifiedBy`, `type`, `thirdPartyId` |
| `state` | string | Non | Filtrer par état d’activité : `approved` (actif/actif), `deactivated` (inactif), `paused`, `saved` (brouillon) |
| `activity_type` | string | Non | Filtrer par type : `ab` (test A/B), `xt` (ciblage d’expérience), `abt` (Automated Personalization) |
| `name_contains` | string | Non | Filtrer les activités dont le nom contient cette chaîne (non-respect de la casse) |
| `starts_after` | string | Non | Date ISO 8601 — activités commençant après cette date |
| `starts_before` | string | Non | Date ISO 8601 — activités commençant avant cette date |
| `modified_after` | string | Non | Date ISO 8601 — activités modifiées après cette date |
| `ends_after` | string | Non | Date ISO 8601 — activités se terminant après cette date |
| `ends_before` | string | Non | Date ISO 8601 — activités se terminant avant cette date |
| `workspace` | string | Non | Filtrer par ID d’espace de travail |
| `segment_id` | string | Non | Filtrer par identifiant de segment d’audience |
| `profile_attribute_id` | string | Non | Filtrer par ID d’attribut de profil |
| `priority` | Entier | Non | Filtrer par valeur de priorité exacte (0-999) |
| `mbox` | string | Non | Filtrer par nom de mbox/d’emplacement |
| `offer_id` | string | Non | Filtrer par identifiant d’offre |
| `view_id` | string | Non | Filtrer par ID de vue SPA |

**Renvoie :** objet JSON avec `activities` (liste d’objets comprenant `id`, `name`, `state`, `type`, `priority`, `modifiedAt`, `startsAt`, `endsAt`) et `total` (nombre total pouvant dépasser la taille de page renvoyée).

**Exemple d’invite :** « Répertorie tous les tests A/B actifs triés en fonction de la dernière modification ».

+++

+++get_ab_activity

Obtenez des informations détaillées sur une activité A/B.

Récupère la configuration complète d’un test A/B spécifique, y compris les expériences, les emplacements, les mesures et les règles de ciblage.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité A/B |

**Renvoie :** les détails complets de l’activité, y compris les métadonnées (nom, état, priorité, dates), les expériences, les emplacements et les offres, les objectifs et mesures, ainsi que les règles de ciblage.

**Exemple d’invite :** « Obtenir des détails sur les 12345 d’activité A/B ».

+++

+++get_xt_activity

Obtenez des informations détaillées sur une activité de ciblage d’expérience (XT).

Récupère la configuration complète d’une activité XT spécifique, y compris les mappages audience-expérience, les emplacements et les mesures.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité XT |

**Retours :** détails complets de l’activité, y compris les métadonnées, les expériences avec les mappages d’audience, les emplacements et les offres, ainsi que les objectifs et les mesures.

**Exemple d’invite :** « Obtention de détails sur les 12345 d’activité de ciblage d’expérience ».

+++

+++get_abt_activity

Obtenez des informations détaillées sur une activité Automated Personalization (AP).

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité AP |

**Renvoie :** les détails complets de l’activité, y compris les métadonnées, les expériences, les emplacements et les paramètres algorithmiques.

**Exemple d’invite :** « Obtenir des détails sur les 12345 d’activité d’Auto-Personalization ».

+++

+++create_ab_activity

Créez une activité de test A/B.

Crée un test A/B avec la configuration spécifiée comprenant les expériences, les offres et le ciblage.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `name` | string | Oui | Nom de l’activité |
| `state` | string | Non | État initial : `approved`, `deactivated` ou `saved` (valeur par défaut : `saved`) |
| `priority` | Entier | Non | Priorité des activités (0-999, valeur par défaut : 0) |
| `starts_at` | string | Non | Date de début (ISO 8601) |
| `ends_at` | string | Non | Date de fin de l&#39;activité (ISO 8601) |
| `experiences` | tableau | Oui | Liste des configurations d’expérience |
| `locations` | tableau | Oui | Liste des configurations d’emplacement/de mbox |
| `goals` | objet | Non | Mesures d’objectif Principal et secondaire |
| `audiences` | tableau | Non | Configurations de l’audience cible |
| `workspace_id` | string | Non | Identifiant Workspace de l’activité |

**Renvoie :** objet d’activité créé avec l’ID qui lui est affecté.

**Exemple d’invite :** « Créez un test A/B appelé « Test du héros de la page d’accueil » avec deux expériences testant différentes images principales sur la mbox du héros de la page d’accueil. »

+++

+++create_xt_activity

Créez une activité de Ciblage d’expérience (XT).

Crée une activité XT qui diffuse différentes expériences à différentes audiences selon des règles de ciblage.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `name` | string | Oui | Nom de l’activité |
| `state` | string | Non | État initial : `approved`, `deactivated` ou `saved` (valeur par défaut : `saved`) |
| `priority` | Entier | Non | Priorité des activités (0-999, valeur par défaut : 0) |
| `starts_at` | string | Non | Date de début (ISO 8601) |
| `ends_at` | string | Non | Date de fin de l&#39;activité (ISO 8601) |
| `experiences` | tableau | Oui | Liste des configurations d’expérience avec des mappages d’audience |
| `locations` | tableau | Oui | Liste des configurations d’emplacement/de mbox |
| `goals` | objet | Non | Mesures d’objectif Principal et secondaire |
| `workspace_id` | string | Non | Identifiant Workspace de l’activité |

**Renvoie :** objet d’activité créé avec l’ID qui lui est affecté.

**Exemple d’invite :** « Créez une activité de ciblage d’expérience appelée « Geo Personalization » qui présente un contenu différent aux visiteurs de différentes régions. »

+++

+++update_ab_activity

Mettez à jour une activité A/B existante.

Utilise un modèle de lecture-modification-écriture : récupère l’état actuel, fusionne vos modifications, valide et envoie la mise à jour.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité à mettre à jour |
| `activity` | objet | Oui | Champs à mettre à jour (nom, priorité, expériences, emplacements, objectifs, etc.) |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Mettez à jour les 12345 d’activité pour modifier l’affectation du trafic sur 70/30. »

+++

+++update_xt_activity

Mettez à jour une activité de ciblage d’expérience existante.

Utilise un modèle de lecture-modification-écriture.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité XT à mettre à jour |
| `activity` | objet | Oui | Champs à mettre à jour |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Mettez à jour les 12345 d’activité XT pour ajouter une nouvelle expérience pour les visiteurs mobiles ».

+++

+++update_abt_activity

Mettre à jour une activité Automated Personalization existante

Utilise un modèle de lecture-modification-écriture.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité AP à mettre à jour |
| `activity` | objet | Oui | Champs à mettre à jour |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Mettez à jour le 12345 d’activité Personalization automatique pour modifier l’objectif d’optimisation. »

+++

+++update_activity_schedule

Mettez à jour les dates de début et de fin d’activité.

Met à jour le planning d’une activité sans modifier les autres paramètres.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `activity_type` | string | Oui | Type d’activité : `ab`, `xt` ou `abt` |
| `starts_at` | string | Non | Nouvelle date de début (ISO 8601) |
| `ends_at` | string | Non | Nouvelle date de fin (ISO 8601) |

**Renvoie :** confirmation de la mise à jour du planning.

**Exemple d’invite :** « Mettez à jour le planning des 12345 d’activité A/B à exécuter du 1er au 31 mai. »

+++

+++update_activity_state

Modifier le statut de l’activité (activer, désactiver ou mettre en pause).

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `state` | string | Oui | Nouveau statut : `approved` (actif/actif), `deactivated` (inactif), `paused` ou `saved` (brouillon) |

**Renvoie :** l’état d’activité mis à jour.

**Exemple d’invite :** « Activer le 12345 d’activité » ou « Suspendre le test du héros de la page d’accueil ».

+++

+++update_activity_name

Renommez une activité.

Met à jour uniquement le nom sans modifier la configuration complète.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `name` | string | Oui | Nom de la nouvelle activité |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Renommez le 12345 d’activité en « Test du héros de la campagne d’été ».

+++

+++update_activity_priority

Modifier la priorité des activités.

Les activités à priorité élevée sont prioritaires lorsque plusieurs activités ciblent le même emplacement.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `priority` | Entier | Oui | Nouvelle valeur de priorité (0-999 ; plus élevée = priorité plus élevée) |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Définissez la priorité du 12345 d’activité sur 100. »

+++

+++add_activity_variant

Ajouter une nouvelle expérience/variante à une activité.

Gère toute la coordination structurelle, y compris la création d’options, le mappage à des emplacements et le rééquilibrage du trafic.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant de l’activité à modifier |
| `activity_type` | string | Oui | Type d’activité : `ab`, `xt` ou `abt` |
| `variant_name` | string | Oui | Nom de la nouvelle expérience/variante |
| `offer_id` | Entier | Non | (Basé sur des formulaires) ID d’offre existant à utiliser |
| `offer_content` | string | Non | (Basé sur des formulaires) Contenu HTML pour une nouvelle offre en ligne |
| `traffic_percentage` | Entier | Non | % de trafic pour la nouvelle variante (1-99). Si cet attribut est omis, le trafic est rééquilibré de manière égale |
| `audience_id` | Entier | Non | Identifiant de l’audience pour la variante (activités XT) |
| `modifications` | tableau | Non | (VEC) Liste des modifications basées sur le sélecteur CSS |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Ajoutez une nouvelle variante appelée « Thème des vacances » aux 12345 d’activité A/B à l’aide du 67890 d’offre. »

+++

+++update_traffic_split

Mettez à jour l’affectation du trafic entre les variantes.

Les pourcentages doivent totaliser exactement 100.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant de l’activité à modifier |
| `activity_type` | string | Oui | Type d’activité : `ab` ou `abt` (XT non pris en charge - ciblé sur l’audience) |
| `splits` | objet | Oui | Nom de l’expérience de mappage du dictionnaire au pourcentage. Doit inclure toutes les expériences et une somme de 100 |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Remplacez la répartition du trafic pour l’activité 12345 par 70 % Contrôle et 30 % Variante A ».

+++

+++update_variant_offer

Modifiez l’offre pour une variante spécifique.

Fonctionne pour les activités basées sur des formulaires (à l’aide de `offer_id`) et les activités du compositeur d’expérience visuelle (à l’aide de `modifications`).

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant de l’activité à modifier |
| `activity_type` | string | Oui | Type d’activité : `ab`, `xt` ou `abt` |
| `variant_name` | string | Oui | Nom de l’expérience/variante à mettre à jour |
| `offer_id` | Entier | Non | (Basé sur des formulaires) Nouvel ID d’offre |
| `offer_content` | string | Non | (Basé sur des formulaires) Contenu HTML pour une nouvelle offre en ligne |
| `modifications` | tableau | Non | (VEC) Nouvelle liste de modifications basées sur le sélecteur CSS |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Mettez à jour l’expérience « Variante A » dans le 12345 d’activité pour utiliser les 99999 d’offre. »

+++

+++remove_activity_variant

Supprimer une expérience/variante d’une activité.

Supprime l’expérience, nettoie les options orphelines et rééquilibre uniformément le trafic entre les variantes restantes.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant de l’activité à modifier |
| `activity_type` | string | Oui | Type d’activité : `ab`, `xt` ou `abt` |
| `variant_name` | string | Oui | Nom de l’expérience/variante à supprimer |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Supprimez l’expérience « Variante de test » du 12345 d’activité A/B. »

+++

## Outils d’offre {#tools-offers}

+++list_target_offers

Répertoriez toutes les offres de votre client [!DNL Target].

Récupère une liste paginée d’offres de contenu avec un filtrage facultatif.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `limit` | Entier | Non | Nombre maximum d&#39;offres à retourner |
| `offset` | Entier | Non | Nombre d’offres à ignorer pour la pagination |
| `type` | string | Non | Filtrez par type d’offre : `content` (HTML), `json` ou `redirect` |
| `name` | string | Non | Filtrer par nom d&#39;offre (correspondance partielle) |

**Renvoie :** objet JSON avec `offers` (liste d’objets comprenant `id`, `name`, `type`, `content`, `modifiedAt`) et `total`.

**Exemple d’invite :** « Répertorier toutes les offres JSON ».

+++

+++get_target_offer

Obtenez des informations détaillées sur une offre spécifique.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `offer_id` | Entier | Oui | Identifiant unique de l’offre |

**Renvoie :** détails complets de l’offre, y compris `id`, `name`, `type`, `content`, `workspace` et `modifiedAt`.

**Exemple d’invite :** « Obtenir les détails de l’67890 de l’offre ».

+++

+++create_target_offer

Créez une offre de contenu HTML.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `name` | string | Oui | Nom de l&#39;offre |
| `content` | string | Oui | HTML ou contenu texte de l’offre |
| `workspace_id` | string | Non | Identifiant Workspace de l’offre |

**Renvoie :** l’offre créée avec son identifiant attribué.

**Exemple d’invite :** « Créez une offre HTML appelée « Bannière de vente d’été » avec une bannière promotionnelle. »

+++

+++create_target_json_offer

Créez une offre JSON pour diffuser des données structurées.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `name` | string | Oui | Nom de l&#39;offre |
| `content` | objet | Oui | Contenu JSON de l’offre |
| `workspace_id` | string | Non | Identifiant Workspace de l’offre |

**Renvoie :** l’offre créée avec son identifiant attribué.

**Exemple d’invite :** « Créez une offre JSON appelée « Configuration des indicateurs de fonctionnalité » avec les paramètres de basculement de fonctionnalité. »

+++

+++update_target_offer

Mettez à jour une offre existante.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `offer_id` | Entier | Oui | Identifiant unique de l’offre à mettre à jour |
| `name` | string | Non | Nom d’offre mis à jour |
| `content` | chaîne ou objet | Non | Contenu de l’offre mis à jour |

**Renvoie :** objet d’offre mis à jour.

**Exemple d’invite :** « Mettre à jour le 67890 d’offre avec du nouveau contenu promotionnel ».

+++

## Outils Audience {#tools-audiences}

+++list_target_audiences

Répertoriez toutes les audiences de votre client [!DNL Target].

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `limit` | Entier | Non | Nombre maximal d’audiences à renvoyer |
| `offset` | Entier | Non | Nombre d’audiences à ignorer pour la pagination |

**Renvoie :** objet JSON avec `audiences` (liste d’objets comprenant `id`, `name`, `description`, `origin`, `modifiedAt`) et `total`.

**Exemple d’invite :** « Répertorier toutes les audiences ».

+++

+++create_target_audience

Créez une audience avec des règles de ciblage.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `name` | string | Oui | Nom de l’audience |
| `description` | string | Non | Description de l’audience |
| `targetRule` | objet | Non | Règles de ciblage (zone géographique, navigateur, attributs personnalisés, etc.) |
| `workspace_id` | string | Non | Identifiant Workspace de l’audience |

**Renvoie :** audience créée avec son identifiant attribué.

**Exemple d’invite :** « Créez une audience appelée « Visiteurs mobiles de Californie » ciblant les utilisateurs mobiles en Californie. »

+++

## Outils de mbox {#tools-mboxes}

+++list_target_mboxes

Répertoriez toutes les mbox de votre client [!DNL Target].

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `limit` | Entier | Non | Nombre maximal de mbox à renvoyer |
| `offset` | Entier | Non | Nombre de mbox à ignorer pour la pagination |
| `name` | string | Non | Filtrer par nom de mbox (correspondance partielle) |
| `status` | string | Non | Filtrer par statut |

**Renvoie :** objet JSON avec `mboxes` (liste d’objets comprenant `name`, `status`, `lastRequestTime`) et `total`.

**Exemple d’invite :** « Répertorier toutes les mbox contenant « homepage ». »

+++

+++get_target_mbox

Obtenez des informations détaillées sur une mbox spécifique.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `mbox_name` | string | Oui | Nom de la mbox |

**Renvoie :** les détails de la mbox, notamment la `name`, la `status` et la liste des activités utilisant la mbox.

**Exemple d’invite :** « Obtention des détails sur la mbox « homepage-hero ». »

+++

+++list_target_mbox_profile_attributes

Répertorier tous les attributs de profil mbox disponibles pour le ciblage.

Aucun paramètre requis.

**Renvoie :** tableau JSON d’objets d’attribut de profil.

**Exemple d’invite :** « Quels attributs de profil sont disponibles pour le ciblage ? »

+++

## Outils de propriété {#tools-properties}

+++list_target_properties

Répertoriez toutes les propriétés de votre client [!DNL Target].

Les propriétés organisent des activités et contrôlent l’accès.

Aucun paramètre requis.

**Renvoie :** liste des objets de propriété, y compris `id`, `name`, `description` et `channel`.

**Exemple d’invite :** « Répertorier toutes les propriétés Target ».

+++

## Outils de reporting {#tools-reporting}

+++get_ab_performance_report

Obtenez un rapport de performances pour une activité A/B.

Récupère les taux de conversion, l’effet élévateur et les niveaux de confiance.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité A/B |
| `report_interval` | string | Non | Période du rapport (par exemple, `last7days`, `last30days` ou une période personnalisée) |

**Retours :** mesures au niveau de l’expérience (visiteurs, conversions, taux de conversion), calculs de l’effet élévateur, niveaux de confiance statistiques et mesures de recettes (si elles sont configurées).

**Exemple d’invite :** « Afficher le rapport de performances des 12345 de test A/B au cours des 30 derniers jours ».

+++

+++get_ab_orders_report

Obtenez un état des commandes/revenus pour une activité A/B.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité A/B |
| `report_interval` | string | Non | Période du rapport |

**Retours : nombre de commandes** chiffre d’affaires et valeur de commande moyenne par expérience.

**Exemple d’invite :** « Obtenir l’état des commandes pour les 12345 d’activité ».

+++

+++get_xt_performance_report

Obtenez un rapport de performances pour une activité de ciblage d’expérience.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité XT |
| `report_interval` | string | Non | Période du rapport |

**Renvoie :** mesures de performances au niveau de l’expérience.

**Exemple d’invite :** « Afficher les performances de mon 54321 d’activité de ciblage d’expérience ».

+++

+++get_xt_orders_report

Obtenez un rapport commandes/revenus pour une activité de ciblage d’expérience.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité XT |
| `report_interval` | string | Non | Période du rapport |

**Retours :** Classer les mesures par expérience.

**Exemple d’invite :** « Obtenir les données de commande pour les 54321 d’activité XT ».

+++

+++get_activity_report_by_name

Recherchez une activité par nom et obtenez son rapport de performances.

Utile lorsque vous connaissez le nom de l’activité, mais pas son identifiant.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_name` | string | Oui | Nom de l’activité à rechercher |
| `report_interval` | string | Non | Période du rapport |

**Retours :** détails de l’activité et mesures de performances.

**Exemple d’invite :** « Obtenez le rapport de performances de mon activité « Test du héros de la page d’accueil ». »

+++

## Outils de prévisualisation {#tools-preview}

+++preview_activity

Générer des URL d’aperçu de l’AQ du navigateur pour une activité [!DNL Target].

Crée des liens d’aperçu cliquables qui forcent l’affichage d’expériences spécifiques, en contournant les règles de ciblage des audiences. Fonctionne pour les activités A/B, XT et Automated Personalization.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | ID d’activité [!DNL Target] à prévisualiser |
| `experience_index` | Entier | Non | Index d’expérience basé sur 0. Si cet attribut est omis, renvoie des URL pour toutes les expériences |
| `url` | string | Non | URL de la page pour l’aperçu. Requis pour les activités basées sur des formulaires. Pour les activités du compositeur d’expérience visuelle, remplace l’emplacement créé, le cas échéant. |

**Renvoie :** les informations d’activité (nom, type, état), les URL d’aperçu pour chaque expérience, ainsi que les noms et index d’expérience.

**Exemple d’invite :** « Générer des URL d’aperçu pour les 12345 d’activité afin que je puisse tester chaque expérience dans mon navigateur ».

+++

## Outils de jeton de réponse {#tools-response-tokens}

+++list_target_response_tokens

Répertoriez tous les jetons de réponse de votre client [!DNL Target].

Récupère tous les jetons de réponse configurés, intégrés et personnalisés.

Aucun paramètre requis.

**Renvoie :** tableau JSON d’objets de jeton de réponse avec le statut `name`, `type` et `enabled`.

**Exemple d’invite :** « Répertorier tous les jetons de réponse ».

+++

+++create_target_response_token

Créez un jeton de réponse personnalisé pour collecter des données supplémentaires dans les réponses [!DNL Target].

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `token_name` | string | Oui | Nom du jeton de réponse |
| `token_type` | string | Oui | Type de jeton : `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO` ou `CRS` |

**Renvoie :** objet jeton de réponse créé.

**Exemple d’invite :** « Créez un jeton de réponse personnalisé appelé « campaign_id » de type ACTIVITY. »

+++

## Outils de révision {#tools-revisions}

+++get_target_revisions

Obtenez le journal d’audit pour un type de ressource.

Récupère les modifications apportées aux ressources [!DNL Target] avec le filtrage facultatif par auteur.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `revision_resource_type` | string | Oui | Type de ressource : `activity`, `offer` ou `audience` |
| `modified_by` | string | Non | Filtrer par utilisateur ayant apporté des modifications |
| `limit` | Entier | Non | Nombre maximal de révisions à renvoyer |
| `offset` | Entier | Non | Nombre de révisions à ignorer pour la pagination |

**Renvoie :** historique des révisions avec horodatages, utilisateurs et descriptions des modifications.

**Exemple d’invite :** « Afficher le journal d’audit pour les modifications d’activité ».

+++

+++get_target_entity_revisions

Récupère toutes les révisions d’une entité spécifique par ID.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `revision_resource_type` | string | Oui | Type de ressource : `activity`, `offer` ou `audience` |
| `entity_id` | Entier | Oui | Identifiant unique de l’entité |

**Renvoie :** tableau JSON de toutes les révisions pour l’entité spécifiée.

**Exemple d’invite :** « Afficher toutes les modifications apportées aux 12345 d’activité ».

+++

## Outils de modèles {#tools-templates}

+++list_target_templates

Répertoriez les ressources et modèles MCP disponibles pour créer des activités et des offres.

Aucun paramètre requis.

**Renvoie :** objet JSON répertoriant les modèles et ressources disponibles.

**Exemple d’invite :** « Quels modèles sont disponibles pour la création d’activités ? »

+++

## Résumé des outils {#tools-summary}

| Catégorie | Nombre | Outils |
|---|---|---|
| Activité | 17 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity`, `create_ab_activity`, `create_xt_activity`, `update_ab_activity`, `update_xt_activity`, `update_abt_activity`, `update_activity_schedule`, `update_activity_state`, `update_activity_name`, `update_activity_priority`, `add_activity_variant`, `update_traffic_split`, `update_variant_offer` `remove_activity_variant` |
| Offre | 5 | `list_target_offers`, `get_target_offer`, `create_target_offer`, `create_target_json_offer`, `update_target_offer` |
| Audience | 2 | `list_target_audiences`, `create_target_audience` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| Propriété | 1 | `list_target_properties` |
| Création de rapports | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| Prévisualiser | 1 | `preview_activity` |
| Jeton de réponse | 2 | `list_target_response_tokens`, `create_target_response_token` |
| Révision | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| Modèle | 1 | `list_target_templates` |
| **Total** | 39 **** | |

## Ressources connexes {#tools-related}

* [Utiliser les clients MCP](target-mcp.md)
* [Auto-hébergement du serveur  [!DNL Adobe Target]  MCP](target-mcp-self-hosted.md)
* [[!DNL Adobe Target] Référence de l’API Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}