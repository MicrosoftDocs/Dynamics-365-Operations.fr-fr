---
title: Modifier les relations hiérarchiques d’un poste
description: Cette procédure illustre comment modifier la relation hiérarchique pour un employé.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmPosition, HcmPositionReportsToDialog, HcmPositionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd884362393674a4f55ea0410548edbb72786fff
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465388"
---
# <a name="modify-reporting-relationships-for-a-position"></a><span data-ttu-id="59bad-103">Modifier les relations hiérarchiques d’un poste</span><span class="sxs-lookup"><span data-stu-id="59bad-103">Modify reporting relationships for a position</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="59bad-104">Cette procédure illustre comment modifier la relation hiérarchique pour un employé.</span><span class="sxs-lookup"><span data-stu-id="59bad-104">This procedure shows how to change the reporting relationship for an employee.</span></span> <span data-ttu-id="59bad-105">La relation hiérarchique peut être utilisée pour acheminer des documents dans le workflow.</span><span class="sxs-lookup"><span data-stu-id="59bad-105">The reporting relationship can be used for routing documents through workflow.</span></span> <span data-ttu-id="59bad-106">La procédure illustre également la manière d’affecter l’employé à des hiérarchies supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="59bad-106">The procedure also shows how to assign the employee to additional hierarchies.</span></span> <span data-ttu-id="59bad-107">Par exemple, un employé peut faire partie d’une équipe de projet avec une relation hiérarchique informelle envers un superviseur du projet.</span><span class="sxs-lookup"><span data-stu-id="59bad-107">For example, an employee might be a part of a project team with an informal reporting relationship to a project supervisor.</span></span> <span data-ttu-id="59bad-108">Les relations hiérarchiques supplémentaires peuvent être définies par rapport au poste afin de convenir à divers scénarios de projet ou de matrice.</span><span class="sxs-lookup"><span data-stu-id="59bad-108">Additional reporting relationships can be defined on the position to accommodate various project or matrix scenarios.</span></span> <span data-ttu-id="59bad-109">Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.</span><span class="sxs-lookup"><span data-stu-id="59bad-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="59bad-110">Accédez à Ressources humaines > Postes > Postes.</span><span class="sxs-lookup"><span data-stu-id="59bad-110">Go to Human resources > Positions > Positions.</span></span>
2. <span data-ttu-id="59bad-111">Utilisez le Filtre rapide pour rechercher les enregistrements.</span><span class="sxs-lookup"><span data-stu-id="59bad-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="59bad-112">Par exemple, filtrez sur le champ Poste avec une valeur de « 000091 ».</span><span class="sxs-lookup"><span data-stu-id="59bad-112">For example, filter on the Position field with a value of '000091'.</span></span>
3. <span data-ttu-id="59bad-113">Dans la liste, cliquer sur le lien dans la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="59bad-113">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="59bad-114">Développez la section Poste de référence.</span><span class="sxs-lookup"><span data-stu-id="59bad-114">Expand the Reports to position section.</span></span>
5. <span data-ttu-id="59bad-115">Cliquez sur Nouveau pour ouvrir la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="59bad-115">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="59bad-116">Dans le champ Référence, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="59bad-116">In the Reports to field, enter or select a value.</span></span>
7. <span data-ttu-id="59bad-117">Cliquez sur Créer.</span><span class="sxs-lookup"><span data-stu-id="59bad-117">Click Create.</span></span>
8. <span data-ttu-id="59bad-118">Développez ou réduisez la section Relations.</span><span class="sxs-lookup"><span data-stu-id="59bad-118">Expand the Relationships section.</span></span>
9. <span data-ttu-id="59bad-119">Cliquez sur Ajouter.</span><span class="sxs-lookup"><span data-stu-id="59bad-119">Click Add.</span></span>
10. <span data-ttu-id="59bad-120">Cochez la case située à gauche de la grille.</span><span class="sxs-lookup"><span data-stu-id="59bad-120">Select the check box on the left of the grid.</span></span>
11. <span data-ttu-id="59bad-121">Dans le champ Nom de la hiérarchie, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="59bad-121">In the Hierarchy name field, enter or select a value.</span></span>
    * <span data-ttu-id="59bad-122">Exemple : Projet</span><span class="sxs-lookup"><span data-stu-id="59bad-122">Example: Project</span></span>  
12. <span data-ttu-id="59bad-123">Dans le champ Poste de référence, saisissez ou sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="59bad-123">In the Reports to position field, enter or select a value.</span></span>  <span data-ttu-id="59bad-124">Exemple : 000437</span><span class="sxs-lookup"><span data-stu-id="59bad-124">Example:  000437</span></span>
13. <span data-ttu-id="59bad-125">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="59bad-125">Click Save.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]