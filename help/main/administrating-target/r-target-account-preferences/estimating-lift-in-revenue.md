---
keywords: effet élévateur dans les recettes;recettes;estimation de l’effet élévateur dans les recettes;calculer l’effet élévateur;valeur estimée
description: Estimez l’effet élévateur que vous pourriez obtenir si chaque visiteur voit l’expérience gagnante, si les tendances se poursuivent comme elles l’ont fait au cours du test.
title: Qu’est-ce que j’estime de l’effet élévateur dans les recettes ?
feature: Administration & Configuration
role: Admin
exl-id: a3c5e20e-f5d5-4b6f-b169-59d5916584ab
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 84%

---

# Estimation de l’effet élévateur dans les recettes

Utilisation [!DNL Adobe Target] pour estimer l’effet élévateur dans les recettes que vous atteindriez si tous les utilisateurs consultaient l’expérience gagnante.

>[!NOTE]
>
>L’effet élévateur estimé n’est pas disponible pour [!UICONTROL Ciblage d’expérience] (XT) actuellement.

La fonctionnalité d’effet élévateur estimé est désactivée par défaut. Elle peut être activée dans les préférences du compte. Seuls les utilisateurs administrateurs d’Experience Cloud peuvent l’activer ou la désactiver. Si l’effet élévateur estimé est activé, les champs correspondants ne s’affichent pas dans l’interface. La désactivation de cette fonctionnalité n’entraîne pas une perte des données, notamment des données utilisées pour les estimations. Celles-ci reposent sur les données collectées, que la fonctionnalité soit activée ou non.

>[!IMPORTANT]
>
>La croissance estimée n’est qu’une estimation. Son exactitude dépend de plusieurs facteurs, notamment des projections de chiffres si la tendance actuelle se poursuit. Ces valeurs sont des estimations reposant sur les anciennes performances et ne doivent pas être utilisées comme des conseils financiers. Les résultats à venir peuvent varier.

Cette estimation calcule le montant de l’effet élévateur obtenu par l’expérience gagnante et le nombre total de visiteurs durant toute la vie de l’activité, et affiche la croissance que vous pourriez obtenir si chaque visiteur affichait l’expérience gagnante, si les tendances ne changent pas durant le test.

L’effet élévateur en termes de revenu est calculé d’après le revenu par visite (RPV) obtenu à partir de l’indicateur d’objectif principal.

L’effet élévateur estimé est calculé à l’aide de la formule suivante : (&lt;winning experience=&quot;&quot; rpv=&quot;&quot;> - &lt;control experience=&quot;&quot; rpv=&quot;&quot; span=&quot;&quot; id=&quot;0&quot; translate=&quot;no&quot; />&lt;total number=&quot;&quot; of=&quot;&quot; visitors=&quot;&quot; in=&quot;&quot; the=&quot;&quot; activity=&quot;&quot;>&#42;

Le chiffre obtenu est arrondi à une décimale au maximum si la forme condensée ne contient qu’un seul chiffre avant la virgule (par exemple, 1,6M, 60K, 900, 8,5K, 205K).

Si par exemple l’expérience gagnante indique une hausse de 0,59 euros et l’expérience de contrôle une hausse de 0,15 euros, l’estimation calcule une hausse de 0,44 euros par visiteur. Si les visiteurs sont au nombre de 75 000, la croissance des recettes obtenue est de 33 000 euros, à condition que tous les visiteurs consultent l’expérience gagnante et que la tendance actuelle se poursuive.

De même, si l’expérience gagnante indique une hausse de 0.17 euros par rapport à l’expérience de contrôle et si le nombre de visiteurs était de 192 000 durant toute la vie du test et que la tendance actuelle se poursuit, la croissance des recettes attendue est de 32 640 euros.

Le champ de l’effet élévateur estimé dans les recettes s’affiche sous la forme « --- » dans les cas suivants :

* le nombre de visiteurs n’est pas suffisant pour calculer une estimation raisonnable ;
* la valeur estimée de la mesure n’a pas été indiquée dans la page de configuration de la mesure ;
* l’expérience la plus performante correspond au contrôle.

Lors de la configuration de l’objectif d’une activité, le champ Valeur estimée fournit une valeur pour celui-ci. Cette valeur permet à Target de calculer l’effet élévateur estimé dans les recettes. Ce champ est facultatif. Toutefois, les recettes incrémentielles des mesures qui ne sont pas liées aux recettes ne peuvent pas être calculées sans ce champ. Les données sont de type devise. Ce champ apparaît progressivement lorsque l’utilisateur a indiqué l’action effectuée pour atteindre l’objectif.

Si 100 % des visiteurs consultent l’expérience gagnante, les recettes estimées apparaissent dans la partie supérieure des rapports Target.
