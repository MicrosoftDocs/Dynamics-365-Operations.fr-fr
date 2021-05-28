---
title: Valeur de champ incorrecte dans TaxTrans
description: Cette rubrique fournit des informations sur la résolution des problèmes de valeurs de champ incorrectes dans TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020161"
---
# <a name="incorrect-field-value-in-taxtrans"></a><span data-ttu-id="17e3c-103">Valeur de champ incorrecte dans TaxTrans</span><span class="sxs-lookup"><span data-stu-id="17e3c-103">Incorrect field value in TaxTrans</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17e3c-104">Si une valeur de champ est incorrecte dans **TaxTrans**, utilisez les informations de cette rubrique pour essayer de résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="17e3c-104">If a field value in **TaxTrans** is incorrect, use the information in this topic to try to resolve the issue.</span></span>

## <a name="overview-of-values"></a><span data-ttu-id="17e3c-105">Aperçu des valeurs</span><span class="sxs-lookup"><span data-stu-id="17e3c-105">Overview of values</span></span>
<span data-ttu-id="17e3c-106">La liste suivante montre que **TaxTrans**, **TaxUncommitted** et **TmpTaxWorkTrans** sont des ensembles de données similaires, mais fonctionnent différemment.</span><span class="sxs-lookup"><span data-stu-id="17e3c-106">The following list shows how **TaxTrans**, **TaxUncommitted**, and **TmpTaxWorkTrans** are similar data sets, but in work differently.</span></span>

  - <span data-ttu-id="17e3c-107">**TaxTrans** est le résultat final de la transaction fiscale affiché et conservé dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="17e3c-107">**TaxTrans** is the final posted tax transaction result persisted in the database.</span></span>
  - <span data-ttu-id="17e3c-108">**TaxUncommitted** est le résultat de taxe calculé intermédiaire conservé dans la base de données (le cas échéant), qui sera utilisé plus tard lors de la comptabilisation.</span><span class="sxs-lookup"><span data-stu-id="17e3c-108">**TaxUncommitted** is the intermediate calculated tax result persisted in the database (if applicable), which will be used later in posting.</span></span>
  - <span data-ttu-id="17e3c-109">**TmpTaxWorkTrans** est le résultat de taxe calculé temporaire dans la table en mémoire (Type de table = InMemory).</span><span class="sxs-lookup"><span data-stu-id="17e3c-109">**TmpTaxWorkTrans** is the temporary calculated tax result in the in-memory table (Table Type = InMemory).</span></span>

<span data-ttu-id="17e3c-110">Si vous trouvez la cause première d'une colonne **TaxTrans** incorrecte, vous avez également trouvé la cause première d'une colonne **TaxUncommitted** ou **TmpTaxWorkTrans** incorrecte.</span><span class="sxs-lookup"><span data-stu-id="17e3c-110">If you find the root cause of an incorrect **TaxTrans** column, you've also found the root cause of an incorrect **TaxUncommitted** or **TmpTaxWorkTrans** column.</span></span> <span data-ttu-id="17e3c-111">En effet, les trois colonnes sont copiées les unes des autres.</span><span class="sxs-lookup"><span data-stu-id="17e3c-111">This is because the three columns are copied from each other.</span></span>

<span data-ttu-id="17e3c-112">En règle générale, lors du calcul de la taxe, **TmpTaxWorkTrans** est généré, puis, le cas échéant, **TaxUncommitted** est généré.</span><span class="sxs-lookup"><span data-stu-id="17e3c-112">Typically, during tax calculation, **TmpTaxWorkTrans** is generated, and then, if applicable, **TaxUncommitted** is generated.</span></span> <span data-ttu-id="17e3c-113">Lors de la validation de la taxe, **TaxTrans** est généré.</span><span class="sxs-lookup"><span data-stu-id="17e3c-113">During tax posting, **TaxTrans** is generated.</span></span>


