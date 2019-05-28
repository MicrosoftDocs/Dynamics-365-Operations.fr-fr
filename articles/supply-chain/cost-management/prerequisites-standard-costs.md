---
title: Prérequis pour les coûts standard
description: Cette rubrique décrit les étapes essentielles de l'utilisation des coûts standard.
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d5a4a4e49ef1cee923011ddab24497c65f85c1e3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547811"
---
# <a name="prerequisites-for-standard-costs"></a>Prérequis pour les coûts standard

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les étapes essentielles de l'utilisation des coûts standard. Les étapes suivantes dépendent des opérations de la société. Par exemple, les étapes diffèrent pour un environnement hors fabrication, un environnement de fabrication qui n'utilise pas de gammes et un environnement de fabrication qui utilise des gammes. 

Pour paramétrer les coûts standard, procédez comme suit :

**1. Créez un groupe de modèles d'article pour les coûts standard.**

La page **Groupes de modèles d'article** permet de créer un nouveau groupe de coûts standard et d'affecter un modèle de stock de **Coût standard**. L'identificateur du groupe de modèles d'article doit être significatif, comme **Coût std**. Activez les cases à cocher pour indiquer que le groupe doit autoriser les stocks financiers négatifs et valider les stocks physiques et financiers. Ce groupe de coûts standard sera affecté aux articles.

**2. Définissez les comptes généraux associés aux écarts de coûts standard.** 

La page **Plan de comptes** permet de définir les comptes généraux associés aux écarts de coûts standard. Ces comptes généraux doivent être définis avant qu'ils puissent être affectés dans la page **Validation**. Les comptes généraux peuvent refléter les groupes d'articles et les groupes de coûts.

**3. Affectez des comptes généraux aux validations d'articles associées aux écarts de coûts standard.** 

La page **Validation** permet d'affecter les comptes généraux associés aux écarts de coûts standard. Vous pouvez spécifier un compte général d'écart par article (ou groupe d'articles) et par groupe de coûts (ou type de groupe de coûts) ou spécifier que le compte spécifique s'applique à tous les articles et tous les groupes de coûts. Ces options correspondent aux relations de coûts pour les tables, les groupes et pour tous. 

Avant de définir les règles de validation d'articles, utilisez la page **Combinaisons de transactions** pour activer les relations de coûts (pour les tables, les groupes et pour tous).

**4. Définissez les paramètres de stock associés aux coûts standard.** 

-  L'onglet **Comptabilité de stock** de la page **Paramétrage des stratégies comptables de stock > Paramètres** permet de définir deux paramètres de contrôle des coûts associés aux coûts standard.

    -  Dans le champ **Analyse des coûts**, sélectionnez **Aucun** ou **Sous-comptabilité**. Si vous sélectionnez **Sous-comptabilité**, l'analyse des coûts est *active*. Une analyse active des coûts est essentielle pour le calcul, la retenue et l'affichage de la segmentation des groupes de coûts dans une structure de produits à plusieurs niveaux pour des articles de coûts standard. Lorsque l'analyse des coûts est active, vous pouvez déclarer et analyser le stock, les travaux en cours et le coût des marchandises vendues par groupe de coûts dans un niveau, dans plusieurs niveaux ou dans le format total. Lorsque l'analyse des coûts est active, l'activation du coût d'un article fabriqué entraînera le stockage de la segmentation des groupes de coûts dans l'enregistrement des coûts de l'article. 

    -  Si vous sélectionnez **Aucun**, la segmentation des groupes de coûts ne sera pas mise à jour pour les articles de coût standard. En d'autres termes, le coût standard d'un article fabriqué sera calculé et mis à jour en tant que montant unique sans segmentation des groupes de coûts. Les contributions de coûts des composants fabriqués seront regroupées sur le montant unique.

-  Dans le champ **Écarts par rapport à standard**, sélectionnez **Résumé** ou **Par groupe de coûts**. Si vous sélectionnez **Par groupe de coûts**, vous pouvez identifier les écarts de prix d'achat et les écarts de production par groupe de coûts. Vous pouvez également identifier les quatre types d'écarts de production : taille du lot, quantité, prix et écarts de remplacement. Si vous sélectionnez **Résumé**, vous ne pouvez pas identifier les écarts par groupe de coûts, ni les quatre types d'écarts de production. Vous pouvez uniquement afficher un écart de production récapitulé.

-  La stratégie d'écarts de coûts standard fonctionne indépendamment de la stratégie d'analyse des coûts. En d'autres termes, vous pouvez choisir la stratégie d'analyse des coûts **Aucun** et sélectionner des écarts par groupe de coûts, pour que les écarts de production par groupe de coûts soient tout de même capturés.

**5. Créez des versions d'évaluation des coûts standard.** 

La page **Paramétrage de la version d'évaluation des coûts** permet de créer une ou plusieurs versions d'évaluation des coûts standard. Chaque version d'évaluation des coûts doit être désignée par un type d'évaluation des **coûts standard** et doit permettre d'inclure des données de coûts.

**6. Préparez un client existant pour utiliser les coûts standard.** 

Les clients qui souhaitent modifier leurs articles existants pour passer à un modèle de stock de coûts standard doivent utiliser la page **Conversions de coût standard**.


<a name="related-topics"></a>Rubriques connexes
--------

[Vue d'ensemble de la conversion du coût standard](standard-cost-conversion-overview.md)

### <a name="blogs"></a>Blogs

#### <a name="community-blogs"></a>Blogs de la communauté

- [Procédure de paramétrage des coûts standard pour les matières directes dans Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [Coûts de main d'œuvre directs standard dans Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)
