---
title: Résoudre les problèmes liés à la prise en charge des solutions
description: Cette rubrique fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 86dd8803f7560ea337f2452e9722fe0151466daf
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748871"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="62117-103">Résoudre les problèmes liés à la prise en charge des solutions</span><span class="sxs-lookup"><span data-stu-id="62117-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="62117-104">Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="62117-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="62117-105">Notamment, elle fournit des informations de résolution des problèmes qui peuvent vous aider à résoudre les problèmes liés à la prise en charge des solutions.</span><span class="sxs-lookup"><span data-stu-id="62117-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62117-106">Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="62117-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="62117-107">La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.</span><span class="sxs-lookup"><span data-stu-id="62117-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="62117-108">Erreur sur la page Double écriture</span><span class="sxs-lookup"><span data-stu-id="62117-108">Error on the Dual-write page</span></span>

<span data-ttu-id="62117-109">Sur la page **Double écriture**, vous pouvez recevoir un message d’erreur semblable à l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="62117-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="62117-110">*L’entité avec un nom « msdyn \_dualwriteentitymap » avec namemapping=’Logical’ est introuvable dans le MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="62117-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="62117-111">Pour résoudre le problème, assurez-vous que la solution principale de double écriture est installée dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="62117-111">To fix the issue, make sure that the dual-write core solution is installed in Dataverse.</span></span> <span data-ttu-id="62117-112">La solution principale de double écriture est une condition préalable à la prise en charge des solutions.</span><span class="sxs-lookup"><span data-stu-id="62117-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]