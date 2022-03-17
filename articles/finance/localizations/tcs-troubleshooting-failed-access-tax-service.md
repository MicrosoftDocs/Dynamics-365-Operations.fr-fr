---
title: Échec de l’accès au service fiscal
description: Cette rubrique explique comment résoudre un problème pour accéder au service de calcul des taxes.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 48a75cd0c1d91c3b3d9c3fb2e6cab93a76756532
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388555"
---
# <a name="failed-to-access-tax-service"></a>Échec de l’accès au service fiscal

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique explique comment corriger l’erreur « Échec de l’accès au service fiscal » du service de calcul des taxes.

## <a name="symptoms"></a>Symptômes

Dans Microsoft Dynamics 365 Finance, accédez à **Taxe** \> **Installer** \> **Configuration de taxe** \> **Paramètres du service de taxe**. Sur l’onglet **Général**, vous activez l’option **Activer le calcul des taxes**. Si vous essayez ensuite de sélectionner une valeur dans le champ **Nom du paramétrage de la fonctionnalité**, une erreur se produit. Le message d’erreur indique « Échec de l’accès au service fiscal ».

## <a name="cause"></a>Cause

Cette erreur se produit car Finance ne peut pas accéder au service de calcul des taxes.

## <a name="resolution"></a>Résolution 

1. Connectez-vous à Microsoft Dynamics Lifecycle Services (LCS).
2. Sur la page **Environnement**, sur l’onglet **Compléments d’environnement**, recherchez l’élément **Calcul des taxes** et vérifiez son statut. Le statut doit être défini sur **Installation** ou **Installé**. Si le complément du service de calcul des taxes n’est pas installé, vous recevrez l’erreur.

## <a name="mitigation"></a>Atténuation

1. Dans LCS, sur la page **Finance**, dans la section **Intégration Power Platform**, sélectionnez **Installer un nouveau complément**.
2. Faites défiler vers le bas de la page et sélectionnez le complément **Calcul des taxes** pour l’installer.
3. Retournez dans votre environnement Finance et essayez d’accéder au service de calcul des taxes.

> [!NOTE]
> Avant d’installer le service de calcul des taxes, consultez les [Conditions préalables requises du service de calcul des taxes](global-get-started-with-tax-calculation-service.md#prerequisites).
> 
> Si vous ne pouvez pas installer le complément, car la section **Intégration Power Platform** n’est pas disponible, voir [Présentation du complément](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Si vous rencontrez toujours l’erreur après avoir installé le complément, contactez votre administrateur système.