## <a name="add-breakpoints"></a><span data-ttu-id="17e3c-114">Ajouter des points d'arrêt</span><span class="sxs-lookup"><span data-stu-id="17e3c-114">Add breakpoints</span></span>
<span data-ttu-id="17e3c-115">Procédez comme suit pour ajouter des points d'arrêt :</span><span class="sxs-lookup"><span data-stu-id="17e3c-115">To add breakpoints, complete the following steps:</span></span> 

1. <span data-ttu-id="17e3c-116">Ajoutez des extensions et des points d'arrêt dans *insérer()* et *mettre à jour()* dans les extensions comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="17e3c-116">Add extensions and breakpoints in *insert()* and *update()* in the extensions as shown below.</span></span>

     - <span data-ttu-id="17e3c-117">**TaxTrans**</span><span class="sxs-lookup"><span data-stu-id="17e3c-117">**TaxTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="17e3c-118">**TaxUncommitted**</span><span class="sxs-lookup"><span data-stu-id="17e3c-118">**TaxUncommitted**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="17e3c-119">**TmpTaxWorkTrans**</span><span class="sxs-lookup"><span data-stu-id="17e3c-119">**TmpTaxWorkTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. <span data-ttu-id="17e3c-120">Vous pouvez également ajouter des points d'arrêt directement lorsque **TaxUncommitted** n'est pas inclus.</span><span class="sxs-lookup"><span data-stu-id="17e3c-120">Alternatively, you can add breakpoints directly when **TaxUncommitted** is not included.</span></span>

     - <span data-ttu-id="17e3c-121">*TaxTrans.insert()*, *TaxTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="17e3c-121">*TaxTrans.insert()*, *TaxTrans.update()*</span></span>
     - <span data-ttu-id="17e3c-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="17e3c-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span></span>

## <a name="reproduce-and-debug"></a><span data-ttu-id="17e3c-123">Reproduire et déboguer</span><span class="sxs-lookup"><span data-stu-id="17e3c-123">Reproduce and debug</span></span>

<span data-ttu-id="17e3c-124">Une fois les points d'arrêt définis, chaque modification de la persistance des données est visible pendant le débogage.</span><span class="sxs-lookup"><span data-stu-id="17e3c-124">After the breakpoints are set, every data persistency change is visible during debugging.</span></span> <span data-ttu-id="17e3c-125">Pour trouver la cause première d'une colonne incorrecte de **TaxTrans**, **TaxUncommitted** ou **TmpTaxWorkTrans**, passez en revue et notez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="17e3c-125">To find the root cause of an incorrect column of **TaxTrans**, **TaxUncommitted**, or **TmpTaxWorkTrans**, review and note the following items:</span></span>

- <span data-ttu-id="17e3c-126">Le dernier point d'arrêt où la colonne est correcte.</span><span class="sxs-lookup"><span data-stu-id="17e3c-126">The last breakpoint where the column is correct.</span></span>
- <span data-ttu-id="17e3c-127">Le premier point d'arrêt où la colonne est incorrecte.</span><span class="sxs-lookup"><span data-stu-id="17e3c-127">The first breakpoint where the column is incorrect.</span></span>
- <span data-ttu-id="17e3c-128">Ce qu'il se passe entre ces deux points.</span><span class="sxs-lookup"><span data-stu-id="17e3c-128">What happens in between those two points.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="17e3c-129">Déterminer si la personnalisation existe</span><span class="sxs-lookup"><span data-stu-id="17e3c-129">Determine whether customization exists</span></span>
<span data-ttu-id="17e3c-130">Si vous avez terminé les étapes des sections précédentes mais que vous n'avez pu résoudre le problème, déterminez s'il existe une personnalisation.</span><span class="sxs-lookup"><span data-stu-id="17e3c-130">If you've completed the steps in the previous sections but have not been able to resolve the issue, determine whether customization exists.</span></span> <span data-ttu-id="17e3c-131">Si aucune personnalisation n'existe, contactez le support Microsoft pour obtenir de l'aide.</span><span class="sxs-lookup"><span data-stu-id="17e3c-131">If no customization exists, contact Microsoft Support for assistance.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

