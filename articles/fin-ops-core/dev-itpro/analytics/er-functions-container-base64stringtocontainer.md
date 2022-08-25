---
title: Fonction Base64StringToContainer pour la gestion des états électroniques
description: Cet article fournit des informations sur l’utilisation de la fonction Base64StringToContainer pour la gestion des états électroniques.
author: kfend
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 96dfffc3d899f1106c6c931efb08c941f5b3c1a6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291232"
---
# <a name="base64stringtocontainer-er-function"></a>Fonction Base64StringToContainer pour la gestion des états électroniques

[!include [banner](../includes/banner.md)]

La [fonction](er-formula-language.md#Functions) `BASE64STRINGTOCONTAINER` convertit l’entrée spécifique de type *Chaîne* en un élément de données de type *[Conteneur](er-functions-category-container.md)*.

## <a name="syntax"></a>Syntaxe

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>Arguments

`input` : *Chaîne*

Chemin d’accès valide d’une source de données du type *Chaîne*.

## <a name="return-values"></a>Valeurs de retour

*Conteneur*

Valeur binaire résultante au format BLOB (Binary Large Object).

## <a name="usage-notes"></a>Notes d’utilisation

L’exception « Paramètre non valide » est levée si la chaîne entrante ne fournit pas un groupe Base64 correct de schémas de codage binaire en texte.

## <a name="example"></a>Exemple

Vous définissez les sources de données suivantes dans la mise en correspondance des modèles :

- La source de données racine **DocuTypeGroupEnum** de type *Dynamics 365 for Operations / Énumération* qui fait référence à l’énumération de l’application **DocuTypeGroup**
- La source de données racine **Client** de type *Dynamics 365 for Operations / Enregistrements de la table* qui fait référence à la table d’application **CustTable**
- La source de données **\#Médias** de type *Champ calculé* qui est configurée de la manière suivante :

    - elle est ajoutée en tant que source de données enfant de la source de données **Client**.
    - Elle contient l’expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.

- La source de données **\#MediaAsBase64String** de type *Champ calculé* qui est configurée de la manière suivante :

    - elle est ajoutée en tant que source de données enfant de la source de données **Client.’\#Médias**.
    - Elle contient l’expression `Customer.'#Media'.'getFileContentAsBase64String()'`.

- La source de données **\#BlobFomBase64** de type *Champ calculé* qui est configurée de la manière suivante :

    - elle est ajoutée en tant que source de données enfant de la source de données **Client.’\#Médias**.
    - Elle contient l’expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.

Dans cet exemple, la source de données **\#MediaAsBase64String** code le contenu binaire de la pièce jointe multimédia actuelle sous forme de texte qui représente un groupe Base64 de schémas de codage binaire-texte. La source de données **\#BlobFomBase64** décode la chaîne Base64 et renvoie une valeur binaire au format BLOB.

![Exemple de sources de données sur la page Concepteur de mise en correspondance de modèles pour la gestion des états électroniques.](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions du conteneur](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
