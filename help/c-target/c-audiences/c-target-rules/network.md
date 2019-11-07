---
keywords: ciblage;réseau;réseau target;fournisseur de services internet;fsi;nom de domaine;vitesse de connexion;fournisseur de services internet target;nom de domaine target;vitesse de connexion target
description: Vous pouvez créer des audiences dans Adobe Target en fonction des détails du réseau.
title: Création d’audiences dans Adobe Target en fonction des détails du réseau.
uuid: 06b9c92a-e9bd-4444-abbc-7b6dffcefea7
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Réseau{#network}

Vous pouvez créer des audiences basées sur les détails du réseau.

1. Dans l’interface [!DNL Target], cliquez sur **[!UICONTROL Audiences]** &gt; **[!UICONTROL Créer une audience]**.
1. Donnez un nom à l’audience.
1. Cliquez sur **[!UICONTROL Ajouter une règle]** &gt; **[!UICONTROL Réseau]**.
1. Cliquez sur **[!UICONTROL Sélectionner]**, puis sélectionnez l’une des options suivantes :

   * **Fournisseur de services Internet :** Un fournisseur de services Internet est une organisation qui fournit un accès Internet à ses abonnés, souvent en échange d’un abonnement payant mensuel ou annuel. La plupart des fournisseurs de services Internet fournissent des services supplémentaires, tels que l’hébergement web ou la messagerie électronique. Le champ Fournisseur de services Internet est un fournisseur de services Internet commercial (par exemple, Comcast ou TimeWarner) ou une autre entité telle qu’une entreprise ou une université.

      Vous trouverez ci-dessous des exemples de fournisseurs de services Internet connus aux États-Unis :

      | Nom populaire | Nom du fournisseur de services Internet | Nom de domaine | Exemple d’adresse IP |
      |---|---|---|---|
      | Cablevision | Cablevision Systems Corp. | *.optonline.net | 68.196.130.239 |
      | CenturyLink | Qwest Communications Company, LLC | *.centurylink.net | 64.40.65.0 |
      | Charter Communications | Charter Communications | *.charter.com | 71.85.225.124 |
      | Comcast | Comcast Cable Communications, Inc. | *.comcast.net | 76.27.24.28 |
      | Cox | Cox Communications Inc. | *cox.net | 68.224.174.22 |
      | Speakeasy | MegaPath Corporation | *.speakeasy.net | 66.93.240.0 |
      | Time Warner | Time Warner Cable Internet LLC | *.res.rr.com | 72.229.28.185 |
      | Verizon FiOS | MCI Communications Services, Inc. d/b/a Verizon Business | *.fios.verizon.net | 173.68.112.34 |
      | Vivint | Smartrove Inc. | *.vivintwireless.net | 170.72.26.105 |
      | AT&amp;T Wireless | AT | *.mycingular.net |  |
      | Sprint mobile | Sprint Personal Communications Systems | adresse ip |  |
      | T-Mobile | T-Mobile USA, Inc. | adresse ip | 208.54.86.0 |
      | Verizon Wireless | Cellco Partnership DBA Verizon Wireless | *.myvzw.com | 70.195.74.199 |

      >[!NOTE]
      >
      >Lorsque vous effectuez un ciblage en fonction du fournisseur de services Internet, utilisez son nom et non le nom populaire. Veillez à créer la règle de sorte qu’elle ne soit pas sensible à la casse ou utilisez toujours le format minuscules.

      Vous pouvez tester les fournisseurs de services Internet et les valeurs de nom de domaine. [](https://www.whoismyisp.org)https://www.whoismyisp.org est une ressource intéressante à des fins de ciblage. Vous pouvez utiliser les exemples d’adresses IP indiqués dans le tableau ci-dessous, ou saisir la vôtre. Puis, utilisez le paramètre `themboxOverride.browserIp= URL` pour imiter cette adresse IP.

   * **Nom de domaine :** Il s’agit du nom de domaine de l’adresse IP du visiteur. Il ne s’agit pas du nom de domaine du site web que vous utilisez avec [!DNL Target]. Ce nom de domaine est associé à l’adresse IP du visiteur et est parfois appelé « nom d’hôte ». Il est souvent très similaire au nom du fournisseur de services Internet. Parfois, le nom d’hôte fait référence à des noms anciens de sociétés qui ont changé la marque de leur nom de fournisseur de services Internet mais pas le nom de domaine.
   * **Vitesse de connexion :** Il s’agit de la vitesse de connexion du visiteur à Internet. Les options sont : large bande, câble, ligne commutée, mobile, oc3, oc12, satellite, t1, t2, sans fil et xdsl.

      Ce champ est basé sur le type de connexion et non sur la vitesse réelle elle-même. [!DNL Target] ne peut pas déterminer la vitesse exacte des connexions. Le type de connexion à large bande est utilisé lorsqu’il n’y a aucune indication d’autres types de connexion. Un type spécifique doit donc être choisi.

1. (Facultatif) Cliquez sur **[!UICONTROL Ajouter une règle]**, puis définissez des règles supplémentaires pour l’audience.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

L’illustration suivante présente une audience qui cible les visiteurs qui utilisent AT&amp;T avec une vitesse de connexion de [!UICONTROL Mobile].

![Ciblage de réseau](assets/target_network.png)

## Vidéo de formation : Création d’audiences

Cette vidéo fournit des informations sur l’utilisation des catégories d’audiences.

* Créer des audiences
* Définir des catégories d’audiences

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=fre_fr)