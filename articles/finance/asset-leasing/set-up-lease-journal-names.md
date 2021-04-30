---
title: Configurer les noms des registres des baux
description: Cette rubrique explique comment définir les noms des journaux de location. Les noms des journaux de location spécifient les journaux dans lesquels les entrées provenant de la location d’actifs sont imputées.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c139df124b249ec9dc5d16096e6f45f22d435456
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880884"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="0eacc-104">Configurer les noms des registres des baux</span><span class="sxs-lookup"><span data-stu-id="0eacc-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0eacc-105">Les noms des journaux de location spécifient les journaux dans lesquels les transactions sont imputées.</span><span class="sxs-lookup"><span data-stu-id="0eacc-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="0eacc-106">Seuls les noms de journaux attribués au type de journal **Location d’actifs** apparaît dans les champs **Reconnaissance initiale** et **Nom du journal mensuel** sur la page **Paramètres de location d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="0eacc-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="0eacc-107">Seul le type de journal **Enregistrement de la facture fournisseur** peut être affecté au champ **Nom du journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="0eacc-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="0eacc-108">Pour configurer les noms des journaux de bail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="0eacc-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="0eacc-109">Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.</span><span class="sxs-lookup"><span data-stu-id="0eacc-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="0eacc-110">Sur l’onglet **Général**, dans le champ **Nom du journal de reconnaissance initiale** et sélectionnez un journal.</span><span class="sxs-lookup"><span data-stu-id="0eacc-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="0eacc-111">Toutes les entrées de journal de reconnaissance initiale seront enregistrées sous ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="0eacc-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="0eacc-112">Dans le champ **Nom du journal des factures**, sélectionnez un journal.</span><span class="sxs-lookup"><span data-stu-id="0eacc-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="0eacc-113">Si l’option **Payer au fournisseur** est définie sur **Oui** pour le registre de location, les factures de location et de paiement des dépenses seront imputées à ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="0eacc-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="0eacc-114">Dans le champ **Nom du journal des baux**, sélectionnez un journal.</span><span class="sxs-lookup"><span data-stu-id="0eacc-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="0eacc-115">Toutes les écritures d’amortissement, d’intérêts et de reclassement à court terme seront enregistrées sous ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="0eacc-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="0eacc-116">Si l’option **Payer au fournisseur** est définie sur **Non** pour le registre de location, les entrées de paiements de location et de paiement des dépenses seront imputées à ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="0eacc-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
