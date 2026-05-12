---
solution: Target
product: target
title: Référence sur les outils du serveur MCP Adobe Target
description: Référence complète des paramètres pour les 21 outils en lecture seule exposés par le serveur MCP Adobe Target.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Beta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: 216b1103f501a3fcf955523d4bcc8254a8ea418d
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 11%

---

# Référence des outils du serveur [!DNL Adobe Target] MCP {#target-mcp-tools-reference}

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est disponible pour tous les clients dans **Public Beta**. Il est actuellement pris en charge dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**.

Cette page est une référence complète pour tous les outils en lecture seule exposés par le serveur MCP [!DNL Adobe Target]. Pour chaque outil, vous trouverez une description, les détails des paramètres, la valeur renvoyée et un exemple d’invite en langage naturel. Pour obtenir des instructions de configuration et des cas d’utilisation, consultez [Prise en main](target-mcp-get-started.md) et [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md).

>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

## Conditions préalables {#tools-prerequisites}

Votre rôle [!DNL Adobe Target] détermine les outils disponibles :

* **Observateur** rôle ou supérieur : accès à tous les outils de lecture
* **Éditeur** rôle : accès aux outils de lecture et d’écriture (création)
* **Approbateur** rôle : accès pour la lecture, l’écriture et l’activation/désactivation des outils

Pour obtenir des instructions de configuration complètes, voir [Prise en main](target-mcp-get-started.md).

## Outils d’activité {#tools-activities}

+++Liste des activités

**Outil :** `list_target_activities`

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

+++Obtenir une activité A/B

**Outil :** `get_ab_activity`

Obtenez des informations détaillées sur une activité A/B.

Récupère la configuration complète d’un test A/B spécifique, y compris les expériences, les emplacements, les mesures et les règles de ciblage.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité A/B |

**Renvoie :** les détails complets de l’activité, y compris les métadonnées (nom, état, priorité, dates), les expériences, les emplacements et les offres, les objectifs et mesures, ainsi que les règles de ciblage.

**Exemple d’invite :** « Obtenir des détails sur les 12345 d’activité A/B ».

+++

+++Obtention d’une activité de ciblage d’expérience

**Outil :** `get_xt_activity`

Obtenez des informations détaillées sur une activité de ciblage d’expérience (XT).

Récupère la configuration complète d’une activité XT spécifique, y compris les mappages audience-expérience, les emplacements et les mesures.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité XT |

**Retours :** détails complets de l’activité, y compris les métadonnées, les expériences avec les mappages d’audience, les emplacements et les offres, ainsi que les objectifs et les mesures.

**Exemple d’invite :** « Obtention de détails sur les 12345 d’activité de ciblage d’expérience ».

+++

+++Obtenir une activité Automated Personalization

**Outil :** `get_abt_activity`

Obtenez des informations détaillées sur une activité Automated Personalization (AP).

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité AP |

**Renvoie :** les détails complets de l’activité, y compris les métadonnées, les expériences, les emplacements et les paramètres algorithmiques.

**Exemple d’invite :** « Obtenir des détails sur les 12345 d’activité d’Auto-Personalization ».

+++

<!--
+++Create an A/B activity

**Tool:** `create_ab_activity`

Create a new A/B test activity.

Creates a new A/B test with the specified configuration including experiences, offers, and targeting.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `audiences` | array | No | Target audience configurations |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an A/B test called 'Homepage Hero Test' with two experiences testing different hero images on the homepage-hero mbox."

+++
-->

<!--
+++Create an Experience Targeting activity

**Tool:** `create_xt_activity`

Create a new Experience Targeting (XT) activity.

Creates an XT activity that delivers different experiences to different audiences based on targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the activity |
| `state` | string | No | Initial state: `approved`, `deactivated`, or `saved` (default: `saved`) |
| `priority` | integer | No | Activity priority (0–999, default: 0) |
| `starts_at` | string | No | Activity start date (ISO 8601) |
| `ends_at` | string | No | Activity end date (ISO 8601) |
| `experiences` | array | Yes | List of experience configurations with audience mappings |
| `locations` | array | Yes | List of location/mbox configurations |
| `goals` | object | No | Primary and secondary goal metrics |
| `workspace_id` | string | No | Workspace ID for the activity |

**Returns:** The created activity object with its assigned ID.

**Example prompt:** "Create an Experience Targeting activity called 'Geo Personalization' that shows different content to visitors from different regions."

+++
-->

<!--
+++Update an A/B activity

**Tool:** `update_ab_activity`

Update an existing A/B activity.

Uses a read-modify-write pattern: fetches the current state, merges your changes, validates, and sends the update.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity to update |
| `activity` | object | Yes | Fields to update (name, priority, experiences, locations, goals, etc.) |

**Returns:** The updated activity object.

