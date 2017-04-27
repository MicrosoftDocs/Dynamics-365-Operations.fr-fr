---
title: "Vue d&quot;ensemble du rapprochement bancaire avancé"
description: "Cet article décrit le flux du processus de rapprochement bancaire avancé. La fonctionnalité avancée de rapprochement bancaire permet d&quot;importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 00f022da597b1de2454e93123de31731c6a65962
ms.openlocfilehash: 20363ef1917f7d0796cb0d5cd8e623c598b5ee01
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Vue d'ensemble du rapprochement bancaire avancé

[!include[banner](../includes/banner.md)]


Cet article décrit le flux du processus de rapprochement bancaire avancé. La fonctionnalité avancée de rapprochement bancaire permet d'importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires.

La fonctionnalité de rapprochement bancaire avancé vous permet d'importer des relevés bancaires. Le relevé bancaire importé peut ensuite être automatiquement rapproché depuis les transactions bancaires. Voici les étapes du flux de rapprochement bancaire avancé.

1.  Configurer une importation de relevé bancaire.
    -   Importer les relevés bancaires via l'infrastructure d'entité de données.
    -   Trois formats de relevé bancaire standard sont incorporés : ISO20022, BAI2 et MT940.
    -   La fonctionnalité peut être étendue à n'importe quel format.

2.  Paramétrer une souche de numéros à utiliser pour le rapprochement bancaire avancé, puis définissez les règles de correspondance du rapprochement bancaire.
    -   Une règle de correspondance de rapprochement est un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de transactions bancaires Microsoft Dynamics 365 for Operations lors du processus de rapprochement. En fonction des procédures de votre entreprise, vous pouvez paramétrer plusieurs règles de correspondance pour automatiser et optimiser votre processus de rapprochement.

3.  Rapprocher les relevés bancaires avec des transactions bancaires Dynamics 365 for Operations.
    -   Exécuter la correspondance et la création des journaux de rapprochement automatiques.
    -   Afficher les relevés bancaires et les transactions bancaires Dynamics 365 for Operations.
    -   Valider automatiquement des transactions bancaires Dynamics 365 for Operations si elles figurent sur un relevé bancaire mais n'apparaissent pas dans Dynamics 365 for Operations.
    -   Générer un relevé de rapprochement.






