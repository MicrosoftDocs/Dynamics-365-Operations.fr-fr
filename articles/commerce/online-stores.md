---
title: Paramétrer un canal de magasin en ligne
description: Cet article fournit des informations sur les canaux de magasins en ligne et leur configuration dans Dynamics 365 Commerce.
author: kfend
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelManagementWorkspace, RetailOnlineStoreList
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16161
ms.assetid: 646d560c-f856-4701-b4ca-44e357ef09b8
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c427b0eba2120123a47f52029d70896be88b9ec0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022581"
---
# <a name="set-up-an-online-store-channel"></a>Paramétrer un canal de magasin en ligne

[!include [banner](includes/banner.md)]

Cet article fournit des informations sur les canaux de magasins en ligne et leur configuration dans Dynamics 365 Commerce.

Commerce prend en charge plusieurs canaux de vente au détail. Ces canaux comprennent les magasins en ligne, les centres d'appels et les magasins de vente au détail (également appelés magasins traditionnels). Les magasins en ligne permettent à un détaillant d'être présent en ligne, afin de donner aux clients la possibilité de se procurer ses produits en ligne, en plus de ses magasins de vente au détail. Si les clients achètent des produits dans un magasin en ligne, ils peuvent se faire expédier les produits ou aller les chercher dans un magasin local. 

Vous créez un magasin en ligne dans le client Commerce. Ce magasin en ligne est ensuite publié sur un magasin en ligne tiers qui est intégré à Commerce. Le magasin en ligne tiers sert de vitrine au magasin en ligne, et vous fournit un système de gestion des clients (CMS) et des fonctionnalités d'interface utilisateur. Plusieurs intégrations de ce type sont disponibles. 

Les propriétés que vous définissez pour le magasin en ligne régissent le comportement du magasin en ligne. Par exemple, vous définissez la hiérarchie de catégories de navigation et l'affectez au magasin en ligne. Lorsque vous publiez le magasin en ligne sur un magasin en ligne tiers, la hiérarchie des catégories de navigation s'affiche dans la version en ligne du magasin. Les clients utilisent ensuite la hiérarchie des catégories de navigation pour parcourir le magasin en ligne et rechercher des produits. 

Pour créer un magasin en ligne, vous devez paramétrer les composants qui activent les transactions à traiter pour le magasin. Par exemple, vous devez ajouter des assortiments, appliquer des attributs et paramétrer les modes de paiement et d'expédition. Vous pouvez également définir des prix, des promotions, des remises, des accords commerciaux et des conditions d'expédition qui sont spécifiques au magasin en ligne. 

Après la publication du magasin en ligne sur le magasin en ligne tiers, vous pouvez créer des catalogues de produits pour le magasin en ligne. Les produits du catalogue deviennent des listes de produits dans le magasin en ligne. Lorsqu'un client achète des produits dans le magasin en ligne, le stock disponible est mis à jour et synchronisé dans le client. En outre, les commandes client sont générées pour les achats et transmises au client pour être traitées et exécutées.

## <a name="set-up-an-online-store"></a>Paramétrage d'un magasin en ligne

Pour paramétrer un magasin en ligne, vous devez effectuer les tâches ci-après.

1. Créez le magasin en ligne.
2. Ajoutez le magasin en ligne aux hiérarchies d'organisation appropriées.
3. Ajoutez des assortiments contenant des produits disponibles dans le magasin en ligne.
4. Affectez ou créez des groupes de prix pour le magasin en ligne.
5. Paramétrez les modes de livraison disponibles dans le magasin en ligne.
6. Affectez les modes de paiement acceptés par le magasin en ligne.
7. Si vous autorisez les clients à commander des produits en ligne et à les retirer ensuite dans un magasin local, affecter des groupes de localisateurs au magasin en ligne.
8. Affectez des attributs pour les canaux, les produits et les commandes client du magasin en ligne. Les attributs de canal s'appliquent à l'ensemble du magasin en ligne, les attributs de produit s'appliquent aux produits qui sont proposés dans le magasin en ligne et les attributs de commande client s'appliquent aux commandes client générées depuis le magasin en ligne.
9. Mettez les attributs en correspondance pour déterminer leur comportement dans le magasin en ligne. Par exemple, des attributs peuvent être définis comme obligatoires ou faire l'objet d'une recherche.
10. Publiez le magasin en ligne pour générer la structure du magasin sur le magasin en ligne tiers de votre choix.

    > [!IMPORTANT]
    > Avant de publier le magasin en ligne, vous devez paramétrer un lieu de distribution pour celui-ci.

## <a name="commerce-channel-navigation-hierarchies"></a>Hiérarchies de navigation du canal de commerce

Avant de créer un magasin en ligne, vous devez définir la hiérarchie de navigation du canal de commerce à utiliser pour celui-ci. La hiérarchie de navigation du canal représente la hiérarchie de catégories affichée dans le magasin en ligne après sa publication. Lorsque vous publiez des catalogues de produits sur le magasin en ligne, les produits du catalogue sont mis en correspondance avec les catégories de la hiérarchie de navigation du canal. Les clients peuvent ensuite utiliser la hiérarchie pour naviguer dans le magasin en ligne.

## <a name="organization-hierarchies"></a>Hiérarchies de l'organisation

Les hiérarchies d'organisation permettent de structurer les canaux de commerce et de matérialiser les relations entre les organisations qui composent votre entreprise. Lorsque vous paramétrez des magasins en ligne, vous pouvez les ajouter à une hiérarchie d'organisation. Les magasins partagent ensuite les données utilisées pour les assortiments, le réapprovisionnement et la génération d'états. 

Lorsque vous créez une hiérarchie d'organisation, vous lui affectez un objectif. L'objectif indiquer comment la hiérarchie est utilisée dans la structure commerciale. Vous pouvez créer une hiérarchie d'organisation pour vos opérations de magasin et l'utiliser pour les assortiments, le réapprovisionnement et la génération d'états. 

Sinon, vous pouvez créer une hiérarchie d'organisation distincte pour chaque objectif. Vous pouvez également créer plusieurs hiérarchies ayant le même objectif et affecter un canal distinct à chacune d'entre elles. Si vous prévoyez de publier des catalogues de produits sur le magasin en ligne, vous devez, au minimum, ajouter le magasin en ligne à une hiérarchie d'organisation pour les assortiments. Les produits d'un catalogue sont sélectionnés à partir des assortiments affectés au magasin en ligne. Lors de la publication du catalogue, le processus de publication compare les dates d'effet de l'assortiment affecté au magasin en ligne aux produits inclus dans le catalogue afin de déterminer les produits à mettre à disposition dans le magasin en ligne.