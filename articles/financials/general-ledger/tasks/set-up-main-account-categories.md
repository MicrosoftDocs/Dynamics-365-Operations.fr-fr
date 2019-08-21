---
title: Paramétrage des catégories de compte principal
description: Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e33df434b6a4361872bad10250fe3547d7c4affa
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834804"
---
# <a name="set-up-main-account-categories"></a>Paramétrer des catégories de compte principal

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI. Les catégories de compte principal créées par défaut peuvent être renommées mais pas supprimées. Des catégories de compte supplémentaires peuvent être créées et utilisées à des fins de génération d'états et d'analyse. La société fictive USMF est citée en exemple dans cette tâche.


## <a name="create-a-main-account-category"></a>Créer une catégorie de compte principal
1. Accédez à Comptabilité > Plan de comptes > Comptes > Catégories de compte principal.
2. Cliquez sur Nouveau.
3. Entrez un nom unique dans le champ Catégorie de compte principal.
4. Dans le champ Description, entrez une description de la catégorie de compte principal.
5. Dans le champ Type de compte principal, sélectionnez le type de compte principal qui est lié à la catégorie.

## <a name="link-main-accounts-to-account-category"></a>Lier des comptes principaux à une catégorie de compte
1. Cliquez sur Lier les comptes principaux.
2. Dans la liste, sélectionnez les comptes principaux à affecter à la catégorie de compte principal.
    * Affecter des comptes principaux à une catégorie de compte principal a pour effet d'agréger les soldes des comptes lorsque cette catégorie est utilisée pour la génération d'états financiers et l'analyse.  
3. Activez ou désactivez l'option Lié pour sélectionner les comptes principaux.
4. Cliquez sur OK.
5. Cliquez sur Oui.

