---
title: Activer les propositions de budget (version préliminaire)
description: Cette rubrique explique comment activer la fonctionnalité de proposition de budget dans Informations financières.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222532"
---
# <a name="enable-budget-proposals-preview"></a>Activer les propositions de budget (version préliminaire)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique explique comment activer la fonctionnalité de proposition de budget dans Informations financières.

1. Utilisez les informations de la page d’environnement dans Microsoft Dynamics Lifecycle Services (LCS) pour se connecter à l’instance principale d’Azure SQL pour cet environnement. Exécutez la commande Transact-SQL (T-SQL) suivante pour activer les déploiements en mode Flighting pour l’environnement sandbox. (Vous devrez peut-être activer l’accès pour votre adresse IP dans LCS avant de pouvoir vous connecter à distance à Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Ignorez cette étape si vous utilisez la version 10.0.20 ou ultérieure, ou si vous utilisez un déploiement Service Fabric. L’équipe Informations financières devrait déjà avoir activé le déploiement en mode Flighting pour vous. Si vous ne voyez pas la fonctionnalité dans l’espace de travail **Gestion des fonctionnalités**, ou si vous rencontrez des problèmes lorsque vous essayez de l’activer, contactez <fiap@microsoft.com>.

2. Ouvrez l’espace de travail **Gestion des fonctionnalités** et procédez comme suit :

    1. Sélectionnez **Rechercher des mises à jour**.
    2. Recherchez **Proposition de budget** et activez cette fonction.

3. Aller à **Budgétisation \> Configurer \> Budgétisation de base \> Proposition de budget (version préliminaire)** et sélectionnez **Activer la fonctionnalité**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
