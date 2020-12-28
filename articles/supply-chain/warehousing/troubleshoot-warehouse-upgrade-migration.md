---
title: Résoudre les problèmes de mise à niveau et de migration vers la gestion avancée des entrepôts
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la mise à niveau et la migration vers la gestion des entrepôts avancée.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d50c6d75ec7cc98109cf81c38ff42b4d2b105b0c
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645815"
---
# <a name="troubleshoot-upgrade-and-migration-to-advanced-warehouse-management"></a><span data-ttu-id="2c3d2-103">Résoudre les problèmes de mise à niveau et de migration vers la gestion avancée des entrepôts</span><span class="sxs-lookup"><span data-stu-id="2c3d2-103">Troubleshoot upgrade and migration to advanced warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c3d2-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors de la mise à niveau et la migration vers la gestion des entrepôts avancée.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-104">This topic describes how to fix common issues that you might encounter while you upgrade and migrate to advanced warehouse management.</span></span>

## <a name="i-receive-the-following-error-message-javasecuritycertcertpathvalidatorexception-trust-anchor-for-certification-path-is-not-found"></a><span data-ttu-id="2c3d2-105">Je reçois le message d'erreur suivant : "java.security.cert.certPathValidatorException : l'ancre validé pour le chemin de certification est introuvable. »</span><span class="sxs-lookup"><span data-stu-id="2c3d2-105">I receive the following error message: "java.security.cert.certPathValidatorException: Trust anchor for certification path is not found."</span></span>

### <a name="issue-description"></a><span data-ttu-id="2c3d2-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="2c3d2-106">Issue description</span></span>

<span data-ttu-id="2c3d2-107">Vous recevez ce message d'erreur dans l'application d'entrepôt, car les certificats auto-signés ne sont pas approuvés sur Android 8+ dans les environnements sur site.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-107">You receive this error message in the warehouse app, because self-signed certificates aren't trusted on Android 8+ in on-premises environments.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2c3d2-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="2c3d2-108">Issue resolution</span></span>

<span data-ttu-id="2c3d2-109">Utilisez une autorité de certification (CA) externe (publique).</span><span class="sxs-lookup"><span data-stu-id="2c3d2-109">Use an external (public) certifying authority (CA).</span></span> <span data-ttu-id="2c3d2-110">Un correctif pour ce problème est disponible dans la version 1.9.0.0 de l'application d'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-110">A fix for this issue is available in version 1.9.0.0 of the warehouse app.</span></span> <span data-ttu-id="2c3d2-111">Pour plus d'informations sur ce problème et comment le résoudre, voir [Résoudre les problèmes de connexion de l'application d'entrepôt](troubleshoot-warehouse-app-connection.md).</span><span class="sxs-lookup"><span data-stu-id="2c3d2-111">For more information about this issue and how to fix it, see [Troubleshoot warehouse app connection issues](troubleshoot-warehouse-app-connection.md).</span></span>

## <a name="what-is-the-approved-process-for-moving-from-basic-warehousing-to-advanced-warehousing"></a><span data-ttu-id="2c3d2-112">Quel est le processus approuvé pour passer de l'entreposage de base à l'entreposage avancé ?</span><span class="sxs-lookup"><span data-stu-id="2c3d2-112">What is the approved process for moving from basic warehousing to advanced warehousing?</span></span>

### <a name="issue-description"></a><span data-ttu-id="2c3d2-113">Description du problème</span><span class="sxs-lookup"><span data-stu-id="2c3d2-113">Issue description</span></span>

<span data-ttu-id="2c3d2-114">Vous utilisez actuellement la gestion des stocks/inventaire et utilisez la fonctionnalité de stock de base, et vous souhaitez passer à l'entreposage avancé pour tirer parti des appareils mobiles, des vagues et du travail.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-114">You're currently running under stock/inventory management and using basic stock functionality, and you want to move to advanced warehousing to take advantage of mobile devices, waves, and work.</span></span> <span data-ttu-id="2c3d2-115">Cependant, vous rencontrez des problèmes lorsque vous essayez d'effectuer cette opération.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-115">However, you're experiencing issues when you try to make this move.</span></span> <span data-ttu-id="2c3d2-116">Par exemple, vous ne pouvez pas modifier vos produits afin qu'ils utilisent des dimensions de stockage (site, entrepôt et emplacement), car les produits ont des transactions les concernant.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-116">For example, you can't change your products so that they use storage dimensions (site, warehouse, and location), because the products have transactions against them.</span></span> <span data-ttu-id="2c3d2-117">Par conséquent, vous devez connaître le processus approuvé pour passer de l'entreposage de base à l'entreposage avancé.</span><span class="sxs-lookup"><span data-stu-id="2c3d2-117">Therefore, you must learn the approved process for moving from basic warehousing to advanced warehousing.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="2c3d2-118">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="2c3d2-118">Issue resolution</span></span>

<span data-ttu-id="2c3d2-119">Pour plus d'informations sur le processus de passage de l'entreposage de base à l'entreposage avancé, consultez les billets de blog et la documentation suivants :</span><span class="sxs-lookup"><span data-stu-id="2c3d2-119">For more information about the process for moving from basic warehousing to advanced warehousing, see the following blog posts and documentation:</span></span>

- [<span data-ttu-id="2c3d2-120">Processus de gestion des entrepôts pour les articles et les entrepôts existants</span><span class="sxs-lookup"><span data-stu-id="2c3d2-120">Enable warehouse management process for existing items and warehouses</span></span>](https://cleverax.wordpress.com/2017/12/06/d365fo-enable-warehouse-management-process-for-existing-items-and-warehouses/)
- [<span data-ttu-id="2c3d2-121">Migration de Microsoft Dynamics AX WMS vers la nouvelle fonctionnalité d'entrepôt et de transport R3</span><span class="sxs-lookup"><span data-stu-id="2c3d2-121">Migration of Microsoft Dynamics AX WMS to new R3 warehouse and transportation functionality</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2015/08/17/migration-of-microsoft-dynamics-ax-wms-to-new-r3-warehouse-and-transportation-functionality/)
- [<span data-ttu-id="2c3d2-122">Migration des éléments WMSI/WMS2</span><span class="sxs-lookup"><span data-stu-id="2c3d2-122">WMSI/WMS2 item migration</span></span>](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/05/03/wmsiwms2-item-migration/)
- [<span data-ttu-id="2c3d2-123">Mise à niveau de la gestion des entrepôts depuis Microsoft Dynamics AX 2012 vers Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="2c3d2-123">Upgrade warehouse management from Microsoft Dynamics AX 2012 to Supply Chain Management</span></span>](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/upgrade-migration-warehouse-management-processes)
