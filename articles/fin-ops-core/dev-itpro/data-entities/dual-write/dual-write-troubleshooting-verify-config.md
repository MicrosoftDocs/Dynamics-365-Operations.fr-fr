---
title: Vérifier que la double écriture est configurée dans les applications Finance and Operations et Common Data Service
description: Cette rubrique explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Common Data Service.
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
ms.openlocfilehash: 2f2ba2564ad3e8e444e27fcc0c586ddf252afabd
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172643"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="ac97d-103">Vérifier que la double écriture est configurée dans les applications Finance and Operations et Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ac97d-103">Verify that dual-write is configured in Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="ac97d-104">Cette rubrique fournit des informations sur la résolution des problèmes de l'intégration de la double écriture entre les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac97d-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="ac97d-105">Notamment, elle explique comment déterminer si la double écriture est configurée dans les applications Finance and Operations et Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac97d-105">Specifically, it explains how you can determine whether dual-write is configured in Finance and Operations apps and in Common Data Service.</span></span>

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a><span data-ttu-id="ac97d-106">Vérifier que la double écriture est configurée dans une application Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ac97d-106">Verify that dual-write is configured in a Finance and Operations app</span></span>

<span data-ttu-id="ac97d-107">Pour déterminer si les erreurs que vous voyez lorsque vous essayez de sauvegarder des enregistrements pour la mise à jour proviennent de la double écriture, vérifiez d'abord que la double écriture est configurée.</span><span class="sxs-lookup"><span data-stu-id="ac97d-107">To determine whether the errors that you see when you try to save records for update come from dual-write, first verify that dual-write is configured.</span></span>

+ <span data-ttu-id="ac97d-108">Si vous avez des privilèges d'administrateur dans l'application Finance and Operations, accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**.</span><span class="sxs-lookup"><span data-stu-id="ac97d-108">If you have admin privileges in the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Dual-write** tile.</span></span> <span data-ttu-id="ac97d-109">Si les détails des environnements liés et la liste des cartes d'entités en cours d'exécution sont affichés, la double écriture est configurée.</span><span class="sxs-lookup"><span data-stu-id="ac97d-109">If the details of the linked environments and the list of entity maps that are running are shown, dual-write is configured.</span></span>

    ![Vérification de la connexion à l'application Finance and Operations lorsque vous disposez de privilèges d'administrateur](media/verify_fin_ops_1.png)

+ <span data-ttu-id="ac97d-111">Si vous ne disposez pas des privilèges d'administrateur, vous recevrez un message d'erreur, *Impossible d'écrire des données dans l'entité \<nom d'entité\>*.</span><span class="sxs-lookup"><span data-stu-id="ac97d-111">If you don't have admin privileges, you will receive an error message, *Unable to write data to entity \<entity name\>*.</span></span> <span data-ttu-id="ac97d-112">Dans l'exemple de l'illustration suivante, vous ne pouvez pas créer un enregistrement client dans l'application Finance and Operations, car la double écriture est configurée, mais les données de référence du groupe de clients et des conditions de paiement n'existent pas dans Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ac97d-112">In the example in the following illustration, you can't create a customer record in the Finance and Operations app, because dual-write is configured, but the customer group and payment terms reference data don't exist in Common Data Service.</span></span>

    ![Vérification de la connexion à l'application Finance and Operations lorsque vous ne disposez pas de privilèges d'administrateur](media/verify_fin_ops_2.png)

<span data-ttu-id="ac97d-114">Pour plus d'informations sur la résolution des problèmes lors de la création de données dans les applications Finance and Operations, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="ac97d-114">For information about how to fix issues when you create data in Finance and Operations apps, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a><span data-ttu-id="ac97d-115">Vérifier que la double écriture est configurée dans Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ac97d-115">Verify that dual-write is configured in Common Data Service</span></span>

<span data-ttu-id="ac97d-116">Lorsque vous créez des données, si vous voyez le champ **Société** sur les pages dans Common Data Service, la double écriture est configurée.</span><span class="sxs-lookup"><span data-stu-id="ac97d-116">When you create data, if you see the **Company** field on pages in Common Data Service, dual-write is configured.</span></span>

![Vérification de la connexion Common Data Service](media/verify_cds.png)

<span data-ttu-id="ac97d-118">Pour plus d'informations sur la résolution des problèmes lors de la création de données dans Common Data Service, voir [Résoudre les problèmes de synchronisation en direct](dual-write-troubleshooting-live-sync.md).</span><span class="sxs-lookup"><span data-stu-id="ac97d-118">For information about how to fix issues when you create data in Common Data Service, see [Troubleshoot live synchronization issues](dual-write-troubleshooting-live-sync.md).</span></span>

<span data-ttu-id="ac97d-119">Pour plus d'informations sur la façon d'afficher les détails des erreurs si vous rencontrez des erreurs lors de la création de données dans Common Data Service, voir [Activer et afficher le journal de suivi des plug-ins dans Common Data Service pour afficher les détails de l'erreur](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span><span class="sxs-lookup"><span data-stu-id="ac97d-119">For information about how to view error details if you encounter any errors while you create data in Common Data Service, see [Enable and view the plug-in trace log in Common Data Service to view error details](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).</span></span>
