---
title: Résoudre les problèmes de travail d’entrepôt
description: Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a00ae517ff583e4231099d8e9f5d5b5a696cf7f7
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645791"
---
# <a name="troubleshoot-warehouse-work"></a><span data-ttu-id="287ca-103">Résoudre les problèmes de travail d’entrepôt</span><span class="sxs-lookup"><span data-stu-id="287ca-103">Troubleshoot warehouse work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="287ca-104">Cette rubrique décrit comment résoudre les problèmes courants que vous pourriez rencontrer lors du travail de réservations en entrepôts dans Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="287ca-104">This topic describes how to fix common issues that you might encounter while you work with warehouse work in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a><span data-ttu-id="287ca-105">Je ne peux pas déplacer des contenants comportant des éléments de numéro de série lorsqu'un numéro vierge et un reçu vierge sont autorisés dans le groupe de dimensions de suivi.</span><span class="sxs-lookup"><span data-stu-id="287ca-105">I can't move license plates that have serial number items when blank issue and blank receipt are allowed on the tracking dimension group.</span></span>

### <a name="issue-description"></a><span data-ttu-id="287ca-106">Description du problème</span><span class="sxs-lookup"><span data-stu-id="287ca-106">Issue description</span></span>

<span data-ttu-id="287ca-107">Vous ne pouvez pas déplacer un contenant à l'aide d'un élément de menu **Mouvement** si le numéro de série a des paramètres de *Émission vierge autorisée* et *Reçu vierge autorisé* sur le groupe de dimensions de suivi, et s'il y a plusieurs contenants au même emplacement, dont certaines ont des numéros de série et d'autres ne les ont pas.</span><span class="sxs-lookup"><span data-stu-id="287ca-107">You can't move a license plate by using a **Movement** menu item if the serial number has settings of *Blank issue allowed* and *Blank receipt allowed* on the tracking dimension group, and if there are multiple license plates in the same location, some of which have serial numbers and some of which don't have them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="287ca-108">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="287ca-108">Issue resolution</span></span>

<span data-ttu-id="287ca-109">Ce problème sera résolu par les modifications déployées dans [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span><span class="sxs-lookup"><span data-stu-id="287ca-109">This issue will be fixed by changes that are deployed in [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687).</span></span> <span data-ttu-id="287ca-110">Ces changements rendront le champ **Numéro de série** facultatif lorsqu'un reçu vierge et une émission vierge sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="287ca-110">Those changes will make the **Serial number** field optional when blank receipt and blank issue are allowed.</span></span>

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a><span data-ttu-id="287ca-111">Je reçois le message d'erreur suivant dans l'application d'entrepôt lorsque je traite des mouvements : "Le propriétaire du stock %1 n'est pas autorisé dans ce processus. »</span><span class="sxs-lookup"><span data-stu-id="287ca-111">I receive the following error message in the warehouse app when I process movements: "The inventory owner %1 is not allowed in this process."</span></span>

### <a name="issue-description"></a><span data-ttu-id="287ca-112">Description du problème</span><span class="sxs-lookup"><span data-stu-id="287ca-112">Issue description</span></span>

<span data-ttu-id="287ca-113">La dimension de suivi **Propriétaire** est manquante lorsque l'application d'entrepôt est utilisée pour effectuer des mouvements.</span><span class="sxs-lookup"><span data-stu-id="287ca-113">The **Owner** tracking dimension is missing when the warehouse app is used to make movements.</span></span> <span data-ttu-id="287ca-114">Un journal de transfert d'inventaire régulier du client Supply Chain Management semble fonctionner comme prévu et ne peut être enregistré que si la dimension **Propriétaire** est remplie.</span><span class="sxs-lookup"><span data-stu-id="287ca-114">A regular inventory transfer journal from the Supply Chain Management client appears to work as intended and can be posted only if the **Owner** dimension is filled in.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="287ca-115">Résolution du problème</span><span class="sxs-lookup"><span data-stu-id="287ca-115">Issue resolution</span></span>

<span data-ttu-id="287ca-116">Microsoft a évalué ce problème et a déterminé qu'il s'agissait d'une limitation de fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="287ca-116">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="287ca-117">Actuellement, les processus de gestion des entrepôts ne prennent en charge que les stocks appartenant à l'entité juridique.</span><span class="sxs-lookup"><span data-stu-id="287ca-117">Currently, warehouse management processes support only inventory that is owned by the legal entity.</span></span>
