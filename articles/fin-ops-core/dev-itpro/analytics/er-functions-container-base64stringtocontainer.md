---
title: Fonction Base64StringToContainer pour la gestion des états électroniques
description: Cette rubrique fournit des informations sur l’utilisation de la fonction Base64StringToContainer pour la gestion des états électroniques.
author: NickSelin
manager: kfend
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0e92ae41a3e0f03cb14d4791ab768f096f2a0523
ms.sourcegitcommit: e8a46e127d70986539c138b27a641bff6f6874d0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2020
ms.locfileid: "4739077"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="c40aa-103">Fonction Base64StringToContainer pour la gestion des états électroniques</span><span class="sxs-lookup"><span data-stu-id="c40aa-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c40aa-104">La [fonction](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` convertit l’entrée spécifique de type *Chaîne* en un élément de données de type *[Conteneur](er-functions-category-container.md)*.</span><span class="sxs-lookup"><span data-stu-id="c40aa-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="c40aa-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c40aa-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="c40aa-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="c40aa-106">Arguments</span></span>

<span data-ttu-id="c40aa-107">`input` : *Chaîne*</span><span class="sxs-lookup"><span data-stu-id="c40aa-107">`input`: *String*</span></span>

<span data-ttu-id="c40aa-108">Chemin d’accès valide d’une source de données du type *Chaîne*.</span><span class="sxs-lookup"><span data-stu-id="c40aa-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c40aa-109">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="c40aa-109">Return values</span></span>

<span data-ttu-id="c40aa-110">*Conteneur*</span><span class="sxs-lookup"><span data-stu-id="c40aa-110">*Container*</span></span>

<span data-ttu-id="c40aa-111">Valeur binaire résultante au format BLOB (Binary Large Object).</span><span class="sxs-lookup"><span data-stu-id="c40aa-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c40aa-112">Notes d’utilisation</span><span class="sxs-lookup"><span data-stu-id="c40aa-112">Usage notes</span></span>

<span data-ttu-id="c40aa-113">L’exception « Paramètre non valide » est levée si la chaîne entrante ne fournit pas un groupe Base64 correct de schémas de codage binaire en texte.</span><span class="sxs-lookup"><span data-stu-id="c40aa-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="c40aa-114">Exemple</span><span class="sxs-lookup"><span data-stu-id="c40aa-114">Example</span></span>

<span data-ttu-id="c40aa-115">Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :</span><span class="sxs-lookup"><span data-stu-id="c40aa-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="c40aa-116">La source de données racine **DocuTypeGroupEnum** de type *Dynamics 365 for Operations / Énumération* qui fait référence à l’énumération de l’application **DocuTypeGroup**</span><span class="sxs-lookup"><span data-stu-id="c40aa-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="c40aa-117">La source de données racine **Client** de type *Dynamics 365 for Operations / Enregistrements de la table* qui fait référence à la table d’application **CustTable**</span><span class="sxs-lookup"><span data-stu-id="c40aa-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="c40aa-118">La source de données **\#Médias** de type *Champ calculé* qui est configurée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="c40aa-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="c40aa-119">elle est ajoutée en tant que source de données enfant de la source de données **Client**.</span><span class="sxs-lookup"><span data-stu-id="c40aa-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="c40aa-120">Elle contient l’expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span><span class="sxs-lookup"><span data-stu-id="c40aa-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="c40aa-121">La source de données **\#MediaAsBase64String** de type *Champ calculé* qui est configurée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="c40aa-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="c40aa-122">elle est ajoutée en tant que source de données enfant de la source de données **Client.’\#Médias**.</span><span class="sxs-lookup"><span data-stu-id="c40aa-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="c40aa-123">Elle contient l’expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span><span class="sxs-lookup"><span data-stu-id="c40aa-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="c40aa-124">La source de données **\#BlobFomBase64** de type *Champ calculé* qui est configurée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="c40aa-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="c40aa-125">elle est ajoutée en tant que source de données enfant de la source de données **Client.’\#Médias**.</span><span class="sxs-lookup"><span data-stu-id="c40aa-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="c40aa-126">Elle contient l’expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span><span class="sxs-lookup"><span data-stu-id="c40aa-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="c40aa-127">Dans cet exemple, la source de données **\#MediaAsBase64String** code le contenu binaire de la pièce jointe multimédia actuelle sous forme de texte qui représente un groupe Base64 de schémas de codage binaire-texte.</span><span class="sxs-lookup"><span data-stu-id="c40aa-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="c40aa-128">La source de données **\#BlobFomBase64** décode la chaîne Base64 et renvoie une valeur binaire au format BLOB.</span><span class="sxs-lookup"><span data-stu-id="c40aa-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Exemple de sources de données sur la page Concepteur de mise en correspondance de modèles pour la gestion des états électroniques](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="c40aa-130">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="c40aa-130">Additional resources</span></span>

[<span data-ttu-id="c40aa-131">Fonctions Conteneur</span><span class="sxs-lookup"><span data-stu-id="c40aa-131">Container functions</span></span>](er-functions-category-container.md)
