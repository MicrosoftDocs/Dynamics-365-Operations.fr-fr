---
title: "Présentation des informations sur les produits"
description: "Cette rubrique fournit des informations sur la gestion des informations sur les produits. La gestion des informations sur les produits nécessite une définition, une catégorisation et des identifiants de produits partagés dans toutes les entités juridiques, ainsi que les configurations spécifiques d'un produit, pour s'adapter aux processus d'entreprise."
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 72dbc5d383352d4d6444d07495fdef00137b1c7f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/26/2018

---

# <a name="product-information-overview"></a>Présentation des informations sur les produits

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

Cette rubrique fournit des informations sur la gestion des informations sur les produits. La gestion des informations sur les produits nécessite une définition, une catégorisation et des identifiants de produits partagés dans toutes les entités juridiques, ainsi que les configurations spécifiques d'un produit, pour s'adapter aux processus d'entreprise. 

Les informations sur les produits sont la base de la chaîne d'approvisionnement et des applications au détail dans tous les secteurs d'activité. Elles font référence aux processus et aux technologies qui ont pour but de gérer des informations sur les produits de manière centralisée (par exemple, entre plusieurs chaînes d'approvisionnement). Il est primordial que les définitions, la documentation, les attributs et les identificateurs de produits partagés soient utilisés. Dans les différents modules d'une solution commerciale, les informations et la configuration spécifiques à un produit sont requises pour gérer des processus d'entreprise liés aux produits, gammes de produits, ou catégories de produits spécifiques.

## <a name="product-definition"></a>Définition du produit

Un produit est principalement défini par un numéro, un nom, ainsi qu'une description du produit. Toutefois, d'autres données sont également nécessaires afin de décrire un produit ou un service :

- Type de produit : Article ou service
- Sous-type de produit : Produits distincts ou produits génériques
- Définition du modèle de variante de produit :

     - Dimensions de produit et groupes de dimensions
     - Nomenclature produit
     - Modèles de configuration de produit

- Association du produit à une ou plusieurs catégories
- Définition des attributs de produit et de catégorie
- Images du produit
- Documents joints
- Unités de mesure et conversions associées
- Traductions pour tous les noms et descriptions

## <a name="distribution-export-and-import-of-product-data"></a>Distribution, exportation et importation des données de produit

La définition du produit peut être créée dans Microsoft Dynamics 365 for Finance and Operations. Elle peut également être importée des systèmes de gestion des cycles de vie des produits, des systèmes de gestion des données relatives aux produits ou des systèmes de gestion d'informations sur les produits. Lorsque plusieurs instances de Finance and Operations sont utilisées, une instance est généralement utilisée comme base des données de produit pour toutes autres instances. Cette approche est prise en charge par un grand ensemble d'entités de données qui activent l'exportation ou l'importation de données de définition de produit d'une instance à une autre.

Pour prendre en charge la distribution des données de produit sur plusieurs instances, Finance and Operations vous permet d'utiliser Common Data Service. Les définitions de produit peuvent être exportées d'une instance de Finance and Operations vers Common Data Service. Les définitions de produit peuvent être utilisées pour mettre en service d'autres applications de gestion, telles que Microsoft Dynamics 365 for Sales, avec les données de produit.

Notez que, dans les organisations dynamiques et agiles, les informations sur le produit changent chaque jour. Par conséquent, la mise à jour des données de produit exactes et réelles est un processus d'entreprise critique en tant que tel.

## <a name="product-masters-and-product-variants"></a>Produits génériques et variantes de produit

Dans un monde Agile, où les produits doivent être rapidement adaptés aux besoins du client, les définitions de produit spécifient un ensemble de produits au lieu de produits distincts. Dans Microsoft Dynamics 365 for Finance and Operations, ces produits sont appelés *Produits génériques*. Les produits génériques tiennent à jour la définition et les règles qui indiquent comment les produits distincts sont décrits et se comportent dans les processus d'entreprise. En fonction de ces définitions, des produits distincts peuvent être générés. Ces produits distincts sont appelés *variantes de produit*.

Dans Finance and Operations, un produit générique est associé à un groupe de dimensions de produit et une technologie de configuration pour spécifier les règles métier. Les dimensions de produit (Couleur, Taille, Style et Configuration) sont un ensemble spécifique d'attributs qui peuvent être utilisés dans l'application pour définir et suivre les comportements spécifiques des produits associés. Ces dimensions aident également les utilisateurs à rechercher et identifier les produits.

## <a name="configuration-technologies"></a>Technologies de configuration

Vous avez le choix entre trois technologies de configuration :

- Les variantes prédéfinies sont définies par des dimensions de produit prédéfinies. La définition de la variante inclut la définition d'une combinaison valide de dimensions spécifiques, telles que la couleur, le style et la taille. Chaque combinaison produit une variante de produit distincte.
- La configuration basée sur les dimensions est généralement utilisée dans les scénarios de fabrication et vous permet d'utiliser la dimension de configuration dans la définition des nomenclatures. Une fois qu'une configuration spécifique est activée, le système utilise le sous-ensemble de lignes de nomenclature valides pour cette configuration dans le cadre de la planification et de la production. Ce concept est également appelé *nomenclature globale*, car une nomenclature partagée est utilisée pour toutes les configurations d'un produit.
- La configuration basée sur les contraintes utilise un modèle de configuration de produit pour décrire tous les attributs possibles et les composants nécessaires afin de décrire toutes les variantes possibles d'un produit dans un modèle unique. Les contraintes des combinaisons d'attributs peuvent être décrites via des expressions régulières ou des contraintes de table. Les modèles et les configurateurs de configuration deviennent plus importants en matière de gestion des informations sur les produits et sont utilisés dans tous les secteurs d'activité.

Lorsque vous planifiez l'implémentation de Finance and Operations, il est primordial que vous choisissiez la technologie de configuration appropriée à un processus d'entreprise. Un produit ne peut pas être converti d'un modèle à un autre après implémentation.

## <a name="product-variant-model-definition-workspace"></a>Espace de travail de définition du modèle de variante de produit

L'espace de travail **Définition du modèle de variante de produit** fournit une vue d'ensemble des produits génériques. Il affiche également le statut du lancement des produits génériques et des variantes de produit associés aux entités juridiques spécifiques.

## <a name="released-products"></a>Produits lancés

Les produits lancés dans une entité juridique spécifique sont appelés *produits lancés*. Les produits peuvent être lancés en vrac dans une entité juridique ou dans diverses entités juridiques en même temps. Comme plusieurs propriétés et attributs des produits doivent être ajoutés par entité juridique, l'espace de travail **Gestion des produits lancés** vous permet de surveiller et d'exécuter les produits lancés récemment dans chaque entité juridique ou dans les sous-organisations d'une entité juridique.

### <a name="released-product-maintenance-workspace"></a>Espace de travail Gestion des produits lancés

Vous pouvez configurer l'espace de travail **Gestion des produits lancés** à partir de l'option de menu **Configurer mon espace de travail**. Sélectionnez une hiérarchie de catégories et une catégorie pour appliquer un filtre. Pour ajuster les données de produit appropriées dans l'espace de travail, vous pouvez également définir, en jours, les plages de gestion pour **Produits lancés récemment** et **Produits lancés arrêtés**.

L'espace de travail se compose d'une synthèse de vignettes et de deux listes. La liste **Dossiers ouverts** affiche les dossiers de produits relatifs aux produits de la hiérarchie de catégories de produit sélectionnée qui ne sont pas terminés ni clôturés. La liste **Lancement récent** affiche les produits qui ont été lancés dans la plage de gestion qui est définie dans la configuration de l'espace de travail. Pour chaque article dans la liste, le contrôle est réalisé et le statut de contrôle est affiché. Ce statut peut indiquer que les configurations requises pour l'entité juridique n'ont pas été exécutées. Dans la liste, vous pouvez accéder directement aux pages **Détails des produits lancés**, **Gestion des attributs de produit**, **Gestion des catégories de produit**, **Paramètres de commande par défaut** et **Traductions des textes** pour effectuer la configuration requise du produit.

### <a name="manually-creating-a-new-released-product"></a>Créer manuellement un nouveau produit lancé

Vous pouvez créer manuellement un produit lancé en une seule exécution, en fonction des processus de l'organisation et de toutes les règles d'entreprise indiquant si cette fonction doit être utilisée. Cette fonction permet de créer un nouveau produit et de le lancer automatiquement dans l'entité juridique actuelle. Pour créer un nouveau produit, cliquez sur **Produits lancés** dans l'espace de travail **Gestion des produits lancés** ou dans la page de liste **Produit lancé**.

