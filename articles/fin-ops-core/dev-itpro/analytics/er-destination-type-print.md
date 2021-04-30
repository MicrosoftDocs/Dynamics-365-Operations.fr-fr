---
title: Type de destination pour l’impression d’états électroniques
description: Cette rubrique explique comment configurer une destination d’imprimante pour chaque composant DOSSIER ou FICHIER d’un format de gestion des états électroniques.
author: NickSelin
ms.date: 02/24/2021
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
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 7749a458020de664d00e81ccf0e480ae459da617
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894002"
---
# <a name="printer-destination"></a><a name="PrinterDestinationType"></a><span data-ttu-id="2de73-103">Destination d’imprimante</span><span class="sxs-lookup"><span data-stu-id="2de73-103">Printer destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2de73-104">Vous pouvez envoyer un document généré directement à une imprimante réseau pour une impression directe.</span><span class="sxs-lookup"><span data-stu-id="2de73-104">You can send a generated document directly to a network printer for direct printing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2de73-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="2de73-105">Prerequisites</span></span>

<span data-ttu-id="2de73-106">Avant de commencer, vous devez installer et configurer l’agent de routage de documents, puis enregistrer les imprimantes réseau.</span><span class="sxs-lookup"><span data-stu-id="2de73-106">Before you begin, you must install and configure the Document Routing Agent, and then register the network printers.</span></span> <span data-ttu-id="2de73-107">Pour plus d’informations, voir [Installer l’agent d’acheminement de document pour activer l’impression réseau](./install-document-routing-agent.md).</span><span class="sxs-lookup"><span data-stu-id="2de73-107">For more information, see [Install the Document Routing Agent to enable network printing](./install-document-routing-agent.md).</span></span>

## <a name="make-the-printer-destination-available"></a><span data-ttu-id="2de73-108">Rendre la destination de l’imprimante disponible</span><span class="sxs-lookup"><span data-stu-id="2de73-108">Make the Printer destination available</span></span>

<span data-ttu-id="2de73-109">Pour rendre la destination de l’**Imprimante** disponible dans l’instance actuelle de Microsoft Dynamics 365 Finance, accédez à l’espace de travail **Gestion des fonctionnalités** et activez les fonctionnalités suivantes, dans cet ordre :</span><span class="sxs-lookup"><span data-stu-id="2de73-109">To make the **Printer** destination available in the current instance of Microsoft Dynamics 365 Finance, go to the **Feature management** workspace, and turn on the following features, in this order:</span></span>

1. <span data-ttu-id="2de73-110">Convertir les documents sortants des rapports électroniques aux formats Microsoft Office vers le format PDF</span><span class="sxs-lookup"><span data-stu-id="2de73-110">Convert Electronic Reporting outbound documents from Microsoft Office formats to PDF</span></span>
2. <span data-ttu-id="2de73-111">Agent d’acheminement de document en tant que destination des rapports électroniques pour les documents sortants</span><span class="sxs-lookup"><span data-stu-id="2de73-111">Document Routing Agent as Electronic Reporting destination for outbound documents</span></span>

