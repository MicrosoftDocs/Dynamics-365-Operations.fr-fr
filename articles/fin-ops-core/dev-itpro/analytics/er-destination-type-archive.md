---
title: Type de destination pour l’archivage d’états électronique
description: Cette rubrique fournit des informations sur la configuration d’une destination d’archive pour chaque composant DOSSIER ou FICHIER d’un format de gestion des états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 72b896ca692a54200ff79b14d0b5dc6ab4b0fe27
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562044"
---
# <a name="archive-er-destination-type"></a><span data-ttu-id="be678-103">Type de destination pour l’archivage d’états électronique</span><span class="sxs-lookup"><span data-stu-id="be678-103">Archive ER destination type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="be678-104">Vous pouvez configurer une destination d’archive pour chaque composant **Dossier** ou **Fichier** d’un format de rapport électronique (ER) configuré pour générer des documents sortants.</span><span class="sxs-lookup"><span data-stu-id="be678-104">You can configure an archive destination for each **Folder** or **File** component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="be678-105">En fonction du paramètre de destination, un document généré est stocké en tant que pièce jointe d’un enregistrement de la liste de tâches d’état électronique.</span><span class="sxs-lookup"><span data-stu-id="be678-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span> <span data-ttu-id="be678-106">Pour afficher les résultats, accédez à **Administration d’organisation** \> **Gestion des états électroniques** \> **Tâches de gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="be678-106">To view the results, go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting jobs**.</span></span>

<span data-ttu-id="be678-107">Vous pouvez utiliser cette option pour envoyer le document généré vers un dossier Microsoft SharePoint ou le stockage Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="be678-107">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="be678-108">Définissez **Activé** sur **Oui** pour envoyer la sortie vers une destination définie par le type de document sélectionné.</span><span class="sxs-lookup"><span data-stu-id="be678-108">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="be678-109">Seuls les types de documents où le groupe est défini sur **Fichier** sont disponibles pour la sélection.</span><span class="sxs-lookup"><span data-stu-id="be678-109">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="be678-110">Vous définissez les [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) de documents dans **Administration d’organisation** \> **Gestion de documents** \> **Types de documents**.</span><span class="sxs-lookup"><span data-stu-id="be678-110">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="be678-111">La configuration des destinations d’états électroniques est identique à la configuration du système de gestion des documents.</span><span class="sxs-lookup"><span data-stu-id="be678-111">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="be678-112">[![Page Types de documents](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="be678-112">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="be678-113">L’emplacement détermine où le fichier est enregistré.</span><span class="sxs-lookup"><span data-stu-id="be678-113">The location determines where the file is saved.</span></span> <span data-ttu-id="be678-114">Une fois la destination **Archive** activée, les résultats peuvent être enregistrés dans l’archive Tâche.</span><span class="sxs-lookup"><span data-stu-id="be678-114">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="be678-115">Vous pouvez afficher les résultats sous **Administration d’organisation** \> **Gestion des états électroniques** \> **Tâches de gestion des états électroniques archivées**.</span><span class="sxs-lookup"><span data-stu-id="be678-115">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="be678-116">Sélectionnez un type de document pour l’archive Tâche en accédant à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques** \> **Paramètres de gestion des états électroniques**.</span><span class="sxs-lookup"><span data-stu-id="be678-116">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="be678-117">Pour plus d’informations, voir [Configurer la structure de gestion des états électroniques (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="be678-117">For more information, see [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="be678-118">SharePoint</span><span class="sxs-lookup"><span data-stu-id="be678-118">SharePoint</span></span>

<span data-ttu-id="be678-119">Vous pouvez enregistrer un fichier dans un dossier SharePoint désigné.</span><span class="sxs-lookup"><span data-stu-id="be678-119">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="be678-120">Pour définir le serveur SharePoint par défaut, accédez à **Administration d’organisation** \> **Gestion des documents** \> **Paramètres de gestion des documents**.</span><span class="sxs-lookup"><span data-stu-id="be678-120">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="be678-121">Sur l’onglet **SharePoint**, configurez le dossier SharePoint.</span><span class="sxs-lookup"><span data-stu-id="be678-121">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="be678-122">Ensuite, vous pouvez le sélectionner comme dossier où la sortie ER sera enregistrée.</span><span class="sxs-lookup"><span data-stu-id="be678-122">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="be678-123">L’emplacement **SharePoint** doit être sélectionné dans ce type de document.</span><span class="sxs-lookup"><span data-stu-id="be678-123">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="be678-124">[![Sélection d’un dossier SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="be678-124">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="be678-125">Stockage Azure</span><span class="sxs-lookup"><span data-stu-id="be678-125">Azure Storage</span></span>

<span data-ttu-id="be678-126">Lorsque l’emplacement du type de document est défini sur **Stockage Azure**, vous pouvez enregistrer un fichier dans le stockage Azure.</span><span class="sxs-lookup"><span data-stu-id="be678-126">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

> [!NOTE] 
> <span data-ttu-id="be678-127">La structure de gestion des états électroniques stocke en permanence les fichiers dans le stockage Blob Azure contrairement à l’infrastructure de gestion des données qui applique la stratégie de rétention de sept jours pour les documents qui doivent être traités.</span><span class="sxs-lookup"><span data-stu-id="be678-127">The ER framework permanently stores files in Azure Blob storage unlike the Data management framework that applies the seven-day retention policy for documents that must be processed.</span></span> <span data-ttu-id="be678-128">Pour plus d’informations, voir [API pour obtenir le statut du message](../data-entities/recurring-integrations.md#api-for-getting-message-status) et [API de contrôle de statut](../data-entities/data-management-api.md#status-check-api).</span><span class="sxs-lookup"><span data-stu-id="be678-128">For more information, see [API for getting message status](../data-entities/recurring-integrations.md#api-for-getting-message-status) and [Status check API](../data-entities/data-management-api.md#status-check-api).</span></span> <span data-ttu-id="be678-129">Les fichiers liés à ER seront stockés dans le stockage Blob Azure en tant que pièces jointes des enregistrements de table d’application aussi longtemps que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="be678-129">The ER-related files will be stored in Azure Blob storage as attachments of application table records as long as necessary.</span></span> <span data-ttu-id="be678-130">Un seul fichier sera supprimé du stockage Blob Azure avec l’enregistrement de la table d’application auquel ce fichier était attaché.</span><span class="sxs-lookup"><span data-stu-id="be678-130">A single file will be deleted from Azure Blob storage along with the application table record that this file was attached to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be678-131">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="be678-131">Additional resources</span></span>

- [<span data-ttu-id="be678-132">Vue d’ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="be678-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="be678-133">Destinations pour la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="be678-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="be678-134">Configurer la gestion des documents</span><span class="sxs-lookup"><span data-stu-id="be678-134">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]