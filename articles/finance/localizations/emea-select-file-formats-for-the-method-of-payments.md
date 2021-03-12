---
title: Formats de fichier des modes de paiement
description: Cette rubrique décrit les deux méthodes d’obtention des formats de fichier que vous pouvez utiliser pour les modes de paiement.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.custom: 262514
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 499d3cf85da395a4b6879e63c8c11cf4c495f18a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005968"
---
# <a name="file-formats-for-methods-of-payment"></a><span data-ttu-id="5b713-103">Formats de fichier des modes de paiement</span><span class="sxs-lookup"><span data-stu-id="5b713-103">File formats for methods of payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b713-104">Cette rubrique décrit les deux méthodes d’obtention des formats de fichier que vous pouvez utiliser pour les modes de paiement.</span><span class="sxs-lookup"><span data-stu-id="5b713-104">This topic describes the two methods for getting file formats that you can use for methods of payment.</span></span>

<span data-ttu-id="5b713-105">Deux méthodes peuvent être utilisées pour obtenir les formats de fichier à utiliser avec les modes de paiement, les formats de fichier de génération d’états électroniques ou les formats de fichier X++.</span><span class="sxs-lookup"><span data-stu-id="5b713-105">There are two methods that you can use to get file formats for use with methods of payment, electronic reporting (ER) file formats or X++ file formats.</span></span> <span data-ttu-id="5b713-106">Lorsque vous paramétrez un mode de paiement pour un client ou un fournisseur, vous indiquez les formats de fichier et les normes qui doivent être utilisés pour les paiements et le mode de traitement des paiements.</span><span class="sxs-lookup"><span data-stu-id="5b713-106">When you set up a method of payment for a customer or vendor, you indicate which file formats and standards should be used for payments and how payments will be processed.</span></span> <span data-ttu-id="5b713-107">Vous pouvez choisir parmi les types de format suivants :</span><span class="sxs-lookup"><span data-stu-id="5b713-107">You can select from the following types of formats:</span></span>

-   <span data-ttu-id="5b713-108">Exportation</span><span class="sxs-lookup"><span data-stu-id="5b713-108">Export</span></span>
-   <span data-ttu-id="5b713-109">Importation</span><span class="sxs-lookup"><span data-stu-id="5b713-109">Import</span></span>
-   <span data-ttu-id="5b713-110">Retourner</span><span class="sxs-lookup"><span data-stu-id="5b713-110">Return</span></span>
-   <span data-ttu-id="5b713-111">Remise</span><span class="sxs-lookup"><span data-stu-id="5b713-111">Remittance</span></span>

### <a name="method-1-electronic-reporting-file-formats"></a><span data-ttu-id="5b713-112">Méthode 1 : formats de fichier de génération d’états électroniques</span><span class="sxs-lookup"><span data-stu-id="5b713-112">Method 1: Electronic reporting file formats</span></span>

<span data-ttu-id="5b713-113">Pour les formats de fichier basés sur les configurations ER, vous devez importer les configurations à partir de Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5b713-113">For file formats that are based on ER configurations, you must import the configurations from Lifecycle Services (LCS).</span></span> <span data-ttu-id="5b713-114">Pour plus d’informations, voir [Télécharger les configurations des états électroniques à partir de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)</span><span class="sxs-lookup"><span data-stu-id="5b713-114">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="5b713-115">Après avoir importé les configurations de génération d’états pour ces formats de fichier, les formats importés sont disponibles dans la page **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="5b713-115">After you import reporting configurations for those file formats, the imported formats will be available to select on the **Methods of payment** page.</span></span> <span data-ttu-id="5b713-116">Le processus d’importation et de sélection des formats de fichier pour l’Europe est similaire à la procédure pour le Japon.</span><span class="sxs-lookup"><span data-stu-id="5b713-116">The process for importing and selecting file formats for Europe is similar to the procedure for Japan.</span></span> <span data-ttu-id="5b713-117">Pour plus d’informations, voir [Activer le format de fichier de paiement JBA](tasks/jba-payment-file-format.md)</span><span class="sxs-lookup"><span data-stu-id="5b713-117">For more details, see [Enable the JBA payment file format](tasks/jba-payment-file-format.md)</span></span>

### <a name="method-2-x-file-formats"></a><span data-ttu-id="5b713-118">Méthode 2 : formats de fichier X++</span><span class="sxs-lookup"><span data-stu-id="5b713-118">Method 2: X++ file formats</span></span>

<span data-ttu-id="5b713-119">Pour sélectionner les formats de fichier basés sur le code X++, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="5b713-119">To select file formats that are based on X++ code, complete the following steps.</span></span>

1.  <span data-ttu-id="5b713-120">Accédez à la page **Modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="5b713-120">Go to the **Methods of payment** page.</span></span>
2.  <span data-ttu-id="5b713-121">Dans l’organisateur **Formats de fichier**, cliquez sur **Paramétrage**.</span><span class="sxs-lookup"><span data-stu-id="5b713-121">On the **File formats** FastTab, click **Setup**.</span></span>
3.  <span data-ttu-id="5b713-122">Sélectionnez l’onglet correspondant au type de format de fichier.</span><span class="sxs-lookup"><span data-stu-id="5b713-122">Select the tab that corresponds with the file format type.</span></span>
4.  <span data-ttu-id="5b713-123">Sélectionnez un format de fichier dans la liste **Disponible** et déplacez-le vers la liste **Sélectionné** avec le contrôle de flèche.</span><span class="sxs-lookup"><span data-stu-id="5b713-123">Select a file format from the **Available** list and move it to the **Selected** list with the arrow control.</span></span>
5.  <span data-ttu-id="5b713-124">Fermez la page **Formats de fichier des modes de paiement**.</span><span class="sxs-lookup"><span data-stu-id="5b713-124">Close the **File formats for methods of payment** page.</span></span>
6.  <span data-ttu-id="5b713-125">Dans l’organisateur **Formats de fichier**, sélectionnez le format de fichier à utiliser pour le mode de paiement dans le champ de format de fichier approprié.</span><span class="sxs-lookup"><span data-stu-id="5b713-125">On the **File formats** FastTab, select the file format to use for the method of payment from the appropriate file format field.</span></span> <span data-ttu-id="5b713-126">Les options de génération d’états électroniques génériques doivent être définies sur **Non** pour les formats de fichier X++.</span><span class="sxs-lookup"><span data-stu-id="5b713-126">The General electronic reporting options should be set to **No** for X++ file formats.</span></span>




