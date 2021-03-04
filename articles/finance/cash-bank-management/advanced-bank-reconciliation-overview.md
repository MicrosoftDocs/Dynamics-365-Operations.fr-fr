---
title: Vue d’ensemble du rapprochement bancaire avancé
description: Cet article décrit le flux du processus de rapprochement bancaire avancé. La fonctionnalité avancée de rapprochement bancaire permet d’importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires.
author: panolte
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 22104
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b26b6e1e50e5a9b53ca6b5315de760f5bcec4769
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443267"
---
# <a name="advanced-bank-reconciliation-overview"></a>Vue d’ensemble du rapprochement bancaire avancé

[!include [banner](../includes/banner.md)]

Cet article décrit le flux du processus de rapprochement bancaire avancé. La fonctionnalité avancée de rapprochement bancaire permet d’importer des relevés bancaires qui peuvent être automatiquement rapprochés dans les transactions bancaires.

La fonctionnalité de rapprochement bancaire avancé vous permet d’importer des relevés bancaires. Le relevé bancaire importé peut ensuite être automatiquement rapproché depuis les transactions bancaires. Voici les étapes du flux de rapprochement bancaire avancé.

1.  Configurer une importation de relevé bancaire.
    -   Importer les relevés bancaires via l’infrastructure d’entité de données.
    -   Trois formats de relevé bancaire standard sont incorporés : ISO20022, BAI2 et MT940.
    -   La fonctionnalité peut être étendue à n’importe quel format.

2.  Paramétrer une souche de numéros à utiliser pour le rapprochement bancaire avancé, puis définissez les règles de correspondance du rapprochement bancaire.
    -   Une règle de correspondance de rapprochement est un ensemble de critères utilisés pour filtrer les lignes de relevé bancaire et les lignes de document bancaire Microsoft Dynamics 365 Finance lors du processus de rapprochement. En fonction des procédures de votre entreprise, vous pouvez paramétrer plusieurs règles de correspondance pour automatiser et optimiser votre processus de rapprochement.

3.  Rapprocher les relevés bancaires avec des transactions bancaires Finance.
    -   Exécuter la correspondance et la création des journaux de rapprochement automatiques.
    -   Afficher les relevés bancaires et les transactions bancaires Finance.
    -   Valider automatiquement des transactions bancaires Finance si elles figurent sur un relevé bancaire mais n’apparaissent pas dans l’application Finance.
    -   Générer un relevé de rapprochement.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]