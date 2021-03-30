---
title: Configurer les paramètres de bail (version préliminaire)
description: Cette rubrique décrit les paramètres de configuration de la location d’actifs, tels que les informations de sécurité et les paramètres de comptabilité.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4bb8372c5e4a1d7183b5d793b142fed92e833d5a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210431"
---
# <a name="configure-lease-parameters"></a><span data-ttu-id="89337-103">Configurer les paramètres de bail</span><span class="sxs-lookup"><span data-stu-id="89337-103">Configure lease parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89337-104">Plusieurs paramètres de configuration affectent le comportement de la location d’actifs.</span><span class="sxs-lookup"><span data-stu-id="89337-104">Several configuration settings affect how Asset leasing behaves.</span></span> <span data-ttu-id="89337-105">Ces paramètres incluent les noms de journaux, les paramètres généraux et les paramètres de profil de publication.</span><span class="sxs-lookup"><span data-stu-id="89337-105">These settings include journal names, general parameters, and posting profile settings.</span></span>

1. <span data-ttu-id="89337-106">Accédez à **Location d’actifs \> Configuration \> Paramètres de location d’actif**.</span><span class="sxs-lookup"><span data-stu-id="89337-106">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="89337-107">Sous l’onglet **Baux**, sélectionnez le raccourci **Général**.</span><span class="sxs-lookup"><span data-stu-id="89337-107">On the **Leases** tab, select the **General** FastTab.</span></span>

    <span data-ttu-id="89337-108">Le paramètre **Autoriser le remplacement manuel de la classification** détermine si la classification du bail peut être remplacée avant la confirmation de l’échéancier de paiement.</span><span class="sxs-lookup"><span data-stu-id="89337-108">The **Allow manual classification override** parameter determines whether the lease classification can be overridden before the payment schedule is confirmed.</span></span>

    <span data-ttu-id="89337-109">Le paramètre **Lot inter-entités** détermine si vous pouvez publier dans d’autres entités juridiques à partir de l’entité juridique actuelle.</span><span class="sxs-lookup"><span data-stu-id="89337-109">The **Cross-entity batch** parameter determines whether you can post to other legal entities from the current legal entity.</span></span> <span data-ttu-id="89337-110">Si ce paramètre est activé, vous pouvez créer des entrées de journal pour les entités juridiques auxquelles vous avez accès.</span><span class="sxs-lookup"><span data-stu-id="89337-110">If this parameter is turned on, you can create journal entries for the legal entities that you have access to.</span></span>

3. <span data-ttu-id="89337-111">Met l’option **Autoriser la suppression des baux confirmés** sur **Oui** pour permettre la suppression des baux dont les échéanciers de paiement ont été confirmés.</span><span class="sxs-lookup"><span data-stu-id="89337-111">Set the **Allow delete of confirmed leases** option to **Yes** to allow leases that have confirmed payment schedules to be deleted.</span></span> <span data-ttu-id="89337-112">Les baux ne peuvent pas être supprimés si des transactions validées ou non comptabilisées leur sont associées, quel que soit le paramètre de cette option.</span><span class="sxs-lookup"><span data-stu-id="89337-112">Leases can't be deleted if posted or unposted transactions are associated with them, regardless of the setting of this option.</span></span> <span data-ttu-id="89337-113">Vous ne pouvez pas restaurer un enregistrement de bail après sa suppression.</span><span class="sxs-lookup"><span data-stu-id="89337-113">You can't restore a lease record after it's deleted.</span></span> <span data-ttu-id="89337-114">Si vous téléchargez des enregistrements pour un bail supprimé, manuellement ou via des entités de données, les informations téléchargées sont traitées comme nouvelles et non comme une mise à jour d’un bail existant.</span><span class="sxs-lookup"><span data-stu-id="89337-114">If you upload any records for a deleted lease, either manually or through data entities, the uploaded information is treated as new, not as an update to an existing lease.</span></span>

    <span data-ttu-id="89337-115">Si vous définissez cette option sur **Oui**, et si le type de transition du registre est **Option de rattrapage cumulatif A ou B**, le système définit le champ **Taux d’emprunt progressif** sur la valeur du champ **Taux d’emprunt progressif à la transition** sur la page **Paramétrage du registre**.</span><span class="sxs-lookup"><span data-stu-id="89337-115">If you set this option to **Yes**, and the transition type of the book is **Cumulative Catchup Option A or B**, the system sets the **Incremental borrowing rate** field to the value of the **Incremental borrowing rate at transition** field on the **Book setup** page.</span></span> <span data-ttu-id="89337-116">Si cette option est définie sur **Non**, le taux du bail principal est fixé sur la valeur du champ **Taux d’emprunt progressif** sur la page **Détails du registre**, quel que soit le type de transition du registre.</span><span class="sxs-lookup"><span data-stu-id="89337-116">If this option is set to **No**, the rate on the head lease is set to the value of the **Incremental borrowing rate** field on the **Book details** page, regardless of the transition type of the book.</span></span>

4. <span data-ttu-id="89337-117">Définit l’option **Autoriser les contrepassations d’amortissement sur la version du registre clôturé** sur **Oui** pour permettre la contrepassation des transactions de dotation aux amortissements.</span><span class="sxs-lookup"><span data-stu-id="89337-117">Set the **Allow depreciation reversals on closed book version** option to **Yes** to allow depreciation expense transactions to be reversed.</span></span> <span data-ttu-id="89337-118">Les transactions de dépenses peuvent être annulées même lorsque la version comptable est fermée.</span><span class="sxs-lookup"><span data-stu-id="89337-118">Expense transactions can be reversed even when the book version is closed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="89337-119">Nous vous recommandons de conserver cette option définie sur **Non**.</span><span class="sxs-lookup"><span data-stu-id="89337-119">We recommend that you keep this option set to **No**.</span></span> <span data-ttu-id="89337-120">Le paramétrage de cette option est utilisé comme une validation et un contrôle pour éviter qu’une version de registre clôturé ne soit accidentellement dépréciée.</span><span class="sxs-lookup"><span data-stu-id="89337-120">The setting of this option is used as a validation and control to prevent a closed book version from being accidently depreciated.</span></span> <span data-ttu-id="89337-121">En gardant l’option définie sur **Non**, vous contribuez à maintenir la précision de la valeur nette et des calculs d’amortissement à venir.</span><span class="sxs-lookup"><span data-stu-id="89337-121">By keeping the option set to **No**, you help keep the net book value and future depreciation calculations accurate.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]