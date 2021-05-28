---
title: Vous ne pouvez pas appliquer un modèle à un produit lancé
description: Vous ne pouvez pas appliquer un modèle à un produit lancé.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ad6efdced9bce924fbf5bc207c92fa2c3a6c79d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026500"
---
# <a name="you-cant-apply-a-template-to-create-a-released-product"></a><span data-ttu-id="30523-103">Vous ne pouvez pas appliquer un modèle pour créer un produit lancé</span><span class="sxs-lookup"><span data-stu-id="30523-103">You can't apply a template to create a released product</span></span>

<span data-ttu-id="30523-104">Numéro de la base de connaissances : 4612097</span><span class="sxs-lookup"><span data-stu-id="30523-104">KB number: 4612097</span></span>

## <a name="symptoms"></a><span data-ttu-id="30523-105">Symptômes</span><span class="sxs-lookup"><span data-stu-id="30523-105">Symptoms</span></span>

<span data-ttu-id="30523-106">Lorsque vous créez un nouveau produit lancé en utilisant la boîte de dialogue **Nouveau produit lancé**, vous pouvez sélectionner un modèle.</span><span class="sxs-lookup"><span data-stu-id="30523-106">When you create a new released product by using the **New released product** dialog box, you can select a template.</span></span> <span data-ttu-id="30523-107">Le modèle doit fournir des paramètres par défaut pour de nombreux champs du nouveau produit lancé.</span><span class="sxs-lookup"><span data-stu-id="30523-107">The template is supposed to provide default settings for many fields of the new released product.</span></span> <span data-ttu-id="30523-108">Cependant, certains ou tous les champs ne sont pas définis une fois que vous avez sélectionné le modèle.</span><span class="sxs-lookup"><span data-stu-id="30523-108">However, some or all of the fields aren't set after you select the template.</span></span>

## <a name="cause"></a><span data-ttu-id="30523-109">Cause</span><span class="sxs-lookup"><span data-stu-id="30523-109">Cause</span></span>

<span data-ttu-id="30523-110">De nombreuses pages dans Microsoft Dynamics 365 Supply Chain Management vous permettent de créer un modèle qui établit les paramètres initiaux pour les enregistrements affichés sur ces pages.</span><span class="sxs-lookup"><span data-stu-id="30523-110">Many pages in Microsoft Dynamics 365 Supply Chain Management let you create a template that establishes initial settings for the records that are shown on those pages.</span></span> <span data-ttu-id="30523-111">Vous pouvez créer l'un de ces modèles en sélectionnant **Enregistrer les informations** dans l'onglet **Options** du volet Actions.</span><span class="sxs-lookup"><span data-stu-id="30523-111">You can create one of these templates by selecting **Record info** on the **Options** tab of the Action Pane.</span></span> <span data-ttu-id="30523-112">Cependant, les produits lancés sont beaucoup plus complexes que la plupart des autres types d'enregistrements.</span><span class="sxs-lookup"><span data-stu-id="30523-112">However, released products are much more complex than most other types of records.</span></span> <span data-ttu-id="30523-113">Bien que vous puissiez sélectionner **Enregistrer les informations** dans la page **Produits lancés** pour créer un modèle, et bien que vous puissiez sélectionner ce modèle lorsque vous créez un produit lancé, le modèle ne fournira pas les valeurs de champ attendues pour le nouveau produit lancé.</span><span class="sxs-lookup"><span data-stu-id="30523-113">Although you can select **Record info** on the **Released products** page to create a template, and although you can select that template when you create a released product, the template won't provide the expected field values for the new released product.</span></span> <span data-ttu-id="30523-114">Par conséquent, vous ne pouvez pas utiliser de modèles "informations d'enregistrement" pour les produits lancés.</span><span class="sxs-lookup"><span data-stu-id="30523-114">Therefore, you can't use "record info" templates for released products.</span></span> <span data-ttu-id="30523-115">Au lieu de cela, vous devez créer des modèles de produits dédiés.</span><span class="sxs-lookup"><span data-stu-id="30523-115">Instead, you must create dedicated product templates.</span></span>

## <a name="resolution"></a><span data-ttu-id="30523-116">Résolution</span><span class="sxs-lookup"><span data-stu-id="30523-116">Resolution</span></span>

<span data-ttu-id="30523-117">Pour créer un modèle de produit, utilisez le menu **Modèle** dans l'onglet **Produit** du volet Actions, pas le bouton **Enregistrer les informations** dans l'onglet **Options**.</span><span class="sxs-lookup"><span data-stu-id="30523-117">To create a product template, use the **Template** menu on the **Product** tab of the Action Pane, not the **Record info** button on the **Options** tab.</span></span>

1. <span data-ttu-id="30523-118">Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.</span><span class="sxs-lookup"><span data-stu-id="30523-118">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="30523-119">Dans le volet Actions, dans l'onglet **Produit** au sein du groupe **Nouveau**, sélectionnez **Modèle**, puis sélectionnez soit **Créer un modèle personnel**, soit **Créer un modèle partagé**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="30523-119">On the Action Pane, on the **Product** tab, in the **New** group, select **Template**, and then select either **Create personal template** or **Create shared template**, as appropriate.</span></span>
