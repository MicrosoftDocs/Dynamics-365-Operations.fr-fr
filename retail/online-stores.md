---
title: Vue d&quot;ensemble du magasin en ligne
description: "Cet article fournit des informations sur des stockages en ligne Retail et comment les paramétrer dans Microsoft Dynamics 365 for Operations."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 40fbf8b4fdfed32dd67013b6b21cc2c8ee3d31e6
ms.lasthandoff: 03/31/2017


---

# <a name="online-store-overview"></a>Vue d'ensemble du magasin en ligne

Cet article fournit des informations sur des stockages en ligne Retail et comment les paramétrer dans Microsoft Dynamics 365 for Operations.

Le module Commerce et vente au détail de Microsoft Dynamics 365 for Operations prend en charge plusieurs canaux de vente au détail. Ces canaux de vente au détail comprennent les magasins en ligne, les centres d'appels et les magasins de vente au détail (également appelés magasins traditionnels). Les magasins en ligne permettent à un détaillant d'être présent en ligne, afin de donner aux clients la possibilité de se procurer ses produits en ligne, en plus de ses magasins de vente au détail. Si les clients achètent des produits dans un magasin en ligne, ils peuvent se faire expédier les produits ou aller les chercher dans un magasin de vente au détail local. Vous créez un magasin en ligne dans le client Dynamics 365 for Operations. Ce magasin en ligne est ensuite publié sur un magasin en ligne tiers qui est intégré à Dynamics 365 for Operations. Le magasin en ligne tiers sert de vitrine au magasin en ligne, et vous fournit un système de gestion des clients (CMS) et des fonctionnalités d'interface utilisateur. Plusieurs intégrations de ce type sont disponibles pour Dynamics 365 for Operations. Les propriétés que vous définissez pour le magasin en ligne régissent le comportement du magasin en ligne. Par exemple, vous définissez la hiérarchie des catégories de navigation dans Dynamics 365 for Operations et l'affectez au magasin en ligne. Lorsque vous publiez le magasin en ligne sur un magasin en ligne tiers, la hiérarchie des catégories de navigation s'affiche dans la version en ligne du magasin. Les clients utilisent ensuite la hiérarchie des catégories de navigation pour parcourir le magasin en ligne et rechercher des produits. Pour créer un magasin en ligne, vous devez paramétrer les composants qui activent les transactions à traiter pour le magasin. Par exemple, vous devez ajouter des assortiments, appliquer des attributs et paramétrer les modes de paiement et d'expédition. Vous pouvez également définir des prix, des promotions, des remises, des accords commerciaux et des conditions d'expédition qui sont spécifiques au magasin en ligne. Après avoir publié le magasin en ligne sur le magasin en ligne tiers, vous pouvez créer des catalogues de produits vendus au détail pour le magasin en ligne. Les produits du catalogue deviennent des listes de produits dans le magasin en ligne. Lorsqu'un client achète des produits dans le magasin en ligne, le stock disponible est mis à jour et synchronisé dans le client. En outre, les commandes client sont générées pour les achats et transmises au client pour être traitées et exécutées.

## <a name="set-up-an-online-store"></a>Paramétrage d'un magasin en ligne
Pour paramétrer un magasin en ligne, vous devez effectuer les tâches ci-après.

1.  Créez le magasin en ligne.
2.  Ajoutez le magasin en ligne aux hiérarchies d'organisation appropriées.
3.  Ajoutez des assortiments contenant des produits disponibles dans le magasin en ligne.
4.  Affectez ou créez des groupes de prix pour le magasin en ligne.
5.  Paramétrez les modes de livraison disponibles dans le magasin en ligne.
6.  Affectez les modes de paiement acceptés par le magasin en ligne.
7.  Si vous autorisez les clients à commander des produits en ligne et à les retirer ensuite dans un magasin local, affecter des groupes de localisateurs au magasin en ligne.
8.  Affectez des attributs pour les canaux, les produits et les commandes client du magasin en ligne. Les attributs de canal s'appliquent à l'ensemble du magasin en ligne, les attributs de produit s'appliquent aux produits qui sont proposés dans le magasin en ligne et les attributs de commande client s'appliquent aux commandes client générées depuis le magasin en ligne.
9.  Mettez les attributs en correspondance pour déterminer leur comportement dans le magasin en ligne. Par exemple, des attributs peuvent être définis comme obligatoires ou faire l'objet d'une recherche.
10. Publiez le magasin en ligne pour générer la structure du magasin sur le magasin en ligne tiers de votre choix. **Important :** avant de publier le magasin en ligne, vous devez paramétrer un lieu de distribution pour celui-ci.

## <a name="retail-channel-navigation-hierarchies"></a>Hiérarchies de navigation du canal de vente au détail
Avant de créer un magasin en ligne, vous devez définir la hiérarchie de navigation du canal de vente au détail à utiliser pour celui-ci. La hiérarchie de navigation du canal de vente au détail représente la hiérarchie de catégories affichée dans le magasin en ligne après la publication du magasin. Lorsque vous publiez les catalogues de produits vendus au détail sur le magasin en ligne, les produits du catalogue sont mis en correspondance avec les catégories de la hiérarchie de navigation du canal de vente au détail. Les clients peuvent ensuite utiliser la hiérarchie pour naviguer dans le magasin en ligne.

## <a name="organization-hierarchies"></a>Hiérarchies d'organisation
Les hiérarchies d'organisation permettent de structurer les canaux de vente au détail. Les hiérarchies d'organisation représentent les relations entre les organisations qui composent votre entreprise. Lorsque vous paramétrez des magasins en ligne, vous pouvez les ajouter à une hiérarchie d'organisation. Les magasins partagent ensuite les données utilisées pour les assortiments, le réapprovisionnement et la génération d'états. Lorsque vous créez une hiérarchie d'organisation, vous lui affectez un objectif. L'objectif indiquer comment la hiérarchie est utilisée dans la structure commerciale. Vous pouvez créer une hiérarchie d'organisation pour vos opérations de magasin et l'utiliser pour les assortiments, le réapprovisionnement et la génération d'états. Sinon, vous pouvez créer une hiérarchie d'organisation distincte pour chaque objectif. Vous pouvez également créer plusieurs hiérarchies ayant le même objectif et affecter un canal distinct à chacune d'entre elles. Si vous prévoyez de publier des catalogues de produits vendus au détail sur le magasin en ligne, vous devez, au minimum, ajouter le magasin en ligne à une hiérarchie d'organisation pour les assortiments. Les produits d'un catalogue sont sélectionnés à partir des assortiments affectés au magasin en ligne. Lors de la publication du catalogue, le processus de publication compare les dates d'effet de l'assortiment affecté au magasin en ligne aux produits inclus dans le catalogue afin de déterminer les produits à mettre à disposition dans le magasin en ligne.


