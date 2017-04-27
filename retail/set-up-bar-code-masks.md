---
title: "Paramétrage de masques de codes-barres"
description: "Cette rubrique décrit la procédure de paramétrage des caractères de masque de code-barres, des masques de code-barres, ainsi que la procédure d&quot;affectation de masques de code-barres aux codes-barres."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core, Retail
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

[!include[banner](includes/banner.md)]


Cette rubrique décrit la procédure de paramétrage des caractères de masque de code-barres, des masques de code-barres, ainsi que la procédure d'affectation de masques de code-barres aux codes-barres.

<a name="set-up-bar-code-mask-characters"></a>Paramétrage des caractères de masque de code-barres
-------------------------------

Les masques de code-barres permettent de créer des codes-barres et d'identifier rapidement les codes-barres qui sont lus au point de vente (PDV). Les masques sont composés de caractères qui ont la fonction d'espaces réservés indiquant le format des codes-barres qui seront créés. Pour configurer un masque de code-barres, vous devez paramétrer des caractères de masque de code-barres. Accédez à **Commerce et vente au détail** &gt; **Gestion des stocks** &gt; **Codes-barres et étiquettes** &gt; **Caractères de masque**. Cliquez sur **Nouveau** pour créer des caractères de masque de code-barres. Les caractères de masque peuvent être créés pour indiquer les données de code-barres suivantes.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Champ**            | **Description**                                                                                                 |
| **Produit**          | Espace réservé pour l'ID produit.                                                                                     |
| **N'importe quel chiffre**       | Permet de spécifier un chiffre qui sera codé en dur dans les codes-barres.                                                  |
| **Chiffre de contrôle**      | Indique que le format de code-barres dans un masque de code-barres utilise un chiffre de contrôle pour confirmer la validité d'un code-barres. |
| **Chiffre de la taille**       | Indique la taille dans un code-barres créé pour une variante de produit qui inclut la taille.                                 |
| **Chiffre de la couleur**      | Indique la couleur dans un code-barres créé pour une variante de produit qui inclut la couleur.                               |
| **Chiffre du style**      | Indique le style dans un code-barres créé pour une variante de produit qui inclut le style.                             |
| **Code licence EAN** | Espace réservé pour la licence EAN émise pour les codes licence EAN.                                                       |
| **Prix**            | Indique le prix pour les codes-barres incorporant le prix.                                                                   |
| **Quantité**         | Indique la quantité dans les codes-barres incorporant la quantité/le poids aléatoire.                                                |
| **Employé**         | Indique le segment de code-barres pour le numéro d'ID employé utilisé pour la connexion au PDV de code-barres.                                  |
| **Client**         | Indique le segment d'ID client.                                                                                  |
| **Saisie de données**       | *Pas encore mis en œuvre.*                                                                                          |
| **Code remise**    | Indique le code remise pour un code-barres utilisé pour ajouter une remise à une transaction de point de vente             |
| **Carte cadeau**        | Indique un numéro de carte cadeau lors de l'émission d'une carte cadeau ou du règlement par ce moyen.                                               |
| **Carte de fidélité**     | Ajoute un numéro de fidélité client à la transaction, et peut être utilisé lors du règlement par points de fidélité.                             |

## <a name="define-bar-code-masks"></a>Définir les masques de codes-barres
Une fois les caractères de masque de codes-barres spécifiés pour les masques de codes-barres requis, accédez à **Commerce et vente au détail** &gt; **Gestion des stocks** &gt; **Codes-barres et étiquettes** &gt; **Paramétrage du masque de code-barres**. Dans cette page, vous pouvez définir des masques de codes-barres qui utilisent les caractères précédemment spécifiés. Ces masques de code-barres seront utilisés lors de la génération de codes-barres et permettent également d'identifier les codes-barres lus au niveau du PDV.

1.  Cliquez sur **Nouveau** pour créer un masque de code-barres.
2.  Entrez des valeurs dans les champs **ID masque** et **Description**, puis sélectionnez un type de masque de code-barres dans le champ **Type**.
3.  Dans la section **Général**, sélectionnez une valeur dans le champ **Norme de code-barres**, puis spécifiez le préfixe de code-barres, si celui-ci est requis.
4.  Dans la section **Segment de masque de code-barres**, ajoutez les segments de code-barres qui seront utilisés dans le code-barres à créer.

Par exemple, pour créer un masque de code-barres avec l'ID « Produit », vous suivriez cette procédure :

1.  Créer un masque de code-barres et sélectionnez le type « Produit ».
2.  Sélectionner une norme de code-barres, par exemple « Code 39 ».
3.  Indiquer un préfixe à utiliser pour identifier facilement le code-barres. Par exemple, « 22 ».
4.  Ajouter un segment de masque. Le segment de masque « Produit » est sélectionné.
5.  Indiquer une longueur pour le segment de produit, par exemple, « 10 ». La longueur doit correspondre à la longueur d'un ID produit communément utilisé dans le magasin. Le masque sera affiché comme aperçu dans la section **Général**, sous **Masque**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Affecter des masques de codes-barres à des code-barres
Les masques de codes-barres doivent être affectés à des codes-barres pour pouvoir être utilisés. En continuant l'exemple précédent, pour affecter le masque de code-barres à un code-barres, procédez comme suit :

1.  Accédez à **Administration d'organisation** &gt; **Paramétrage** &gt; **Codes-barres**. Cliquez sur **Nouveau** pour créer un code-barres.
2.  Entrez des valeurs dans les champs **Paramétrage des codes-barres** et **Paramétrage**.
3.  Dans la section **General**, dans le champ **Type de code-barres**, sélectionnez « Code 39 ». Dans le champ **ID** **Masque**, sélectionnez le masque « Produit » créé précédemment.
4.  Sous **Taille**, entrez « 12 ».
5.  Cliquez sur **Enregistrer**.

Le masque de code-barres peut à présent être utilisé pour créer des codes-barres pour des produits. Les étapes ci-dessus sont des exemples de création de masques de codes-barres pour des produits, mais elles illustrent également comment créer des masques de codes-barres pour tous les autres types de codes-barres pris en charge. Les masques, les types et la longueur de codes-barres doivent être ajustés à l'utilisation dans votre environnement spécifique.




