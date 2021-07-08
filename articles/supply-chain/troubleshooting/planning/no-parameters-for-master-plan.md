---
title: Les paramètres du plan directeur n’existent pas
description: Lorsque vous essayez de confirmer une commande planifiée, vous recevez un message d’erreur indiquant qu’aucun paramètre n’existe pour le plan directeur.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294076"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a><span data-ttu-id="69e96-103">Les paramètres du plan directeur n’existent pas</span><span class="sxs-lookup"><span data-stu-id="69e96-103">Parameters for the master plan don't exist</span></span>

<span data-ttu-id="69e96-104">Code d’erreur : SYS25368</span><span class="sxs-lookup"><span data-stu-id="69e96-104">Error code: SYS25368</span></span>

## <a name="symptoms"></a><span data-ttu-id="69e96-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="69e96-105">Symptoms</span></span>

<span data-ttu-id="69e96-106">Lorsque vous essayez de confirmer une commande planifiée, vous recevez le message d’erreur suivant :</span><span class="sxs-lookup"><span data-stu-id="69e96-106">When you try to firm a planned order, you receive the following error message:</span></span>

> <span data-ttu-id="69e96-107">Absence de paramètres pour le plan général %1.</span><span class="sxs-lookup"><span data-stu-id="69e96-107">Parameters for master plan %1 do not exist.</span></span>

## <a name="cause"></a><span data-ttu-id="69e96-108">Cause</span><span class="sxs-lookup"><span data-stu-id="69e96-108">Cause</span></span>

<span data-ttu-id="69e96-109">En raison de problèmes de configuration, le système ne peut pas trouver les paramètres du plan spécifié.</span><span class="sxs-lookup"><span data-stu-id="69e96-109">Because of configuration issues, the system can't find the settings for the specified plan.</span></span>

## <a name="resolution"></a><span data-ttu-id="69e96-110">Résolution</span><span class="sxs-lookup"><span data-stu-id="69e96-110">Resolution</span></span>

- <span data-ttu-id="69e96-111">Accédez à **Plan directeur \> Paramétrage \> Plans \> Plans directeurs** et assurez-vous qu’un plan portant le nom spécifié existe.</span><span class="sxs-lookup"><span data-stu-id="69e96-111">Go to **Master planning \> Setup \> Plans \> Master plans**, and make sure that a plan that has the specified name exists.</span></span>
