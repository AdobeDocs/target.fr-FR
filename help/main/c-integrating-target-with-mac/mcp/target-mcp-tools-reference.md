---
solution: Target
product: target
title: Référence sur les outils du serveur MCP Adobe Target
description: Référence complète des paramètres pour tous les outils exposés par le serveur MCP Adobe Target, y compris les opérations de lecture et d’écriture.
feature: Integrations
topic: Experimentation, Personalization, Artificial Intelligence
badge: label="Version bêta" type="Informative"
role: Developer, User
level: Intermediate, Experienced
source-git-commit: aa7a47b00b86a47c97996b667ee0d73db52650aa
workflow-type: tm+mt
source-wordcount: '3046'
ht-degree: 14%

---

# Référence des outils du serveur [!DNL Adobe Target] MCP {#target-mcp-tools-reference}

>[!AVAILABILITY]
>
>Le serveur MCP [!DNL Adobe Target] est disponible pour tous les clients dans **Public Beta**. Il est actuellement pris en charge dans **Claude Web**, **Claude Desktop**, **Claude Code**, **Cursor** et **ChatGPT**.

Cette page est une référence complète pour tous les outils exposés par le serveur MCP [!DNL Adobe Target]. Pour chaque outil, vous trouverez une description, les détails des paramètres, la valeur renvoyée et un exemple d’invite en langage naturel. Pour obtenir des instructions de configuration et des cas d’utilisation, consultez [Prise en main](target-mcp-get-started.md) et [Cas d’utilisation et procédures pas à pas](target-mcp-use-cases.md).

>[!IMPORTANT]
>
>Le protocole MCP (Model Context Protocol) est une norme open source émergente qui peut présenter des risques pour la sécurité ou la fiabilité. Les intégrations de serveurs Adobe MCP et la documentation associée sont fournies « en l’état », sans garantie d’aucune sorte.
>
>La connexion des clients ou serveurs MCP aux produits Adobe est une configuration choisie par le client. Ce dernier est chargé d’évaluer la sécurité et l’adéquation de toute intégration MCP. Adobe n’est pas responsable des problèmes résultant d’une mauvaise configuration, d’une utilisation abusive du MCP, de vulnérabilités dans les implémentations tierces ou d’actions involontaires effectuées par le biais de workflows prenant en charge MCP.
>
>Pour réduire les risques, Adobe encourage à tester les intégrations dans un environnement Sandbox avant une utilisation productive et à examiner et valider soigneusement toutes les actions et réponses initiées par MCP avant de les confirmer ou de s’y fier.

## Conditions préalables {#tools-prerequisites}

Votre rôle [!DNL Adobe Target] détermine les outils disponibles :

* **Observateur** rôle ou supérieur : accès à tous les outils en lecture seule
* **Éditeur** rôle ou supérieur : accès aux outils de lecture et d’écriture (création, mise à jour)
* **Approbateur** rôle : accès à tous les outils, y compris l&#39;activation et la désactivation

Pour obtenir des instructions de configuration complètes, voir [Prise en main](target-mcp-get-started.md).

## Outils d’activité {#tools-activities}

>[!NOTE]
>
>Les opérations de lecture et d’écriture ont une portée différente. `get_activity` récupère les activités de tous les types (test A/B, ciblage d’expérience, Automated Personalization, affectation automatique, test multivarié, recommandations). `update_activity` prend en charge les tests A/B, le ciblage d’expérience et Automated Personalization. Les activités d’affectation automatique, de test multivarié et de recommandations sont en lecture seule via le serveur MCP.

| Fonction | Test A/B | Ciblage d’expérience | Automated Personalization | Affectation automatique | Test multivarié | Recommandations |
|---|---|---|---|---|---|---|
| `get_activity` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `list_target_activities` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `get_activity_performance_report` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `get_activity_orders_report` | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| `update_activity` | ✓ | ✓ | ✓ | — | — | — |
| Modifications du cycle de vie (état, priorité, nom, planning) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Modifications des variantes et du trafic | ✓ | ✓ | ✓ | — | — | — |
| Créer | ✓ | ✓ | — | — | — | — |

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
| `activity_type` | string | Non | Filtrer par type : `ab` (test A/B), `xt` (ciblage d’expérience), `abt` (Automated Personalization), `auto_allocate` (affectation automatique), `mvt` (test multivarié), `recs` (recommandations) |
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

+++Obtenir une activité

**Outil :** `get_activity`

Obtenez des informations détaillées sur une activité de n’importe quel type.

Récupère la configuration complète d’une activité spécifique en détectant automatiquement le type d’activité. Prend en charge les activités de test A/B, de ciblage d’expérience, d’Automated Personalization, d’affectation automatique, de test multivarié et de recommandations.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |

**Renvoie :** les détails complets de l’activité, y compris les métadonnées (nom, état, priorité, dates), les expériences, les emplacements et les offres, les objectifs et mesures, ainsi que les règles de ciblage.

