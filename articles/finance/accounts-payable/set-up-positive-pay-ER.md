---
title: Configurer et générer des fichiers de paie positifs à l'aide d'états électroniques
description: Cette rubrique décrit comment paramétrer le paiement positif à l'aide d'états électroniques.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 43dd1a9cba1fe8df5cff26fe76af7e2957a0d6a4
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544484"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Configurer des fichiers de paie positifs à l'aide d'états électroniques

Paramétrez le paiement positif pour générer la liste électronique de chèques qui est fournie à la banque. Puis, lorsque le chèque est présenté à la banque, la banque le compare avec la liste des chèques. Si le chèque correspond à un chèque de la liste, la banque le compense. Si le chèque ne correspond pas à un chèque dans la liste, la banque le conserve pour examen.

## <a name="set-up-the-electronic-reporting-configuration"></a>Paramétrer la configurations de la gestion des états électroniques

1. Accédez à **Espaces de travail \> États électroniques**.
2. Sur la vignette du fournisseur de configuration **Microsoft**, sélectionnez **Référentiels**.
3. Sélectionnez **Global**, puis sélectionnez **Ouvrir**.
4. Si une connexion au référentiel doit être établie, sélectionnez le lien bleu dans la boîte de dialogue.
5. Dans la liste de configurations, recherchez et sélectionnez **Modèle de paiement positif \> Format de paiement positif**.
6. Dans l'organisateur **Versions**, sélectionnez la version la plus récente, puis sélectionnez **Importer**.

## <a name="set-up-a-positive-pay-format"></a>Paramétrer un format de paiement positif

1. Accédez à **Gestion de la trésorerie et de la banque \> Paramétrage \> Formats de paiement positifs**.
2. Cliquez sur **Nouveau**.
3. Définissez les champs **Format du paiement** et **Description**.
4. Cochez la case **Format d’exportation électronique générique**.
5. Définissez le champ **Configuration du format d'exportation** sur **Format de paiement positif**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Affecter un format de paiement positif à un compte bancaire

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Ouvrez le compte bancaire.
3. Dans l'organisateur **Général**, définissez le champ **Format de paiement positif** au format qui a été créé précédemment.
4. Définissez le champ **Date de début du paiement positif** à la date du jour.

## <a name="generate-a-positive-pay-file"></a>Générer un fichier de paiement positif

1. Accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**.
2. Ouvrez un compte bancaire pour lequel un paiement positif est mis en place.
3. Sélectionnez **Gérer les paiements \> Paiement positif \> Fichier de paiement positif**.
4. Définissez le champ **Date limite**. Les chèques émis avant cette date seront inclus.

Le fichier XML résultant sera téléchargé.
