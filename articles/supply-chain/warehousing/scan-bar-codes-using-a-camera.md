---
title: Lire les codes-barres à l’aide d’une caméra dans l’application mobile Gestion des entrepôts
description: Cette rubrique explique comment configurer l’application mobile Gestion des entrepôts pour lire les codes-barres à l’aide de la caméra d’un appareil mobile.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831216"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="87c87-103">Lire les codes-barres à l’aide d’une caméra dans l’application mobile Gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="87c87-103">Scan bar codes using a camera in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87c87-104">Cette rubrique explique comment configurer l’application mobile Gestion des entrepôts pour lire les codes-barres à l’aide de la caméra d’un appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="87c87-104">This topic explains how to set up the Warehouse Management mobile app to scan bar codes using a camera on a mobile device.</span></span>

## <a name="setup"></a><span data-ttu-id="87c87-105">Paramétrage</span><span class="sxs-lookup"><span data-stu-id="87c87-105">Setup</span></span>

<span data-ttu-id="87c87-106">Dans les paramètres d’affichage de l’application mobile Gestion des entrepôts, vous pouvez choisir si la caméra doit être utilisée pour la lecture des codes-barres.</span><span class="sxs-lookup"><span data-stu-id="87c87-106">In the display settings of the Warehouse Management mobile app, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="87c87-107">Si vous activez l’option **Utiliser la caméra comme scanneur**, vous pourrez utiliser la caméra sur chaque champ de saisie si le mode de saisie favori est défini sur **Lecture**.</span><span class="sxs-lookup"><span data-stu-id="87c87-107">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span>

<span data-ttu-id="87c87-108">Pour contrôler si un champ de saisie peut être lu, dans la page **Noms de champ d’application d’entrepôt**, définissez **Mode de saisie favori** sur **Lecture**.</span><span class="sxs-lookup"><span data-stu-id="87c87-108">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="87c87-109">Lorsque cette option est sélectionnée, une caméra peut être utilisée pour la lecture dans l’application mobile Gestion des entrepôts.</span><span class="sxs-lookup"><span data-stu-id="87c87-109">When this option is selected, a camera can be used for scanning in the Warehouse Management mobile app.</span></span> <span data-ttu-id="87c87-110">Pour plus d’informations, voir [Configurer les champs pour l’application mobile Gestion des entrepôts](configure-app-field-names-priorities-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="87c87-110">For more information, see [Configure fields for the Warehouse Management mobile app](configure-app-field-names-priorities-warehouse.md).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="87c87-111">Formats de code-barres pris en charge</span><span class="sxs-lookup"><span data-stu-id="87c87-111">Supported bar code formats</span></span>

<span data-ttu-id="87c87-112">Les formats de code-barres les plus courants sont pris en charge, notamment les codes 128, 39, 93, EAN-8, EAN-13, UPC-E, UPC-A et QR.</span><span class="sxs-lookup"><span data-stu-id="87c87-112">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span>

## <a name="navigation"></a><span data-ttu-id="87c87-113">Navigation</span><span class="sxs-lookup"><span data-stu-id="87c87-113">Navigation</span></span>

<span data-ttu-id="87c87-114">La page Caméra sera lancée sur chaque page si le champ de saisie a pour son **Mode de saisie favori** défini sur *Lecture*. Lorsque vous êtes sur la page Caméra, utilisez les options suivantes pour naviguer :</span><span class="sxs-lookup"><span data-stu-id="87c87-114">The camera page will be initiated on each page where the input field has its **Preferred input mode** set to *Scanning*, when you are on the camera page use the following options to navigate:</span></span>

- <span data-ttu-id="87c87-115">Sélectionnez le bouton Précédent pour revenir à la page **Tâche et détails**.</span><span class="sxs-lookup"><span data-stu-id="87c87-115">Select the back button to go back to the **Task and details** page.</span></span>
- <span data-ttu-id="87c87-116">Sélectionnez le crayon sur la page **Tâche et détails** pour accéder à la page dans laquelle vous pouvez effectuer une saisie manuelle.</span><span class="sxs-lookup"><span data-stu-id="87c87-116">Select the pencil on the **Task and details** page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="87c87-117">Sélectionnez la caméra dans la page **Tâche et détails** pour revenir à la page Caméra.</span><span class="sxs-lookup"><span data-stu-id="87c87-117">Select the camera on the **Task and details** page to go back to the camera page.</span></span>

<span data-ttu-id="87c87-118">Sur la page Caméra, lorsque vous sélectionnez le bouton Caméra, il apparaît estompé lorsque vous tentez d’identifier un code-barres.</span><span class="sxs-lookup"><span data-stu-id="87c87-118">On the camera page, when you select the camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="87c87-119">Si un code-barres n’est pas reconnu dans les 5 secondes, le processus expirera et le bouton Caméra redeviendra disponible.</span><span class="sxs-lookup"><span data-stu-id="87c87-119">If a bar code is not identified within 5 seconds, the process will time out and the camera button will become available again.</span></span> <span data-ttu-id="87c87-120">Vous pourrez ensuite tenter de lire à nouveau un code-barres.</span><span class="sxs-lookup"><span data-stu-id="87c87-120">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="87c87-121">Lorsque vous dirigez la caméra vers un code-barres, conservez le code-barres aligné entre les crochets pour obtenir le meilleur résultat.</span><span class="sxs-lookup"><span data-stu-id="87c87-121">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="87c87-122">Lorsqu’un code-barres est lu correctement, le résultat est traité et vous passez à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="87c87-122">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="87c87-123">Si l’étape suivante contient un autre champ de saisie dont le mode de saisie favori est défini sur Lecture, la page Caméra redémarrera.</span><span class="sxs-lookup"><span data-stu-id="87c87-123">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="87c87-124">Si l’étape suivante n’est pas un champ de lecture, la page Caméra ne se lancera pas.</span><span class="sxs-lookup"><span data-stu-id="87c87-124">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]