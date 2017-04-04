---
title: "Paramétrage de masques de codes-barres"
description: "Cette rubrique décrit la procédure de paramétrage des caractères de masque de code-barres, masques de codes-barres, et la manière d&quot;affecter des masques de codes-barres à des codes-barres."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fe598799d52cacd84da775ac7ace8cf9a30ae5fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-code-masks"></a>Paramétrage de masques de codes-barres

Cette rubrique décrit la procédure de paramétrage des caractères de masque de code-barres, masques de codes-barres, et la manière d'affecter des masques de codes-barres à des codes-barres.

<a name="set-up-bar-code-mask-characters"></a>Paramétrage des caractères de masque de code-barres
-------------------------------

Les masques de codes-barres permettent de créer des codes-barres et identifier rapidement les codes-barres qui sont analysés dans le point de vente (POS). Les masques sont composés des caractères qui agissent comme espaces réservés qui indiquent le format des codes-barres qui seront créés. Pour configurer un masque de code-barres, vous devez paramétrer des caractères de masque de code-barres. Allez ** au détail et commerce ** &gt; ** à la gestion des stocks ** &gt; ** les codes-barres et les étiquettes ** &gt; ** des caractères de masque **. Cliquez sur ** nouveau ** pour créer des caractères de masque de code-barres. Les caractères de masque peuvent être créés pour indiquer les données suivantes de code-barres.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Field**            | **Description**                                                                                                 |
| **Product**          | L'espace réservé pour l'ID produit.                                                                                     |
| **Any number**       | Permet de spécifier un numéro qui sera dur codé dans les codes-barres.                                                  |
| **Check digit**      | Indique que le format de code-barres dans un masque de code-barres utilise un chiffre de contrôle pour confirmer la validité d'un code-barres. |
| **Size digit**       | Indique la taille dans un code-barres créé pour une variante de produit qui inclut la taille.                                 |
| **Color digit**      | Permet d'indiquer la couleur dans un code-barres créé pour une variante de produit qui inclut la couleur.                               |
| **Style digit**      | Indique le style dans un code-barres créé pour une variante de produit qui inclut un style.                             |
| **EAN license code** | L'espace réservé pour la licence EAN émise pour les codes licence EAN.                                                       |
| **Prix**            | Indique le prix pour les codes-barres incorporés par prix.                                                                   |
| **Quantity**         | Indique la quantité dans la quantité/les codes-barres incorporés poids par aléatoire.                                                |
| **Employee**         | Indique le segment de code-barres pour le numéro d'ID employé utilisé pour la connexion du PDV de code-barres.                                  |
| **Customer**         | Indique le segment d'ID client.                                                                                  |
| ** Saisie de données **       | *Not pourtant implemented.*                                                                                          |
| **Discount code**    | Indique le code remise pour un code-barres utilisé pour ajouter une remise à une transaction de point de vente             |
| **Carte cadeau**        | Indique un numéro de carte cadeau en publiant ou lors de le règlement par carte cadeau.                                               |
| **Loyalty card**     | Ajoute un client fidèle à la transaction, et peut être utilisé lors de le règlement par fidélité.                             |

## <a name="define-bar-code-masks"></a>Définissez des masques de codes-barres
Une fois les caractères de masque de code-barres soient spécifiés pour les masques de codes-barres nécessaires, passez ** au détail et commerce ** &gt; ** à la gestion des stocks ** &gt; ** les codes-barres et les étiquettes ** &gt; ** masque de code-barres paramétré **. Dans cette page, vous pouvez définir des masques de codes-barres qui utilisent les caractères précédemment spécifié. Ces masques de codes-barres seront utilisés lors de les codes-barres et permettent également d'identifier les codes-barres analysés au niveau de le POS.

1.  Cliquez sur ** nouveau ** pour créer un masque de code-barres.
2.  Entrez des valeurs dans ** ID masque ** et ** ** description des champs, puis sélectionnez un masque de code-barres dans ** type ** le champ.
3.  Dans ** général ** la section, sélectionnez une valeur dans ** de codes-barres standard ** le champ, puis spécifiez le préfixe de code-barres, si un code est requis.
4.  Dans ** segment de masque de code-barres ** la section, ajoutez les segments de code-barres qui seront utilisés dans le code-barres à créer.

Comme exemple, pour créer un masque de code-barres à l'ID « produit » de masque, vous feriez ce qui suit :

1.  Créez un masque de code-barres et sélectionnez le type « produit ».
2.  Sélectionnez un de codes-barres standard, par exemple, « Code 39 ».
3.  Indiquez un préfixe à utiliser pour identifier facilement le code-barres. Par exemple, « 22 ".
4.  Ajoutez un segment de masque. Segment de masque de « produit » est sélectionnée.
5.  Fournissez une longueur pour le segment de produit, par exemple, « 10 ". La longueur doit correspondre à la durée d'un ID produit généralement utilisée dans le magasin. Le masque sera affiché comme aperçu dans ** général ** la section sous ** masque **.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Masques de codes-barres d'affecter à des codes-barres
Les masques de codes-barres doivent être affectés à des codes-barres pour pouvoir être utilisés. En continuant l'exemple précédent, d'affecter le masque de code-barres à un code-barres, procédez comme suit :

1.  Allez ** Administration d'organisation ** &gt; ** au paramétrage ** &gt; ** des codes-barres **. Cliquez sur ** nouveau ** pour créer un code-barres.
2.  Entrez des valeurs dans ** codes-barres ** ** paramétrage ** et ** paramétrage ** des champs.
3.  Dans ** général ** section dans, ** type de code-barres ** le champ, sélectionnez le code « 39 ». Dans ** masque ** ** l'ID ** le champ, sélectionnez le masque de « produit » précédemment créé.
4.  Sous ** taille **, entrez « 12 ".
5.  Click **Save**.

Le masque de code-barres peut à présent permettre de créer des codes-barres des produits. Les étapes ci-avant sont des exemples de la création des masques de codes-barres pour les produits, mais elles illustrent également comment créer des masques de codes-barres pour tous les autres types pris en charge des codes-barres. Les masques, les types, et la longueur de codes-barres doivent être ajustés pour une utilisation dans votre environnement spécifique.