<span data-ttu-id="2de73-112">[![Activation de la fonction de destination de l’imprimante ER dans la gestion des fonctionnalités](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span><span class="sxs-lookup"><span data-stu-id="2de73-112">[![Turning on the ER printer destination feature in Feature management](./media/ER_Destinations-EnablePrinterDestinationFeature.png)](./media/ER_Destinations-EnablePrinterDestinationFeature.png)</span></span>

### <a name="applicability"></a><span data-ttu-id="2de73-113">Conditions d’application</span><span class="sxs-lookup"><span data-stu-id="2de73-113">Applicability</span></span>

<span data-ttu-id="2de73-114">La destination de l’**Imprimante** ne peut être configurée que pour les composants de fichier utilisés pour générer une sortie au format PDF imprimable (fusion PDF ou éléments de format de fichier PDF) ou Microsoft Office Excel / Format Word (fichier Excel).</span><span class="sxs-lookup"><span data-stu-id="2de73-114">The **Printer** destination can be configured only for file components that are used to generate output in either printable PDF format (PDF Merger or PDF file format elements) or Microsoft Office Excel/Word format (Excel file).</span></span> <span data-ttu-id="2de73-115">Lorsque la sortie est générée au format PDF, elle est envoyée à une imprimante.</span><span class="sxs-lookup"><span data-stu-id="2de73-115">When output is generated in PDF format, it's sent to a printer.</span></span> <span data-ttu-id="2de73-116">Lorsque la sortie est générée au format Microsoft Office, elle est automatiquement convertie au format PDF, puis envoyée à une imprimante.</span><span class="sxs-lookup"><span data-stu-id="2de73-116">When output is generated in Microsoft Office format, it's automatically converted to PDF format and then sent to a printer.</span></span>

### <a name="limitations"></a><span data-ttu-id="2de73-117">Limitations</span><span class="sxs-lookup"><span data-stu-id="2de73-117">Limitations</span></span>

<span data-ttu-id="2de73-118">La destination de l’**Imprimante** est implémentée uniquement pour les déploiements cloud.</span><span class="sxs-lookup"><span data-stu-id="2de73-118">The **Printer** destination is implemented only for cloud deployments.</span></span>

### <a name="use-the-printer-destination"></a><span data-ttu-id="2de73-119">Utiliser la destination de l’imprimante</span><span class="sxs-lookup"><span data-stu-id="2de73-119">Use the Printer destination</span></span>

1. <span data-ttu-id="2de73-120">Définissez l’option **Activé** sur **Oui** pour envoyer un document généré à une imprimante.</span><span class="sxs-lookup"><span data-stu-id="2de73-120">Set the **Enabled** option to **Yes** to send a generated document to a printer.</span></span>
2. <span data-ttu-id="2de73-121">Dans le champ **Nom d’imprimante**, sélectionnez l’imprimante réseau requise.</span><span class="sxs-lookup"><span data-stu-id="2de73-121">In the **Printer name** field, select the required network printer.</span></span>
3. <span data-ttu-id="2de73-122">Définissez l’option **Enregistrer dans les archives d’impression ?** sur **Oui** pour stocker la sortie générée dans l’archive d’impression, afin qu’elle soit disponible pour une impression ultérieure.</span><span class="sxs-lookup"><span data-stu-id="2de73-122">Set the **Save in print archive?** option to **Yes** to store the generated output in the print archive, so that it's available for further printing.</span></span> <span data-ttu-id="2de73-123">Pour accéder ultérieurement à la sortie archivée, accédez à **Administration de l’organisation** \>**Recherches et états** \>**Archive d’état**.</span><span class="sxs-lookup"><span data-stu-id="2de73-123">To access archived output later, go to **Organization administration** \> **Inquiries and reports** \> **Report archive**.</span></span>

<span data-ttu-id="2de73-124">[![Utilisation de la destination de l’imprimante](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span><span class="sxs-lookup"><span data-stu-id="2de73-124">[![Using the Printer destination](./media/ER_Destinations-PrinterDestination.png)](./media/ER_Destinations-PrinterDestination.png)</span></span>

> [!NOTE]
> <span data-ttu-id="2de73-125">L’option **Convertir en PDF** ne doit pas être activée lorsque vous configurez la destination de l’**Imprimante**.</span><span class="sxs-lookup"><span data-stu-id="2de73-125">The **Convert to PDF** option doesn't have to be turned on when you configure the **Printer** destination.</span></span> <span data-ttu-id="2de73-126">La conversion PDF à des fins d’impression se produira même si l’option est désactivée.</span><span class="sxs-lookup"><span data-stu-id="2de73-126">The PDF conversion for printing purposes will occur even if the option is turned off.</span></span>

<span data-ttu-id="2de73-127">Pour utiliser une [orientation de la page](electronic-reporting-destinations.md#SelectPdfPageOrientation) spécifique lorsque vous imprimez un document sortant au format Excel, vous devez activer l’option **Convertir en PDF**.</span><span class="sxs-lookup"><span data-stu-id="2de73-127">To use a specific [page orientation](electronic-reporting-destinations.md#SelectPdfPageOrientation) when you print an outbound document in Excel format, you must turn on the **Convert to PDF** option.</span></span> <span data-ttu-id="2de73-128">Lorsque vous définissez l’option **Convertir en PDF** sur **Oui**, le champ **Orientation de la page** devient disponible.</span><span class="sxs-lookup"><span data-stu-id="2de73-128">When you set the **Convert to PDF** option to **Yes**, the **Page orientation** field becomes available.</span></span> <span data-ttu-id="2de73-129">Dans le champ **Orientation de la page**, sélectionnez une orientation de la page.</span><span class="sxs-lookup"><span data-stu-id="2de73-129">In the **Page orientation** field, you can select a page orientation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2de73-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="2de73-130">Additional resources</span></span>

- [<span data-ttu-id="2de73-131">Vue d’ensemble des états électroniques</span><span class="sxs-lookup"><span data-stu-id="2de73-131">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="2de73-132">Destinations pour la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="2de73-132">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]