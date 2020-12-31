---
title: Fonction QRCODE ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction QRCODE États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b62ed829202028ca0cbf95a0dbc3460d047ca5a5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682965"
---
# <a name="qrcode-er-function"></a><span data-ttu-id="c7782-103">Fonction QRCODE ER</span><span class="sxs-lookup"><span data-stu-id="c7782-103">QRCODE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7782-104">La fonction `QRCODE` renvoie une valeur de *Conteneur* qui présente l’une image de code à réponse rapide (code QR) de la chaîne spécifiée au format binaire.</span><span class="sxs-lookup"><span data-stu-id="c7782-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7782-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c7782-105">Syntax</span></span>

```vb
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="c7782-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="c7782-106">Arguments</span></span>

<span data-ttu-id="c7782-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c7782-107">`text`: *String*</span></span>

<span data-ttu-id="c7782-108">Valeur *Chaîne* qui représente le texte d’origine.</span><span class="sxs-lookup"><span data-stu-id="c7782-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="c7782-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="c7782-109">Return values</span></span>

<span data-ttu-id="c7782-110">*Conteneur*</span><span class="sxs-lookup"><span data-stu-id="c7782-110">*Container*</span></span>

<span data-ttu-id="c7782-111">Flux binaire résultant.</span><span class="sxs-lookup"><span data-stu-id="c7782-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="c7782-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="c7782-112">Example</span></span>

<span data-ttu-id="c7782-113">Vous pouvez configurer un format d’états électroniques (ER) pour générer un document sortant dans le format Microsoft Office (classeurs Excel ou documents Word) en utilisant un modèle prédéfini.</span><span class="sxs-lookup"><span data-stu-id="c7782-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="c7782-114">Ce modèle peut contenir un objet **Image** (classeur Excel) ou un **Contrôle du contenu de l’image** (Document Word) comme espace réservé pour une image de code QR.</span><span class="sxs-lookup"><span data-stu-id="c7782-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="c7782-115">Vous devez ajouter au format ER configuré un élément **Cellule** qui sera utilisé pour remplir cet espace réservé.</span><span class="sxs-lookup"><span data-stu-id="c7782-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="c7782-116">Pour spécifier quelles informations seront stockées dans un code QR, vous devez définir une liaison pour cet élément **Cellule**.</span><span class="sxs-lookup"><span data-stu-id="c7782-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="c7782-117">Par exemple, vous pouvez configurer une telle liaison comme contenant l’expression suivante :</span><span class="sxs-lookup"><span data-stu-id="c7782-117">For example, you can configure such binding as containing the following expression:</span></span>

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="c7782-118">Lorsque vous exécutez le format ER configuré, la valeur de texte du champ **LabelText** de la source de données **model.ListOfShelfLabels** sera utilisée pour générer une image de code QR.</span><span class="sxs-lookup"><span data-stu-id="c7782-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="c7782-119">Cette image remplacera un espace réservé d’image de code QR dans le modèle de document en utilisant pour générer un document sortant.</span><span class="sxs-lookup"><span data-stu-id="c7782-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="c7782-120">Lorsque cette image du document généré est numérisée, elle renvoie le texte qui a été extrait du champ **LabelText** de la source de données **model.ListOfShelfLabels**.</span><span class="sxs-lookup"><span data-stu-id="c7782-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="c7782-121">Pour plus d’informations, voir [Intégrer des images et des formes dans les documents que vous générez à l’aide de la gestion d’ER](electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="c7782-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c7782-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c7782-122">Additional resources</span></span>

[<span data-ttu-id="c7782-123">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="c7782-123">Text functions</span></span>](er-functions-category-text.md)
