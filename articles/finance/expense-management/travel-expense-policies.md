---
title: Définir les stratégies de dépenses
description: Vous pouvez définir des stratégies de dépenses que vos travailleurs sont tenus de suivre lorsqu'ils entrent et soumettent des états de dépenses et des demandes de voyage dans Microsoft Dynamics 365 Finance.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d3b4a8f6cf74bb1fe7e53a4dfdd607f604e16e3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187450"
---
# <a name="define-expense-policies"></a><span data-ttu-id="d26ce-103">Définir les stratégies de dépenses</span><span class="sxs-lookup"><span data-stu-id="d26ce-103">Define expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d26ce-104">Vous pouvez définir des stratégies ou règles que vos collaborateurs sont tenus de suivre lorsqu'ils entrent et soumettent des états de dépenses et des demandes de voyage.</span><span class="sxs-lookup"><span data-stu-id="d26ce-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="d26ce-105">L'application de stratégies des dépenses permet une gestion efficace des dépenses.</span><span class="sxs-lookup"><span data-stu-id="d26ce-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="d26ce-106">Par exemple, vous pouvez définir une stratégie pour les frais d'hôtel à New York, qui stipule que la dépense par nuit ne peut pas dépasser 250 USD</span><span class="sxs-lookup"><span data-stu-id="d26ce-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="d26ce-107">Si un travailleur soumet un état de dépenses ou une demande de déplacement dans lesquels le taux de la chambre dépasse ce montant, le système notifie le</span><span class="sxs-lookup"><span data-stu-id="d26ce-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="d26ce-108">travailleur qu'il a dépassé le montant prévu par la stratégie pour ces frais.</span><span class="sxs-lookup"><span data-stu-id="d26ce-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="d26ce-109">Vous pouvez configurer le message que le travailleur recevra lorsque vous</span><span class="sxs-lookup"><span data-stu-id="d26ce-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="d26ce-110">définissez la stratégie.</span><span class="sxs-lookup"><span data-stu-id="d26ce-110">define the policy.</span></span>      
        
<span data-ttu-id="d26ce-111">Vous pouvez définir trois types de stratégies :</span><span class="sxs-lookup"><span data-stu-id="d26ce-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="d26ce-112">Avertissement – Permet au travailleur d'envoyer un état de dépenses ou une demande de voyage, mais la dépense sera marquée pour tous les approbateurs et</span><span class="sxs-lookup"><span data-stu-id="d26ce-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="d26ce-113">pour un état ultérieur.</span><span class="sxs-lookup"><span data-stu-id="d26ce-113">for later reporting.</span></span>        

- <span data-ttu-id="d26ce-114">Erreur – Nécessite que le travailleur modifie la dépense pour respecter la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage.</span><span class="sxs-lookup"><span data-stu-id="d26ce-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="d26ce-115">Justification – Nécessite que le travailleur ou un responsable entre une justification du dépassement du montant prévu par la stratégie avant d'envoyer l'état de dépenses ou la demande de voyage.</span><span class="sxs-lookup"><span data-stu-id="d26ce-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

## <a name="policy-tips"></a><span data-ttu-id="d26ce-116">Conseils de stratégie</span><span class="sxs-lookup"><span data-stu-id="d26ce-116">Policy tips</span></span>
<span data-ttu-id="d26ce-117">Voici quelques suggestions pour vous aider lors de la création de nouvelles stratégies pour la gestion des dépenses.</span><span class="sxs-lookup"><span data-stu-id="d26ce-117">Here are a few suggestions that can assist you whe creating new policies for expense management.</span></span> 
* <span data-ttu-id="d26ce-118">Les stratégies sont effectives de date et ne prennent pas effet si la stratégie est créée avec une date postérieure à la date à laquelle la dépense s'est produite.</span><span class="sxs-lookup"><span data-stu-id="d26ce-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="d26ce-119">Par exemple, si vous créez une stratégie aujourd'hui pour appliquer une dépense de repas maximale de 50 $, aucune dépense existante entrée depuis d'hier n'est vérifiée par rapport à cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="d26ce-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="d26ce-120">En créant une stratégie pour une catégorie de dépenses qui peut être détaillée, envisagez d'ajouter une condition pour le type de ligne de dépense.</span><span class="sxs-lookup"><span data-stu-id="d26ce-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="d26ce-121">Certaines stratégies pouvant nécessiter un reçu peuvent ne pas être utile pour les lignes détaillées et doivent être uniquement appliquées à l'en-tête de ligne ou une ligne non détaillée.</span><span class="sxs-lookup"><span data-stu-id="d26ce-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 

## <a name="when-to-evaluate-policies"></a><span data-ttu-id="d26ce-122">Quand évaluer des stratégies</span><span class="sxs-lookup"><span data-stu-id="d26ce-122">When to evaluate policies</span></span>

<span data-ttu-id="d26ce-123">Dans les paramètres de gestion des dépenses, il existe une option pour évaluer les stratégies de gestion des dépenses lorsqu'une ligne est enregistrée ou lorsqu'un état de dépenses est soumis.</span><span class="sxs-lookup"><span data-stu-id="d26ce-123">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="d26ce-124">Si vous choisissez d'évaluer lorsqu'une ligne est enregistrée cela garantit que les utilisateurs ont une visibilité antérieure de ce qu'ils doivent effectuer pour renseigner leur état de dépenses en une seule fois.</span><span class="sxs-lookup"><span data-stu-id="d26ce-124">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="d26ce-125">Sinon, vous pouvez retarder l'évaluation de la stratégie et gagner du temps si vous effectuez une validation à la fin, lors de la soumission au workflow.</span><span class="sxs-lookup"><span data-stu-id="d26ce-125">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
