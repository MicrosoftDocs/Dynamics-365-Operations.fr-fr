---
title: Paramétrer des catégories de compte principal
description: Cette rubrique explique comment paramétrer les catégories de compte principales dans Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 957fdc184410dc85f54cd3163799a9003f0727bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222214"
---
# <a name="set-up-main-account-categories"></a>Paramétrer des catégories de compte principal

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer les catégories de compte principales. Les catégories de compte principal sont utilisées pour les états par défaut dans les états financiers et dans Power BI. Les catégories de compte principal créées par défaut peuvent être renommées mais pas supprimées. Des catégories de compte supplémentaires peuvent être créées et utilisées à des fins de génération d’états et d’analyse. Cette rubrique utilise la société fictive USMF.

## <a name="create-a-main-account-category"></a>Créer une catégorie de compte principal
1. Dans le volet de navigation, accédez à **Modules > Comptabilité > Plan de comptes > Comptes > Catégories de compte principales**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Catégorie de compte principale**, saisissez un nom unique.
4. Dans le **champ Description**, entrez une description de la catégorie de compte principal.
5. Dans le champ **Type de compte principal**, sélectionnez le type de compte principal qui est lié à la catégorie.

## <a name="link-main-accounts-to-account-category"></a>Lier des comptes principaux à une catégorie de compte
1. Cliquez sur **Lier les comptes principaux**.
2. Dans la liste, sélectionnez les comptes principaux à affecter à la catégorie de compte principal en cochant les cases dans la colonne **Lié**. Affecter des comptes principaux à une catégorie de compte principal a pour effet d’agréger les soldes des comptes lorsque cette catégorie est utilisée pour la génération d’états financiers et l’analyse.  
3. Activez ou désactivez l’option **Lié** pour choisir les comptes principaux.
4. Cliquez sur **OK**.
5. Cliquez sur **Oui**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]