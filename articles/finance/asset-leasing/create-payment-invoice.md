---
title: Créer des factures de paiement
description: Cette rubrique explique comment créer des factures de location mensuelles. Vous pouvez créer des factures pour des locations individuelles ou vous pouvez utiliser un processus par lots pour les créer pour plusieurs baux.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 303fb0e70530fdc29cb129736b01c0e0e8d02075
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969576"
---
# <a name="create-payment-invoices"></a><span data-ttu-id="5b0ad-104">Créer des factures de paiement</span><span class="sxs-lookup"><span data-stu-id="5b0ad-104">Create payment invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b0ad-105">Vous pouvez créer des factures mensuelles pour des locations individuelles ou vous pouvez utiliser un processus par lots pour les créer pour plusieurs baux.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-105">You can create monthly invoices for individual leases, or you can use a batch process to create them for multiple leases.</span></span> <span data-ttu-id="5b0ad-106">La procédure suivante montre comment créer une entrée de paiement de location individuelle lorsque le paramètre **Payer au fournisseur** sur la page **Configuration du registre de location** est activé.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-106">The following procedure shows how to create an individual lease payment entry when the **Pay to Vendor** parameter on the **Lease book setup** page is turned on.</span></span>

1. <span data-ttu-id="5b0ad-107">Sur la page **Résumé du bail**, sélectionnez un bail, puis sélectionnez **Registres \> Calendrier de paiement**.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-107">On the **Lease summary** page, select a lease, and then select **Books \> Payment schedule**.</span></span>
2. <span data-ttu-id="5b0ad-108">Sélectionnez le paiement à effectuer, puis sélectionnez **Créer un journal**.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-108">Select the payment that must be made, and then select **Create journal**.</span></span> <span data-ttu-id="5b0ad-109">Vous recevez un message indiquant qu’un journal a été créé pour le paiement sélectionné.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-109">You receive a message that states that a journal was created against the selected payment.</span></span>
3. <span data-ttu-id="5b0ad-110">Sélectionnez **Journaux de facturation**, puis sélectionnez la facture à payer.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-110">Select **Invoice journals**, and then select the invoice that must be paid.</span></span>
4. <span data-ttu-id="5b0ad-111">Sur l’onglet **Lignes**, vérifiez l’écriture de journal avant de la valider dans la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-111">On the **Lines** tab, review the journal entry before you post it to the general ledger.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b0ad-112">Par défaut, les lignes de facture fournisseur qui sont créées utilisent le profil de validation fournisseur de la page **Paramètres de la comptabilité fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-112">By default, the vendor invoice lines that are created use the vendor posting profile from the **Accounts payable parameters** page.</span></span>

5. <span data-ttu-id="5b0ad-113">Sélectionnez le journal adéquat, puis sélectionnez la facture à payer.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-113">Select the correct journal, and then select the invoice that must be paid.</span></span>

    <span data-ttu-id="5b0ad-114">Pour cet exemple, le paramètre **Payer au fournisseur** du registre de location est activé.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-114">For this example, the **Pay to Vendor** parameter on the lease book is turned on.</span></span> <span data-ttu-id="5b0ad-115">Par conséquent, la facture sera dans le journal des factures.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-115">Therefore, the invoice will be in the invoice journal.</span></span> <span data-ttu-id="5b0ad-116">La section **Aperçu** présente un résumé de l’entrée de journal et la section **Lignes** montre les détails des lignes de journal réelles.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-116">The **Overview** section shows a summary of the journal entry, and the **Lines** section shows details of the actual journal lines.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b0ad-117">Si le paramètre **Payer au fournisseur** est désactivé, les écritures du journal des paiements seront répertoriées sur la page **Location d’actifs** pour le registre de location, et le système créera une entrée de bail d’actif au lieu d’une facture.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-117">If the **Pay to Vendor** parameter is turned off, payment journal entries will be listed on the **Asset leasing** page for the lease book, and the system will create an asset leasing entry instead of an invoice.</span></span> <span data-ttu-id="5b0ad-118">L’entrée de paiement de location sera enregistrée dans le nom de journal spécifié dans le champ **Journal mensuel des baux**.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-118">The lease payment entry will be posted to the journal name that is specified in the **Monthly lease journal** field.</span></span>

6. <span data-ttu-id="5b0ad-119">Une fois la transaction enregistrée, vous pouvez afficher les informations de transaction et la valeur comptable du passif de location en sélectionnant **Transactions de passif** dans le registre de location.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-119">After the transaction is posted, you can view the transaction information and the carrying value of the lease liability by selecting **Liability transactions** in the lease book.</span></span>

    <span data-ttu-id="5b0ad-120">Dans l’échéancier de paiement, la case **Journal publié** sera cochée et la ligne affichera le numéro du journal de la facture.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-120">In the payment schedule, the **Journal posted** check box will be selected, and the line will show the invoice journal number.</span></span> <span data-ttu-id="5b0ad-121">Après avoir créé un journal des paiements et une écriture pour ce journal, vous devez contrepasser l’écriture avant de pouvoir la recréer.</span><span class="sxs-lookup"><span data-stu-id="5b0ad-121">After a payment journal and an entry for that journal have been created, you must reverse the entry before it can be re-created.</span></span>