**Exemple d’invite :** « Obtenir des détails sur les 12345 d’activité ».

+++

+++Créer une activité A/B

**Outil :** `create_ab_activity`

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

+++Création d’une activité de ciblage d’expérience

**Outil :** `create_xt_activity`

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

+++Mettre à jour une activité

**Outil :** `update_activity`

Mettez à jour un test A/B, un ciblage d’expérience ou une activité Automated Personalization existants.

Utilise un modèle de lecture-modification-écriture : récupère l’état actuel, fusionne vos modifications, valide et envoie la mise à jour. Prend en charge les activités de test A/B, de ciblage d’expérience et d’Automated Personalization. Les activités d’affectation automatique, de test multivarié et de recommandations sont en lecture seule. Les paramètres `goal`, `audience_ids` et `additional_metrics` structurés sont pris en charge uniquement pour les tests A/B et le ciblage d’expérience ; les activités Automated Personalization acceptent les mises à jour de fusion de champs simples.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité à mettre à jour |
| `activity` | objet | Oui | Champs à mettre à jour (nom, priorité, expériences, emplacements, objectifs, etc.) |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Mettez à jour les 12345 d’activité pour modifier l’affectation du trafic sur 70/30. »

+++

+++Mettre à jour le planning d’activité

**Outil :** `update_activity_schedule`

Mettez à jour les dates de début et de fin d’activité.

Met à jour le planning d’une activité sans modifier les autres paramètres.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `starts_at` | string | Non | Nouvelle date de début (ISO 8601) |
| `ends_at` | string | Non | Nouvelle date de fin (ISO 8601) |

**Renvoie :** confirmation de la mise à jour du planning.

**Exemple d’invite :** « Mettez à jour le planning des 12345 d’activité A/B à exécuter du 1er au 31 mai. »

+++

+++Modifier l’état de l’activité

**Outil :** `update_activity_state`

Modifier le statut de l’activité (activer, désactiver ou mettre en pause).

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `state` | string | Oui | Nouveau statut : `approved` (actif/actif), `deactivated` (inactif), `paused` ou `saved` (brouillon) |

**Renvoie :** l’état d’activité mis à jour.

**Exemple d’invite :** « Activer le 12345 d’activité » ou « Suspendre le test du héros de la page d’accueil ».

+++

+++Renommer une activité

**Outil :** `update_activity_name`

Renommez une activité.

Met à jour uniquement le nom sans modifier la configuration complète.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `name` | string | Oui | Nom de la nouvelle activité |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Renommez le 12345 d’activité en « Test du héros de la campagne d’été ».

+++

+++Modifier la priorité des activités

**Outil :** `update_activity_priority`

Modifier la priorité des activités.

Les activités à priorité élevée sont prioritaires lorsque plusieurs activités ciblent le même emplacement.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `priority` | Entier | Oui | Nouvelle valeur de priorité (0-999 ; plus élevée = priorité plus élevée) |

**Renvoie :** objet Activity mis à jour.

**Exemple d’invite :** « Définissez la priorité du 12345 d’activité sur 100. »

+++

+++Ajouter une variante à une activité

**Outil :** `add_activity_variant`

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

+++Mettre à jour la répartition du trafic

**Outil :** `update_traffic_split`

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

+++Modifier l’offre d’une variante

**Outil :** `update_variant_offer`

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

+++Supprimer une variante d’une activité

**Outil :** `remove_activity_variant`

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

+++Création d’une offre HTML

**Outil :** `create_target_offer`

Créez une offre de contenu HTML.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `name` | string | Oui | Nom de l&#39;offre |
| `content` | string | Oui | HTML ou contenu texte de l’offre |
| `workspace_id` | string | Non | Identifiant Workspace de l’offre |

**Renvoie :** l’offre créée avec son identifiant attribué.

**Exemple d’invite :** « Créez une offre HTML appelée « Bannière de vente d’été » avec une bannière promotionnelle. »

+++

+++Créer une offre JSON

**Outil :** `create_target_json_offer`

Créez une offre JSON pour diffuser des données structurées.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `name` | string | Oui | Nom de l&#39;offre |
| `content` | objet | Oui | Contenu JSON de l’offre |
| `workspace_id` | string | Non | Identifiant Workspace de l’offre |

**Renvoie :** l’offre créée avec son identifiant attribué.

**Exemple d’invite :** « Créez une offre JSON appelée « Configuration des indicateurs de fonctionnalité » avec les paramètres de basculement de fonctionnalité. »

+++

+++Mise à jour d’une offre

**Outil :** `update_target_offer`

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

+++Obtenir une audience

**Outil :** `get_target_audience`

Obtenez les détails de l’audience, y compris les règles de ciblage.

Récupère la configuration complète d’une audience spécifique, y compris ses règles et conditions de ciblage.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `audience_id` | Entier | Oui | Identifiant unique de l’audience |

**Renvoie :** détails complets de l’audience, y compris les `id`, `name`, `description`, `origin`, règles de ciblage et le nombre d’activités associées.

