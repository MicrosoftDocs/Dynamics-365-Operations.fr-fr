--- 
title: "Ajouter un calcul à un modèle de configuration de produit"
description: "Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 9ac2d9bcc316a57941136c248a0c5ff030a1fe49
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="add-a-calculation-to-a-product-configuration-model"></a>Ajouter un calcul à un modèle de configuration de produit

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment ajouter un nouveau calcul à un modèle de configuration de produit. Elle montre comment créer une expression logique utilisant l'opérateur « Si » pour définir une hauteur de haut-parleur de 10 pour les haut-parleurs blancs et de 15 pour les autres finitions. Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.


## <a name="add-a-calculation"></a>Ajouter un calcul

## <a name="create-calculation-expression"></a>Créer une expression de calcul
1. Cliquez sur Modifier l'expression.
2. Dans le champ ConstraintBody, entrez « If[CabinetFinish=="White", 10, 15] ».
3. Cliquez sur Valider.
4. Cliquez sur Fermer.
5. Cliquez sur OK.


