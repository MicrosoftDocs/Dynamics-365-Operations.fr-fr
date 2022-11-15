---
title: Configurer l’importation avancée des rapprochements bancaires à l’aide de la génération d’états électroniques
description: Cet article explique comment utiliser la gestion des états électroniques pour configurer le processus d’importation de rapprochement bancaire.
author: angelad116
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: d24e117b21e291dba1e41d9fa15187b84ff795cf
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752718"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Configurer l’importation avancée des rapprochements bancaires à l’aide de la génération d’états électroniques

[!include [banner](../includes/banner.md)]

La fonctionnalité de rapprochement bancaire avancé permet d’importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 Finance. Cet article explique comment configurer la fonctionnalité d’importation de vos relevés bancaires. Le paramétrage de l’importation de relevé bancaire varie selon le format de votre relevé bancaire électronique. Microsoft Dynamics 365 Finance prend en charge trois formats de relevés bancaires : ISO20022, MT940 et BAI2. 

## <a name="set-up-the-electronic-reporting-configuration"></a>Paramétrer la configurations de la gestion des états électroniques

1. Accédez à **Espaces de travail \> États électroniques**.
2. Sur la vignette du fournisseur de configuration **Microsoft**, sélectionnez **Référentiels**.
3. Sélectionnez **Global**, puis sélectionnez **Ouvrir**.
4. Si une connexion au référentiel doit être établie, sélectionnez le lien bleu dans la boîte de dialogue.
5. Dans la liste de configurations, recherchez **Modèle de relevé de rapprochement bancaire avancé \> Format ABR BAI2**.
6. Sélectionnez le format **BAI2**.
7. Dans l’organisateur **Versions**, sélectionnez la version la plus récente, puis sélectionnez **Importer**.

## <a name="set-up-the-bank-statement-format"></a>Configurer le format de relevé bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Configuration du rapprochement bancaire avancé \> Format de relevé bancaire**.
2. Cliquez sur **Nouveau**.
3. Définissez les champs **Format de relevé** et **Nom**.
4. Cochez la case **Format d’importation électronique générique**.
5. Définissez le champ **Configuration du format d’importation** sur **BAI2**.

## <a name="set-up-the-bank-account"></a>Configurer le compte bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Ouvrez le compte bancaire.
3. Dans l’organisateur **Rapprochement**, définissez l’option **Rapprochement bancaire avancé** sur **Oui**.
4. Définissez le champ **Format de relevé** sur le format **BAI2** que vous avez créé précédemment.

## <a name="import-the-bank-statement"></a>Importer le relevé bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Rapprochement de relevé bancaire \> Relevés bancaires**.
2. En haut de la page **Relevés bancaires**, sélectionnez **Importer le relevé**.
3. Définissez le champ **Compte bancaire** sur le compte bancaire du relevé.
4. Définissez le champ **Format de relevé** sur le format **BAI2** que vous avez créé précédemment.
5. Sélectionnez **Parcourir**, puis sélectionnez le fichier **BAI**.
6. Sélectionnez **Charger**.
7. Sélectionnez **OK** pour importer le fichier sélectionné.


## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Exemples de formats de relevé bancaire et de mises en page techniques
Voici des exemples de définitions de mise en page techniques de fichier d’importation de rapprochement bancaire avancé et trois fichiers d’exemples de relevé bancaire associés : [Exemples de fichiers d’importation](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Définition de mise en page technique                             | Fichier d’exemple de relevé bancaire          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)     |
| DynamicsAXISO20022Layout | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)     |