**Exemple d’invite :** « Obtenez des détails sur les 12345 d’audience et affichez-moi leurs règles de ciblage. »

+++

+++Création d’une audience

**Outil :** `create_target_audience`

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

+++Obtention d’un rapport de performances d’activité

**Outil :** `get_activity_performance_report`

Obtenez un rapport de performances pour une activité de n’importe quel type.

Récupère les taux de conversion, l’effet élévateur et les niveaux de confiance. Prend en charge les activités de test A/B, de ciblage d’expérience, d’Automated Personalization, d’affectation automatique, de test multivarié et de recommandations.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `report_interval` | string | Non | Période du rapport (par exemple, `last7days`, `last30days` ou une période personnalisée) |

**Retours :** mesures au niveau de l’expérience (visiteurs, conversions, taux de conversion), calculs de l’effet élévateur, niveaux de confiance statistiques et mesures de recettes (si elles sont configurées).

**Exemple d’invite :** « Affichez-moi le rapport de performances des 12345 d’activité au cours des 30 derniers jours ».

+++

+++Obtenir un rapport sur les ordres d&#39;activité

**Outil :** `get_activity_orders_report`

Obtenez un état des commandes/revenus pour une activité de n’importe quel type.

Prend en charge les activités de test A/B, de ciblage d’expérience, d’Automated Personalization, d’affectation automatique, de test multivarié et de recommandations.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité |
| `report_interval` | string | Non | Période du rapport |

**Retours : nombre de commandes** chiffre d’affaires et valeur de commande moyenne par expérience.

**Exemple d’invite :** « Obtenir l’état des commandes pour les 12345 d’activité ».

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

+++Obtention d’un rapport Analytics for Target (A4T)

**Outil :** `get_a4t_report`

Récupérer un rapport Analytics for Target (A4T) pour une activité [!DNL Target].

Valide la configuration A4T de l’activité, puis exécute des requêtes GraphQL sur [!DNL Adobe Analytics] pour récupérer des mesures côté Analytics. Disponible uniquement pour les activités pour lesquelles les rapports A4T sont configurés.

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `activity_id` | Entier | Oui | Identifiant unique de l’activité [!DNL Target] |
| `report_interval` | string | Non | Période du rapport (par exemple, `last7days`, `last30days` ou une période personnalisée) |

**Retours :** mesures côté Analytics pour l’activité, y compris le nombre de visiteurs, les conversions, le chiffre d’affaires et l’effet élévateur par expérience, provenant directement de l’[!DNL Adobe Analytics].

**Exemple d’invite :** « Extrayez le rapport A4T pour mon test d’optimisation du passage en caisse et résumez les données de conversion côté Analytics. »

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

+++Créer un jeton de réponse

**Outil :** `create_target_response_token`

Créez un jeton de réponse personnalisé pour collecter des données supplémentaires dans les réponses [!DNL Target].

| Paramètre | Type | Requis | Description |
|---|---|---|---|
| `token_name` | string | Oui | Nom du jeton de réponse |
| `token_type` | string | Oui | Type de jeton : `SCRIPT`, `ACTIVITY`, `MBOX`, `GEO` ou `CRS` |

**Renvoie :** objet jeton de réponse créé.

**Exemple d’invite :** « Créez un jeton de réponse personnalisé appelé « campaign_id » de type ACTIVITY. »

+++

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
| Activité | 13 | `list_target_activities`, `get_activity`, `create_ab_activity`, `create_xt_activity`, `update_activity`, `update_activity_schedule`, `update_activity_state`, `update_activity_name`, `update_activity_priority`, `add_activity_variant`, `update_traffic_split`, `update_variant_offer`, `remove_activity_variant` |
| Offre | 5 | `list_target_offers`, `get_target_offer`, `create_target_offer`, `create_target_json_offer`, `update_target_offer` |
| Audience | 4 | `list_target_audiences`, `get_target_audience`, `create_target_audience`, `update_target_audience` |
| Mbox | 3 | `list_target_mboxes`, `get_target_mbox`, `list_target_mbox_profile_attributes` |
| Propriété | 1 | `list_target_properties` |
| Création de rapports | 4 | `get_activity_performance_report`, `get_activity_orders_report`, `get_activity_report_by_name`, `get_a4t_report` |
| Prévisualiser | 1 | `preview_activity` |
| Jeton de réponse | 2 | `list_target_response_tokens`, `create_target_response_token` |
| Révision | 2 | `get_target_revisions`, `get_target_entity_revisions` |
| AT.js | 2 | `get_atjs_settings`, `get_atjs_versions` |
| Modèle | 1 | `list_target_templates` |
| **Total** | **38** | |

## Ressources connexes {#tools-related}

* [Utiliser les clients MCP](target-mcp.md)
* [Référence de l’API [!DNL Adobe Target] Admin](https://developers.adobe.com/target/administer/admin-api/){target="_blank"}
