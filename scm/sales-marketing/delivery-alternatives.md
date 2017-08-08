---
title: Autres modes de livraison
description: "Les responsables des commandes client peuvent utiliser la page Autres modes de livraison pour connaître les options alternatives d'exécution de commande."
author: YuyuScheller
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 33fe96562777443bffc5dac30fd3a273bcffb6e0
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---

# <a name="delivery-alternatives"></a>Autres modes de livraison

[!include[banner](../includes/banner.md)]


Les responsables des commandes client peuvent utiliser la page Autres modes de livraison pour connaître les options alternatives d'exécution de commande.

Dans Microsoft Dynamics 365 for Operations version 1611 (novembre 2016), les responsables des commandes client peuvent utiliser la page **Autres modes de livraison** pour connaître les options alternatives d'exécution de commande. La mise en page revisitée fournit une meilleure vue d'ensemble de toutes les options alternatives. Elle permet également aux responsables des commandes d'accéder à des informations autres que celles de la société actuelle pour saisir des occasions d'exécution de commande. Ils peuvent désormais afficher les opportunités intersociétés et les opportunités des fournisseurs externes. En triant les options par date de livraison, les responsables des commandes client peuvent afficher une liste intelligente répertoriant les alternatives de livraison. En outre, les paramètres les aident à mieux gérer les livraisons suggérées. Puisque le temps de transport peut affecter les dates de livraison, les responsables des commandes client peuvent explorer les différents choix de transport offerts par les transporteurs. Des informations détaillées sont affichées pour chaque suggestion, de sorte que les responsables des commandes peuvent prendre des décisions informées directement depuis la page **Autres modes de livraison**.

## <a name="open-the-delivery-alternatives-page"></a>Ouvrir la page Autres modes de livraison
Vous pouvez ouvrir la page **Autres** **modes de livraison** depuis la ligne de la commande client.

1.  Cliquez sur **Produits et approvisionnement** &gt; **Autres modes de livraison**.
2.  Cliquez sur **Détails de ligne** &gt; **Livraison** &gt; **Autres modes de livraison.**

Vous pouvez également ouvrir la page **Autres modes de livraison** en ouvrant l'espace de travail **Commandes et information client**, puis en &gt; cliquant sur **Commandes et favoris** **Lignes de commande différées** &gt; **Autres modes de livraison** **Remarque :** vous ne pouvez ouvrir la page **Autres modes de livraison** que si les deux conditions suivantes sont remplies :

-   Toutes les informations obligatoires de la ligne de vente sont renseignées.
-   Le champ **Vérification de la date de livraison** est défini sur une valeur autre que **Aucune**.

## <a name="delivery-date-control-methods"></a>Méthodes de contrôle de la date de livraison
La méthode de contrôle de la date de livraison détermine comment le système crée des dates de livraison, la manière dont les alternatives de livraison sont calculées, et les informations affichées. Notez que le contrôle des données de livraison prend en compte les calendriers. Par conséquent, les calendriers suivants peuvent affecter la date de réception suggérée : Calendrier d'entrepôt, Calendrier de transport, Calendrier du fournisseur, et Calendrier client. Le tableau suivant décrit chaque méthode de contrôle de la date de livraison.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Méthode</strong></td>
<td><strong>Description</strong></td>
</tr>
<tr class="even">
<td><strong>Aucune</strong></td>
<td><ul>
<li>Les alternatives de livraison pour les lignes de vente ne sont pas prises en charge. Cette option arrête le contrôle des données de livraison.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Délai de vente</strong></td>
<td><ul>
<li>Les alternatives de livraison sont calculées sur la base du délai de vente prédéfini. Les jours de transport sont calculés sur la base du mode de livraison.</li>
<li>Les alternatives de livraison incluent les entrepôts avec du stock disponible, et les commandes d'approvisionnement/demande.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>DAV</strong></td>
<td><ul>
<li>Les alternatives de livraison sont calculées en fonction de la logique « DAV » (ATP). La disponibilité actuelle et la disponibilité future prévue sont prises en compte. Les jours de transport sont calculés sur la base du mode de livraison.</li>
<li>Les alternatives de livraison incluent les entrepôts avec du stock disponible, et les commandes d'approvisionnement/demande.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>DAV + Marge de sortie</strong></td>
<td><ul>
<li>Les alternatives de livraison sont calculées comme pour la méthode DAV, mais la marge de sortie est incluse dans le calcul.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>CTP</strong></td>
<td><ul>
<li>Les alternatives de livraison sont calculées en fonction de la logique « capable to promise » (CTP). L'éclatement de production est utilisé pour déterminer la disponibilité. Notez que la logique CTP décale au minimum les dates de livraison en fonction du délai de vente. Les jours de transport sont calculés sur la base du mode de livraison.</li>
<li>Les alternatives de livraison incluent des suggestions pour les entrepôts suivants :
<ul>
<li>Entrepôt actuel</li>
<li>Entrepôt par défaut</li>
<li>Tous les entrepôts avec du stock disponible</li>
<li>Tous les entrepôts avec des commandes d'approvisionnement</li>
<li>Tous les entrepôts avec des versions de nomenclature (BOM) actives</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>Afficher des informations sur les alternatives de livraison
Cette section fournit des informations sur les alternatives de livraison disponibles sous chaque onglet de la page **Autres modes de livraison**.

### <a name="products"></a>Produits

