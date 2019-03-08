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
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e46c7c86b93a3471ba10ec7ae6789f227bc9779c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "311448"
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

