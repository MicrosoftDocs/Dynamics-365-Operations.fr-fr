---
title: Ajouter un calcul à un modèle de configuration de produit
description: Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e23d33c6911310cca6aac0df4589e909568a86a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5258069"
---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Ajouter un calcul à un modèle de configuration de produit

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit. Elle montre comment créer une expression logique utilisant l’opérateur « Si » pour définir une hauteur de haut-parleur de 10 pour les haut-parleurs blancs et de 15 pour les autres finitions. Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.


## <a name="add-a-calculation"></a>Ajouter un calcul

## <a name="create-calculation-expression"></a>Créer une expression de calcul
1. Cliquez sur Modifier l’expression.
2. Dans le champ ConstraintBody, entrez « If[CabinetFinish=="White", 10, 15] ».
3. Cliquez sur Valider.
4. Cliquez sur Fermer.
5. Cliquez sur OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]