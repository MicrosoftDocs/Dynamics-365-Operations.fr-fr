---
title: Rendre unique le délimiteur du plan de comptes
description: Dans Dynamics 365 for Finance and Operations, vous ne pouvez pas avoir le même séparateur pour le plan de comptes et les valeurs de dimension. Vous devez modifier les valeurs de délimiteur après la mise à niveau.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8cc05772e7ee125a5ce8603c4d5f8719e8895c73
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851769"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="8f15b-104">Rendre unique le délimiteur du plan de comptes</span><span class="sxs-lookup"><span data-stu-id="8f15b-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f15b-105">Dans Microsoft Dynamics AX 2012, vous pouviez utiliser le même délimiteur pour votre plan de comptes et les valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="8f15b-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="8f15b-106">Dans Dynamics 365 for Finance and Operations, vous ne pouvez pas avoir le même séparateur pour le plan de comptes et les valeurs de dimension.</span><span class="sxs-lookup"><span data-stu-id="8f15b-106">In Dynamics 365 for Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="8f15b-107">Si un délimiteur est en double, vous pouvez le modifier après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="8f15b-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="8f15b-108">Cette fonctionnalité est disponible dans :</span><span class="sxs-lookup"><span data-stu-id="8f15b-108">This feature is available in:</span></span>
- <span data-ttu-id="8f15b-109">Dynamics 365 for Finance and Operations version 8.0</span><span class="sxs-lookup"><span data-stu-id="8f15b-109">Dynamics 365 for Finance and Operations version 8.0</span></span>
- <span data-ttu-id="8f15b-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Impossible d'entrer des dimensions financières lorsque les valeurs de la dimension contiennent le délimiteur de plan de comptes</span><span class="sxs-lookup"><span data-stu-id="8f15b-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="8f15b-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Impossible de choisir un sous-projet lorsque comme dimension lorsque le format de celui-ci contient le délimiteur de dimension</span><span class="sxs-lookup"><span data-stu-id="8f15b-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="8f15b-112">Mettre à jour le délimiteur</span><span class="sxs-lookup"><span data-stu-id="8f15b-112">Update delimiter</span></span>
<span data-ttu-id="8f15b-113">En cas de conflit avec le plan de comptes, le délimiteur de plan de comptes et le format de l'ID de projet/sous-projet peut être modifié.</span><span class="sxs-lookup"><span data-stu-id="8f15b-113">If there is a conflict with the Chart of Accounts, the Chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="8f15b-114">Aucun autre délimiteur de dimension ne peut être modifié.</span><span class="sxs-lookup"><span data-stu-id="8f15b-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="8f15b-115">Vous pouvez modifier le séparateur de plan de comptes après la mise à niveau vers Finance and Operations dans **Paramètres de comptabilité** > **Plan de comptes et dimensions** > **Modifier le délimiteur**.</span><span class="sxs-lookup"><span data-stu-id="8f15b-115">You can change the chart of accounts delimiter after upgrade to Finance and Operations in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="8f15b-116">Si le seul conflit est avec le format d'ID de projet/sous-projet, vous pouvez modifier cette valeur dans **Paramètres de gestion et comptabilité des projets** > **Général** > **Modifier le format du sous-projet**.</span><span class="sxs-lookup"><span data-stu-id="8f15b-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="8f15b-117">Procédure pour déterminer si votre environnement nécessite des délimiteurs mis à jour</span><span class="sxs-lookup"><span data-stu-id="8f15b-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="8f15b-118">Si les délimiteurs de votre environnement mis à niveau sont en conflit, vous pouvez rencontrer de l'instabilité en entrant des valeurs dans un contrôle d'accès segmenté et un contrôle d'entrée de dimension.</span><span class="sxs-lookup"><span data-stu-id="8f15b-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="8f15b-119">Cela signifie que vous devez toujours utiliser les recherches ou un menu volant pour la saisie des combinaisons de compte et de dimensions.</span><span class="sxs-lookup"><span data-stu-id="8f15b-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>
