---
title: Afficher les résultats de l’automatisation des factures fournisseur (version préliminaire)
description: Cette rubrique explique comment afficher le statut des factures fournisseur qui sont dans le processus automatisé de soumission au flux de travail.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3b87af4c64f8021a1b23cca5d8f38ac21c8efbd4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248086"
---
# <a name="view-vendor-invoice-automation-results"></a><span data-ttu-id="fb4dc-103">Afficher les résultats de l’automatisation des factures fournisseur</span><span class="sxs-lookup"><span data-stu-id="fb4dc-103">View vendor invoice automation results</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fb4dc-104">Cette rubrique explique comment afficher le statut des factures fournisseur qui sont dans le processus automatisé de soumission au flux de travail.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-104">This topic explains how to view the status of vendor invoices that are in the automated submit-to-workflow process.</span></span> <span data-ttu-id="fb4dc-105">Les détails de l’historique de l’automatisation sont conservés pour chaque facture fournisseur importée.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-105">Details of the automation history are maintained for each imported vendor invoice.</span></span> <span data-ttu-id="fb4dc-106">En fonction des processus métier que vous avez automatisés, la page **Factures fournisseur en attente** affiche les valeurs **Statut de la mise en correspondance automatique des réceptions** et **Statut de la soumission automatisée au workflow**.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-106">Depending on the business processes that you've automated, the **Pending vendor invoices** page shows **Automated receipt match status** and **Automated submit to workflow status** values.</span></span> <span data-ttu-id="fb4dc-107">Vous pouvez afficher les détails et dresser un plan pour vous concentrer sur les factures qui ont échoué à une étape automatisée.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-107">You can view the details and make a plan to focus on the invoices that failed an automated step.</span></span> <span data-ttu-id="fb4dc-108">Ensuite, après avoir corrigé le problème, vous pouvez reprendre le processus automatisé pour la facture importée.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-108">Then, after you correct the issue, you can resume the automated process for the imported invoice.</span></span>

<span data-ttu-id="fb4dc-109">Avant de pouvoir modifier une facture qui a été soumise, vous devez suspendre le traitement automatisé.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-109">Before you can edit an invoice that has been submitted, you must pause the automated processing.</span></span> <span data-ttu-id="fb4dc-110">Si une facture dans le processus automatisé de soumission au workflow doit être suspendue, définissez le champ **Inclure dans le traitement automatisé** sur **Non** dans la page **Factures fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-110">If an invoice in the automated submit-to-workflow process must be paused, set the **Include in Automated processing** field to **No** on the **Vendor invoices** page.</span></span> <span data-ttu-id="fb4dc-111">L’automatisation ne fonctionnera pas tant que l’option **Inclure dans le traitement automatisé** ne sera pas définie sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-111">Automation then won't run until **Include in Automated processing** is set to **Yes**.</span></span> <span data-ttu-id="fb4dc-112">Une facture peut être suspendue de toute automatisation ultérieure si elle n’est pas encore dans le système de workflow et n’est pas utilisée par le processus automatisé.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-112">An invoice can be paused from further automation if it isn't yet in the workflow system and isn't used by the automated process.</span></span>

<span data-ttu-id="fb4dc-113">Si une facture importée est soumise au processus de soumission au workflow, vous pouvez afficher la valeur de son **Statut d’automatisation** dans la page **Factures fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-113">If an imported invoice is subject to the submit-to-workflow process, you can view its **Automation status** value on the **Vendor invoices** page.</span></span> <span data-ttu-id="fb4dc-114">Les statuts suivants sont suivis :</span><span class="sxs-lookup"><span data-stu-id="fb4dc-114">The following statuses are tracked:</span></span>

- <span data-ttu-id="fb4dc-115">**Inclus** - Les processus automatisés définis dans la page **Paramètres de la comptabilité fournisseur** fonctionnent correctement mais ne sont pas encore terminés.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-115">**Included** – The automated processes that are defined on the **Accounts payable parameters** page are running correctly but haven't yet been completed.</span></span>
- <span data-ttu-id="fb4dc-116">**Suspendu** - Les processus automatisés définis dans la page **Paramètres de la comptabilité fournisseur** ont été exécutées, mais au moins une étape du processus a échoué.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-116">**Paused** – The automated processes that are defined on the **Accounts payable parameters** page have run, but at least one step in the process failed.</span></span> <span data-ttu-id="fb4dc-117">Le statut **Suspendu** est également appliqué si le champ **Inclure dans le traitement automatisé** est défini sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-117">The **Paused** status is also applied if the **Include in automated processing** field is set to **No**.</span></span> <span data-ttu-id="fb4dc-118">Vous pouvez afficher les défaillances en sélectionnant le bouton **Afficher les résultats les plus récents**.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-118">You can view the failures by selecting **View most recent results**.</span></span>
- <span data-ttu-id="fb4dc-119">**Dans le workflow** - La facture importée a été soumise au système de workflow, soit par le processus de flux de travail automatisé, soit manuellement.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-119">**In workflow** – The imported invoice has been submitted to the workflow system, either by the automated submit-to-workflow process or manually.</span></span>
- <span data-ttu-id="fb4dc-120">**Workflow terminé** - Le processus de workflow est terminé pour la facture importée.</span><span class="sxs-lookup"><span data-stu-id="fb4dc-120">**Workflow complete** – The workflow process has been completed for the imported invoice.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]