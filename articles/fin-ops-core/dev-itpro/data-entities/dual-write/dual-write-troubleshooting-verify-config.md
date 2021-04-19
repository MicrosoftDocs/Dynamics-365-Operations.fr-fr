---
title: Vérifiez la configuration de la double écriture dans les applications Finance and Operations et Dataverse
description: Cette rubrique explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Dataverse.
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
ms.openlocfilehash: af746d1d20ddd1552bce797288c6d62d69d7bd16
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748847"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a><span data-ttu-id="67927-103">Vérifiez la configuration de la double écriture dans les applications Finance and Operations et Dataverse</span><span class="sxs-lookup"><span data-stu-id="67927-103">Verify dual-write configuration in Finance and Operations apps and Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="67927-104">Cette rubrique fournit des informations sur la résolution des problèmes de l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="67927-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="67927-105">Notamment, elle explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Dataverse.</span><span class="sxs-lookup"><span data-stu-id="67927-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Dataverse.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="67927-106">Vérifier que la double écriture est configurée dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="67927-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="67927-107">Pour déterminer si les erreurs que vous voyez lorsque vous essayez d’enregistrer des lignes pour la mise à jour proviennent de la double écriture, vérifiez d’abord que la double écriture est configurée.</span><span class="sxs-lookup"><span data-stu-id="67927-107">To determine whether the errors that you see when you try to save rows for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="67927-108">Si vous avez des privilèges d’administrateur dans l’application Finance and Operations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="67927-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="67927-109">Si les détails des environnements liés et la liste des cartes de tables en cours d’exécution sont affichés, la double écriture est configurée.</span><span class="sxs-lookup"><span data-stu-id="67927-109">If the details of the linked environments and the list of table maps that are running are shown, dual-write is configured.</span></span>

    ![Vérification de la connexion à l’application Finance and Operations lorsque vous disposez de privilèges d’administrateur](media/verify_fin_ops_1.png)

+ <span data-ttu-id="67927-111">Si vous ne disposez pas des privilèges d’administrateur, vous recevrez un message d’erreur, *Impossible d’écrire des données dans l’entité \<entity name\>*.</span><span class="sxs-lookup"><span data-stu-id="67927-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="67927-112">Dans l’exemple de l’illustration suivante, vous ne pouvez pas créer une ligne client dans l’application Finance and Operations, car la double écriture est configurée, mais les données de référence du groupe de clients et des conditions de paiement n’existent pas dans Dataverse.</span><span class="sxs-lookup"><span data-stu-id="67927-112">In the example in the following illustration, you can't create a customer row in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Dataverse.</span></span>

    ![Vérification de la connexion à l’application Finance and Operations lorsque vous ne disposez pas de privilèges d’administrateur](media/verify_fin_ops_2.png)

<span data-ttu-id="67927-114">Pour plus d’informations sur la résolution des problèmes lors de la création de données dans les applications Finance and Operations, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="67927-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a><span data-ttu-id="67927-115">Vérifier que la double écriture est configurée dans Dataverse</span><span class="sxs-lookup"><span data-stu-id="67927-115">Verify that dual-write is configured in Dataverse</span></span>

<span data-ttu-id="67927-116">Lorsque vous créez des données, si vous voyez la colonne **Société** sur les pages dans Dataverse, la double écriture est configurée.</span><span class="sxs-lookup"><span data-stu-id="67927-116">When you create data, if you see the **Company** column on pages in Dataverse, dual-write is configured.</span></span>

![Vérification de la connexion Dataverse](media/verify_cds.png)

<span data-ttu-id="67927-118">Pour plus d’informations sur la résolution des problèmes lors de la création de données dans Dataverse, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="67927-118">For information about how to fix issues when you create data in Dataverse, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="67927-119">Pour plus d’informations sur la façon d’afficher les détails des erreurs si vous rencontrez des erreurs lors de la création de données dans Dataverse, voir [Activer et afficher le journal de suivi des plug-ins dans Dataverse pour afficher les détails de l’erreur](dual-write-troubleshooting.md#enable-view-trace).</span><span class="sxs-lookup"><span data-stu-id="67927-119">For information about how to view error details if you encounter any errors while you create data in Dataverse, see [Enable and view the plug-in trace log in Dataverse to view error details](dual-write-troubleshooting.md#enable-view-trace).</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]