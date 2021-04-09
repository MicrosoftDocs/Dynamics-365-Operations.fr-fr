---
title: Créer des chèques dont le statut est Nul
description: Cette rubrique explique comment créer des chèques nuls pour un compte bancaire sur la page Chèques.
author: abruer
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 1b01daa86055156092d035d61aad78a13349f869
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815954"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="70c7a-103">Créer des chèques dont le statut est Nul</span><span class="sxs-lookup"><span data-stu-id="70c7a-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70c7a-104">Cette rubrique explique comment créer des chèques nuls.</span><span class="sxs-lookup"><span data-stu-id="70c7a-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="70c7a-105">Par exemple, vous pouvez créer un chèque nul pour enregistrer un chèque qui a été endommagé et ne peut pas être utilisé pour le paiement.</span><span class="sxs-lookup"><span data-stu-id="70c7a-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="70c7a-106">Dans la page **Chèques**, vous effectuez les tâches de maintenance concernant les chèques.</span><span class="sxs-lookup"><span data-stu-id="70c7a-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="70c7a-107">Par exemple, vous pouvez créer de nouveaux numéros de chèque et supprimer des chèques.</span><span class="sxs-lookup"><span data-stu-id="70c7a-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="70c7a-108">Vous pouvez également créer des chèques ayant le statut **Nul**.</span><span class="sxs-lookup"><span data-stu-id="70c7a-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="70c7a-109">Quand un chèque nul a été créé, il est impossible de le supprimer ou de le réutiliser dans le système.</span><span class="sxs-lookup"><span data-stu-id="70c7a-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="70c7a-110">Cette fonction n’est disponible sur la page **Chèques** que si vous activez la fonctionnalité **Créer des chèques ayant le statut nul dans la page Chèques** sur la page **Gestion des fonctionnalités**.</span><span class="sxs-lookup"><span data-stu-id="70c7a-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="70c7a-111">Si la fonction n’est pas activée, les chèques ayant le statut **Nul** ne peuvent être créés qu’à partir de la boîte de dialogue **Paiement par chèque** au moment du processus de génération de paiement dans la Comptabilité fournisseur.</span><span class="sxs-lookup"><span data-stu-id="70c7a-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="70c7a-112">Pour ouvrir la page **Chèques**, accédez à **Gestion de la trésorerie et de la banque \> Comptes bancaires \> Comptes bancaires**, puis, dans le volet Actions, sous l’onglet **Gérer les paiements**, dans le groupe **Informations associées**, sélectionnez **Chèques**.</span><span class="sxs-lookup"><span data-stu-id="70c7a-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="70c7a-113">Sinon, accédez à **Gestion de la trésorerie et de la banque \> Recherches et états \> Chèques**.</span><span class="sxs-lookup"><span data-stu-id="70c7a-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="70c7a-114">Ensuite, pour créer des chèques ayant le statut **Nul**, dans le volet Actions, sélectionnez **Créer des chèques nuls**.</span><span class="sxs-lookup"><span data-stu-id="70c7a-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="70c7a-115">Pendant que le système crée les chèques nuls, le compte bancaire associé est temporairement désactivé.</span><span class="sxs-lookup"><span data-stu-id="70c7a-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="70c7a-116">Ce comportement permet de réduire le risque que des paiements soient générés en même temps que des chèques nuls sont créés.</span><span class="sxs-lookup"><span data-stu-id="70c7a-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="70c7a-117">Une fois le processus terminé, le compte bancaire associé est réactivé.</span><span class="sxs-lookup"><span data-stu-id="70c7a-117">When the processing is completed, the associated bank account is reactivated.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]