---
title: Fonctionnalité de facturation fractionnée
description: Cette rubrique décrit la configuration et la fonctionnalité de fractionnement des factures par adresse de livraison et numéro de compte fiscal (TAN).
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
ms.openlocfilehash: 7dddbb9f69a9735c2a03d2b23928f5cb92d4e0fd
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023243"
---
# <a name="split-invoice-functionality"></a><span data-ttu-id="38932-103">Fonctionnalité de facturation fractionnée</span><span class="sxs-lookup"><span data-stu-id="38932-103">Split invoice functionality</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38932-104">Cette rubrique décrit la configuration et la fonctionnalité de fractionnement des factures par adresse de livraison et numéro de compte fiscal (TAN).</span><span class="sxs-lookup"><span data-stu-id="38932-104">This topic describes the setup and functionality for splitting invoices by delivery address and tax account number (TAN).</span></span>

<span data-ttu-id="38932-105">Sur la page **Paramètres des comptes fournisseurs**, dans l'onglet **Général**, sélectionnez la case à cocher **Reçu de produit** ou **Facture** et fractionner un reçu de produit ou une facture qui a des adresses de livraison et des TAN différents sur la page **Commande fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="38932-105">On the **Accounts payable parameters** page, on the **General** tab, select the **Product receipt** or **Invoice** checkbox to post and split a product receipt or invoice that has different delivery addresses and TANs on the **Purchase order** page.</span></span> <span data-ttu-id="38932-106">La facture validée sera ensuite divisée par adresse de livraison et TAN.</span><span class="sxs-lookup"><span data-stu-id="38932-106">The posted invoice will then be split by delivery address and TAN.</span></span>

<span data-ttu-id="38932-107">Dans l'onglet **Mise à jour récapitulative**, sur le raccourci **Fractionner basé sur**, sur la ligne **Informations de livraison**, définissez l'option **Confirmation**, **Prélèvement**, **Bon de livraison** ou **Facture** sur **Oui** pour enregistrer et fractionner une confirmation, une liste de prélèvement, un bon de livraison ou une facture où différentes adresses de livraison et TAN sont définis pour différentes lignes de facture sur la page **Commande client**.</span><span class="sxs-lookup"><span data-stu-id="38932-107">On the **Summary update** tab, on the **Split based on** FastTab, in the **Delivery information** row, set the **Confirmation**, **Picking list**, **Packing slip**, or **Invoice** option to **Yes** to post and split a confirmation, picking list, packing slip, or invoice where different delivery addresses and TANs are defined for different invoice lines on the **Sales order** page.</span></span> <span data-ttu-id="38932-108">La facture validée sera d'abord divisée par adresse de livraison, puis sur la base du TAN.</span><span class="sxs-lookup"><span data-stu-id="38932-108">The invoice will be split first by delivery address and then by TAN.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="38932-109">Si aucune option pour **Informations de livraison** n'est définie sur **Oui**, la facture sera enregistrée comme une seule facture.</span><span class="sxs-lookup"><span data-stu-id="38932-109">If no options for **Delivery information** are set to **Yes**, the invoice will be posted as a single invoice.</span></span> <span data-ttu-id="38932-110">Aucun fractionnement de facture n'aura lieu.</span><span class="sxs-lookup"><span data-stu-id="38932-110">No invoice splitting will occur.</span></span>
> - <span data-ttu-id="38932-111">Pour fractionner et valider un bon de livraison où les lignes de facture ont des adresses de livraison et des TAN différents, vous devez définir l'option **Bon de livraison** pour **Informations de livraison** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="38932-111">To split and post a packing slip where the invoice lines have different delivery addresses and TANs, you must set the **Packing slip** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="38932-112">Pour fractionner et valider une facture où les lignes de facture ont des adresses de livraison et des TAN différents, vous devez définir l'option **Facture** pour **Informations de livraison** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="38932-112">To split and post an invoice where the invoice lines have different delivery addresses and TANs, you must set the **Invoice** option for **Delivery information** to **Yes**.</span></span>
> - <span data-ttu-id="38932-113">Pour fractionner et valider une facture où les lignes de facture ont des adresses de livraison différentes mais le même TAN, vous devez définir l'option **Facture** pour **Informations de livraison** sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="38932-113">To post an invoice where the invoice lines have different delivery addresses but the same TAN, set the **Invoice** option for **Delivery information** to **No**.</span></span> <span data-ttu-id="38932-114">La facture validée sera divisée par adresse de livraison.</span><span class="sxs-lookup"><span data-stu-id="38932-114">The invoice will be split by delivery address.</span></span>

## <a name="example"></a><span data-ttu-id="38932-115">Exemple</span><span class="sxs-lookup"><span data-stu-id="38932-115">Example</span></span>

<span data-ttu-id="38932-116">Dans cet exemple, l'option **Facture** pour **Informations de livraison** est paramétrée sur **Oui** dans l'onglet **Mise à jour récapitulative** de la page **Paramètres des comptes fournisseurs**.</span><span class="sxs-lookup"><span data-stu-id="38932-116">In this example, the **Invoice** option for **Delivery information** is set to **Yes** on the **Summary update** tab of the **Accounts payable parameters** page.</span></span> <span data-ttu-id="38932-117">Une facture d'achat est validée avec la configuration suivante pour les adresses de livraison et les TAN sur les lignes :</span><span class="sxs-lookup"><span data-stu-id="38932-117">A purchase invoice is posted that has the following setup for delivery addresses and TANs on the lines:</span></span>

- <span data-ttu-id="38932-118">**Ligne d'article 1 :** Adresse de livraison 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="38932-118">**Item line 1:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="38932-119">**Ligne d'article 2 :** Adresse de livraison 1, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="38932-119">**Item line 2:** Delivery address 1, TAN-ABCD12345A</span></span>
- <span data-ttu-id="38932-120">**Ligne d'article 3 :** Adresse de livraison 2, TAN-ABCE12345B</span><span class="sxs-lookup"><span data-stu-id="38932-120">**Item line 3:** Delivery address 2, TAN-ABCE12345B</span></span>
- <span data-ttu-id="38932-121">**Ligne d'article 4 :** Adresse de livraison 3, TAN-ABCD12345A</span><span class="sxs-lookup"><span data-stu-id="38932-121">**Item line 4:** Delivery address 3, TAN-ABCD12345A</span></span>

<span data-ttu-id="38932-122">Dans ce cas, la facture originale est scindée en deux factures et validée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="38932-122">In this case, the original invoice is split into two invoices and posted in the following way:</span></span>

- <span data-ttu-id="38932-123">La facture 1 est validée pour la ligne d'article 1 et la ligne d'article 2, car les deux lignes ont la même adresse de livraison et TAN.</span><span class="sxs-lookup"><span data-stu-id="38932-123">Invoice 1 is posted for item line 1 and item line 2, because both lines have the same delivery address and TAN.</span></span>
- <span data-ttu-id="38932-124">La facture 2 est validée pour la ligne d'article 3.</span><span class="sxs-lookup"><span data-stu-id="38932-124">Invoice 2 is posted for item line 3.</span></span>
- <span data-ttu-id="38932-125">La facture 3 est validée pour la ligne d'article 4.</span><span class="sxs-lookup"><span data-stu-id="38932-125">Invoice 3 is posted for item line 4.</span></span>
