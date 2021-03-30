---
title: Créer et associer des caisses enregistreuses
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
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af9743f17cebb3484c3ec5b0315347c575a474bd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246994"
---
# <a name="create-and-associate-registers"></a><span data-ttu-id="08927-103">Créer et associer des caisses enregistreuses</span><span class="sxs-lookup"><span data-stu-id="08927-103">Create and associate registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08927-104">Cette procédure montre comment créer un registre de point de vente.</span><span class="sxs-lookup"><span data-stu-id="08927-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="08927-105">La société fictive USRT sert d'exemple dans cette procédure.</span><span class="sxs-lookup"><span data-stu-id="08927-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="08927-106">Accédez à Commerce et vente au détail > Paramétrage du canal > Paramétrage du PD > Caisses enregistreuses.</span><span class="sxs-lookup"><span data-stu-id="08927-106">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="08927-107">Cliquez sur Nouveau.</span><span class="sxs-lookup"><span data-stu-id="08927-107">Click New.</span></span>
3. <span data-ttu-id="08927-108">Dans le champ Numéro de registre, tapez un identifiant pour le nouveau registre.</span><span class="sxs-lookup"><span data-stu-id="08927-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="08927-109">L'ID de registre inclut généralement des codes qui aident à associer le registre au magasin auquel il appartient, et à l'emplacement dans le magasin.</span><span class="sxs-lookup"><span data-stu-id="08927-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="08927-110">Dans le champ Nom, entrez un nom descriptif pour le registre.</span><span class="sxs-lookup"><span data-stu-id="08927-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="08927-111">Entrez ou sélectionnez une valeur dans le champ Numéro de magasin.</span><span class="sxs-lookup"><span data-stu-id="08927-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="08927-112">Saisissez ou sélectionnez une valeur dans le champ Profil matériel.</span><span class="sxs-lookup"><span data-stu-id="08927-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="08927-113">Les profils matériels permettent de spécifier les périphériques qui seront associés à la caisse enregistreuse, comme le tiroir-caisse ou l'imprimante de tickets.</span><span class="sxs-lookup"><span data-stu-id="08927-113">Hardware profiles are used to specify the peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="08927-114">Saisissez ou sélectionnez une valeur dans le champ Profil visuel.</span><span class="sxs-lookup"><span data-stu-id="08927-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="08927-115">Des profils visuels sont utilisés pour spécifier les images utilisées dans l’arrière-plan de l’ouverture de session et l’arrière-plan du PDV, ainsi que les thèmes pour le PDV.</span><span class="sxs-lookup"><span data-stu-id="08927-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="08927-116">Tapez une valeur dans le champ Numéro de caisse enregistreuse TEF du TPV.</span><span class="sxs-lookup"><span data-stu-id="08927-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="08927-117">Le numéro TEF du TPV est utilisé pour informer le processeur de paiement du terminal de paiement qui envoie des demandes d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="08927-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="08927-118">Cette valeur s'appelle souvent « ID terminal » ou « TID ».</span><span class="sxs-lookup"><span data-stu-id="08927-118">This value is often called the "Terminal ID" or "TID".</span></span> <span data-ttu-id="08927-119">On trouve généralement le terme TID sur un autocollant sur le dispositif de paiement.</span><span class="sxs-lookup"><span data-stu-id="08927-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="08927-120">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="08927-120">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]