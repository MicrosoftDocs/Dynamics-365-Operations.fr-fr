---
title: Modifier les dimensions financières des transactions de vente au détail
description: Cette rubrique décrit la procédure de modification des dimensions financières des transactions de détail dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: ff16d8e2e75a877e5ca7de604c7915e908473da6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792703"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a><span data-ttu-id="9b498-103">Modifier les dimensions financières des transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="9b498-103">Edit financial dimensions for retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b498-104">Cette rubrique décrit la procédure de modification des dimensions financières des transactions de détail dans Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9b498-104">This topic describes how to edit financial dimensions for retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="edit-financial-dimensions"></a><span data-ttu-id="9b498-105">Modifier les dimensions financières</span><span class="sxs-lookup"><span data-stu-id="9b498-105">Edit financial dimensions</span></span>

<span data-ttu-id="9b498-106">Pour modifier les dimensions financières des transactions de vente au détail dans Commerce Headquarters, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="9b498-106">To edit financial dimensions for retail transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9b498-107">Ouvrez la page **Configuration de dimension financière pour les applications d’intégration**.</span><span class="sxs-lookup"><span data-stu-id="9b498-107">Open the **Financial dimensions configuration for integrating applications** page.</span></span>
1. <span data-ttu-id="9b498-108">Sélectionnez l’enregistrement **Intégration des dimensions par défaut** actif.</span><span class="sxs-lookup"><span data-stu-id="9b498-108">Select the active **Default dimensions integration** record.</span></span>
1. <span data-ttu-id="9b498-109">Dans le raccourci **Dimensions financières**, assurez-vous que toutes les dimensions que vous souhaitez modifier dans la feuille de calcul Excel sont présentes dans la liste **Sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="9b498-109">On the **Financial dimensions** FastTab, make sure that all the dimensions that you want to edit in the Excel worksheet are present in the **Selected** list.</span></span> <span data-ttu-id="9b498-110">Pour plus d’informations, consultez [Entités de données](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span><span class="sxs-lookup"><span data-stu-id="9b498-110">For more information, see [Data entities](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span></span>
1. <span data-ttu-id="9b498-111">Téléchargez et ouvrez le fichier Excel à partir de la page **Relevés**, de la page **Transactions de vente au détail** ou de la vignette **Échecs de validation de transaction** dans l’espace de travail **Finances du magasin**.</span><span class="sxs-lookup"><span data-stu-id="9b498-111">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="9b498-112">Pour modifier la dimension financière de la transaction, sélectionnez **Design**, puis sélectionnez le symbole du crayon en regard de la ligne **Transaction (vérifiable)**.</span><span class="sxs-lookup"><span data-stu-id="9b498-112">To change the transaction financial dimension, select **Design**, and then select the pencil symbol next to the **Transaction (auditable)** row.</span></span>
1. <span data-ttu-id="9b498-113">Trouvez et sélectionnez le champ **FinancialDimensionDisplayValue**, sélectionnez une cellule dans l’en-tête de la feuille de calcul Excel, puis sélectionnez **Ajouter une étiquette**.</span><span class="sxs-lookup"><span data-stu-id="9b498-113">Find and select the **FinancialDimensionDisplayValue** field, select a cell in the header part of the Excel worksheet, and then select **Add label**.</span></span>
1. <span data-ttu-id="9b498-114">Sélectionnez une cellule sous celle que vous avez sélectionnée à l’étape précédente, sélectionnez **Ajouter une valeur**, puis **Rafraîchir**.</span><span class="sxs-lookup"><span data-stu-id="9b498-114">Select a cell below the cell that you selected in the previous step, select **Add Value**, and then select **Refresh**.</span></span> <span data-ttu-id="9b498-115">Les dimensions financières sont ajoutées à la feuille de calcul Excel et peuvent ensuite être modifiées et publiées.</span><span class="sxs-lookup"><span data-stu-id="9b498-115">The financial dimensions are added to the Excel worksheet, and they can then be edited and published.</span></span>
1. <span data-ttu-id="9b498-116">Pour modifier les dimensions sur les lignes de transaction, sélectionnez la ligne **Transactions de vente (vérifiables)**, sélectionnez le symbole du crayon, puis répétez les étapes 6 et 7.</span><span class="sxs-lookup"><span data-stu-id="9b498-116">To change the dimensions on the transaction lines, select the **Sales transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>
1. <span data-ttu-id="9b498-117">Pour modifier les dimensions sur les lignes de paiement, sélectionnez la ligne **Transactions de paiement (vérifiables)**, sélectionnez le symbole du crayon, puis répétez les étapes 6 et 7.</span><span class="sxs-lookup"><span data-stu-id="9b498-117">To change the dimensions on the payment lines, select the **Payment transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b498-118">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="9b498-118">Additional resources</span></span>

[<span data-ttu-id="9b498-119">Modifier et vérifier les transactions de gestion des disponibilités et des paiements au comptant sans livraison</span><span class="sxs-lookup"><span data-stu-id="9b498-119">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="9b498-120">Modifier et vérifier les commandes en ligne et les transactions de commandes client asynchrones</span><span class="sxs-lookup"><span data-stu-id="9b498-120">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="9b498-121">Créer un classeur Excel pour modifier les transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="9b498-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="9b498-122">Ajouter des champs à un classeur Excel pour modifier les transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="9b498-122">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]