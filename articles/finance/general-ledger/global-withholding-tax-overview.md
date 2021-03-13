---
title: Retenue à la source globale
description: Cette rubrique fournit des informations sur la fonctionnalité de retenue à la source globale et sur la manière de la configurer. La fonctionnalité de retenue à la source globale est améliorée pour les transactions fournisseur et client, de sorte que la retenue à la source est calculée au niveau de l'article.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
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
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 17ed1dcae97f6cd28175c483be5ca3ce96d59e05
ms.sourcegitcommit: 053f4cda6862fbcd9e3aa6e9cb009e7de833beac
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/28/2021
ms.locfileid: "5075736"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="47fa2-104">Retenue à la source globale</span><span class="sxs-lookup"><span data-stu-id="47fa2-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47fa2-105">Cette rubrique fournit des informations sur la fonctionnalité de retenue à la source globale et explique comment la configurer.</span><span class="sxs-lookup"><span data-stu-id="47fa2-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="47fa2-106">Cette nouvelle fonctionnalité est disponible dans la version 10.0.17 et ultérieures.</span><span class="sxs-lookup"><span data-stu-id="47fa2-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="47fa2-107">La fonctionnalité de retenue à la source globale est améliorée pour les transactions fournisseur et client, de sorte que la retenue à la source est calculée au niveau de l'article.</span><span class="sxs-lookup"><span data-stu-id="47fa2-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="47fa2-108">Le solde du compte de retenue à la source provenant des transactions d'achat peut être réglé en exécutant la tâche de paiement de la retenue à la source sur le compte de règlement de la retenue à la source.</span><span class="sxs-lookup"><span data-stu-id="47fa2-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="47fa2-109">La retenue à la source globale ne prend pas en charge la fonction **Tenir les frais à jour** sur les pages de bon de commande, de facture fournisseur et de commande client.</span><span class="sxs-lookup"><span data-stu-id="47fa2-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="47fa2-110">Activer la retenue à la source globale</span><span class="sxs-lookup"><span data-stu-id="47fa2-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="47fa2-111">Dans l’espace de travail **Gestion des fonctionnalités**, sélectionnez **Retenue à la source globale**, puis sélectionnez **Activer maintenant**.</span><span class="sxs-lookup"><span data-stu-id="47fa2-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="47fa2-112">Accédez à **Taxe \> Paramétrage \> Paramètres \> Paramètres de comptabilité**, puis dans l'onglet **Retenue à la source**, définissez l'option **Activer la retenue à la source globale** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="47fa2-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="47fa2-113">Sélectionnez **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="47fa2-113">Select **Save**.</span></span>
4. <span data-ttu-id="47fa2-114">Actualisez la page dans votre navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="47fa2-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="47fa2-115">La fonctionnalité de retenue à la source globale ne peut pas être activée pour les pays/régions où des solutions de retenue à la source localisées existent déjà.</span><span class="sxs-lookup"><span data-stu-id="47fa2-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="47fa2-116">Ces pays comprennent, sans s'y limiter, l'Inde, le Brésil, la Thaïlande, l'Arabie saoudite, l'Irlande, la Grande-Bretagne et les États-Unis.</span><span class="sxs-lookup"><span data-stu-id="47fa2-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>
