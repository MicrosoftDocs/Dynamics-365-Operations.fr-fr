---
title: " Créer et associer des caisses enregistreuses"
description: Cette procédure montre comment créer un registre de point de vente.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ac75d390b8bbb94c6e039b374b51462d348e355
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057156"
---
# <a name="create-and-associate-registers"></a><span data-ttu-id="a597f-103"> Créer et associer des caisses enregistreuses</span><span class="sxs-lookup"><span data-stu-id="a597f-103">Create and associate registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a597f-104">Cette procédure montre comment créer un registre de point de vente.</span><span class="sxs-lookup"><span data-stu-id="a597f-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="a597f-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="a597f-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="a597f-106">Accédez à Commerce et vente au détail > Paramétrage du canal > Paramétrage du PD > Caisses enregistreuses.</span><span class="sxs-lookup"><span data-stu-id="a597f-106">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="a597f-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="a597f-107">Click New.</span></span>
3. <span data-ttu-id="a597f-108">Dans le champ Numéro de registre, tapez un identifiant pour le nouveau registre.</span><span class="sxs-lookup"><span data-stu-id="a597f-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="a597f-109">L'ID de registre inclut généralement des codes qui aident à associer le registre au magasin auquel il appartient, et à l'emplacement dans le magasin.</span><span class="sxs-lookup"><span data-stu-id="a597f-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="a597f-110">Dans le champ Nom, entrez un nom descriptif pour le registre.</span><span class="sxs-lookup"><span data-stu-id="a597f-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="a597f-111">Entrez ou sélectionnez une valeur dans le champ Numéro de magasin.</span><span class="sxs-lookup"><span data-stu-id="a597f-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="a597f-112">Saisissez ou sélectionnez une valeur dans le champ Profil matériel.</span><span class="sxs-lookup"><span data-stu-id="a597f-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="a597f-113">Les profils matériels permettent de spécifier les périphériques qui seront associés à la caisse enregistreuse, comme le tiroir-caisse ou l'imprimante de tickets.</span><span class="sxs-lookup"><span data-stu-id="a597f-113">Hardware profiles are used to specify the peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="a597f-114">Saisissez ou sélectionnez une valeur dans le champ Profil visuel.</span><span class="sxs-lookup"><span data-stu-id="a597f-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="a597f-115">Des profils visuels sont utilisés pour spécifier les images utilisées dans l’arrière-plan de l’ouverture de session et l’arrière-plan du PDV, ainsi que les thèmes pour le PDV.</span><span class="sxs-lookup"><span data-stu-id="a597f-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="a597f-116">Tapez une valeur dans le champ Numéro de caisse enregistreuse TEF du TPV.</span><span class="sxs-lookup"><span data-stu-id="a597f-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="a597f-117">Le numéro TEF du TPV est utilisé pour informer le processeur de paiement du terminal de paiement qui envoie des demandes d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="a597f-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="a597f-118">Cette valeur s'appelle souvent « ID terminal » ou « TID ».</span><span class="sxs-lookup"><span data-stu-id="a597f-118">This value is often called the "Terminal ID" or “TID”.</span></span> <span data-ttu-id="a597f-119">On trouve généralement le terme TID sur un autocollant sur le dispositif de paiement.</span><span class="sxs-lookup"><span data-stu-id="a597f-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="a597f-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="a597f-120">Click Save.</span></span>

