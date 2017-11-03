---
title: "Vue d'ensemble du rapprochement bancaire avancé"
description: "Cet article décrit le flux du processus de rapprochement bancaire avancé. La fonctionnalité avancée de rapprochement bancaire permet d'importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 33150777222faa97af7488c59ab13cb0fb9e8e2c
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

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
    -   Une règle de correspondance de rapprochement est un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de transactions bancaires Microsoft Dynamics 365 for Finance and Operations, Enterprise edition lors du processus de rapprochement. En fonction des procédures de votre entreprise, vous pouvez paramétrer plusieurs règles de correspondance pour automatiser et optimiser votre processus de rapprochement.

3.  Rapprocher les relevés bancaires avec des transactions bancaires Finance and Operations.
    -   Exécuter la correspondance et la création des journaux de rapprochement automatiques.
    -   Afficher les relevés bancaires et les transactions bancaires Finance and Operations.
    -   Valider automatiquement des transactions bancaires Finance and Operations si elles figurent sur un relevé bancaire mais n'apparaissent pas dans Finance and Operations.
    -   Générer un relevé de rapprochement.






