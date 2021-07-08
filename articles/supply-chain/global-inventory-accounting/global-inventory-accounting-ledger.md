---
title: Registre de la comptabilité globale des stocks
description: Cette rubrique décrit les registres de la comptabilité globale des stocks, qui sont définis par la combinaison d’une devise, d’un calendrier, d’une convention et d’une association avec une entité juridique.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea3434675aa3b7f2304be93ef9b489747994fa9d
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273154"
---
# <a name="global-inventory-accounting-ledger"></a><span data-ttu-id="69adf-103">Registre de la comptabilité globale des stocks</span><span class="sxs-lookup"><span data-stu-id="69adf-103">Global Inventory Accounting ledger</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="69adf-104">La comptabilité globale des stocks possède son propre ensemble de registres.</span><span class="sxs-lookup"><span data-stu-id="69adf-104">Global Inventory Accounting has its own set of ledgers.</span></span> <span data-ttu-id="69adf-105">Chaque fois qu’une transaction liée aux stocks est traitée pour une entité juridique pertinente, le système peut comptabiliser cette transaction dans n’importe quel nombre de registres de la comptabilité globale des stocks, selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="69adf-105">Each time an inventory-related transaction is processed for a relevant legal entity, the system can account for that transaction in any number of Global Inventory Accounting ledgers, as required.</span></span>

<span data-ttu-id="69adf-106">Un registre est une archive des mesures de débit et de crédit.</span><span class="sxs-lookup"><span data-stu-id="69adf-106">A ledger is a register of debit and credit measures.</span></span> <span data-ttu-id="69adf-107">Ces mesures sont classées en utilisant des éléments de coût et des comptes auxiliaires.</span><span class="sxs-lookup"><span data-stu-id="69adf-107">These measures are classified by using cost elements and subledger accounts.</span></span> <span data-ttu-id="69adf-108">Un registre de la comptabilité globale des stocks est défini par la combinaison d’une devise, d’un calendrier, d’une convention et d’une association avec une entité juridique.</span><span class="sxs-lookup"><span data-stu-id="69adf-108">A Global Inventory Accounting ledger is defined by its combination of a currency, a calendar, a convention, and an association with a legal entity.</span></span>

<span data-ttu-id="69adf-109">Pour configurer vos registres de comptabilité globale des stocks, accédez à **Comptabilité globale des stocks \> Paramétrage \> Registres de la comptabilité globale des stocks**.</span><span class="sxs-lookup"><span data-stu-id="69adf-109">To set up your Global Inventory Accounting ledgers, go to **Global inventory accounting \> Setup \> Global inventory accounting ledgers**.</span></span> <span data-ttu-id="69adf-110">Pour chaque registre, définissez les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="69adf-110">For each ledger, set the following fields:</span></span>

