---
title: Configurer les noms des registres des baux
description: Cette rubrique explique comment définir les noms des journaux de location. Les noms des journaux de location spécifient les journaux dans lesquels les entrées provenant de la location d’actifs sont imputées.
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
ms.openlocfilehash: 89c5fc768aafe9e5de9adcde32e7b4d0a084941b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990915"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="2bce9-104">Configurer les noms des registres des baux</span><span class="sxs-lookup"><span data-stu-id="2bce9-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2bce9-105">Les noms des journaux de location spécifient les journaux dans lesquels les transactions sont imputées.</span><span class="sxs-lookup"><span data-stu-id="2bce9-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="2bce9-106">Seuls les noms de journaux attribués au type de journal **Location d’actifs** apparaît dans les champs **Reconnaissance initiale** et **Nom du journal mensuel** sur la page **Paramètres de location d’actifs**.</span><span class="sxs-lookup"><span data-stu-id="2bce9-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="2bce9-107">Seul le type de journal **Enregistrement de la facture fournisseur** peut être affecté au champ **Nom du journal des factures**.</span><span class="sxs-lookup"><span data-stu-id="2bce9-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="2bce9-108">Pour configurer les noms des journaux de bail, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="2bce9-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="2bce9-109">Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.</span><span class="sxs-lookup"><span data-stu-id="2bce9-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="2bce9-110">Sur l’onglet **Général**, dans le champ **Nom du journal de reconnaissance initiale** et sélectionnez un journal.</span><span class="sxs-lookup"><span data-stu-id="2bce9-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="2bce9-111">Toutes les entrées de journal de reconnaissance initiale seront enregistrées sous ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="2bce9-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="2bce9-112">Dans le champ **Nom du journal des factures**, sélectionnez un journal.</span><span class="sxs-lookup"><span data-stu-id="2bce9-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="2bce9-113">Si l’option **Payer au fournisseur** est définie sur **Oui** pour le registre de location, les factures de location et de paiement des dépenses seront imputées à ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="2bce9-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="2bce9-114">Dans le champ **Nom du journal des baux**, sélectionnez un journal.</span><span class="sxs-lookup"><span data-stu-id="2bce9-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="2bce9-115">Toutes les écritures d’amortissement, d’intérêts et de reclassement à court terme seront enregistrées sous ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="2bce9-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="2bce9-116">Si l’option **Payer au fournisseur** est définie sur **Non** pour le registre de location, les entrées de paiements de location et de paiement des dépenses seront imputées à ce nom de journal.</span><span class="sxs-lookup"><span data-stu-id="2bce9-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>
