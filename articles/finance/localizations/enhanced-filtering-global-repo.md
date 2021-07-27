---
title: Filtrage amélioré par RCS dans le référentiel RCS/Global
description: Cette rubrique décrit les capacités de filtrage améliorées pour le référentiel RCS Global, qui ont été améliorées pour inclure les filtres supplémentaires.
author: JaneA07
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0aa172550f86a9918a9aaa811e49cb20e7befcdb
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359247"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a>Options de filtrage améliorées RCS pour trouver des configurations dans le référentiel global/RCS

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les capacités de filtrage améliorées pour le référentiel Regulatory Configuration Services (RCS) Global, qui ont été améliorées pour inclure les la capacité de filtrer avec les critères suivants : 
- **Pays/région** : basé sur les codes pays ISO  
- Types de **Balises** pour :
  - Zone fonctionnelle
  - Fonctionnalités
  - Secteur 
  - Document commercial 

Pour faciliter la recherche des configurations spécifiques ou connexes, vous pouvez appliquer des filtres, individuellement ou en groupe. Par exemple, pour rechercher un seul type de documents commerciaux configurables liés aux factures fournisseur, vous pouvez appliquer un filtre **Type de document commercial** pour rechercher ce type de document. 

[![Section Filtre pour le référentiel Global.](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG) 

Vous pouvez affiner la recherche en sélectionnant le type de document, par exemple « facture fournisseur » et en cliquant sur **Appliquer le filtre**. L’exemple suivant montre les résultats lors du filtrage sur **Type de document commercial** avec le type de document ajouté. 

[![Filtre appliqué et Importer pour le type de document commercial.](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG) 

Les résultats filtrés peuvent être importés dans un référentiel RCS d’utilisateurs ou un environnement Dynamics 365 Finance, individuellement ou en tant qu’ensemble. Pour ce faire, sélectionnez le groupe de configurations et cliquez sur **Importer**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]