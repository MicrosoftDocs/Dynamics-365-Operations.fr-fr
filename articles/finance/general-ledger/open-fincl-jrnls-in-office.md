---
title: Ouvrir des modèles de journal financier dans Office
description: Cette rubrique décrit les problèmes qui peuvent se produire lorsque vous créez des journaux financiers personnalisés à l’aide d’un modèle Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0773f47551b2460ec310b92b67c634b433147749
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2021
ms.locfileid: "6089455"
---
# <a name="open-financial-journal-templates-in-office"></a><span data-ttu-id="b3b5b-103">Ouvrir des modèles de journal financier dans Office</span><span class="sxs-lookup"><span data-stu-id="b3b5b-103">Open financial journal templates in Office</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b3b5b-104">Cette rubrique décrit les problèmes qui peuvent se produire lorsque vous créez des journaux financiers personnalisés à l’aide d’un modèle Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-104">This topic describes issues that might occur when you create custom financial journals by using a Microsoft Excel template.</span></span>

## <a name="symptom"></a><span data-ttu-id="b3b5b-105">Problème</span><span class="sxs-lookup"><span data-stu-id="b3b5b-105">Symptom</span></span>

<span data-ttu-id="b3b5b-106">Vous avez créé un modèle Excel personnalisé pour les journaux financiers, mais il n’apparaît pas dans le menu **Ouvrir les lignes dans Excel**.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-106">You created a custom Excel template for financial journals, but it doesn't appear on the **Open lines in Excel** menu.</span></span> <span data-ttu-id="b3b5b-107">Ou bien, il apparaît dans le menu, mais un autre modèle est ouvert lorsque vous le sélectionnez.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-107">Alternatively, it does appear on the menu, a different template is opened but when you select it.</span></span>

## <a name="resolution"></a><span data-ttu-id="b3b5b-108">Résolution</span><span class="sxs-lookup"><span data-stu-id="b3b5b-108">Resolution</span></span>

<span data-ttu-id="b3b5b-109">La fonctionnalité Ouvrir dans Excel par défaut utilise la source de données racine (table) de la page actuelle pour déterminer les modèles Office ou les entités de données qui apparaissent comme options dans le menu **Ouvrir dans Excel**.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-109">The default Open in Excel functionality uses the root data source (table) of the current page to determine which Office templates or data entities appear as options on the **Open in Excel** menu.</span></span> <span data-ttu-id="b3b5b-110">Ce comportement n’est pas une expérience idéale pour les journaux financiers, car ces derniers utilisent les mêmes tables (LedgerJournalTable et LedgerJournalTrans) comme source de données racine de nombreux autres types de journaux.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-110">This behavior isn't an ideal experience for financial journals, because financial journals use the same tables (LedgerJournalTable and LedgerJournalTrans) as the root data source of many other types of journals.</span></span>

<span data-ttu-id="b3b5b-111">Pour les journaux financiers, la fonctionnalité Ouvrir les lignes dans Excel est destinée à afficher des modèles conçus pour le journal dans le contexte duquel vous travaillez actuellement, comme le journal des opérations diverses ou un journal des paiements.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-111">For financial journals, the Open Lines in Excel functionality is intended to show templates that are designed for the journal that you're currently working in the context of, such as the general journal or a payment journal.</span></span> <span data-ttu-id="b3b5b-112">Par exemple, un modèle destiné à être utilisé avec un journal des paiements fournisseur sera conçu pour appliquer votre compte principal comme compte fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-112">For example, a template that is intended to be used with a vendor payment journal will be designed to enforce your primary account as a vendor account.</span></span>

<span data-ttu-id="b3b5b-113">Si vous souhaitez promouvoir un modèle afin qu’il soit disponible dans les menus **Ouvrir les lignes dans Excel** et **Ouvrir dans Excel**, une expérience simple pour les développeurs consiste à implémenter l’interface **LedgerIJournalExcelTemplate** et à étendre la classe **DocuTemplateRegistrationBase**.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-113">If you want to promote a template so that it's available on the **Open lines in Excel** and **Open in Excel** menus, an easy developer experience is to implement the **LedgerIJournalExcelTemplate** interface and extend the **DocuTemplateRegistrationBase** class.</span></span> <span data-ttu-id="b3b5b-114">De nombreux exemples de cette approche sont implémentés dans le système.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-114">Many examples of this approach are implemented in the system.</span></span> <span data-ttu-id="b3b5b-115">Un exemple qui peut servir de référence est l’interface **LedgerDailyJournalExcelTemplate** créée pour le journal des opérations diverses (ou le journal quotidien).</span><span class="sxs-lookup"><span data-stu-id="b3b5b-115">One example that can be used for reference is the **LedgerDailyJournalExcelTemplate** interface that was created for the general journal (or daily journal).</span></span>

<span data-ttu-id="b3b5b-116">Lorsque l’interface **LedgerIJournalExcelTemplate** est implémentée pour votre modèle, le menu **Ouvrir les lignes dans Excel** filtrera les modèles selon le type de votre journal et n’affichera que les modèles disponibles pour ce journal.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-116">When the **LedgerIJournalExcelTemplate** interface is implemented for your template, the **Open Lines in Excel** menu will filter templates by the journal type of your journal and will show only the templates that are available for that journal.</span></span> <span data-ttu-id="b3b5b-117">L’interface fournit également une méthode de validation qui garantit qu’un modèle ne peut pas être ouvert pour un journal s’il ne répond pas aux exigences du type de compte.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-117">The interface also provides a validation method that ensures that a template can't be opened for a journal if it doesn't meet the account type requirements.</span></span> <span data-ttu-id="b3b5b-118">Par exemple, vous pouvez spécifier que le type de compte doit être **Fournisseur** ou **Général**.</span><span class="sxs-lookup"><span data-stu-id="b3b5b-118">For example, you can specify that the account type must be of the **Vendor** or **Ledger** type.</span></span>

<span data-ttu-id="b3b5b-119">Pour plus d’informations sur cette fonctionnalité, consultez [Ajouter des modèles au menu Ouvrir les lignes dans Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span><span class="sxs-lookup"><span data-stu-id="b3b5b-119">For more information about this functionality, see [Add templates to the Open lines in Excel menu](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span></span>
