--- 
title: " Configurer des recommandations de produit exécutées par Machine Learning"
description: "Cette procédure actualise les données du magasin des entités qui sont utilisées par le système Machine Learning exécutant les recommandations de produit, puis active les recommandations de produit pour les clients POS."
author: ashishmsft
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BIMeasurementDeployManagementEntityStore, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 6c3f838372cc17414741ccc3165e129c46d19a6a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/11/2018

---
# <a name="configure-machine-learning-powered-product-recommendations"></a><span data-ttu-id="df6c0-103"> Configurer des recommandations de produit exécutées par Machine Learning</span><span class="sxs-lookup"><span data-stu-id="df6c0-103">Configure machine learning-powered product recommendations</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="df6c0-104">Cette procédure actualise les données du magasin des entités qui sont utilisées par le système Machine Learning exécutant les recommandations de produit, puis active les recommandations de produit pour les clients POS.</span><span class="sxs-lookup"><span data-stu-id="df6c0-104">This procedure refreshes the data in the Entity store that is used by the machine learning system that powers product recommendations, and then enables product recommendations on POS clients.</span></span> <span data-ttu-id="df6c0-105">Cette procédure utilise la société USRT dans les données de démonstration.</span><span class="sxs-lookup"><span data-stu-id="df6c0-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="df6c0-106">Accédez à Administration système > Paramétrage > Magasin des entités.</span><span class="sxs-lookup"><span data-stu-id="df6c0-106">Go to System administration > Setup > Entity Store.</span></span>
2. <span data-ttu-id="df6c0-107">Dans la liste, recherchez et sélectionnez l'enregistrement « RetailSales ».</span><span class="sxs-lookup"><span data-stu-id="df6c0-107">In the list, find and select the record 'RetailSales'.</span></span>
3. <span data-ttu-id="df6c0-108">Cliquez sur Actualiser.</span><span class="sxs-lookup"><span data-stu-id="df6c0-108">Click Refresh.</span></span>
4. <span data-ttu-id="df6c0-109">Cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="df6c0-109">Click OK.</span></span>
5. <span data-ttu-id="df6c0-110">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df6c0-110">Close the page.</span></span>
6. <span data-ttu-id="df6c0-111">Accédez à Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres des ventes au détail.</span><span class="sxs-lookup"><span data-stu-id="df6c0-111">Go to Retail and commerce > Headquarters setup > Parameters > Retail parameters.</span></span>
7. <span data-ttu-id="df6c0-112">Cliquez sur l'onglet Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="df6c0-112">Click the Machine learning tab.</span></span>
8. <span data-ttu-id="df6c0-113">Sélectionnez Oui dans le champ Activer les recommandations produit.</span><span class="sxs-lookup"><span data-stu-id="df6c0-113">Select 'Yes' in the Enable product recommendations field.</span></span>
    * <span data-ttu-id="df6c0-114">Si vous recevez le message « Impossible de récupérer les modèles de recommandation », cela est dû au fait que vous avez actualisé le magasin des entités très récemment et le système n'a peut-être pas terminé d'assimiler les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="df6c0-114">If you receive the message "The recommendation models couldn't be retrieved", it’s because you refreshed the Entity Store very recently and the system may not have finished assimilating the new data.</span></span> <span data-ttu-id="df6c0-115">Patientez 2 ou 3 heures et recommencez.</span><span class="sxs-lookup"><span data-stu-id="df6c0-115">Wait 2-3 hours and try again.</span></span>  
9. <span data-ttu-id="df6c0-116">Cliquez sur Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="df6c0-116">Click Save.</span></span>
10. <span data-ttu-id="df6c0-117">Fermez la page.</span><span class="sxs-lookup"><span data-stu-id="df6c0-117">Close the page.</span></span>


