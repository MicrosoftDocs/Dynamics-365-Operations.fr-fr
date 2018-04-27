---
title: "Paramétrage de masques de codes-barres"
description: "Cette rubrique décrit la procédure de paramétrage des caractères de masque de code-barres, des masques de code-barres, ainsi que la procédure d'affectation de masques de code-barres aux codes-barres."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 671155cbf76c1570374a1602cd6590117cffa28e
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-bar-code-masks"></a>Paramétrage de masques de codes-barres

[!INCLUDE [banner](includes/banner.md)]

Cette rubrique décrit la procédure de paramétrage des caractères de masque de code-barres, des masques de code-barres, ainsi que la procédure d'affectation de masques de code-barres aux codes-barres.

<a name="set-up-bar-code-mask-characters"></a>Paramétrage des caractères de masque de code-barres
-------------------------------

Les masques de code-barres permettent de créer des codes-barres et d'identifier rapidement les codes-barres qui sont lus au point de vente (PDV). Les masques sont composés de caractères qui ont la fonction d'espaces réservés indiquant le format des codes-barres qui seront créés. Pour configurer un masque de code-barres, vous devez paramétrer des caractères de masque de code-barres. Accédez à **Vente au détail** &gt; **Gestion des stocks** &gt; **Codes-barres et étiquettes** &gt; **Caractères de masque**. Cliquez sur **Nouveau** pour créer des caractères de masque de code-barres. Les caractères de masque peuvent être créés pour indiquer les données de code-barres suivantes.

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
| **Code remise**    | *Obsolète* à partir de la version printemps 2017 de Dynamics 365 for Retail. Précédemment : indique le code remise pour un code-barres utilisé pour ajouter une remise à une transaction de point de vente.                                                                   |
| **Code coupon**      | Indique le code de coupon pour un code-barres utilisé pour ajouter une remise à une commande de vente au détail. Il a remplacé le code de remise.     |
| **Carte cadeau**        | Indique un numéro de carte cadeau lors de l'émission d'une carte cadeau ou du règlement par ce moyen.                                               |
| **Carte de fidélité**     | Ajoute un numéro de fidélité client à la transaction, et peut être utilisé lors du règlement par points de fidélité.                             |

## <a name="define-bar-code-masks"></a>Définir les masques de codes-barres
Une fois les caractères de masque de codes-barres spécifiés pour les masques de codes-barres requis, accédez à **Vente au détail** &gt; **Gestion des stocks** &gt; **Codes-barres et étiquettes** &gt; **Paramétrage du masque de code-barres**. Dans cette page, vous pouvez définir des masques de codes-barres qui utilisent les caractères précédemment spécifiés. Ces masques de code-barres seront utilisés lors de la génération de codes-barres et permettent également d'identifier les codes-barres lus au niveau du PDV.

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




