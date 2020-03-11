---
title: Fonction QRCODE ER
description: Cette rubrique fournit des informations sur l'utilisation de la fonction QRCODE États électroniques (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a52dbce29140591baf4be97baef237dce1f2511
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040846"
---
# <span data-ttu-id="40805-103"><a name="QRCODE">Fonction QRCODE ER</a></span><span class="sxs-lookup"><span data-stu-id="40805-103"><a name="QRCODE">QRCODE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40805-104">La fonction `QRCODE` renvoie une valeur de *Conteneur* qui présente l'une image de code à réponse rapide (code QR) de la chaîne spécifiée au format binaire.</span><span class="sxs-lookup"><span data-stu-id="40805-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="40805-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="40805-105">Syntax</span></span>

```vb
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="40805-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="40805-106">Arguments</span></span>

<span data-ttu-id="40805-107">`text` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="40805-107">`text`: *String*</span></span>

<span data-ttu-id="40805-108">Valeur *Chaîne* qui représente le texte d'origine.</span><span class="sxs-lookup"><span data-stu-id="40805-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="40805-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="40805-109">Return values</span></span>

<span data-ttu-id="40805-110">*Conteneur*</span><span class="sxs-lookup"><span data-stu-id="40805-110">*Container*</span></span>

<span data-ttu-id="40805-111">Flux binaire résultant.</span><span class="sxs-lookup"><span data-stu-id="40805-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="40805-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="40805-112">Example</span></span>

<span data-ttu-id="40805-113">Vous pouvez configurer un format d'états électroniques (ER) pour générer un document sortant dans le format Microsoft Office (classeurs Excel ou documents Word) en utilisant un modèle prédéfini.</span><span class="sxs-lookup"><span data-stu-id="40805-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="40805-114">Ce modèle peut contenir un objet **Image** (classeur Excel) ou un **Contrôle du contenu de l'image** (Document Word) comme espace réservé pour une image de code QR.</span><span class="sxs-lookup"><span data-stu-id="40805-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="40805-115">Vous devez ajouter au format ER configuré un élément **Cellule** qui sera utilisé pour remplir cet espace réservé.</span><span class="sxs-lookup"><span data-stu-id="40805-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="40805-116">Pour spécifier quelles informations seront stockées dans un code QR, vous devez définir une liaison pour cet élément **Cellule**.</span><span class="sxs-lookup"><span data-stu-id="40805-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="40805-117">Par exemple, vous pouvez configurer une telle liaison comme contenant l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="40805-117">For example, you can configure such binding as containing the following expression:</span></span>

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="40805-118">Lorsque vous exécutez le format ER configuré, la valeur de texte du champ **LabelText** de la source de données **model.ListOfShelfLabels** sera utilisée pour générer une image de code QR.</span><span class="sxs-lookup"><span data-stu-id="40805-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="40805-119">Cette image remplacera un espace réservé d'image de code QR dans le modèle de document en utilisant pour générer un document sortant.</span><span class="sxs-lookup"><span data-stu-id="40805-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="40805-120">Lorsque cette image du document généré est numérisée, elle renvoie le texte qui a été extrait du champ **LabelText** de la source de données **model.ListOfShelfLabels**.</span><span class="sxs-lookup"><span data-stu-id="40805-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="40805-121">Pour plus d'informations, voir [Intégrer des images et des formes dans les documents que vous générez à l'aide de la gestion d'ER](electronic-reporting-embed-images-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="40805-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40805-122">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="40805-122">Additional resources</span></span>

[<span data-ttu-id="40805-123">Fonctions texte</span><span class="sxs-lookup"><span data-stu-id="40805-123">Text functions</span></span>](er-functions-category-text.md)
