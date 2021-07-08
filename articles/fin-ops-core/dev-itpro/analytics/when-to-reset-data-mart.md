---
title: FAQ sur les réinitialisations du mini-data warehouse
description: Cette rubrique fournit des réponses à quelques-unes des questions fréquemment posées sur les réinitialisations du mini-data warehouse.
author: jinniew
ms.date: 06/09/2021
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
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266607"
---
# <a name="data-mart-resets-faq"></a><span data-ttu-id="e2e85-103">FAQ sur les réinitialisations du mini-data warehouse</span><span class="sxs-lookup"><span data-stu-id="e2e85-103">Data mart resets FAQ</span></span>

<span data-ttu-id="e2e85-104">Cette rubrique fournit des réponses à quelques-unes des questions fréquemment posées sur les réinitialisations du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="e2e85-104">This topic provides answers to some frequently asked questions about data mart resets.</span></span> <span data-ttu-id="e2e85-105">Une réinitialisation du mini-data warehouse peut être un processus chronophage et, selon les circonstances, peut ne pas être la solution requise.</span><span class="sxs-lookup"><span data-stu-id="e2e85-105">A reset of the data mart can be a time-consuming process and, depending on the circumstances, might not be the solution that is required.</span></span> <span data-ttu-id="e2e85-106">Par conséquent, cette rubrique inclut des informations sur les circonstances dans lesquelles une réinitialisation du mini-data warehouse peut être utile, ainsi que sur les circonstances dans lesquelles il est peu probable qu’elle soit utile.</span><span class="sxs-lookup"><span data-stu-id="e2e85-106">Therefore, this topic includes information about circumstances where a data mart reset might help and also circumstances where it's unlikely to help.</span></span>

## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="e2e85-107">Qu’est-ce que la réinitialisation d’un mini-data warehouse ?</span><span class="sxs-lookup"><span data-stu-id="e2e85-107">What is a data mart reset?</span></span>

<span data-ttu-id="e2e85-108">Une réinitialisation du mini-data warehouse désactivera les tâches d’intégration, supprimera toutes les données du mini-data warehouse, puis réactivera l’intégration.</span><span class="sxs-lookup"><span data-stu-id="e2e85-108">A data mart reset will disable the integration tasks, delete all the data mart data, and then re-enable integration.</span></span>

<span data-ttu-id="e2e85-109">Pour garantir que de anciennes données ne sont pas insérées, une réinitialisation du mini-data warehouse ne peut être démarrée qu’une fois les tâches existantes terminées.</span><span class="sxs-lookup"><span data-stu-id="e2e85-109">To ensure that old data isn't inserted, a data mart reset can be started only after existing tasks are completed.</span></span> <span data-ttu-id="e2e85-110">Si vous essayez de réinitialiser le mini-data warehouse avant que toutes les tâches ne soient terminées, vous pouvez recevoir un message tel que « La réinitialisation du mini-data warehouse n’a pas pu être traitée en raison d’une tâche active.</span><span class="sxs-lookup"><span data-stu-id="e2e85-110">If you try to reset the data mart before all tasks are completed, you might receive a message such as, "The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="e2e85-111">Réessayez ultérieurement. »</span><span class="sxs-lookup"><span data-stu-id="e2e85-111">Please try again later."</span></span>

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a><span data-ttu-id="e2e85-112">Quand dois-je effectuer une réinitialisation d’un mini-data warehouse ?</span><span class="sxs-lookup"><span data-stu-id="e2e85-112">When do I have to do a data mart reset?</span></span>

<span data-ttu-id="e2e85-113">Si une ou plusieurs des affirmations suivantes s’appliquent à votre situation, votre organisation peut bénéficier d’une réinitialisation du mini-data warehouse :</span><span class="sxs-lookup"><span data-stu-id="e2e85-113">If one or more of the following statements apply to your situation, your organization can benefit from a data mart reset:</span></span>

- <span data-ttu-id="e2e85-114">La base de données de l’application a été restaurée.</span><span class="sxs-lookup"><span data-stu-id="e2e85-114">The application database was restored.</span></span>
- <span data-ttu-id="e2e85-115">Vous avez ouvert un ticket de support et un ingénieur du support vous a demandé de réinitialiser le mini-data warehouse dans le cadre d’une étape de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="e2e85-115">You opened a support ticket, and a Support engineer instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a><span data-ttu-id="e2e85-116">Quand la réinitialisation d’un mini-data warehouse est-elle inappropriée ?</span><span class="sxs-lookup"><span data-stu-id="e2e85-116">When is a data mart reset inappropriate?</span></span>

