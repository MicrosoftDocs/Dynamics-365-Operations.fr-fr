---
title: "Valider avec des registres dérivés"
description: "Cet article décrit l'utilisation des registres déduits."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 94eb82936da2a51a25105b26723088fb7dee9ae5
ms.contentlocale: fr-fr
ms.lasthandoff: 11/03/2017

---

# <a name="post-with-derived-books"></a><span data-ttu-id="51742-103">Valider avec des registres dérivés</span><span class="sxs-lookup"><span data-stu-id="51742-103">Post with derived books</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="51742-104">Cet article décrit l'utilisation des registres déduits.</span><span class="sxs-lookup"><span data-stu-id="51742-104">This article describes how to use derived books.</span></span>

<span data-ttu-id="51742-105">Si vous validez des transactions pour un registre contenant des registres déduits, les transactions de registres déduits sont validées automatiquement dans les journaux, les commandes fournisseur ou les factures financières.</span><span class="sxs-lookup"><span data-stu-id="51742-105">When you post transactions for a book that contains derived books, the derived book transactions are posted automatically in journals, purchase orders, or free text invoices.</span></span> <span data-ttu-id="51742-106">Toutefois, si vous préparez les transactions de registre principales dans le journal des immobilisations, vous pouvez afficher et modifier les montants des transactions dérivées avant de les valider.</span><span class="sxs-lookup"><span data-stu-id="51742-106">However, if you prepare the primary book transactions in the Fixed assets journal, you can view and modify the amounts of the derived transactions before you post them.</span></span>
-   <span data-ttu-id="51742-107">Certains comptes (de taxe, client ou fournisseur) ne sont mis à jour qu'une seule fois par les validations du registre principal.</span><span class="sxs-lookup"><span data-stu-id="51742-107">Certain accounts, such as sales tax and customer or vendor accounts, are updated only once by postings of the primary book.</span></span> <span data-ttu-id="51742-108">Les transactions du registre déduit sont validées dans les comptes définis pour le registre déduit dans la page Profils de validation d'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="51742-108">The derived book transactions are posted to the accounts that have been defined for the derived book in the Fixed asset posting profiles page.</span></span>
-   <span data-ttu-id="51742-109">L'acquisition est souvent utilisée comme type de transaction pour le registre déduit.</span><span class="sxs-lookup"><span data-stu-id="51742-109">Acquisition is often used as the transaction type for the derived books.</span></span> <span data-ttu-id="51742-110">Utilisez-le lorsque le registre et le registre des déduit doivent être appliqués à l'immobilisation à partir du moment de l'acquisition de l'immobilisation.</span><span class="sxs-lookup"><span data-stu-id="51742-110">You use this when the book and the derived book should be applied to the fixed asset from the time of the acquisition of the fixed asset.</span></span>
-   <span data-ttu-id="51742-111">D'autres valeurs de type de transaction peuvent également s'appliquer.</span><span class="sxs-lookup"><span data-stu-id="51742-111">Other values for the transaction type can also apply.</span></span> <span data-ttu-id="51742-112">Par exemple, si le registre principal et les registres déduits ont les mêmes intervalles concernant la vente ou la cession, tous les types de transactions d'immobilisation sont disponibles pour le paramétrage d'un registre déduit.</span><span class="sxs-lookup"><span data-stu-id="51742-112">For example, if the primary book and the derived books have the same intervals regarding sale or disposal, all fixed asset transaction types are available for the setup of a derived book.</span></span>

> [!WARNING]
> <span data-ttu-id="51742-113">Un amortissement validé dans le registre déduit sera du même montant que celui validé pour le registre principal.</span><span class="sxs-lookup"><span data-stu-id="51742-113">Depreciation posted in the derived book will be the same amount as was posted for the primary book.</span></span> <span data-ttu-id="51742-114">Si les méthodes d'amortissement des registres diffèrent, vous ne devez pas générer de transactions d'amortissement à l'aide du processus déduit.</span><span class="sxs-lookup"><span data-stu-id="51742-114">If the depreciation methods are different between the books, you should not generate depreciation transactions using the derived process.</span></span> |

## <a name="example"></a><span data-ttu-id="51742-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="51742-115">Example</span></span> 
<span data-ttu-id="51742-116">Les informations suivantes décrivent le paramétrage des transactions d'acquisition avec la fonctionnalité de registre déduit.</span><span class="sxs-lookup"><span data-stu-id="51742-116">The following information describes how to set up acquisition transactions with the derived book functionality.</span></span>

1.  <span data-ttu-id="51742-117">Créez des registres dans la page Registres.</span><span class="sxs-lookup"><span data-stu-id="51742-117">Create the books on the Books page.</span></span>
    -   <span data-ttu-id="51742-118">Registre pour la comptabilité : MV 1, couche de validation actuelle</span><span class="sxs-lookup"><span data-stu-id="51742-118">The book for accounting: VM 1, Current posting layer</span></span>
    -   <span data-ttu-id="51742-119">Registre pour les taxes : MV 2, couche de validation des taxes</span><span class="sxs-lookup"><span data-stu-id="51742-119">The book for tax purposes: VM 2, Tax posting layer</span></span>

2.  <span data-ttu-id="51742-120">Sous MV 1, cliquez sur l'onglet Registres dérivés. Sélectionnez MV 2 dans le champ Registre et Acquisition dans le champ Type de transaction.</span><span class="sxs-lookup"><span data-stu-id="51742-120">On VM 1, click the Derived books tab. Select VM 2 in the Book field, and Acquisition in the Transaction type field.</span></span>

<span data-ttu-id="51742-121">Les registres peuvent alors être associés à des immobilisations spécifiques.</span><span class="sxs-lookup"><span data-stu-id="51742-121">The books then can be attached to specific fixed assets.</span></span> 

<span data-ttu-id="51742-122">Si une acquisition est validée pour une immobilisation avec le registre MV 1, elle est validée non seulement dans MV 1, mais également dans le registre dérivé MV 2.</span><span class="sxs-lookup"><span data-stu-id="51742-122">When an acquisition is posted for a fixed asset with book VM 1, the acquisition is posted not only on VM 1, but also on the derived book VM 2.</span></span> <span data-ttu-id="51742-123">Le statut des deux registres d'immobilisation est mis à jour sur Ouvert.</span><span class="sxs-lookup"><span data-stu-id="51742-123">The status of both fixed asset books is updated to Open.</span></span>

> [!NOTE]                                                                                                         
> <span data-ttu-id="51742-124">Si vous n'utilisez pas de registre déduit, vous devez valider l'acquisition de l'immobilisation tant pour le registre MV 1 que pour le registre MV 2.</span><span class="sxs-lookup"><span data-stu-id="51742-124">If you do not use derived books, you must post the acquisition of the fixed asset both for book VM 1 and book VM 2.</span></span>

<span data-ttu-id="51742-125">Pour plus d'informations, voir [Registres dérivés](derived-books.md).</span><span class="sxs-lookup"><span data-stu-id="51742-125">For more information, see [Derived books](derived-books.md)</span></span>