Cet onglet affiche une synthèse du produit et les détails de la ligne de vente actuelle.

### <a name="delivery-alternatives"></a>Autres modes de livraison

Cet onglet affiche une liste des alternatives de livraison triées par des données de réception. Au-dessus de la liste, vous pouvez sélectionner les options sur lesquelles baser les suggestions. Vous pouvez également sélectionner le mode de livraison, qui détermine les jours de transport. Les options suivantes sont disponibles :

-   **Inclure d'autres variantes de produit** - Cette option est disponible pour les produits qui ont des variantes de produit. Les alternatives de livraison d'autres variantes de produit seront incluses. Cette option n'est pas disponible pour la logique CTP.
-   **Inclure une quantité partielle** - Par défaut, seules les suggestions conformes à la quantité complète de la ligne de vente sont incluses. Sélectionnez cette option pour inclure des suggestions qui ne remplissent que partiellement la ligne de commande. Cette option est utile lorsque le client demande une date de livraison anticipée et accepte une livraison partielle.
-   **Inclure des dates ultérieures** - Par défaut, seules les suggestions préférables (qui sont antérieures) aux dates actuelles sur la ligne de vente sont affichées. Sélectionnez cette option pour inclure des dates ultérieures. Cette option peut être utile dans les situations où des paramètres autres que la date sont prioritaires. Par exemple, un fournisseur ou un entrepôt spécifique peut être préféré.
-   **Mode de livraison** - Permet de sélectionner le mode de livraison préféré pour optimiser le temps et le coût de transport. Vous verrez immédiatement l'effet de cette option sur les alternatives de livraison suggérées. Par conséquent, elle vous permet de comparer les alternatives.
-   **Inclure l'approvisionnement** - Lorsque l'approvisionnement est activé, les alternatives de livraison suggérées incluent des options permettant de s'approvisionner chez les fournisseurs externes et d'autres sociétés de l'entreprise (intersociétés). L'option **Inclure l'approvisionnement** est prise en charge pour le contrôle de date de livraison DAV et DAV + Marge de sortie. Les options d'approvisionnement chez le fournisseur par défaut du produit et chez tous les fournisseurs approuvés pour le produit sont incluses.
-   Pour les fournisseurs externes, le calcul est basé sur le délai d'achat.
-   Pour les intersociétés, le calcul prend en considération ce qui est disponible chez la société d'approvisionnement, selon contrôle de date de livraison paramétré pour la société d'approvisionnement.
-   **Type de livraison** (Approprié pour l'approvisionnement)
    -   **Stock** - Les produits sont expédiés à partir de l'entrepôt d'approvisionnement vers le site/entrepôt indiqué sur la ligne de vente. Ils sont ensuite expédiés depuis cet entrepôt au client.
    -   **Livraison directe** - Les produits sont expédiés directement à partir de l'entrepôt d'approvisionnement vers le client.

### <a name="availability-information"></a>Informations de disponibilité

Les informations de cet onglet se rapportent à la ligne d'alternative de livraison sélectionnée. Les informations suivantes sont affichées, en fonction du contrôle de date de livraison pour la ligne de vente :

-   **Délai de vente**
    -   **Disponible aujourd'hui** - Affiche le stock physique disponible actuel, le stock physique réservé, et le stock physique disponible.
    -   **Paramètres** - Affiche l'unité de stock et le délai de vente.

-   **DAV et DAV + Marge de sortie**
    -   **Disponible aujourd'hui** - Affiche le stock physique disponible actuel, le stock physique réservé, et le stock physique disponible.
    -   **Paramètres** - Affiche l'unité de stock et le délai de vente.
    -   **Disponibilité future**  - Affiche une représentation graphique de la disponibilité actuelle et future pour le site et l'entrepôt sélectionnés sous **Autres modes de livraison**. Vous pouvez cliquer sur les colonnes du tableau pour voir des informations plus détaillées sur la disponibilité future du produit. Le curseur affiche la liste des commandes d'approvisionnement et de demande appropriées dans la plage de gestion DAV.

-   **CTP**
    -   **Disponible aujourd'hui** - Affiche le stock physique disponible actuel, le stock physique réservé, et le stock physique disponible.
    -   **Paramètres** - Affiche l'unité de stock et le délai de vente.
    -   **Éclatement** - Affiche un éclatement d'approvisionnement pour l'alternative de livraison sélectionnée. Vous pouvez utiliser **Paramétrage** pour modifier les champs et les dimensions de stock qui sont affichés dans l'éclatement.

### <a name="impact-of-selected-alternative"></a>Impact du remplacement sélectionné

Cet onglet met en surbrillance l'impact de l'alternative de livraison sélectionnée. Si vous cliquez sur **OK**, la ligne est mise à jour avec les valeurs en surbrillance dans les colonnes SÉLECTIONNÉES. Notez que, si la quantité de l'alternative de livraison sélectionnée est inférieure à la quantité de la ligne de vente, un plan de livraison est créé, et la ligne de commande est fractionnée en deux lignes : une ligne pour la quantité sélectionnée et une ligne pour la quantité restante. Vous pouvez également mettre à jour la ligne commerciale afin qu'elle corresponde aux lignes planifiées et affecte la tarification.

<a name="see-also"></a>Voir également :
--------

[Promesse de commande](/dynamics365/unified-operations/supplychain/sales-marketing/delivery-dates-available-promise-calculations)





