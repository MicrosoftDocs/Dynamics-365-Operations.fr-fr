---
title: Résoudre les problèmes de mise à niveau et de migration vers la gestion avancée des entrepôts
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la mise à niveau et la migration vers la gestion des entrepôts avancée.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 953b828667a01157767c3ca79349fe972b0fbe9b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826393"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="48949-103">Résoudre les problèmes de mise à niveau et de migration vers la gestion avancée des entrepôts</span><span class="sxs-lookup"><span data-stu-id="48949-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48949-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la mise à niveau et la migration vers la gestion des entrepôts avancée.</span><span class="sxs-lookup"><span data-stu-id="48949-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="48949-105">Je reçois le message d’erreur suivant : "java.security.cert.certPathValidatorException : l’ancre validé pour le chemin de certification est introuvable. »</span><span class="sxs-lookup"><span data-stu-id="48949-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="48949-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="48949-106">Issue description</span></span>

<span data-ttu-id="48949-107">Vous recevez ce message d’erreur dans l’application mobile Gestion des entrepôts, car les certificats auto-signés ne sont pas approuvés sur Android 8+ dans les environnements sur site.</span><span class="sxs-lookup"><span data-stu-id="48949-107">You receive this error message in the Warehouse Management mobile app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="48949-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="48949-108">Issue resolution</span></span>

<span data-ttu-id="48949-109">Utilisez une autorité de certification (CA) externe (publique).</span><span class="sxs-lookup"><span data-stu-id="48949-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="48949-110">Un correctif pour ce problème est disponible dans la version 1.9.0.0 de l’application d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="48949-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="48949-111">Pour plus d’informations sur ce problème et comment le résoudre, voir [Résoudre les problèmes de connexion de l’application mobile Gestion des entrepôts](troubleshoot-warehouse-app-connection.md).</span><span class="sxs-lookup"><span data-stu-id="48949-111">For more information about this issue and how to fix it, see [Troubleshoot Warehouse Management mobile app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="48949-112">Quel est le processus approuvé pour passer de l’entreposage de base à l’entreposage avancé ?</span><span class="sxs-lookup"><span data-stu-id="48949-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="48949-113">Description du problème</span><span class="sxs-lookup"><span data-stu-id="48949-113">Issue description</span></span>

<span data-ttu-id="48949-114">Vous utilisez actuellement la gestion des stocks/inventaire et utilisez la fonctionnalité de stock de base, et vous souhaitez passer à l’entreposage avancé pour tirer parti des appareils mobiles, des vagues et du travail.</span><span class="sxs-lookup"><span data-stu-id="48949-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="48949-115">Cependant, vous rencontrez des problèmes lorsque vous essayez d’effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="48949-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="48949-116">Par exemple, vous ne pouvez pas modifier vos produits afin qu’ils utilisent des dimensions de stockage (site, entrepôt et emplacement), car les produits ont des transactions les concernant.</span><span class="sxs-lookup"><span data-stu-id="48949-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="48949-117">Par conséquent, vous devez connaître le processus approuvé pour passer de l’entreposage de base à l’entreposage avancé.</span><span class="sxs-lookup"><span data-stu-id="48949-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="48949-118">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="48949-118">Issue resolution</span></span>

<span data-ttu-id="48949-119">Pour plus d’informations sur le processus de passage de l’entreposage de base à l’entreposage avancé, consultez les billets de blog et la documentation suivants :</span><span class="sxs-lookup"><span data-stu-id="48949-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="48949-120">Processus de gestion des entrepôts pour les articles et les entrepôts existants</span><span class="sxs-lookup"><span data-stu-id="48949-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="48949-121">Migration de Microsoft Dynamics AX WMS vers la nouvelle fonctionnalité d’entrepôt et de transport R3</span><span class="sxs-lookup"><span data-stu-id="48949-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="48949-122">Migration des éléments WMSI/WMS2</span><span class="sxs-lookup"><span data-stu-id="48949-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="48949-123">Mise à niveau de la gestion des entrepôts depuis Microsoft Dynamics AX 2012 vers Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="48949-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]