---
title: Modifier une prévision de la demande manuellement
description: Cette rubrique décrit comment modifier la prévision pour un article
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889022"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="0108e-103">Modifier une prévision de la demande manuellement</span><span class="sxs-lookup"><span data-stu-id="0108e-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0108e-104">Cette procédure permet d’indiquer comment modifier la prévision pour un article.</span><span class="sxs-lookup"><span data-stu-id="0108e-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="0108e-105">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="0108e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0108e-106">Cette procédure est destinée au gestionnaire de production.</span><span class="sxs-lookup"><span data-stu-id="0108e-106">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="0108e-107">Modifier la prévision pour un article sélectionné</span><span class="sxs-lookup"><span data-stu-id="0108e-107">Modify the forecast for a selected item</span></span>

<span data-ttu-id="0108e-108">Pour modifier la prévision pour un article sélectionné :</span><span class="sxs-lookup"><span data-stu-id="0108e-108">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="0108e-109">Accédez à **Modules \> Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="0108e-109">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="0108e-110">Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.</span><span class="sxs-lookup"><span data-stu-id="0108e-110">In the list, find and select the desired record.</span></span> <span data-ttu-id="0108e-111">Sélectionnez l’article dont vous souhaitez modifier la prévision.</span><span class="sxs-lookup"><span data-stu-id="0108e-111">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="0108e-112">Dans le volet Actions, ouvrez l'onglet **Planifier** et sélectionnez **Prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="0108e-112">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="0108e-113">Dans la liste, sélectionnez une ligne.</span><span class="sxs-lookup"><span data-stu-id="0108e-113">In the list, select a row.</span></span> <span data-ttu-id="0108e-114">S’il n’existe aucune ligne de prévision, créez une ligne en sélectionnant **Nouveau** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0108e-114">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="0108e-115">Entrez un nombre positif dans le champ **Quantité vendue**.</span><span class="sxs-lookup"><span data-stu-id="0108e-115">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="0108e-116">Ce chiffre représente la quantité prévue pour l’article.</span><span class="sxs-lookup"><span data-stu-id="0108e-116">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="0108e-117">Une erreur s'affichera si vous entrez un nombre négatif.</span><span class="sxs-lookup"><span data-stu-id="0108e-117">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="0108e-118">Renseignez les autres champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0108e-118">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="0108e-119">Sélectionnez **Enregistrer** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="0108e-119">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a><span data-ttu-id="0108e-120">Modifier la prévision pour un ou plusieurs articles dans Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="0108e-120">Modify the forecast for one or more items Microsoft Excel</span></span>

<span data-ttu-id="0108e-121">Pour modifier la prévision pour un ou plusieurs articles dans Microsoft Excel :</span><span class="sxs-lookup"><span data-stu-id="0108e-121">To modify the forecast for one or more items Microsoft Excel:</span></span>

1. <span data-ttu-id="0108e-122">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0108e-122">Do one of the following:</span></span>
    - <span data-ttu-id="0108e-123">Ouvrez la page **Prévision de la demande** pour n'importe quel article (peu importe lequel), comme décrit dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="0108e-123">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="0108e-124">Accédez à **Planification \> Prévision \> Entrée manuelle de la prévision \> Lignes de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="0108e-124">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="0108e-125">Dans le volet Actions, sélectionnez **Ouvrir dans Microsoft Office \> Entrées de prévision de la demande**.</span><span class="sxs-lookup"><span data-stu-id="0108e-125">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="0108e-126">Sélectionnez un emplacement de téléchargement, enregistrez, puis ouvrez le fichier téléchargé dans Excel.</span><span class="sxs-lookup"><span data-stu-id="0108e-126">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="0108e-127">Si vous voyez un avertissement, sélectionnez **Activer la modification**.</span><span class="sxs-lookup"><span data-stu-id="0108e-127">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="0108e-128">Dans Excel, connectez-vous à Supply Chain Management à l'aide du volet des tâches Microsoft Dynamics.</span><span class="sxs-lookup"><span data-stu-id="0108e-128">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="0108e-129">Vous devez vous connecter avec l'option **Maintenir la connexion** activée et vous devez faire confiance à l'application de connexion aux données.</span><span class="sxs-lookup"><span data-stu-id="0108e-129">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="0108e-130">La feuille de calcul Excel affiche désormais toutes les lignes de prévision de la demande actuelle pour votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="0108e-130">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="0108e-131">Ajoutez, supprimez et modifiez les lignes de prévision de la demande selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0108e-131">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="0108e-132">Sélectionnez **Publier** dans le volet des tâches de Microsoft Dynamics pour charger vos modifications dans Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0108e-132">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
