---
title: Fonction FORMAT ER
description: Cette rubrique fournit des informations sur l’utilisation de la fonction FORMAT États électroniques (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 8b347a7209ee543f6bd687c2864203eb632d6a4a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688411"
---
# <a name="format-er-function"></a>Fonction FORMAT ER

[!include [banner](../includes/banner.md)]

La fonction `FORMAT` renvoie à la chaîne spécifiée comme valeur de *Chaîne* une fois qu’elle a été mise en forme en substituant toutes les occurrences de **%N** par le *N* ième argument.

## <a name="syntax"></a>Syntaxe

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>Arguments

`string` : *Chaîne*

Référence à une source de données du type *Chaîne* qui doit être formatée. Cet argument est obligatoire.

`argument 1` : *Chaîne*

Premier argument utilisé pour remplacer les occurrences de **%1**. Cet argument est obligatoire.

`argument N` : *Chaîne*

*N* ième argument utilisé pour remplacer les occurrences de **%2**, **%3**, etc. Ces arguments supplémentaires sont facultatifs.

## <a name="return-values"></a>Valeurs de retour

*Chaîne*

Valeur de texte résultante.

## <a name="usage-notes"></a>Notes d’utilisation

Si un argument n’est pas fourni pour un paramètre, le paramètre est renvoyé comme **"%N"** dans la chaîne. Pour les valeurs de type *Réel*, la conversion de chaîne par défaut est limitée à deux décimales.

## <a name="example"></a>Exemple

Dans l’illustration suivante, la source de données **PaymentModel** renvoie une liste des enregistrements client à l’aide du composant **Client**. Elle renvoie la valeur de la date de traitement en utilisant le champ **ProcessingDate**.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

Dans le format d’états électroniques (ER) conçu pour générer un fichier électronique pur les clients sélectionnés, **PaymentModel** est sélectionné comme source de données et contrôle le flux de processus. Si un client sélectionné est arrêté à la date lorsque l’état est traité, une exception est levée pour informer l’utilisateur. La formule qui est conçue pour ce type de contrôle de traitement peut utiliser les ressources suivantes :

- Libellé SYS70894, avec le texte suivant :

    - **Pour l’anglais (États-Unis) :** « Nothing to print »
    - **Pour l’allemand :** « Nichts zu drucken »

- Libellé SYS18389, avec le texte suivant :

    - **Pour l’anglais (États-Unis) :** "Customer %1 is stopped for %2".
    - **Pour l’allemand :** "Debitor "%1’’ wird für %2 gesperrt".

Voici l’expression qui peut être conçue.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

Si un rapport est traité pour le client **Litware Retail** le 17 décembre 2015, dans la culture **EN-US** et la langue **EN-US**, cette formule renvoie le texte suivant, qui peut être présenté à l’utilisateur comme message d’exception :

*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*

Si le même état est traité pour le client **Litware Retail** le 17 décembre 2015, dans la culture **DE** et la langue **DE**, la formule renvoie le texte suivant, qui utilise un format de date différent :

*Nichts zu drucken. Debitor ’Litware Retail’ wird für 17.12.2015 gesperrt.*

>[!NOTE]
> La syntaxe suivante est appliquée aux formules de génération d’états électroniques pour les libellés :
>
> - **Pour les libellés des ressources dans l’application Microsoft Dynamics 365 Finance :** **\@X**, où **X** est l’ID libellé de l’arbre d’objets d’application (AOA)
> - **Pour les libellés se trouvant dans les configurations d’ER :** **@GER_LABEL:X**, où **X** est l’ID libellé dans la configuration d’ER

## <a name="additional-resources"></a>Ressources supplémentaires

[Fonctions texte](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]