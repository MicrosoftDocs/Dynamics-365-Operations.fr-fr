---
title: Taxe au preneur
description: "Cette rubrique explique comment paramétrer la taxe sur la valeur ajoutée au preneur (TVA) pour les pays européens."
author: epodkolz
manager: AnnBe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6ce0b7b35264c05555d8b3a18e70484202a289d6
ms.openlocfilehash: 64a9381224ebe9dfeac8a3fab0211937a8df733c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/07/2018

---

# <a name="reverse-charge-vat"></a>Taxe au preneur

[!include[banner](../includes/banner.md)]

Cette rubrique décrit une approche générique pour paramétrer la taxe sur la valeur ajoutée au preneur (TVA) pour les pays européens.

La taxe au preneur est un schéma de taxe qui déplace la responsabilité comptable et la déclaration de TVA du vendeur vers l'acheteur des marchandises et/ou des services. Par conséquent, les destinataires des marchandises et/ou des services signalent la TVA d'aval (rôle de vendeur) et la TVA d'amont (rôle d'acheteur) dans leur déclaration de TVA.

La Directive de l'Union européenne (EU) a laissé les États membres déterminer comment ils adapteraient les besoins génériques aux besoins locaux. Par conséquent, dans certains pays, le schéma Taxe au preneur est implémenté uniquement pour certaines marchandises et/ou services, et il existe des conditions ou des seuils supplémentaires sur les montants des ventes. Dans d'autres pays, la responsabilité du paiement de la TVA dépend du statut du fournisseur et de l'acheteur. Si l'acheteur est exposé à payer la TVA, ce fait doit être clairement indiqué sur la facture envoyée au fournisseur. Par exemple, la facture doit inclure les mots « Taxe au preneur » et doit indiquer les postes sous le schéma Taxe au preneur. 

Pour appliquer la taxe au preneur, vous devez effectuer le paramétrage suivant.

## <a name="set-up-sales-tax-codes"></a>Paramétrer des codes taxe
Il est recommandé d'utiliser des codes de taxe distincts pour les opérations d'achat et les opérations de vente.

<table>
<body>
<tr>
<td><strong>Code taxe pour les ventes</strong></td>
<td>Créez un code taxe pour les opérations de vente soumises à la taxe au preneur (<strong>Taxe</strong> > <strong>Taxes indirectes</strong> > <strong>Taxe</strong> > <strong>Codes taxe</strong>).
</td>
</tr>
<tr>
<td><strong>Code taxe pour les achats</strong></td>
<td><p>Créez des codes de taxe positifs et négatifs pour la taxe au preneur pour les achats (<strong>Taxe</strong> > <strong>Taxes indirectes</strong> > <strong>Taxe</strong> > <strong>Codes taxe</strong>).</p>
<ol>
<li>Créez un code taxe qui a une valeur positive.</li>
<li>Créez un code taxe qui a une valeur négative. Définissez l'option <strong>Autoriser les pourcentages de taxe négatifs</strong> sur <strong>Oui</strong>.
Vous devrez affecter ce code taxe négatif à un groupe de taxe d'article, puis affecter ce groupe aux articles soumis à la TVA au preneur.</li>
</ol>
<p>Pour plus d'informations, consultez la section suivante « Paramétrer les groupes de taxe et les groupes de taxe d'article ».</p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a>Paramétrer les groupes de taxe et les groupes de taxe d'article
Il est recommandé d'utiliser des groupes de taxes distincts pour les opérations d'achat et les opérations de vente.

<table>
<tr>
<td><strong>Groupes de taxes pour les ventes</strong></td>
<td>Créez un groupe de taxes pour les opérations de vente soumises à la taxe au preneur (<strong>Taxe</strong> > <strong>Taxes indirectes</strong> > <strong>Taxe</strong> > <strong>Groupes de taxes</strong>). Sous l'onglet <strong>Paramétrage</strong>, entrez un code taxe pour la taxe au preneur dans ce groupe. Activez les cases à cocher <strong>Exonéré</strong> et <strong>Taxe au preneur</strong> pour le code taxe.</td>
</tr>
<tr>
<td><strong>Groupes de taxes pour les achats</strong></td>
<td>Créez un groupe de taxes pour les opérations d'achat soumises à la taxe au preneur (<strong>Taxe</strong> > <strong>Taxes indirectes</strong> > <strong>Taxe</strong> > <strong>Groupes de taxes</strong>). Sous l'onglet <strong>Paramétrage</strong>, incluez des codes taxe positifs et négatifs à ce groupe. Activez la case à cocher <strong>Taxe au preneur</strong> pour le code taxe avec une valeur négative.</td>
</tr>
<tr>
<td><strong>Groupes de taxe d'article</strong></td>
<td>Créez ou mettez le groupe de taxe d'article à jour avec le code taxe qui est négatif (<strong>Taxe</strong> > <strong>Taxes indirectes</strong> > <strong>Taxe</strong> > <strong>Groupes de taxe d'article</strong>). Vous devez affecter le groupe de taxe d'article par défaut aux produits et catégories soumis à la taxe au preneur.</td>
</tr>
</table>

