---
title: Définition des paramètres TDS dans Comptabilité client et Comptabilité fournisseur
description: Cette rubrique explique comment définir des paramètres dans Comptes fournisseurs et Comptes clients pour prendre en charge les déductions de la taxe retenue à la source (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 4540cdfff2362d8fb7cc2b4cccf9c340be9750ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023238"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a><span data-ttu-id="ba34f-103">Définition des paramètres TDS dans Comptabilité client et Comptabilité fournisseur</span><span class="sxs-lookup"><span data-stu-id="ba34f-103">Set TDS parameters in Accounts payable and Accounts receivable</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba34f-104">Cette rubrique explique comment définir des paramètres dans Comptes fournisseurs et Comptes clients pour prendre en charge les déductions de la taxe retenue à la source (TDS).</span><span class="sxs-lookup"><span data-stu-id="ba34f-104">This topic explains how to set parameters in Accounts payable and Accounts receivable to support Tax Deducted at Source (TDS) deductions.</span></span>

1. <span data-ttu-id="ba34f-105">Accédez à **Taxe \> Configuration \> Paramètres \> Paramètres de la comptabilité client**.</span><span class="sxs-lookup"><span data-stu-id="ba34f-105">Go to **Tax \> Setup \> Parameters \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="ba34f-106">Dans l'onglet **Mises à jour**, sélectionnez **Mettre à jour les lignes de commande** pour ouvrir la boîte de dialogue **Mettre à jour les lignes de commande**.</span><span class="sxs-lookup"><span data-stu-id="ba34f-106">On the **Updates** tab, select **Update order lines** to open the **Update order lines** dialog box.</span></span>
3. <span data-ttu-id="ba34f-107">Dans la section **Groupe TDS**, dans le champ **Mise à jour du groupe TDS**, spécifiez la méthode à utiliser pour mettre à jour le groupe TDS au niveau de la ligne.</span><span class="sxs-lookup"><span data-stu-id="ba34f-107">In the **TDS group** section, in the **Updating TDS group** field, specify the method to use to update the TDS group at the line level.</span></span> <span data-ttu-id="ba34f-108">Ce paramètre est utilisé lorsque le groupe TDS est mis à jour sur un en-tête de commande.</span><span class="sxs-lookup"><span data-stu-id="ba34f-108">This setting is used when the TDS group is updated on an order header.</span></span> <span data-ttu-id="ba34f-109">Les options suivantes sont disponibles :</span><span class="sxs-lookup"><span data-stu-id="ba34f-109">The following options are available:</span></span>

    - <span data-ttu-id="ba34f-110">**Jamais** - Le groupe TDS n'est pas mis à jour sur les lignes de commande lorsqu'il est mis à jour sur l'en-tête de commande.</span><span class="sxs-lookup"><span data-stu-id="ba34f-110">**Never** – The TDS group isn't updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="ba34f-111">**Toujours** - Le groupe TDS est automatiquement mis à jour sur les lignes de commande lorsqu'il est mis à jour sur l'en-tête de commande.</span><span class="sxs-lookup"><span data-stu-id="ba34f-111">**Always** – The TDS group is automatically updated on the order lines when it's updated on the order header.</span></span>
    - <span data-ttu-id="ba34f-112">**Rapide** - Les utilisateurs reçoivent un message qui les invite à mettre à jour le groupe TDS sur les lignes de commande.</span><span class="sxs-lookup"><span data-stu-id="ba34f-112">**Prompt** – Users receive a message that prompts them to update the TDS group on the order lines.</span></span>
4. <span data-ttu-id="ba34f-113">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba34f-113">Select **OK**.</span></span>

    <span data-ttu-id="ba34f-114">[![Boîte de dialogue Mettre à jour les lignes de commande](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span><span class="sxs-lookup"><span data-stu-id="ba34f-114">[![Update order lines dialog box](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)</span></span>

5. <span data-ttu-id="ba34f-115">Accédez à **Taxe \> Configuration \> Paramètres \> Paramètres de la comptabilité fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="ba34f-115">Go to **Tax \> Setup \> Parameters \> Accounts payable parameters**.</span></span>
6. <span data-ttu-id="ba34f-116">Dans l'onglet **Général**, dans le raccourci **Fractionner en fonction des informations de livraison**, définissez l'option **Reçu de produit** sur **Oui** pour enregistrer et fractionner un reçu de produit qui a des adresses de livraison et des numéros de compte fiscaux (TAN) différents.</span><span class="sxs-lookup"><span data-stu-id="ba34f-116">On the **General** tab, on the **Split based on delivery information** FastTab, set the **Product receipt** option to **Yes** to post and split a product receipt that has different delivery addresses and tax account numbers (TANs).</span></span> <span data-ttu-id="ba34f-117">Si cette option est définie sur **Non**, vous ne pouvez pas valider un bon de livraison d'achat comportant des adresses de livraison et des TAN différents.</span><span class="sxs-lookup"><span data-stu-id="ba34f-117">If this option is set to **No**, you can't post a purchase packing slip that has different delivery addresses and TANs.</span></span>
7. <span data-ttu-id="ba34f-118">Définit l'option **Facturer** pour **Oui** pour enregistrer et fractionner une facture d'achat qui a des adresses de livraison et des TAN différents.</span><span class="sxs-lookup"><span data-stu-id="ba34f-118">Set the **Invoice** option to **Yes** to post and split a purchase invoice that has different delivery addresses and TANs.</span></span>

    <span data-ttu-id="ba34f-119">[![Fractionnement basé sur les informations de livraison FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span><span class="sxs-lookup"><span data-stu-id="ba34f-119">[![Split based on delivery information FastTab](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)</span></span>

8. <span data-ttu-id="ba34f-120">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="ba34f-120">Close the page.</span></span>
