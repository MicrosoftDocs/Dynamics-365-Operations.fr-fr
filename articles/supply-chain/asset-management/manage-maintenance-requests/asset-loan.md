---
title: Financements reposant sur l'actif
description: Cette rubrique décrit comment enregistrer des financements reposant sur l'actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cba680d0ad626e0275539d7478a83639a9d22635
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889647"
---
# <a name="asset-loans"></a><span data-ttu-id="64e57-103">Financements reposant sur l'actif</span><span class="sxs-lookup"><span data-stu-id="64e57-103">Asset loans</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="64e57-104">Si votre société reçoit des actifs destinés à des travaux de réparation ou de maintenance depuis des sites internes ou des clients, et si vous prêtez temporairement des actifs à ces sites ou à ces clients, le module Gestion des actifs peut suivre les prêts d'actifs.</span><span class="sxs-lookup"><span data-stu-id="64e57-104">If your company receives assets for repair or maintenance jobs from either internal locations or customers, and if you temporarily loan assets to those locations or customers, Asset Management can track the asset loans.</span></span>

## <a name="register-asset-loans-on-a-maintenance-request"></a><span data-ttu-id="64e57-105">Enregistrer des financements reposant sur des actifs dans le cadre d'une demande de maintenance</span><span class="sxs-lookup"><span data-stu-id="64e57-105">Register asset loans on a maintenance request</span></span>

1. <span data-ttu-id="64e57-106">Sélectionnez **Gestion des actifs** \> **Commun** \> **Demandes de maintenance** \> **Toutes les demandes de maintenance** ou **Demandes de maintenance actives**.</span><span class="sxs-lookup"><span data-stu-id="64e57-106">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="64e57-107">Sélectionnez la demande de maintenance pour enregistrer un financement reposant sur l'actif, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="64e57-107">Select the maintenance request to register an asset loan on, and then select **Edit**.</span></span>
3. <span data-ttu-id="64e57-108">Dans la page **Demande**, sélectionnez **Envoyer l'actif d'emprunt**.</span><span class="sxs-lookup"><span data-stu-id="64e57-108">On the **Request** page, select **Send loan asset**.</span></span>
4. <span data-ttu-id="64e57-109">Sélectionnez l'actif, puis entrez la date de retour prévue.</span><span class="sxs-lookup"><span data-stu-id="64e57-109">Select the asset, and enter the expected return date.</span></span>
5. <span data-ttu-id="64e57-110">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64e57-110">Select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="64e57-111">Vous pouvez envoyer un actif d'emprunt si un actif du même type d'actif est disponible.</span><span class="sxs-lookup"><span data-stu-id="64e57-111">You can send a loan asset only if an asset of the same asset type is available.</span></span>
> - <span data-ttu-id="64e57-112">L'actif que vous prêtez doit avoir un état de cycle de vie d'actif lui permettant d'être utilisé en tant qu'actif d'emprunt, tel que **InStorage**.</span><span class="sxs-lookup"><span data-stu-id="64e57-112">The asset that you loan must have an asset lifecycle state that allows it to be used as a loan asset, such as **InStorage**.</span></span> <span data-ttu-id="64e57-113">Lorsque l'emprunt d'actif est enregistré, l'état de cycle de vie de l'actif est automatiquement mis à jour, par exemple, **OnLoan**.</span><span class="sxs-lookup"><span data-stu-id="64e57-113">When the asset loan is registered, the asset lifecycle state of the asset is automatically updated to, for example, **OnLoan**.</span></span>

<span data-ttu-id="64e57-114">Pour afficher la liste de tous les actifs que vous avez prêtés à d'autres emplacements ou clients, sélectionnez **Gestion des actifs** \> **Commun** \> **Financement reposant sur l'actif** \> **Tous les financements reposant sur l'actif**.</span><span class="sxs-lookup"><span data-stu-id="64e57-114">To view a list of all the assets that you've loaned to other locations or customers, select **Asset management** \> **Common** \> **Asset loan** \> **All asset loans**.</span></span> <span data-ttu-id="64e57-115">Si la case à cocher **Terminé** est activée pour un actif, l'actif a été enregistré comme retourné à votre société.</span><span class="sxs-lookup"><span data-stu-id="64e57-115">If the **Ended** check box is selected for an asset, the asset has been registered as returned to your company.</span></span>

![Gérer les demandes de maintenance](media/06-manage-maintenance-requests.png)

<span data-ttu-id="64e57-117">Dans la page **Financements actifs reposant sur l'actif**, vous pouvez afficher une liste de toutes les actifs d'emprunt qui n'ont pas encore été retournés à votre société.</span><span class="sxs-lookup"><span data-stu-id="64e57-117">On the **Active asset loans** page, you can view a list of all the loan assets that haven't yet been returned to your company.</span></span>

## <a name="register-loan-assets-as-returned"></a><span data-ttu-id="64e57-118">Enregistrer l'actif d'emprunt comme retourné</span><span class="sxs-lookup"><span data-stu-id="64e57-118">Register loan assets as returned</span></span>

1. <span data-ttu-id="64e57-119">Sélectionnez **Gestion des actifs** \> **Commun** \> **Financement reposant sur l'actif** \> **Financements actifs reposant sur l'actif**.</span><span class="sxs-lookup"><span data-stu-id="64e57-119">Select **Asset management** \> **Common** \> **Asset loan** \> **Active asset loans**.</span></span>
2. <span data-ttu-id="64e57-120">Sélectionnez le financement reposant sur l'actif à enregistrer comme étant retourné, puis sélectionnez **Retourner un financement reposant sur l'actif**.</span><span class="sxs-lookup"><span data-stu-id="64e57-120">Select the asset loan to register as returned, and then select **Return asset loan**.</span></span>
3. <span data-ttu-id="64e57-121">Dans le champ **Retourné**, entrez de date et l'heure.</span><span class="sxs-lookup"><span data-stu-id="64e57-121">In the **Returned** field, enter the date and time.</span></span>
4. <span data-ttu-id="64e57-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64e57-122">Select **OK**.</span></span>
5. <span data-ttu-id="64e57-123">Actualisez la page de liste **Financements actifs reposant sur l'actif**, et assurez-vous que l'emprunt d'actif n'apparaît plus dans la liste.</span><span class="sxs-lookup"><span data-stu-id="64e57-123">Refresh the **Active asset loans** list page, and notice that the asset loan no longer appears in the list.</span></span>
