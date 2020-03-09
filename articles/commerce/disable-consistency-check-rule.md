---
title: Désactiver les règles dans le vérificateur de cohérence des transactions de vente au détail
description: Cette rubrique décrit la fonctionnalité de désactivation des règles du vérificateur de cohérence des transactions dans Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 51a02d6f305cbad9784cf1b811188d0e06b6f15b
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057635"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="ec473-103">Désactiver les règles dans le vérificateur de cohérence des transactions de vente au détail</span><span class="sxs-lookup"><span data-stu-id="ec473-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="ec473-104">Les détaillants peuvent avoir des scénarios et des processus métier qui leur sont propres.</span><span class="sxs-lookup"><span data-stu-id="ec473-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="ec473-105">Par conséquent, toutes les règles disponibles par défaut dans le vérificateur de cohérence des transactions commerciales ne s'appliquent pas à tous les détaillants.</span><span class="sxs-lookup"><span data-stu-id="ec473-105">Therefore, not all the rules that are included by default in the commerce transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="ec473-106">Pour tenir compte des différences, Microsoft Dynamics 365 Commerce fournit une fonctionnalité permettant de désactiver les règles qui ne s'appliquent pas.</span><span class="sxs-lookup"><span data-stu-id="ec473-106">To accommodate differences, Microsoft Dynamics 365 Commerce provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="ec473-107">Pour afficher la liste des règles disponibles dans le vérificateur de cohérence des transactions dans votre environnement, et pour afficher le statut de chaque règle, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**, puis sélectionnez l'onglet **Validation de transaction**.</span><span class="sxs-lookup"><span data-stu-id="ec473-107">To view the list of rules that are available in the transaction consistency checker in your environment, and to see the status of each rule, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="ec473-108">Par défaut, le statut de chaque règle est défini sur **Activé**.</span><span class="sxs-lookup"><span data-stu-id="ec473-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="ec473-109">Par conséquent, toutes les règles sont utilisées pour valider les transactions avant qu'elles soient extraites dans les relevés commerciaux.</span><span class="sxs-lookup"><span data-stu-id="ec473-109">Therefore, all the rules are used to validate transactions before they are pulled into the commerce statements.</span></span> <span data-ttu-id="ec473-110">Pour désactiver une règle, modifiez son statut en **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="ec473-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="ec473-111">Les règles désactivées ne sont pas prises en compte lorsque les transactions sont validées au cours du processus de calcul des relevés.</span><span class="sxs-lookup"><span data-stu-id="ec473-111">Disabled rules aren't considered when transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="ec473-112">Pour contourner l'ensemble du processus de validation, indépendamment des règles activées, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**, puis, dans l'onglet **Validation de transaction**, définissez l'option **Désactiver le vérificateur de cohérence pour les transactions commerciales** sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ec473-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Commerce transactions** option to **Yes**.</span></span> <span data-ttu-id="ec473-113">Une fois cette option définie sur **Non**, elle ne peut pas être redéfinie sur **Oui** à partir de l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ec473-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
