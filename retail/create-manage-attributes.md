---
title: "Création et gestion des attributs"
description: "Cet article décrit les attributs dans Microsoft Dynamics 365 for Operations. Les attributs vous permettent de décrire un produit et ses caractéristiques via les champs définis par l&quot;utilisateur."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 26c628e10aaa5f47bc87d7510ca8f41ab3630204
ms.lasthandoff: 03/31/2017


---

# <a name="create-and-manage-attributes"></a>Création et gestion des attributs

Cet article décrit les attributs dans Microsoft Dynamics 365 for Operations. Les attributs vous permettent de décrire un produit et ses caractéristiques via les champs définis par l'utilisateur.

Les attributs vous permettent de décrire un produit et ses caractéristiques via les champs définis par l'utilisateur. Par exemple, vous pouvez spécifier la capacité de stockage du produit et la capacité du disque dur, et indiquer si le produit est conforme à la norme Energy Star. Les attributs peuvent être associés à diverses entités de vente au détail, telles que des catégories de produits et des canaux de vente au détail, et des valeurs par défaut peuvent être définies pour eux. Les produits héritent leurs attributs et les valeurs par défaut de ces attributs lorsqu'ils sont associés à des catégories de produits ou à des canaux de vente au détail. Les valeurs par défaut peuvent être remplacées au niveau du produit individuel, au niveau de canal de vente au détail, ou dans un catalogue de vente au détail.

#### <a name="examples"></a>Exemples

Catégorie

Attribut

Valeurs autorisées

Valeur par défaut

TV et vidéo

Marque

Toute valeur de **Marque** valide

Aucun(e)

TV

Taille d'écran

**50 cm**–**200 cm**

Aucun(e)

Résolution verticale

**480i****720p****1080i** ou **1080p**

**1080p**

Fréquence d'actualisation de l'écran

**60 hz**, **120 hz** ou **240 hz**

**60 hz**

Entrées HDMI

**0**–**10**

**3**

Entrées DVI

**0**–**10**

**1**

Entrées composites

**0**–**10**

**2**

Entrées de composants

**0**–**10**

**1**

LCD

Compatible 3D

**Oui** ou **Non**

**Oui**

Activé pour la 3D

**Oui** ou **Non**

**Non**

Plasma

Température de fonctionnement

**0**–**43** degrés

**0**

Température de fonctionnement

**0**–**43** degrés

**100**

Projection

Garantie du tube de projection

**6****12** ou **18** mois

**12**

\# de tubes de projection

**1**–**5**

**3**

## <a name="attribute-type"></a>Type d'attribut
  [![attributes-fixed-copy](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) Les attributs sont basés sur les types d'attributs. Les types d'attributs identifient le type de données pouvant être spécifiées pour un attribut spécifique. Actuellement, Microsoft Dynamics 365 for Operations prend en charge les types d'attributs suivants :

-   **Devise** – Ce type d'attribut prend en charge les valeurs de devise. Il peut être lié (autrement dit, il peut prendre en charge une plage de valeurs), ou il peut être laissé ouvert.
-   **Date et heure** – Ce type d'attribut prend en charge les valeurs de date et d'heure. Il peut être lié (autrement dit, il peut prendre en charge une plage de valeurs), ou il peut être laissé ouvert.
-   **Décimal** – Ce type d'attribut prend en charge les valeurs numériques qui incluent des décimales. Il prend également en charge les unités de mesure. Il peut être lié (autrement dit, il peut prendre en charge une plage de valeurs), ou il peut être laissé ouvert.
-   **Entier** – Ce type d'attribut prend en charge les valeurs numériques. Il prend également en charge les unités de mesure. Il peut être lié (autrement dit, il peut prendre en charge une plage de valeurs), ou il peut être laissé ouvert.
-   **Texte** – Ce type d'attribut prend en charge les valeurs de texte. Il prend également en charge un ensemble prédéfini de valeurs possibles (énumération).
-   **Booléen** – Ce type d'attribut prend en charge les valeurs binaires (**vrai**/**faux**).
-   **Référence**.

## <a name="attribute"></a>Attribut
  [![createandmanageattribute-8](./media/createandmanageattribute-8.png)](./media/createandmanageattribute-8.png) Outre le nom, le nom convivial, la description et le texte d'aide, un ou plusieurs des types d'informations suivants peuvent être capturés pour un attribut :

-   Valeur par défaut
-   Métadonnées d'attribut, telles que les métadonnées qui indiquent si l'attribut peut être trouvé, raffiné, ou trié

## <a name="attribute-group"></a>Groupe d'attributs
  [![createandmanageattribute-10](./media/createandmanageattribute-10.png)](./media/createandmanageattribute-10.png) Une fois les attributs définis, ils peuvent être regroupés en groupes d'attributs. Les groupes d'attributs fournissent des regroupements d'attributs individuels, et peuvent être affectés à des catégories de vente au détail ou à des canaux de vente au détail.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Affectation de groupes d'attributs à des catégories de vente au détail
  [![createandmanageattribute-12](./media/createandmanageattribute-12.png)](./media/createandmanageattribute-12.png) Un ou plusieurs groupes d'attributs peuvent être associés à des nœuds de catégorie dans la hiérarchie des catégories de produits vendus au détail. Lorsque les produits ont été classés en catégorie, ils héritent des attributs inclus aux groupes d'attributs.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Affectation de groupes d'attributs à des catégories de magasins de vente au détail
  [![createandmanageattribute-13-1024x576](./media/createandmanageattribute-13-1024x576.png)](./media/createandmanageattribute-13-1024x576.png) Un ou plusieurs groupes d'attributs peuvent être associés à un ou plusieurs magasins de vente au détail dans la hiérarchie des magasins de vente au détail. Lorsque des produits ont été enrichis pour des magasins de vente au détail spécifiques, ils héritent des attributs inclus aux groupes d'attributs.

## <a name="overriding-attribute-values"></a>Remplacement des valeurs d'attribut
### <a name="at-the-product-level"></a>Au niveau du produit

  [![createandmanageattribute-14-1024x576](./media/createandmanageattribute-14-1024x576.png)](./media/createandmanageattribute-14-1024x576.png) Les valeurs par défaut des attributs peuvent être remplacées au niveau du produit (c'est-à-dire, pour des produits individuels).

### <a name="in-a-retail-catalog"></a>Dans un catalogue de vente au détail

  [![createandmanageattribute-2](./media/createandmanageattribute-2.png)](./media/createandmanageattribute-2.png) Pour des produits individuels, les valeurs par défaut des attributs peuvent être remplacées dans des catalogues spécifiques qui sont ciblés pour des canaux de vente au détail spécifiques.

### <a name="at-the-retail-channel-level"></a>Au niveau du canal de vente au détail

  [![createandmanageattribute-1](./media/createandmanageattribute-1.jpg)](./media/createandmanageattribute-1.jpg) Pour des produits individuels, les valeurs par défaut des attributs peuvent être remplacées dans des catalogues spécifiques qui sont ciblés pour des canaux de vente au détail spécifiques.