<span data-ttu-id="e2e85-117">Voici certaines des circonstances dans lesquelles il est déconseillé de réinitialiser un mini-data warehouse :</span><span class="sxs-lookup"><span data-stu-id="e2e85-117">Here are some of the circumstances where we don't recommend that you reset the data mart:</span></span>

- <span data-ttu-id="e2e85-118">Vous rencontrez des problèmes de performances associés à une synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="e2e85-118">You're experiencing performance issues that are associated with data synchronization.</span></span>
- <span data-ttu-id="e2e85-119">Vous rencontrez un schéma de réinitialisation récurrent pour l’une des raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="e2e85-119">You have a recurring reset pattern for any of the following reasons:</span></span>

    - <span data-ttu-id="e2e85-120">**Données manquantes** : si vous remarquez que des données sont manquantes, ouvrez un ticket de support auprès de Microsoft pour examiner le format de l’état et les éventuels problèmes de synchronisation des données.</span><span class="sxs-lookup"><span data-stu-id="e2e85-120">**Missing data** – If you notice that data is missing, open a support ticket with Microsoft to review your report format and possible data synchronization issues.</span></span>
    - <span data-ttu-id="e2e85-121">**État d’intégration bloqué**</span><span class="sxs-lookup"><span data-stu-id="e2e85-121">**Stuck integration state**</span></span>
    - <span data-ttu-id="e2e85-122">**Enregistrements périmés** : les enregistrements périmés ne justifient pas nécessairement une réinitialisation du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="e2e85-122">**Stale records** – Stale records by themselves don't necessarily justify a data mart reset.</span></span> <span data-ttu-id="e2e85-123">Si vous disposez d’un ensemble de données volumineux, le processus de réinitialisation mettra du temps à s’exécuter, mais il est peu probable qu’il conduise à une amélioration.</span><span class="sxs-lookup"><span data-stu-id="e2e85-123">If you have a large data set, the reset process will take some time to run but is unlikely to lead to any improvement.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="e2e85-124">Si je réinitialise le mini-data warehouse, vais-je perdre les états que j’ai déjà conçus ?</span><span class="sxs-lookup"><span data-stu-id="e2e85-124">If I reset the data mart, will I lose reports that I've already designed?</span></span>

<span data-ttu-id="e2e85-125">Non.</span><span class="sxs-lookup"><span data-stu-id="e2e85-125">No.</span></span> <span data-ttu-id="e2e85-126">Vos états sont stockés dans des tables SQL qui ne sont pas affectées par une réinitialisation du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="e2e85-126">Your reports are stored in SQL tables that aren't affected by a data mart reset.</span></span> <span data-ttu-id="e2e85-127">Si vous craignez de perdre des états que vous avez conçus, vous pouvez sauvegarder les conceptions que vous ne voulez pas perdre.</span><span class="sxs-lookup"><span data-stu-id="e2e85-127">If you're concerned about losing reports that you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="e2e85-128">Pour sauvegarder les conceptions, ouvrez Report Designer et accédez à **Entreprise \> Entreprises \> Blocs élémentaires \> Exporter**.</span><span class="sxs-lookup"><span data-stu-id="e2e85-128">To back up designs, open Report Designer, and go to **Company \> Companies \> Building Blocks \> Export**.</span></span>
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a><span data-ttu-id="e2e85-129">Tous les utilisateurs doivent-ils quitter le système avant que je puisse réinitialiser le mini-data warehouse ?</span><span class="sxs-lookup"><span data-stu-id="e2e85-129">Do all users have to exit the system before I can reset the data mart?</span></span>

<span data-ttu-id="e2e85-130">Non.</span><span class="sxs-lookup"><span data-stu-id="e2e85-130">No.</span></span> <span data-ttu-id="e2e85-131">Les utilisateurs peuvent continuer à travailler dans le système pendant la réinitialisation du mini-data warehouse.</span><span class="sxs-lookup"><span data-stu-id="e2e85-131">Users can continue to work in the system during a data mart reset.</span></span> <span data-ttu-id="e2e85-132">Cependant, ils ne pourront pas accéder aux états créés avec Financial Reporter tant que la réinitialisation ne sera pas terminée.</span><span class="sxs-lookup"><span data-stu-id="e2e85-132">However, until the reset is completed, users won't be able to access any reports that were created by using Financial Reporter.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