**Example prompt:** "Update activity 12345 to change the traffic allocation to 70/30."

+++
-->

<!--
+++Update an Experience Targeting activity

**Tool:** `update_xt_activity`

Update an existing Experience Targeting activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the XT activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update XT activity 12345 to add a new experience for mobile visitors."

+++
-->

<!--
+++Update an Automated Personalization activity

**Tool:** `update_abt_activity`

Update an existing Automated Personalization activity.

Uses a read-modify-write pattern.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the AP activity to update |
| `activity` | object | Yes | Fields to update |

**Returns:** The updated activity object.

**Example prompt:** "Update Auto-Personalization activity 12345 to change the optimization goal."

+++
-->

<!--
+++Update activity schedule

**Tool:** `update_activity_schedule`

Update activity start and end dates.

Updates the schedule for an activity without modifying other settings.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `activity_type` | string | Yes | Type of activity: `ab`, `xt`, or `abt` |
| `starts_at` | string | No | New start date (ISO 8601) |
| `ends_at` | string | No | New end date (ISO 8601) |

**Returns:** Confirmation of the schedule update.

**Example prompt:** "Update the schedule for A/B activity 12345 to run from May 1st to May 31st."

+++
-->

<!--
+++Change activity state

**Tool:** `update_activity_state`

Change activity state (activate, deactivate, or pause).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `state` | string | Yes | New state: `approved` (live/active), `deactivated` (inactive), `paused`, or `saved` (draft) |

**Returns:** The updated activity state.

**Example prompt:** "Activate activity 12345" or "Pause the Homepage Hero Test."

+++
-->

<!--
+++Rename an activity

**Tool:** `update_activity_name`

Rename an activity.

Updates only the name without modifying the full configuration.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `name` | string | Yes | New activity name |

**Returns:** The updated activity object.

**Example prompt:** "Rename activity 12345 to 'Summer Campaign Hero Test'."

+++
-->

<!--
+++Change activity priority

**Tool:** `update_activity_priority`

Change activity priority.

Higher-priority activities take precedence when multiple activities target the same location.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The unique identifier of the activity |
| `priority` | integer | Yes | New priority value (0–999; higher = higher priority) |

**Returns:** The updated activity object.

**Example prompt:** "Set the priority of activity 12345 to 100."

+++
-->

<!--
+++Add a variant to an activity

**Tool:** `add_activity_variant`

Add a new experience/variant to an activity.

Handles all structural coordination including creating options, mapping to locations, and rebalancing traffic.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name for the new experience/variant |
| `offer_id` | integer | No | (Form-based) Existing offer ID to use |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `traffic_percentage` | integer | No | Traffic % for the new variant (1–99). If omitted, traffic is rebalanced evenly |
| `audience_id` | integer | No | Audience ID for the variant (XT activities) |
| `modifications` | array | No | (VEC) List of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Add a new variant called 'Holiday Theme' to A/B activity 12345 using offer 67890."

+++
-->

<!--
+++Update traffic split

**Tool:** `update_traffic_split`

Update traffic allocation across variants.

