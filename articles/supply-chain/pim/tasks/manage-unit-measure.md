---
title: Gérer l'unité de mesure
description: Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l'unité et sa description, et définir des règles de conversion pour les unités associées.
author: sorenva
manager: tfehr
ms.date: 07/08/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, UnitOfMeasure, UnitOfMeasureReportingTranslation, UnitOfMeasureTranslation, UnitOfMeasureConversion, UnitOfMeasureConversionEditOrCreate, UnitOfMeasureLookup, UnitOfMeasureCalculator, UnitOfMeasureWizard, UnitOfMeasureLookupTest
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8d9b6f18fdc1c47d6a695ca6a2330f6f02fc1bd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427744"
---
# <a name="manage-unit-of-measure"></a>Gérer l'unité de mesure

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment définir une unité de mesure, fournir des traductions pour l'unité et sa description, et définir des règles de conversion pour les unités associées. Vous pouvez découvrir cette procédure à l'aide de la société fictive de démonstration USMF ou de vos propres données.

1. Accédez à **Volet de navigation > Modules > Gestion d'informations sur les produits > Gestion des produits lancés**.
2. Cliquez sur **Unités**.

## <a name="create-a-unit-of-measure"></a>Créer une unité de mesure
1. Cliquez sur **Nouveau**.
2. Dans le champ **Unité**, tapez une valeur. Entrez l'ID ou le symbole à utiliser en se rapportant à l'unité de mesure.  
3. Tapez une valeur dans le champ **Description**. Entrez un nom descriptif pour l'unité de mesure dans la langue du système.  
4. Dans le champ **Classe d'unités**, sélectionnez une option. Une classe d'unités définit le regroupement logique, tel que la superficie, la masse ou la quantité, dont l'unité de mesure fait partie.  
5. Dans le champ **Précision décimale**, entrez un nombre. Indiquez le nombre de décimales auxquelles l'unité de mesure convertie doit être arrondie lorsqu'un calcul est réalisé pour l'unité de mesure.  
6. Cliquez sur **Enregistrer**.

## <a name="define-unit-translations"></a>Définir des traductions d'unité
1. Dans le volet **Actions**, cliquez sur **Textes d'unité**.
2. Cliquez sur **Nouveau**. Utilisez le texte d'unité pour créer une traduction de l'ID ou d'un symbole représentant l'unité de mesure à utiliser sur des documents externes dans les langues du client ou spécifiques au fournisseur.  
3. Dans le champ **Langue**, saisissez ou sélectionnez une valeur.
4. Tapez une valeur dans le champ **Texte**.
5. Cliquez sur **Enregistrer**.
6. Fermez la page.
7. Dans le volet **Actions**, cliquez sur **Descriptions de l'unité traduite**.
8. Cliquez sur **Nouveau**. Définissez des descriptions spécifiques à une langue pour l'unité de mesure.  
9. Dans le champ **Langue**, saisissez ou sélectionnez une valeur.
10. Tapez une valeur dans le champ **Description**.
11. Cliquez sur **Enregistrer**.
12. Fermez la page.

## <a name="define-unit-conversion-rules"></a>Définir des règles de conversion d'unités
1. Dans le volet **Actions**, cliquez sur **Conversion d'unités**. Définissez les règles pour convertir l'unité de mesure vers et depuis d'autres unités de mesure appartenant à la classe d'unités sélectionnée.  
2. Cliquez sur **Nouveau** pour ouvrir la boîte de dialogue.
3. Dans le champ **Facteur**, entrez un nombre. Facteur de conversion entre l'Unité d'origine et l'Unité de destination. Par exemple, le facteur de conversion du centimètre vers le mètre est 100, car il y a 100 centimètres dans 1 mètre.  
4. Dans le champ **Unité de destination**, saisissez ou sélectionnez une valeur.
5. Dans le champ **Arrondi**, sélectionnez une option. Définissez l'arrondi de la valeur convertie.  
6. Cliquez sur **OK**.
7. Fermez la page.

