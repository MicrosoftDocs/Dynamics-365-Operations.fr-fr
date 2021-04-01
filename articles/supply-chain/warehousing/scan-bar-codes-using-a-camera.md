---
title: Lire les codes-barres à l’aide d’une caméra dans l’application d’entrepôt
description: Cette rubrique explique comment configurer l’application d’entrepôt pour lire les codes-barres à l’aide de la caméra d’un appareil mobile.
author: MarkusFogelberg
manager: tfehr
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 28a49736f43bd2d3bfd4c6856f2f87079a005ba2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239300"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-app"></a><span data-ttu-id="1e6c0-103">Lire les codes-barres à l’aide d’une caméra dans l’application d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="1e6c0-103">Scan bar codes using a camera in the warehouse app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1e6c0-104">Cette rubrique explique comment configurer l’application d’entrepôt pour lire les codes-barres à l’aide de la caméra d’un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-104">This topic explains how to set up the warehouse app to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1e6c0-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="1e6c0-105">Prerequisites</span></span>
<span data-ttu-id="1e6c0-106">Pour utiliser cette fonction, la version 1.2.0.0 de l’application d’entrepôt doit être installée, et l’appareil doit avoir une caméra.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-106">To use this feature, you need to have version 1.2.0.0 of the warehouse app installed, and your device must have a camera.</span></span> <span data-ttu-id="1e6c0-107">Lorsque vous ouvrez l’application après la mise à jour, vous serez invité(e) à autoriser l’application pour utiliser la caméra.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-107">When you open the app after updating, you will be prompted to allow the app to use the camera.</span></span> <span data-ttu-id="1e6c0-108">Si votre appareil ne possède pas de caméra, aucune invite ne s’affichera et vous ne pourrez pas utiliser la caméra en tant que scanneur.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="1e6c0-109">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="1e6c0-109">Setup</span></span>
<span data-ttu-id="1e6c0-110">Dans les paramètres d’affichage de l’application d’entrepôt, vous pouvez choisir si la caméra doit être utilisée pour la lecture des codes-barres.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-110">In the Display settings of the warehouse application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="1e6c0-111">Si vous activez l’option **Utiliser la caméra comme scanneur**, vous pourrez utiliser la caméra sur chaque champ de saisie si le mode de saisie favori est défini sur **Lecture**.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="1e6c0-112">Pour contrôler si un champ de saisie peut être lu, dans la page **Noms de champ d’application d’entrepôt**, définissez **Mode de saisie favori** sur **Lecture**.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-112">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="1e6c0-113">Lorsque cette option est sélectionnée, une caméra peut être utilisée pour la lecture dans l’application d’entrepôt.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-113">When this option is selected, a camera can be used for scanning in the warehouse app.</span></span> <span data-ttu-id="1e6c0-114">Pour plus d’informations sur la configuration des noms de champs d’application dans l’application Entreposage, voir [Configurer les noms de champ d’application dans l’application d’entrepôt](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="1e6c0-114">For information about how to configure app field names in Warehousing, see [Configure app field names in warehouse app](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="1e6c0-115">Formats de code-barres pris en charge</span><span class="sxs-lookup"><span data-stu-id="1e6c0-115">Supported bar code formats</span></span>
<span data-ttu-id="1e6c0-116">Les formats de code-barres les plus courants sont pris en charge, notamment les codes 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A et QR.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="1e6c0-117">Navigation</span><span class="sxs-lookup"><span data-stu-id="1e6c0-117">Navigation</span></span>
<span data-ttu-id="1e6c0-118">La page Caméra sera lancée sur chaque page si le champ de saisie a pour son mode de saisie favori défini sur Lecture. Lorsque vous êtes sur la page Caméra, utilisez les options suivantes pour naviguer :</span><span class="sxs-lookup"><span data-stu-id="1e6c0-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="1e6c0-119">Cliquez sur le bouton Précédent pour revenir à la page Tâche et détails.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="1e6c0-120">Cliquez sur le crayon sur la page Tâche et détails pour accéder à la page dans laquelle vous pouvez effectuer une saisie manuelle.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="1e6c0-121">Cliquez sur la caméra dans la page Tâche et détails pour revenir à la page Caméra.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="1e6c0-122">Page Tâche et détails</span><span class="sxs-lookup"><span data-stu-id="1e6c0-122">Task and details page</span></span> | <span data-ttu-id="1e6c0-123">Page Caméra</span><span class="sxs-lookup"><span data-stu-id="1e6c0-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![Page de détails de l’exemple de tâche de lecture de la caméra](./media/camera-scanning-example-task-detail-page50.png)          | ![Page plus petite d’exemple de caméra de lecture de la caméra](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="1e6c0-126">Sur la page Caméra, lorsque vous cliquez sur le bouton Caméra, il apparaît estompé lorsque vous tentez d’identifier un code-barres.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="1e6c0-127">Si un code-barres n’est pas reconnu dans les 5 secondes, le processus expirera et le bouton Caméra redeviendra disponible.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="1e6c0-128">Vous pourrez ensuite tenter de lire à nouveau un code-barres.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="1e6c0-129">Lorsque vous dirigez la caméra vers un code-barres, conservez le code-barres aligné entre les crochets pour obtenir le meilleur résultat.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="1e6c0-130">Lorsqu’un code-barres est lu correctement, le résultat est traité et vous passez à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="1e6c0-131">Si l’étape suivante contient un autre champ de saisie dont le mode de saisie favori est défini sur Lecture, la page Caméra redémarrera.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="1e6c0-132">Si l’étape suivante n’est pas un champ de lecture, la page Caméra ne se lancera pas.</span><span class="sxs-lookup"><span data-stu-id="1e6c0-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]