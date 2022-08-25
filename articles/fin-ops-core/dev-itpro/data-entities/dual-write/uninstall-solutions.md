---
title: Désinstaller les solutions d’orchestration de l’application en double écriture
description: Cet article décrit comment désinstaller les solutions d’orchestration de l’application en double écriture.
author: RamaKrishnamoorthy
ms.date: 03/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2022-01-21
ms.openlocfilehash: fd9dc98ec1323a2ef262a330a400a6bd3833e554
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288728"
---
# <a name="uninstall-dual-write-application-orchestration-solutions"></a>Désinstaller les solutions d’orchestration de l’application en double écriture

[!include [banner](../../includes/banner.md)]

Cet article décrit comment désinstaller les solutions d’orchestration de l’application en double écriture.

Certains clients installent involontairement le package d’orchestration d’application à double écriture qui installe plusieurs solutions dans leur environnement Microsoft Dataverse. L’installation de solutions superflues dans le package peut entraîner des problèmes inattendus et indésirables.

Pour résoudre les problèmes liés à l’installation du package d’orchestration d’applications à double écriture, désinstallez les solutions à double écriture indésirables dans l’ordre suivant :

1. Dynamics365FinanceAndOperationsAnchor_managed
1. msdyn_OneFSSCM_managed (si présent)
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps_managed
1. Dynamics365Notes_managed (Pour désinstaller cette solution, vous devez ouvrir un ticket de support auprès de Microsoft.)
1. DualWriteCore_managed
1. Dynamics365AssetManagementApp_managed
1. Dynamics365AssetManagement_managed
1. Dynamics365SupplyChainExtended_managed
1. Dynamics365FinanceExtended_managed
1. HCMCommon_managed
1. Dynamics365FinanceAndOperationsCommon_managed
1. Dynamics365Company_managed
1. CurrencyExchangeRates_managed
1. msdyn_AssetCommon_managed
1. FieldServiceCommon_managed

Si des solutions de carnet d’adresses tiers et global ont été installées, désinstallez-les dans l’ordre suivant :

1. Dynamics365FinanceAndOperationsAnchor
1. Dynamics365FinanceAndOperationsDualWriteEntityMaps
1. msdyn_DualWriteCore
1. Dynamics365AssetManagementApp
1. Dynamics365AssetManagement
1. Dynamics365SupplyChainExtended
1. Dynamics365FinanceExtended
1. HCMCommon
1. Dynamics365FinanceAndOperationsCommon
1. Tiers
1. Dynamics365Company_managed
1. CurrencyExchangeRates
1. msdyn_AssetCommon
1. FieldServiceCommon