## <a name="set-up-reverse-charge-groups"></a>Définir les groupes de taxe au preneur
Dans la page **Groupes d'articles soumis à la taxe au preneur** (**Taxe** > **Paramétrage** > **Taxe** > **Groupes d'articles soumis à la taxe au preneur**), vous pouvez définir des groupes de produits ou services, ou d'autres produits ou services, auxquels peut s'appliquer la taxe au preneur. Pour chaque groupe d'articles au preneur, définissez la liste d'articles, de groupes d'articles et de catégories pour les ventes et/ou les achats.

## <a name="set-up-reverse-charge-rules"></a>Définir les règles sur la taxe au preneur
Dans la page **Règles pour la taxe au preneur** (**Taxe** > **Paramétrage** > **Taxe** > **Règles pour la taxe au preneur**), vous pouvez définir des règles d'applicabilité à des fins d'achat et de vente. Vous pouvez configurer un ensemble de règles d'applicabilité de la taxe au preneur. Pour chaque règle, définissez les champs suivants :

- **Type de document** – Sélectionnez **Commande fournisseur**, **Journal des factures fournisseur**, **Commande client**, **Facture financière**, **Journal des factures client** et/ou **Facture fournisseur**.
- **Type de pays/région du partenaire** – Sélectionnez **Local**, **UE** ou **Étranger**. Ou, si la règle peut être appliquée à tous les partenaires commerciaux, indépendamment du pays ou de la région de leur adresse, sélectionnez **Tous**.
- **Adresse de livraison locale** – Activez cette case à cocher pour appliquer la règle aux livraisons dans le même pays ou la même région. Cette case à cocher ne peut pas être activée pour les types de document **Journal des factures fournisseur** et **Journal des factures client**.
- **Groupe d'articles soumis à la taxe au preneur** - Sélectionnez le groupe auquel la règle peut être appliquée.
- **Montant seuil** – Le schéma au preneur est appliqué à une facture uniquement si la valeur des articles et/ou des services inclus dans le groupe d'articles au preneur dépasse la limite que vous spécifiez ici.

Vous pouvez utiliser les champs **Date d'effet** et **Date d'expiration** pour définir la période à laquelle la règle est effective.

En outre, vous pouvez indiquer si une notification s'affiche et la ligne du document est mise à jour avec le groupe de taxes au preneur par défaut si la condition pour cette ligne de document est remplie. Les options suivantes sont disponibles :

- **Aucun** – La ligne de document n'est pas mise à jour.
- **Invite** – Une notification s'affiche pour confirmer que la taxe au preneur s'applique.
- **Ensemble** – La ligne de document est mise à jour sans notification supplémentaire.

## <a name="set-up-default-parameters"></a>Configuration des paramètres par défaut
Pour activer la fonction, dans la page **Paramètres de comptabilité**, sous l'onglet **Taxe au preneur**, définissez l'option **Autoriser la taxe au preneur** sur **Oui**. Dans les champs **Groupe de taxe de commande fournisseur** et **Groupe de taxe de commande client**, sélectionnez les groupes de taxe par défaut. Lorsqu'une condition d'applicabilité de la taxe au preneur est respectée, la ligne de commande client ou fournisseur est mise à jour avec ces groupes de taxe.

## <a name="reverse-charge-on-a-sales-invoice"></a>Taxe au preneur sur une facture client
Pour les ventes sous le schéma Taxe au preneur, le vendeur ne facture pas la TVA. Au lieu de cela, la facture indique à la fois les éléments qui sont assujettis à la taxe au preneur et le montant total de la taxe au preneur.

Lorsqu'une facture client est publiée avec la taxe au preneur, les transactions taxées ont la direction de taxe **Taxe collectée** et la taxe nulle, et la case à cocher **Taxe au preneur** est sélectionnée.

## <a name="reverse-charge-on-a-purchase-invoice"></a>Taxe au preneur sur une facture d'achat
Pour les achats sous le schéma Taxe au preneur, l'acheteur qui reçoit la facture qui inclut la taxe au preneur agit en tant qu'acheteur et le vendeur à des fins comptables de TVA.

Lorsqu'une facture d'achat soumise à la taxe au preneur est validée, deux transactions de TVA sont créées. Une transaction a la direction de taxe **Taxe déductible**. L'autre transaction a la direction de taxe **Taxe collectée** et la case **Taxe au preneur** est cochée.

