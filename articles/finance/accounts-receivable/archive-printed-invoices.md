---
title: Archiver les factures client imprimées avec des numéros de hachage
description: Cette rubrique explique comment activer l’archivage afin de stocker des factures client imprimées avec des numéros de hachage.
author: ilyako
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d502ec5d286573c72e207419b66f283183009c09
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557478"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a><span data-ttu-id="f796f-103">Archiver les factures client imprimées avec des numéros de hachage</span><span class="sxs-lookup"><span data-stu-id="f796f-103">Archive printed customer invoices with hash numbers</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="f796f-104">Dans certains pays, il existe une obligation légale de stocker les numéros de hachage calculés dans le système avec les impressions de certains documents.</span><span class="sxs-lookup"><span data-stu-id="f796f-104">In some countries, there is a legal requirement to store calculated hash numbers in the system together with printouts of some documents.</span></span> <span data-ttu-id="f796f-105">Les numéros de hachage peuvent être utilisés pour les rapports destinés aux autorités et pendant les audits.</span><span class="sxs-lookup"><span data-stu-id="f796f-105">Hash numbers can be used for reporting to authorities and during audits.</span></span>

<span data-ttu-id="f796f-106">Cette rubrique explique comment configurer l’archivage afin de stocker des factures client imprimées avec des numéros de hachage.</span><span class="sxs-lookup"><span data-stu-id="f796f-106">This topic explains how to configure archiving in order to store printed customer invoices with hash numbers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f796f-107">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="f796f-107">Prerequisites</span></span>

- <span data-ttu-id="f796f-108">Dans l’espace de travail **Gestion des fonctionnalités**, activez la fonctionnalité **Archiver les factures client imprimées avec des numéros de hachage**.</span><span class="sxs-lookup"><span data-stu-id="f796f-108">In the **Feature management** workspace, turn on the feature, **Archive printed customer invoices with hash numbers**.</span></span> <span data-ttu-id="f796f-109">Pour plus d’informations, voir [Vue d’ensemble de la gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f796f-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="f796f-110">Configurez les formats imprimables des documents requis dans **Gestion de l’impression**.</span><span class="sxs-lookup"><span data-stu-id="f796f-110">Configure the printable formats of required documents in **Print management**.</span></span>

<span data-ttu-id="f796f-111">Cette fonctionnalité s’applique aux documents suivants.</span><span class="sxs-lookup"><span data-stu-id="f796f-111">This functionality is applicable to the following documents.</span></span>

<span data-ttu-id="f796f-112">**Comptabilité client**</span><span class="sxs-lookup"><span data-stu-id="f796f-112">**Accounts receivable**</span></span>
- <span data-ttu-id="f796f-113">Facture client</span><span class="sxs-lookup"><span data-stu-id="f796f-113">Customer invoice</span></span>
- <span data-ttu-id="f796f-114">Avoir du client</span><span class="sxs-lookup"><span data-stu-id="f796f-114">Customer credit note</span></span>
- <span data-ttu-id="f796f-115">Facture financière</span><span class="sxs-lookup"><span data-stu-id="f796f-115">Free text invoice</span></span>
- <span data-ttu-id="f796f-116">Avoir financier</span><span class="sxs-lookup"><span data-stu-id="f796f-116">Free text credit note</span></span>

<span data-ttu-id="f796f-117">**Gestion et comptabilité des projets**</span><span class="sxs-lookup"><span data-stu-id="f796f-117">**Project management and accounting**</span></span>
- <span data-ttu-id="f796f-118">Facture de projet</span><span class="sxs-lookup"><span data-stu-id="f796f-118">Project invoice</span></span>
- <span data-ttu-id="f796f-119">Avoir de projet</span><span class="sxs-lookup"><span data-stu-id="f796f-119">Project credit note</span></span>

## <a name="configure-customer-master-data"></a><span data-ttu-id="f796f-120">Configurer les données principales du client</span><span class="sxs-lookup"><span data-stu-id="f796f-120">Configure customer master data</span></span>
<span data-ttu-id="f796f-121">Procédez comme suit pour configurer les données client et activer la possibilité d’enregistrer automatiquement les factures imprimées en tant que pièces jointes.</span><span class="sxs-lookup"><span data-stu-id="f796f-121">Complete the following steps to configure customer data and turn on the ability to automatically save printed invoices as attachments.</span></span>

1. <span data-ttu-id="f796f-122">Accédez à **Comptabilité client** > **Tous les clients**.</span><span class="sxs-lookup"><span data-stu-id="f796f-122">Go to **Accounts receivable** > **All customers**.</span></span> 
2. <span data-ttu-id="f796f-123">Sélectionnez un client, et sur le raccourci **Facture et livraison**, dans la section **FACTURE ÉLECTRONIQUE**, dans le champ **Pièce jointe à la facture électronique**, sélectionnez **Oui**.</span><span class="sxs-lookup"><span data-stu-id="f796f-123">Select a customer, and on the **Invoice and delivery** FastTab, in the **E-INVOCE** section, in the **eInvoice attachment** field, select **Yes**.</span></span>

## <a name="print-invoices"></a><span data-ttu-id="f796f-124">Imprimer les factures</span><span class="sxs-lookup"><span data-stu-id="f796f-124">Print invoices</span></span>
<span data-ttu-id="f796f-125">Vous pouvez publier et imprimer n’importe quelle facture financière, facture client et facture de projet ou avoir pour le client configuré dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="f796f-125">You can post and print any free text, customer, and project invoice or credit note for the customer configured in the previous procedure.</span></span>

<span data-ttu-id="f796f-126">Ouvrez la page **Pièces jointes** pour la facture imprimée.</span><span class="sxs-lookup"><span data-stu-id="f796f-126">Open the **Attachments** page for the printed invoice.</span></span> <span data-ttu-id="f796f-127">Sur le raccourci **Pièce jointe**, dans le groupe de champs **Détails supplémentaires**, dans **Numéro de hachage du document**, recherchez le numéro de hachage enregistré calculé pour la facture imprimée.</span><span class="sxs-lookup"><span data-stu-id="f796f-127">On the **Attachment** FastTab, in the **Additional details** field group, in **Document hash number** field, find the stored hash number calculated for the printed invoice.</span></span>

![Numéro de hachage de la pièce jointe](media/attach-hash-num.jpg)

