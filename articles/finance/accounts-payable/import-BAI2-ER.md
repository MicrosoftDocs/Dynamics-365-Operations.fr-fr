---
title: Configurer l'importation avancée des rapprochements bancaires à l'aide de la génération d'états électroniques
description: Cette rubrique explique comment utiliser la génération d'états électroniques pour configurer le processus d'importation de rapprochement bancaire avancé pour les relevés BAI2.
author: panolte
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
ms.openlocfilehash: 39f1d8ba561ab0e36346f1dfb4f70df318c92a37
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544500"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Configurer l'importation avancée des rapprochements bancaires à l'aide de la génération d'états électroniques

[!include [banner](../includes/banner.md)]

La fonctionnalité de rapprochement bancaire avancé permet d’importer des relevés bancaires électroniques et de les rapprocher automatiquement avec des transactions bancaires dans Microsoft Dynamics 365 Finance. Cette rubrique explique comment configurer la fonctionnalité d’importation de vos relevés bancaires BAI2.

## <a name="set-up-the-electronic-reporting-configuration"></a>Paramétrer la configurations de la gestion des états électroniques

1. Accédez à **Espaces de travail \> États électroniques**.
2. Sur la vignette du fournisseur de configuration **Microsoft**, sélectionnez **Référentiels**.
3. Sélectionnez **Global**, puis sélectionnez **Ouvrir**.
4. Si une connexion au référentiel doit être établie, sélectionnez le lien bleu dans la boîte de dialogue.
5. Dans la liste de configurations, recherchez **Modèle de relevé bancaire \> Modèle de relevé bancaire BAI2**.
6. Sélectionnez le format **BAI2**.
7. Dans l'organisateur **Versions**, sélectionnez la version la plus récente, puis sélectionnez **Importer**.

## <a name="set-up-the-bank-statement-format"></a>Configurer le format de relevé bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Configuration du rapprochement bancaire avancé \> Format de relevé bancaire**.
2. Cliquez sur **Nouveau**.
3. Définissez les champs **Format de relevé** et **Nom**.
4. Cochez la case **Format d’importation électronique générique**.
5. Définissez le champ **Configuration du format d'importation** sur **BAI2**.

## <a name="set-up-the-bank-account"></a>Configurer le compte bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Ouvrez le compte bancaire.
3. Dans l'organisateur **Rapprochement**, définissez l’option **Rapprochement bancaire avancé** sur **Oui**.
4. Définissez le champ **Format de relevé** sur le format **BAI2** que vous avez créé précédemment.

## <a name="import-the-bank-statement"></a>Importer le relevé bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Rapprochement de relevé bancaire \> Relevés bancaires**.
2. En haut de la page **Relevés bancaires**, sélectionnez **Importer le relevé**.
3. Définissez le champ **Compte bancaire** sur le compte bancaire du relevé.
4. Définissez le champ **Format de relevé** sur le format **BAI2** que vous avez créé précédemment.
5. Sélectionnez **Parcourir**, puis sélectionnez le fichier **BAI**.
6. Sélectionnez **Charger**.
7. Sélectionnez **OK** pour importer le fichier sélectionné.
