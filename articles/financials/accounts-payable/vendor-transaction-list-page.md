---
title: Page Liste des transactions fournisseur
description: Cette rubrique fournit des informations sur la page Liste des transactions fournisseur pour Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: fr-fr
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a><span data-ttu-id="7c031-103">Page Liste des transactions fournisseur</span><span class="sxs-lookup"><span data-stu-id="7c031-103">Vendor transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="7c031-104">Afficher les règlements</span><span class="sxs-lookup"><span data-stu-id="7c031-104">View settlements</span></span>

<span data-ttu-id="7c031-105">L'onglet **Afficher les règlements** du volet Actions permet d'accéder rapidement à l'historique des règlements et à d'autres informations sur l'ensemble de la transaction de règlement.</span><span class="sxs-lookup"><span data-stu-id="7c031-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="7c031-106">Vous pouvez également afficher des transactions supplémentaires associées à la transaction sélectionnée, soit parce qu'elles faisaient partie du même règlement, soit parce qu'il s'agit de paiements créés dans le même journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="7c031-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="7c031-107">Sélectionnez **Comptabilité fournisseur \> Tous les fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="7c031-107">Select **Accounts payable \> All vendors**.</span></span>
2. <span data-ttu-id="7c031-108">Sélectionnez un fournisseur avec des transactions, puis sélectionnez **Fournisseur \> Transactions**.</span><span class="sxs-lookup"><span data-stu-id="7c031-108">Select a vendor that has transactions, and then select **Vendor \> Transactions**.</span></span>
3. <span data-ttu-id="7c031-109">Sélectionnez une transaction à rechercher.</span><span class="sxs-lookup"><span data-stu-id="7c031-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="7c031-110">Sélectionnez l'onglet **Afficher les règlements** dans le volet Actions.</span><span class="sxs-lookup"><span data-stu-id="7c031-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="7c031-111">La boîte de dialogue **Afficher les règlements** s'ouvre et affiche la transaction sélectionnée et tous les documents réglés qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="7c031-111">The **View settlements** dialog box opens and shows the selected transaction and all documents that are settled against it.</span></span> <span data-ttu-id="7c031-112">Cette boîte de dialogue ressemble à la vue de l'historique des règlements, mais elle comprend tous les documents associés.</span><span class="sxs-lookup"><span data-stu-id="7c031-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span>

5. <span data-ttu-id="7c031-113">Vous pouvez effectuer plusieurs tâches dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7c031-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="7c031-114">Sélectionnez un ou plusieurs N° documents, puis sélectionnez l'un des menus suivants :</span><span class="sxs-lookup"><span data-stu-id="7c031-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="7c031-115">**Afficher la comptabilité** – Tous les N° documents associés aux documents sélectionnés s'affichent.</span><span class="sxs-lookup"><span data-stu-id="7c031-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="7c031-116">Sélectionnez **Fermer** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7c031-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="7c031-117">**Exporter** – Exportez les N° documents sélectionnés vers Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="7c031-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="7c031-118">**Afficher les paiements associés** – Toutes les transactions du journal des paiements qui ont été créées dans le journal des paiements associé au document sélectionné s'affichent.</span><span class="sxs-lookup"><span data-stu-id="7c031-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="7c031-119">En outre, tous les règlements associés à ces paiements s'affichent.</span><span class="sxs-lookup"><span data-stu-id="7c031-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="7c031-120">L'intitulé de ce menu est également remplacé par **Afficher les règlements**.</span><span class="sxs-lookup"><span data-stu-id="7c031-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="7c031-121">Sélectionnez **Afficher les règlements** pour afficher uniquement les transactions disponibles lorsque vous avez ouvert pour la première fois la boîte de dialogue **Afficher les règlements**.</span><span class="sxs-lookup"><span data-stu-id="7c031-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="7c031-122">**Régler les transactions** – Ce menu apparaît si le document initial sélectionné n'était pas totalement réglé.</span><span class="sxs-lookup"><span data-stu-id="7c031-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="7c031-123">Lorsque vous le sélectionnez, la boîte de dialogue **Afficher les règlements** s'ouvre pour vous permettre de sélectionner des transactions à régler.</span><span class="sxs-lookup"><span data-stu-id="7c031-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="7c031-124">**Annuler les règlements** – Ce menu apparaît si le document initial sélectionné était totalement réglé.</span><span class="sxs-lookup"><span data-stu-id="7c031-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="7c031-125">Lorsque vous le sélectionnez, la boîte de dialogue **Annuler les règlements** s'affiche pour vous permettre d'annuler les règlements effectués pour ce document.</span><span class="sxs-lookup"><span data-stu-id="7c031-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>

