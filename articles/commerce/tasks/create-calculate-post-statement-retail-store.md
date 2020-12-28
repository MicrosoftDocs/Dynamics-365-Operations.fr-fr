---
title: Créer, calculer et valider des relevés pour un magasin de vente au détail
description: Cette rubrique décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21f1b0a34205e192957405bc9d298c45c8bb4d25
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412322"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="6841a-103">Créer, calculer et valider des relevés pour un magasin de vente au détail</span><span class="sxs-lookup"><span data-stu-id="6841a-103">Create, calculate, and post statements for a retail store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6841a-104">Cette rubrique décrit les étapes manuelles pour créer, calculer et valider un relevé pour un magasin.</span><span class="sxs-lookup"><span data-stu-id="6841a-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="6841a-105">Des traitements par lots peuvent également être configurés pour les mêmes tâches.</span><span class="sxs-lookup"><span data-stu-id="6841a-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="6841a-106">Les étapes de configuration et d'exécution des traitements par lots sont disponibles dans d'autres rubriques.</span><span class="sxs-lookup"><span data-stu-id="6841a-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="6841a-107">Pour effectuer cette procédure, vous devez disposer des transactions effectuées dans le PDV et extraites dans Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6841a-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Commerce.</span></span> <span data-ttu-id="6841a-108">Cet enregistrement utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="6841a-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="6841a-109">Sélectionnez **Finances du magasin** sur la page d'accueil.</span><span class="sxs-lookup"><span data-stu-id="6841a-109">Select **Store financials** from the home page.</span></span>
2. <span data-ttu-id="6841a-110">Sélectionnez **Nouveau relevé**.</span><span class="sxs-lookup"><span data-stu-id="6841a-110">Select **New statement**.</span></span>
3. <span data-ttu-id="6841a-111">Dans le champ **Numéro de magasin**, sélectionnez une option dans le menu déroulant.</span><span class="sxs-lookup"><span data-stu-id="6841a-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="6841a-112">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="6841a-112">Select **OK**.</span></span>
5. <span data-ttu-id="6841a-113">Le groupe **Paramétrage** contient les paramètres qui contrôlent les transactions incluses dans le relevé et leur regroupement en lignes de relevé.</span><span class="sxs-lookup"><span data-stu-id="6841a-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="6841a-114">Vous pouvez ouvrir le groupe **Paramétrage** et modifier ces paramètres, ou vous pouvez utiliser les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="6841a-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="6841a-115">Le champ **Méthode de relevé** définit la manière dont les lignes de relevé sont regroupées.</span><span class="sxs-lookup"><span data-stu-id="6841a-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="6841a-116">Sélectionnez un membre du personnel ou une caisse enregistreuse dans le champ **Personnel/caisse enregistreuse** si vous souhaitez calculer un relevé uniquement pour ce membre du personnel ou cette caisse enregistreuse spécifique.</span><span class="sxs-lookup"><span data-stu-id="6841a-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="6841a-117">Dans le champ **Méthode de clôture**, sélectionnez une option.</span><span class="sxs-lookup"><span data-stu-id="6841a-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="6841a-118">Sélectionnez **Calcul du relevé** du volet Actions.</span><span class="sxs-lookup"><span data-stu-id="6841a-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="6841a-119">Cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="6841a-119">Select **Yes**.</span></span>
    - <span data-ttu-id="6841a-120">Après le calcul du relevé, des lignes doivent être créées avec les montants totaux pour chaque mode de paiement et chaque méthode de relevé utilisé.</span><span class="sxs-lookup"><span data-stu-id="6841a-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="6841a-121">Saisissez un montant compté dans chaque ligne s'il doit être saisi ou mis à jour.</span><span class="sxs-lookup"><span data-stu-id="6841a-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="6841a-122">Le champ Compté est renseigné avec les montants des comptages de caisse effectués dans le PDV.</span><span class="sxs-lookup"><span data-stu-id="6841a-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="6841a-123">Sélectionnez **Validation du relevé** du volet Actions.</span><span class="sxs-lookup"><span data-stu-id="6841a-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="6841a-124">Sélectionnez **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="6841a-124">Select **Close**.</span></span>
11. <span data-ttu-id="6841a-125">Fermez le volet.</span><span class="sxs-lookup"><span data-stu-id="6841a-125">Close the pane.</span></span>
12. <span data-ttu-id="6841a-126">Sur la page d'accueil, sélectionnez **Finances du magasin**.</span><span class="sxs-lookup"><span data-stu-id="6841a-126">At the home page, select **Store financials**.</span></span>
13. <span data-ttu-id="6841a-127">Sélectionnez l'onglet **Relevés validés**.</span><span class="sxs-lookup"><span data-stu-id="6841a-127">Select the **Posted statements** tab.</span></span>

