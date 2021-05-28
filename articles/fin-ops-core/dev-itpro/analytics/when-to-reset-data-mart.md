---
title: Quand réinitialiser un mini-Data Warehouse
description: Cette rubrique répertorie les circonstances qui peuvent être améliorées en réinitialisant un mini-Data Warehouse et les circonstances dans lesquelles la réinitialisation de votre mini-Data Warehouse n’est probablement pas utile.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988990"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="21301-103">Quand réinitialiser un mini-Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="21301-103">When to reset a data mart</span></span>

<span data-ttu-id="21301-104">La réinitialisation d’un mini-Data Warehouse peut prendre beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="21301-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="21301-105">Selon les circonstances, cette action peut ne pas être la solution nécessaire.</span><span class="sxs-lookup"><span data-stu-id="21301-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="21301-106">Cette rubrique répertorie les circonstances qui peuven être améliorées en réinitialisant un mini-Data Warehouse, ainsi que les circonstances dans lesquelles la réinitialisation de votre mini-Data Warehouse n’est probablement pas utile.</span><span class="sxs-lookup"><span data-stu-id="21301-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a><span data-ttu-id="21301-107">Quand dois-je effectuer une réinitialisation d’un mini-Data Warehouse ?</span><span class="sxs-lookup"><span data-stu-id="21301-107">When do I need to do a data mart reset?</span></span>
<span data-ttu-id="21301-108">Tenez compte des questions suivantes avant de réinitialiser un mini-Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="21301-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="21301-109">Une réponse affirmative à une ou plusieurs questions peut indiquer que votre organisation peut bénéficier de la réinitialisation du mini-Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="21301-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="21301-110">La base de données de l'application a-t-elle été restaurée ?</span><span class="sxs-lookup"><span data-stu-id="21301-110">Was the application database restored?</span></span>
- <span data-ttu-id="21301-111">Si vous avez ouvert un incident de support et qu'un ingénieur du support vous a demandé de réinitialiser le mini-data warehouse dans le cadre d’une étape de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="21301-111">If you've opened a support incident that and a support engineer has instructed you to reset the data mart as part of a troubleshooting step?</span></span>
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="21301-112">Quand n’est-il pas approprié de réinitialiser un mini-data warehouse ?</span><span class="sxs-lookup"><span data-stu-id="21301-112">When is it not appropriate to reset a data mart?</span></span>
<span data-ttu-id="21301-113">Il est déconseillé de réinitialiser un mini-data warehouse dans certains circonstances.</span><span class="sxs-lookup"><span data-stu-id="21301-113">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="21301-114">En voici quelques exemples.</span><span class="sxs-lookup"><span data-stu-id="21301-114">These include the following.</span></span> 

- <span data-ttu-id="21301-115">Vous rencontrez des problèmes de performances associés à une synchronisation de données.</span><span class="sxs-lookup"><span data-stu-id="21301-115">You're experiencing performance issues that are associated with a data sync.</span></span> 
- <span data-ttu-id="21301-116">Si vous avez un modèle de réinitialisation récurrent pour l’une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="21301-116">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="21301-117">**Données manquantes**</span><span class="sxs-lookup"><span data-stu-id="21301-117">**Missing data**</span></span> 
  - <span data-ttu-id="21301-118">**État d'intégration bloqué**</span><span class="sxs-lookup"><span data-stu-id="21301-118">**Stuck integration state**</span></span> 
  - <span data-ttu-id="21301-119">**Enregistrements périmés** : les enregistrements périmés ne justifient pas nécessairement la réinitialisation du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="21301-119">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="21301-120">Si vous disposez d’un ensemble de données volumineux, le processus de réinitialisation mettra du temps à s’exécuter, mais il est peu probable qu’il se traduise par une amélioration.</span><span class="sxs-lookup"><span data-stu-id="21301-120">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="21301-121">Qu'est-ce que la réinitialisation d'un mini-data warehouse ?</span><span class="sxs-lookup"><span data-stu-id="21301-121">What is a data mart reset?</span></span>
- <span data-ttu-id="21301-122">Une réinitialisation ne démarre que lorsque les tâches existantes sont terminées.</span><span class="sxs-lookup"><span data-stu-id="21301-122">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="21301-123">Cela garantit que les anciennes données ne sont pas insérées.</span><span class="sxs-lookup"><span data-stu-id="21301-123">This ensures that old data is not inserted.</span></span> <span data-ttu-id="21301-124">À ce stade, vous pouvez voir un message tel que « La réinitialisation du mini-data warehouse n’a pas pu être traitée en raison d’une tâche active.</span><span class="sxs-lookup"><span data-stu-id="21301-124">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="21301-125">Réessayez ultérieurement. »</span><span class="sxs-lookup"><span data-stu-id="21301-125">Please try again later.”</span></span>
- <span data-ttu-id="21301-126">La réinitialisation désactivera les tâches d’intégration et supprimera toutes les données du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="21301-126">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="21301-127">L’intégration est réactivée.</span><span class="sxs-lookup"><span data-stu-id="21301-127">The integration is re-enabled.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="21301-128">Si je réinitialise le mini-data warehouse, vais-je perdre les rapports que j'ai déjà conçus ?</span><span class="sxs-lookup"><span data-stu-id="21301-128">If I reset the data mart, will I lose reports that I've already designed?</span></span> 
<span data-ttu-id="21301-129">Non, vos rapports sont stockés dans des tables SQL qui ne sont pas affectées par une réinitialisation du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="21301-129">No, your reports are stored in SQL tables that are not impacted by a reset of the data mart.</span></span> <span data-ttu-id="21301-130">Si vous craignez de perdre des rapports que vous avez conçus, vous pouvez sauvegarder les conceptions que vous ne voulez pas perdre.</span><span class="sxs-lookup"><span data-stu-id="21301-130">If you are concerned about losing any reports you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="21301-131">Pour les sauvegarder, ouvrez le Concepteur de rapports et accédez à **Entreprise > Entreprises> Blocs élémentaires > Exporter**.</span><span class="sxs-lookup"><span data-stu-id="21301-131">To back them up, open Report Designer and go to **Company > Companies > Building Blocks > Export**.</span></span>
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a><span data-ttu-id="21301-132">Est-il nécessaire que tous les utilisateurs quittent le système pour réinitialiser le mini-data warehouse ?</span><span class="sxs-lookup"><span data-stu-id="21301-132">Is it necessary for all users to exit the system to reset the data mart?</span></span>
<span data-ttu-id="21301-133">Non, les utilisateurs peuvent continuer à travailler dans le système pendant la réinitialisation du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="21301-133">No, users can continue working in the system during the data mart reset.</span></span> <span data-ttu-id="21301-134">Cependant, ils ne pourront pas accéder aux rapports créés avec Financial Reporter tant que la réinitialisation ne sera pas terminée.</span><span class="sxs-lookup"><span data-stu-id="21301-134">However, they won’t be able to access any reports that were created with Financial Reporter until the reset is finished.</span></span> 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
