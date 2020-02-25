---
title: Type de destination pour l'archivage d'états électronique
description: Cette rubrique fournit des informations sur la configuration d'une destination d'archive pour chaque composant DOSSIER ou FICHIER d'un format de rapport électronique (ER) configuré pour générer des documents sortants.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 15611a4f0000ca5ccb0ac3f4012251d5bf5689ec
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019768"
---
# <span data-ttu-id="e2fea-103"><a name="ArchiveDestinationType">Destination de l'archive</a></span><span class="sxs-lookup"><span data-stu-id="e2fea-103"><a name="ArchiveDestinationType">Archive destination</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2fea-104">Vous pouvez configurer une destination d'archive pour chaque composant DOSSIER ou FICHIER d'un format de rapport électronique (ER) configuré pour générer des documents sortants.</span><span class="sxs-lookup"><span data-stu-id="e2fea-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="e2fea-105">En fonction du paramètre de destination, un document généré est stocké en tant que pièce jointe d'un enregistrement de la liste de tâches d'état électronique.</span><span class="sxs-lookup"><span data-stu-id="e2fea-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="e2fea-106">Vous pouvez utiliser cette option pour envoyer le document généré vers un dossier Microsoft SharePoint ou le stockage Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e2fea-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="e2fea-107">Définissez **Activé** sur **Oui** pour envoyer la sortie vers une destination définie par le type de document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="e2fea-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="e2fea-108">Seuls les types de documents où le groupe est défini sur **Fichier** sont disponibles pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="e2fea-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="e2fea-109">Vous définissez les [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documents dans **Administration d’organisation** \> **Gestion de documents** \> **Types de documents**.</span><span class="sxs-lookup"><span data-stu-id="e2fea-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="e2fea-110">La configuration des destinations d'états électroniques est identique à la configuration du système de gestion des documents.</span><span class="sxs-lookup"><span data-stu-id="e2fea-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="e2fea-111">[![Page Types de documents](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="e2fea-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="e2fea-112">L’emplacement détermine où le fichier est enregistré.</span><span class="sxs-lookup"><span data-stu-id="e2fea-112">The location determines where the file is saved.</span></span> <span data-ttu-id="e2fea-113">Une fois la destination **Archive** activée, les résultats peuvent être enregistrés dans l'archive Tâche.</span><span class="sxs-lookup"><span data-stu-id="e2fea-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="e2fea-114">Vous pouvez afficher les résultats sous **Administration d'organisation** \> **Gestion des états électroniques** \> **Tâches de gestion des états électroniques archivées**.</span><span class="sxs-lookup"><span data-stu-id="e2fea-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="e2fea-115">Sélectionnez un type de document pour l'archive Tâche en accédant à **Administration d'organisation** \> **Espaces de travail** \> **Gestion des états électroniques** \> **Paramètres de gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="e2fea-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="e2fea-116">Pour plus d'informations, voir [Configurer la structure de gestion des états électroniques (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="e2fea-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="e2fea-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e2fea-117">SharePoint</span></span>

<span data-ttu-id="e2fea-118">Vous pouvez enregistrer un fichier dans un dossier SharePoint désigné.</span><span class="sxs-lookup"><span data-stu-id="e2fea-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="e2fea-119">Pour définir le serveur SharePoint par défaut, accédez à **Administration d’organisation** \> **Gestion des documents** \> **Paramètres de gestion des documents**.</span><span class="sxs-lookup"><span data-stu-id="e2fea-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="e2fea-120">Sur l'onglet **SharePoint**, configurez le dossier SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e2fea-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="e2fea-121">Ensuite, vous pouvez le sélectionner comme dossier où la sortie ER sera enregistrée.</span><span class="sxs-lookup"><span data-stu-id="e2fea-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="e2fea-122">L'emplacement **SharePoint** doit être sélectionné dans ce type de document.</span><span class="sxs-lookup"><span data-stu-id="e2fea-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="e2fea-123">[![Sélection d'un dossier SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="e2fea-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="e2fea-124">Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="e2fea-124">Azure Storage</span></span>

<span data-ttu-id="e2fea-125">Lorsque l’emplacement du type de document est défini sur **Stockage Azure**, vous pouvez enregistrer un fichier dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="e2fea-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e2fea-126">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="e2fea-126">Additional resources</span></span>

- [<span data-ttu-id="e2fea-127">Vue d'ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="e2fea-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="e2fea-128">Destinations pour la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="e2fea-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="e2fea-129">Configurer la gestion des documents</span><span class="sxs-lookup"><span data-stu-id="e2fea-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
