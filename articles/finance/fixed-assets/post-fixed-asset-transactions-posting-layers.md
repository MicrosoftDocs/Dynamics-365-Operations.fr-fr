---
title: Valider des transactions d'immobilisation dans des couches de validation
description: Cet article donne une vue d'ensemble de la fonctionnalité de couche de validation pour les transactions d'immobilisation.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3001
ms.assetid: 7dabde57-0843-47c3-85ef-f36b6f472e30
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ab5adfdec259207898d25778e4e3bbbaebb452f1
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177704"
---
# <a name="post-fixed-asset-transactions-to-posting-layers"></a>Valider des transactions d'immobilisation dans des couches de validation

[!include [banner](../includes/banner.md)]

Cet article donne une vue d'ensemble de la fonctionnalité de couche de validation pour les transactions d'immobilisation.

Une immobilisation est souvent amortie de différentes manières, en fonction des différents objectifs. L'amortissement à des fins fiscales est calculé conformément aux règles de taxe actuelles afin d'atteindre l'amortissement le plus élevé possible avant impôts, tandis que l'amortissement à des fins de génération d'états est calculé conformément à la législation et aux normes comptables. Les différents types d'amortissements sont calculés et enregistrés de manière distincte dans les couches de validation.

Chaque registre associé à une immobilisation est paramétré pour une couche de validation particulière qui a un objectif d'amortissement global. Il existe dix couches de validation : Actuel, Opérations, Taxes, puis sept couches personnalisées. Vous pouvez aussi désactiver la validation dans la comptabilité pour le registre en définissant le champ Valider dans la comptabilité sur Non. Le champ Couche de validation est alors automatiquement défini sur Aucune. En général, les registres qui ne sont pas validés dans la comptabilité sont utilisés à des fins de déclaration de taxe. Cette approche vous donne une flexibilité supplémentaire pour supprimer les transactions historiques du registre des actifs, car elles n'ont pas été validées dans la comptabilité.

Les journaux des immobilisations sont définis à l'aide de la page  Noms des journaux sous Comptabilité > Paramétrage du journal > Noms des journaux. Chaque journal dans lequel vous pouvez valider des amortissements est défini par son nom pour une seule et unique couche de validation. La couche de validation du journal ne peut pas être modifiée. Cette restriction permet de garantir que les transactions de chaque couche de validation sont distinctes. Au moins un nom de journal doit être créé pour chaque couche de validation. Si vous utilisez des registres qui ne sont pas validés dans la comptabilité, vous devez également créer un journal dans lequel la couche de validation est définie sur Aucune.

Vous pouvez désigner les comptes généraux pour les transactions d'immobilisation dans la page Profils de validation d'immobilisation. Pour chaque profil de validation, vous devez sélectionner le type de transaction et le registre appropriés, puis désigner les comptes généraux. Paramétrez un enregistrement de profil de validation pour chaque registre qui sera validé dans la comptabilité.

> [!NOTE] 
> En utilisant les registres déduits, vous pouvez valider des transactions dans les différentes couches de validation simultanément. Vous créez les transactions du registre principal dans un journal dans lequel la couche de validation qui correspond à la couche de validation du registre. Lors de la validation, les transactions du registre déduit sont validées dans leurs couches de validation appropriées.

Pour plus d'informations, voir [Registres dérivés](derived-books.md) et [Validation avec des registres déduits](post-derived-value-models.md).



