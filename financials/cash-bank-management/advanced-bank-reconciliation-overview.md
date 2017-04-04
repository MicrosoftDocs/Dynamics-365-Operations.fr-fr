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

Cet article décrit le flux du processus de rapprochement bancaire avancé. La fonctionnalité avancée de rapprochement bancaire permet d'importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires.

La fonctionnalité de rapprochement bancaire avancé vous permet d'importer des relevés bancaires. Le relevé bancaire importé peut ensuite être automatiquement rapproché depuis les transactions bancaires. Voici les étapes du flux de rapprochement bancaire avancé.

1.  Configurer une importation de relevé bancaire.
    -   Importer les relevés bancaires via l'infrastructure d'entité de données.
    -   Trois formats de relevé bancaire standard sont incorporés : ISO20022, BAI2 et MT940.
    -   La fonctionnalité peut être étendue à n'importe quel format.

2.  Paramétrer une souche de numéros à utiliser pour le rapprochement bancaire avancé, puis définissez les règles de correspondance du rapprochement bancaire.
    -   Un rapprochement Règle correspondante est un ensemble de critères utilisés pour filtrer les lignes du relevé bancaire et Microsoft Dynamics 365 pour les lignes de transaction bancaire d'opérations durant le processus de rapprochement. Selon votre pratique commerciale, vous pouvez paramétrer plusieurs règle correspondante d'automatiser et optimiser votre processus de rapprochement.

3.  Permet de rapprocher les relevés bancaires avec Dynamics 365 pour les transactions bancaires d'opérations.
    -   Exécuter la correspondance et la création des journaux de rapprochement automatiques.
    -   Permet d'afficher les relevés bancaires et le Dynamics 365 pour les transactions bancaires d'opérations côte à côte.
    -   Permet de valider automatiquement Dynamics 365 pour les transactions bancaires d'opérations si elles apparaissent dans un relevé bancaire mais n'apparaissent pas dans Dynamics 365 pour les opérations.
    -   Générer un relevé de rapprochement.




