---
title: Résoudre les problèmes liés à la prise en charge des solutions
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 013e37269ec3df2bede15b28cffcc175967de9a3
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172619"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="e2f12-103">Résoudre les problèmes liés à la prise en charge des solutions</span><span class="sxs-lookup"><span data-stu-id="e2f12-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="e2f12-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e2f12-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="e2f12-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.</span><span class="sxs-lookup"><span data-stu-id="e2f12-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2f12-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d'administrateur système ou les identifiants d'admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e2f12-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="e2f12-107">La section pour chaque problème explique si un rôle spécifique ou des informations d'identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="e2f12-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="e2f12-108">Erreur sur la page Double écriture</span><span class="sxs-lookup"><span data-stu-id="e2f12-108">Error on the Dual-write page</span></span>

<span data-ttu-id="e2f12-109">Sur la page **Double écriture**, vous pouvez recevoir un message d'erreur semblable à l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="e2f12-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="e2f12-110">*L'entité avec un nom « msdyn \_dualwriteentitymap » avec namemapping='Logical' est introuvable dans le MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="e2f12-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="e2f12-111">Pour résoudre le problème, assurez-vous que la solution principale de double écriture est installée dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="e2f12-111">To fix the issue, make sure that the dual-write core solution is installed in Common Data Service.</span></span> <span data-ttu-id="e2f12-112">La solution principale de double écriture est une condition préalable à la prise en charge des solutions.</span><span class="sxs-lookup"><span data-stu-id="e2f12-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>