The percentages must sum to exactly 100.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab` or `abt` (XT not supported — audience-targeted) |
| `splits` | object | Yes | Dictionary mapping experience name to percentage. Must include all experiences and sum to 100 |

**Returns:** The updated activity object.

**Example prompt:** "Change the traffic split for activity 12345 to 70% Control and 30% Variant A."

+++
-->

<!--
+++Change a variant's offer

**Tool:** `update_variant_offer`

Change the offer for a specific variant.

Works for both form-based activities (using `offer_id`) and VEC activities (using `modifications`).

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to update |
| `offer_id` | integer | No | (Form-based) New offer ID |
| `offer_content` | string | No | (Form-based) HTML content for a new inline offer |
| `modifications` | array | No | (VEC) New list of CSS selector-based modifications |

**Returns:** The updated activity object.

**Example prompt:** "Update the 'Variant A' experience in activity 12345 to use offer 99999."

+++
-->

<!--
+++Remove a variant from an activity

**Tool:** `remove_activity_variant`

Remove an experience/variant from an activity.

Removes the experience, cleans up orphaned options, and rebalances traffic evenly across remaining variants.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `activity_id` | integer | Yes | The ID of the activity to modify |
| `activity_type` | string | Yes | Activity type: `ab`, `xt`, or `abt` |
| `variant_name` | string | Yes | Name of the experience/variant to remove |

**Returns:** The updated activity object.

**Example prompt:** "Remove the 'Test Variant' experience from A/B activity 12345."

+++
-->

## Outils d’offre {#tools-offers}

+++Liste des offres

**Outil :** `list_target_offers`

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

+++Obtenir une offre

**Outil :** `get_target_offer`

Obtenez des informations détaillées sur une offre spécifique.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `offer_id` | Entier | Oui | Identifiant unique de l’offre |

**Renvoie :** détails complets de l’offre, y compris `id`, `name`, `type`, `content`, `workspace` et `modifiedAt`.

**Exemple d’invite :** « Obtenir les détails de l’67890 de l’offre ».

+++

<!--
+++Create an HTML offer

**Tool:** `create_target_offer`

Create a new HTML content offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | string | Yes | HTML or text content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create an HTML offer called 'Summer Sale Banner' with a promotional banner."

+++

+++Create a JSON offer

**Tool:** `create_target_json_offer`

Create a new JSON offer for delivering structured data.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the offer |
| `content` | object | Yes | JSON content for the offer |
| `workspace_id` | string | No | Workspace ID for the offer |

**Returns:** The created offer with its assigned ID.

**Example prompt:** "Create a JSON offer called 'Feature Flags Config' with feature toggle settings."

+++

+++Update an offer

**Tool:** `update_target_offer`

Update an existing offer.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `offer_id` | integer | Yes | The unique identifier of the offer to update |
| `name` | string | No | Updated offer name |
| `content` | string or object | No | Updated offer content |

**Returns:** The updated offer object.

**Example prompt:** "Update offer 67890 with new promotional content."

+++
-->

## Outils Audience {#tools-audiences}

+++Liste des audiences

**Outil :** `list_target_audiences`

Répertoriez toutes les audiences de votre client [!DNL Target].

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `limit` | Entier | Non | Nombre maximal d’audiences à renvoyer |
| `offset` | Entier | Non | Nombre d’audiences à ignorer pour la pagination |

**Renvoie :** objet JSON avec `audiences` (liste d’objets comprenant `id`, `name`, `description`, `origin`, `modifiedAt`) et `total`.

**Exemple d’invite :** « Répertorier toutes les audiences ».

+++

<!--
+++Create an audience

**Tool:** `create_target_audience`

Create a new audience with targeting rules.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `name` | string | Yes | Name of the audience |
| `description` | string | No | Description of the audience |
| `targetRule` | object | No | Targeting rules (geo, browser, custom attributes, etc.) |
| `workspace_id` | string | No | Workspace ID for the audience |

**Returns:** The created audience with its assigned ID.

**Example prompt:** "Create an audience called 'Mobile Visitors from California' targeting mobile users in CA."

+++
-->

## Outils de mbox {#tools-mboxes}

+++Mbox de liste

**Outil :** `list_target_mboxes`

Répertoriez toutes les mbox de votre client [!DNL Target].

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `limit` | Entier | Non | Nombre maximal de mbox à renvoyer |
| `offset` | Entier | Non | Nombre de mbox à ignorer pour la pagination |
| `name` | string | Non | Filtrer par nom de mbox (correspondance partielle) |
| `status` | string | Non | Filtrer selon le statut |

**Renvoie :** objet JSON avec `mboxes` (liste d’objets comprenant `name`, `status`, `lastRequestTime`) et `total`.

**Exemple d’invite :** « Répertorier toutes les mbox contenant « homepage ». »

+++

+++Obtenir une mbox

**Outil :** `get_target_mbox`

Obtenez des informations détaillées sur une mbox spécifique.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `mbox_name` | string | Oui | Nom de la mbox |

**Renvoie :** les détails de la mbox, notamment la `name`, la `status` et la liste des activités utilisant la mbox.

**Exemple d’invite :** « Obtention des détails sur la mbox « homepage-hero ». »

+++

+++Répertorier les attributs de profil mbox

**Outil :** `list_target_mbox_profile_attributes`

Répertorier tous les attributs de profil mbox disponibles pour le ciblage.

Aucun paramètre requis.

**Renvoie :** tableau JSON d’objets d’attribut de profil.

**Exemple d’invite :** « Quels attributs de profil sont disponibles pour le ciblage ? »

+++

## Outils de propriété {#tools-properties}

+++Propriétés de la liste

**Outil :** `list_target_properties`

Répertoriez toutes les propriétés de votre client [!DNL Target].

Les propriétés organisent des activités et contrôlent l’accès.

Aucun paramètre requis.

**Renvoie :** liste des objets de propriété, y compris `id`, `name`, `description` et `channel`.

**Exemple d’invite :** « Répertorier toutes les propriétés Target ».

+++

## Outils de reporting {#tools-reporting}

+++Obtenir un rapport de performances A/B

**Outil :** `get_ab_performance_report`

Obtenez un rapport de performances pour une activité A/B.

Récupère les taux de conversion, l’effet élévateur et les niveaux de confiance.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité A/B |
| `report_interval` | string | Non | Période du rapport (par exemple, `last7days`, `last30days` ou une période personnalisée) |

**Retours :** mesures au niveau de l’expérience (visiteurs, conversions, taux de conversion), calculs de l’effet élévateur, niveaux de confiance statistiques et mesures de recettes (si elles sont configurées).

**Exemple d’invite :** « Afficher le rapport de performances des 12345 de test A/B au cours des 30 derniers jours ».

+++

+++Obtenir un rapport sur les commandes A/B

**Outil :** `get_ab_orders_report`

Obtenez un état des commandes/revenus pour une activité A/B.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité A/B |
| `report_interval` | string | Non | Période du rapport |

**Retours : nombre de commandes** chiffre d’affaires et valeur de commande moyenne par expérience.

**Exemple d’invite :** « Obtenir l’état des commandes pour les 12345 d’activité ».

+++

+++Obtention d’un rapport de performances de ciblage d’expérience

**Outil :** `get_xt_performance_report`

Obtenez un rapport de performances pour une activité de ciblage d’expérience.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité XT |
| `report_interval` | string | Non | Période du rapport |

**Renvoie :** mesures de performances au niveau de l’expérience.

**Exemple d’invite :** « Afficher les performances de mon 54321 d’activité de ciblage d’expérience ».

+++

+++Obtention d&#39;un rapport sur les ordres de ciblage d&#39;expérience

**Outil :** `get_xt_orders_report`

Obtenez un rapport commandes/revenus pour une activité de ciblage d’expérience.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité XT |
| `report_interval` | string | Non | Période du rapport |

**Retours :** Classer les mesures par expérience.

**Exemple d’invite :** « Obtenir les données de commande pour les 54321 d’activité XT ».

+++

+++Obtention d&#39;un rapport de performances par nom d&#39;activité

**Outil :** `get_activity_report_by_name`

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

+++Prévisualiser une activité

**Outil :** `preview_activity`

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

+++Liste des jetons de réponse

**Outil :** `list_target_response_tokens`

Répertoriez tous les jetons de réponse de votre client [!DNL Target].

Récupère tous les jetons de réponse configurés, intégrés et personnalisés.

Aucun paramètre requis.

**Renvoie :** tableau JSON d’objets de jeton de réponse avec le statut `name`, `type` et `enabled`.

**Exemple d’invite :** « Répertorier tous les jetons de réponse ».

+++

<!--
+++Create a response token

**Tool:** `create_target_response_token`

Create a new custom response token for collecting additional data in [!DNL Target] responses.

| Parameter | Type | Required | Description |
|---|---|---|---|
| `token_name` | string | Yes | Name of the response token |
| `token_type` | string | Yes | Type of token: `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO`, or `CRS` |

**Returns:** The created response token object.

**Example prompt:** "Create a custom response token called 'campaign_id' of type ACTIVITY."

+++
-->

## Outils de révision {#tools-revisions}

+++Obtenir le journal d’audit

**Outil :** `get_target_revisions`

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

+++Obtention des révisions pour une entité spécifique

**Outil :** `get_target_entity_revisions`

Récupère toutes les révisions d’une entité spécifique par ID.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `revision_resource_type` | string | Oui | Type de ressource : `activity`, `offer` ou `audience` |
| `entity_id` | Entier | Oui | Identifiant unique de l’entité |

**Renvoie :** tableau JSON de toutes les révisions pour l’entité spécifiée.

**Exemple d’invite :** « Afficher toutes les modifications apportées aux 12345 d’activité ».

+++

## Outils de modèles {#tools-templates}

+++Répertorier les modèles disponibles

**Outil :** `list_target_templates`

Répertoriez les ressources et modèles MCP disponibles pour créer des activités et des offres.

Aucun paramètre requis.

**Renvoie :** objet JSON répertoriant les modèles et ressources disponibles.

**Exemple d’invite :** « Quels modèles sont disponibles pour la création d’activités ? »

+++

## Résumé des outils {#tools-summary}

| Catégorie | Nombre | de recherche |
|---|---|---|
| Activité | 4 | `list_target_activities`, `get_ab_activity`, `get_xt_activity`, `get_abt_activity` |
| Offre | 2 | `list_target_offers`, `get_target_offer` |
| Audience | 1 | `list_target_audiences` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| Propriété | 1 | `list_target_properties` |
| Création de rapports | 5 | `get_ab_performance_report`, `get_ab_orders_report`, `get_xt_performance_report`, `get_xt_orders_report`, `get_activity_report_by_name` |
| Prévisualiser | 1 | `preview_activity` |
| Jeton de réponse | 1 | `list_target_response_tokens` |
| Révision | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| Modèle | 1 | `list_target_templates` |
| **Total** | **21** | |

## Ressources connexes {#tools-related}

* [Utiliser les clients MCP](target-mcp.md)
* [Référence de l’API [!DNL Adobe Target] Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