- <span data-ttu-id="69adf-111">**Nom** : saisissez le nom du registre.</span><span class="sxs-lookup"><span data-stu-id="69adf-111">**Name** – Enter the name of the ledger.</span></span>
- <span data-ttu-id="69adf-112">**Description** : entrez une description du registre.</span><span class="sxs-lookup"><span data-stu-id="69adf-112">**Description** – Enter a description of the ledger.</span></span>
- <span data-ttu-id="69adf-113">**Calendrier fiscal** : précisez le calendrier fiscal du registre.</span><span class="sxs-lookup"><span data-stu-id="69adf-113">**Fiscal calendar** – Specify the fiscal calendar for the ledger.</span></span>
- <span data-ttu-id="69adf-114">**Devise et type de taux de change** : utilisez les champs de ce raccourci pour sélectionner la devise comptable utilisée par le registre et le type de taux de change.</span><span class="sxs-lookup"><span data-stu-id="69adf-114">**Currency and exchange rate type** – Use the fields on this FastTab to select the accounting currency that the ledger uses, and the exchange rate type.</span></span> <span data-ttu-id="69adf-115">La devise que vous sélectionnez peut différer de la devise utilisée par l’entité juridique.</span><span class="sxs-lookup"><span data-stu-id="69adf-115">The currency that you select can differ from the currency that the legal entity uses.</span></span> <span data-ttu-id="69adf-116">Dans la comptabilité globale des stocks, les utilisateurs peuvent définir autant de registres de coûts qu’ils le souhaitent.</span><span class="sxs-lookup"><span data-stu-id="69adf-116">In Global Inventory Accounting, users can define as many costing ledgers as they require.</span></span> <span data-ttu-id="69adf-117">La comptabilité globale des stocks prend en charge la comptabilité des stocks dans plusieurs devises et dans plusieurs estimations de valeur.</span><span class="sxs-lookup"><span data-stu-id="69adf-117">Global Inventory Accounting supports inventory accounting in multiple currencies and in multiple valuations.</span></span> <span data-ttu-id="69adf-118">Définisse les champs suivants :</span><span class="sxs-lookup"><span data-stu-id="69adf-118">Set the following fields:</span></span>

    - <span data-ttu-id="69adf-119">**Devise** : sélectionnez la devise d’évaluation des coûts dans laquelle les valeurs liées aux stocks sont gérées.</span><span class="sxs-lookup"><span data-stu-id="69adf-119">**Currency** – Select the costing currency that inventory-related values are maintained in.</span></span> <span data-ttu-id="69adf-120">Ces valeurs comprennent la valeur d’inventaire, le coût des marchandises vendues, les stocks en transit et toutes sortes d’écarts.</span><span class="sxs-lookup"><span data-stu-id="69adf-120">These values include the inventory value, cost of goods sold, inventory in transit, and all kinds of variance.</span></span>
    - <span data-ttu-id="69adf-121">**Type de taux de change** : sélectionnez le taux de change que le système doit utiliser pour convertir le montant de la transaction dans la devise de la transaction et le coût standard des articles dans la devise d’évaluation des coûts.</span><span class="sxs-lookup"><span data-stu-id="69adf-121">**Exchange rate type** – Select the exchange rate that the system should use to convert the transaction amount in the transaction currency and the standard cost of the items into the costing currency.</span></span>

- <span data-ttu-id="69adf-122">**Nom de la convention** : spécifiez une convention.</span><span class="sxs-lookup"><span data-stu-id="69adf-122">**Convention name** – Specify a convention.</span></span> <span data-ttu-id="69adf-123">Une convention est un ensemble de politiques qui établissent la manière dont les coûts seront comptabilisés dans ce registre.</span><span class="sxs-lookup"><span data-stu-id="69adf-123">A convention is a collection of policies that establish how costs will be accounted in this ledger.</span></span>
- <span data-ttu-id="69adf-124">**Entité juridique** : le registre tiendra compte des documents qui sont imputés à l’entité juridique sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="69adf-124">**Legal entity** – The ledger will account the documents that are posted to the selected legal entity.</span></span>
- <span data-ttu-id="69adf-125">**Amorçage** : sélectionnez si les transactions de stock qui ont été créées avant la création du registre doivent être traitées selon la devise et la convention du registre.</span><span class="sxs-lookup"><span data-stu-id="69adf-125">**Priming** – Select whether inventory transactions that were created before the ledger was created should be processed according to the currency and convention in the ledger.</span></span> <span data-ttu-id="69adf-126">Vous devez sélectionner l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="69adf-126">Select one of the following values:</span></span>

    - <span data-ttu-id="69adf-127">**Activé** : le registre doit traiter les transactions qui ont été créées avant la création du registre.</span><span class="sxs-lookup"><span data-stu-id="69adf-127">**Activated** – The ledger should process transactions that were created before the ledger was created.</span></span>
    - <span data-ttu-id="69adf-128">**Désactivé** : le registre doit traiter uniquement les transactions qui ont été créées après la création du registre.</span><span class="sxs-lookup"><span data-stu-id="69adf-128">**Deactivated** – The ledger should process only transactions that are created after the ledger was created.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="69adf-129">Vous **ne pourrez pas** revenir et définir ce champ après avoir saisi de nouveaux documents.</span><span class="sxs-lookup"><span data-stu-id="69adf-129">You will **not** be able to come back and set this field after you enter new documents.</span></span>

- <span data-ttu-id="69adf-130">**Statut** : le système définit automatiquement le statut des registres nouvellement créés sur *Préparer*.</span><span class="sxs-lookup"><span data-stu-id="69adf-130">**Status** – The system automatically sets the status of newly created ledgers to *Prepare*.</span></span>
