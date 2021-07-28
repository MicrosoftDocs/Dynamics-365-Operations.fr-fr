---
title: Mécanisme de Taxe au preneur pour le régime TVA/TPS
description: Cette rubrique explique comment paramétrer la taxe sur la valeur ajoutée au preneur (TVA) pour les pays européens, l’Arabie saoudite et Singapour.
author: epodkolz
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom, Singapore, Bahrain, Kuwait, Oman, Qatar
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a537509fe034d85f8f4f441dc82d54efd3ed4f28
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348883"
---
# <a name="reverse-charge-mechanism-for-vatgst-scheme"></a>Mécanisme de Taxe au preneur pour le régime TVA/TPS

[!include [banner](../includes/banner.md)]

Cette rubrique décrit une approche générique pour configurer la fonctionnalité de Taxe au preneur pour les pays/régions qui adoptent les régimes de TVA ou de TPS.
                                                                                 
La disponibilité de la fonctionnalité dans le pays/la région est gérée par les fonctionnalités suivantes dans l’espace de travail **Gestion des fonctionnalités**.

| Fonctionnalité                                              | Pays/région                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Aucune fonction spécifique                                | Autriche </br>Belgique </br>Bulgarie </br>Croatie </br>Chypre </br>République tchèque </br>Danemark  </br>Estonie  </br>Finlande  </br>France  </br>Allemagne  </br>Hongrie  </br>Islande  </br>Irlande  </br>Italie  </br>Lettonie  </br>Liechtenstein  </br>Lituanie  </br>Luxembourg  </br>Pays-Bas  </br>Norvège Pologne </br>Portugal </br>Roumanie  </br>Arabie Saoudite </br>Singapour  </br>Slovaquie  </br>Slovénie  </br>Espagne  </br>Suède  </br>Suisse  </br>Royaume-Uni  </br>Émirats arabes unis |
| Taxe au preneur pour d’autres pays            | Bahreïn  </br>Koweït  </br>Oman  </br>Qatar                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Activer le mécanisme de la taxe au preneur pour le modèle TVA/TPS | Tous les autres pays/régions sauf :  </br>Brésil  </br>Inde  </br>Russie                                                                                                                                                                                                                                                                                                                                                                                         |
 
 Pour plus d’informations, consultez la section [Activer le mécanisme de Taxe au preneur pour la fonction de régime TVA/TPS](#enable-reverse-charge) plus loin dans cette rubrique.

La taxe au preneur est un schéma de taxe qui déplace la responsabilité comptable et la déclaration de TVA du vendeur vers l’acheteur des marchandises et/ou des services. Par conséquent, les destinataires des marchandises et/ou des services signalent la TVA d’aval (rôle de vendeur) et la TVA d’amont (rôle d’acheteur) sur leur déclaration de TVA.

Dans certains pays ou certaines régions, le schéma Taxe au preneur est implémenté uniquement pour certaines marchandises et/ou services, et il existe des conditions ou des seuils supplémentaires sur les montants des ventes. Dans d’autres pays ou régions, la responsabilité du paiement de la TVA dépend du statut du fournisseur et de l’acheteur. Si l’acheteur est exposé à payer la TVA, ce fait doit être clairement indiqué sur la facture envoyée au fournisseur. Par exemple, la facture doit inclure les mots « Taxe au preneur » et doit indiquer les postes sous le schéma Taxe au preneur. 

Pour appliquer la taxe au preneur, vous devez effectuer le paramétrage suivant.

## <a name="set-up-sales-tax-codes"></a>Paramétrer des codes taxe
Il est recommandé d’utiliser des codes de taxe distincts pour les opérations de vente et les opérations d’achat.

<table>
<body>
<tr>
<td><strong>Code taxe pour les ventes</strong></td>
<td>Créez un code taxe pour les opérations de vente soumises à la taxe au preneur (<strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Taxe</strong> &gt; <strong>Codes taxe</strong>).
</td>
</tr>
<tr>
<td><strong>Code taxe pour les achats</strong></td>
<td><p>Créez des codes de taxe positifs et négatifs pour la taxe au preneur pour les achats (<strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Taxe</strong> &gt; <strong>Codes taxe</strong>).</p>
<ol>
<li>Créez un code taxe qui a une valeur positive.</li>
<li>Créez un code taxe qui a une valeur négative. Définissez l’option <strong>Autoriser les pourcentages de taxe négatifs</strong> sur <strong>Oui</strong>.
Vous devrez affecter ce code taxe négatif à un groupe de taxe d’article, puis affecter ce groupe aux articles soumis à la TVA au preneur.</li>
</ol>
<p>Pour plus d’informations, consultez la section suivante &quot;Paramétrer les groupes de taxe et les groupes de taxe d’article&quot;.</p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><a name="sales-tax-item-sales-tax-groups"></a>Paramétrer des groupes de taxe et groupes de taxe d’article
Il est recommandé d’utiliser des groupes de taxes distincts pour les opérations de vente et les opérations d’achat.

<table>
<tr>
<td><strong>Groupes de taxes pour les ventes</strong></td>
<td>Créez un groupe de taxes pour les opérations de vente soumises à la taxe au preneur (<strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Taxe</strong> &gt; <strong>Groupes de taxes</strong>). Sous l’onglet <strong>Paramétrage</strong>, entrez un code taxe pour la taxe au preneur dans ce groupe. Activez les cases à cocher <strong>Exonéré</strong> et <strong>Taxe au preneur</strong> pour le code taxe.</td>
</tr>
<tr>
<td><strong>Groupes de taxes pour les achats</strong></td>
<td>Créez un groupe de taxes pour les opérations d’achat soumises à la taxe au preneur (<strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Taxe</strong> &gt; <strong>Groupes de taxes</strong>). Sous l’onglet <strong>Paramétrage</strong>, incluez des codes taxe positifs et négatifs à ce groupe. Activez la case à cocher <strong>Taxe au preneur</strong> pour le code taxe avec une valeur négative.</td>
</tr>
<tr>
<td><strong>Groupes de taxe d’article</strong></td>
<td>Créez ou mettez le groupe de taxe d’article à jour avec le code taxe qui est négatif (<strong>Taxe</strong> &gt; <strong>Taxes indirectes</strong> &gt; <strong>Taxe</strong> &gt; <strong>Groupes de taxe d’article</strong>). Vous devez affecter le groupe de taxe d’article par défaut aux produits et catégories soumis à la taxe au preneur.</td>
</tr>
</table>

## <a name="set-up-reverse-charge-item-groups"></a><a name="reverse-charge-item-group"></a>Définir les groupes d’articles de taxe au preneur
Dans la page **Groupes d’articles soumis à la taxe au preneur** (**Taxe** &gt; **Paramétrage** &gt; **Taxe** &gt; **Groupes d’articles soumis à la taxe au preneur**), vous pouvez définir des groupes de produits ou services, ou d’autres produits ou services, auxquels peut s’appliquer la taxe au preneur. Pour chaque groupe d’articles au preneur, définissez la liste d’articles, de groupes d’articles et de catégories pour les ventes et/ou les achats.

## <a name="set-up-reverse-charge-rules"></a><a name="reverse-charge-rules"></a>Définir les règles sur la taxe au preneur
Dans la page **Règles pour la taxe au preneur** (**Taxe** &gt; **Paramétrage** &gt; **Taxe** &gt; **Règles pour la taxe au preneur**), vous pouvez définir des règles d’applicabilité à des fins d’achat et de vente. Vous pouvez configurer un ensemble de règles d’applicabilité de la taxe au preneur. Pour chaque règle, définissez les champs suivants :

- **Type de document** – Sélectionnez **Commande fournisseur**, **Journal des factures fournisseur**, **Commande client**, **Facture financière**, **Journal des factures client** et/ou **Facture fournisseur**.
- **Type de pays/région du partenaire** – Sélectionnez **Local**, **UE**, **GCC** ou **Étranger**. Ou, si la règle peut être appliquée à tous les partenaires commerciaux, indépendamment du pays ou de la région de leur adresse, sélectionnez **Tous**.
- **Adresse de livraison locale** – Activez cette case à cocher pour appliquer la règle aux livraisons dans le même pays ou la même région. Cette case à cocher ne peut pas être activée pour les types de document **Journal des factures fournisseur** et **Journal des factures client**.
- **Groupe d’articles soumis à la taxe au preneur** – Sélectionnez le groupe auquel la règle peut être appliquée.
- **Montant seuil** – Le schéma au preneur est appliqué à une facture uniquement si la valeur des articles et/ou des services inclus dans le groupe d’articles au preneur dépasse la limite que vous spécifiez ici.

Vous pouvez également utiliser les champs **Date d’effet** et **Date d’expiration** pour définir la période à laquelle la règle est effective.

En outre, vous pouvez indiquer si une notification s’affiche et la ligne du document est mise à jour avec le groupe de taxes au preneur par défaut si la condition pour cette ligne de document est remplie. Les options suivantes sont disponibles :

- **Aucun** – La ligne de document n’est pas mise à jour.
- **Invite** – Une notification s’affiche pour confirmer que la taxe au preneur s’applique.
- **Ensemble** – La ligne de document est mise à jour sans notification supplémentaire.

## <a name="set-up-countryregion-properties"></a><a name="Set-up-Country/region-properties"></a>Configurer les propriétés de pays/régions
Sur la page **Paramètres du commerce extérieur** (**Taxe** &gt; **Configurer** &gt; **Taxe de vente** &gt; **Commerce extérieur** &gt; **Paramètres du commerce extérieur**), sur l’onglet **Propriétés pays/région**, définissez le pays/la région de l’entité juridique actuelle sur *National*. Définissez le **Type pays/régions** des pays/régions de l’UE qui participent au commerce intracommunautaire avec l’entité juridique actuelle sur *UE*. Définissez le **Type pays/régions** des pays/régions GCC qui participent au commerce GCC avec l’entité juridique actuelle sur *GCC*.

## <a name="set-up-default-parameters"></a>Configuration des paramètres par défaut
Pour activer la fonction pour la taxe au preneur, dans la page **Paramètres de comptabilité**, sous l’onglet **Taxe au preneur**, définissez l’option **Autoriser la taxe au preneur** sur **Oui**. Dans les champs **Groupe de taxe de commande fournisseur** et **Groupe de taxe de commande client**, sélectionnez les groupes de taxe par défaut. Lorsqu’une condition d’applicabilité de la taxe au preneur est respectée, la ligne de commande client ou fournisseur est mise à jour avec ces groupes de taxe.

## <a name="reverse-charge-on-a-sales-invoice"></a><a name="reverse-charge-sale"></a>Taxe au preneur sur une facture client
Pour les ventes sous le schéma Taxe au preneur, le vendeur ne facture pas la TVA. Au lieu de cela, la facture indique à la fois les éléments qui sont assujettis à la taxe au preneur et le montant total de la taxe au preneur.

Lorsqu’une facture client avec la taxe au preneur est publiée, les transactions taxées ont la direction de taxe **Taxe collectée** et la taxe nulle, et la case **Taxe au preneur** et **Exonération** sont cochées.

## <a name="reverse-charge-on-a-purchase-invoice"></a><a name="reverse-charge-purchase"></a>Taxe au preneur sur une facture d’achat
Pour les achats sous le schéma Taxe au preneur, l’acheteur qui reçoit la facture qui inclut la taxe au preneur agit en tant qu’acheteur et le vendeur à des fins comptables de TVA.

Lorsqu’une facture d’achat soumise à la taxe au preneur est validée, deux transactions de TVA sont créées. Une transaction a la direction de taxe **Taxe déductible**. L’autre transaction a la direction de taxe **Taxe collectée** et la case **Taxe au preneur** est cochée.

Dans le capture d’écran suivant, une transaction a l’ordre **Taxe déductible**, et l’autre transaction a la direction **Taxe collectée**. 

![Taxe validée.](media/apac-sau-posted-sales-tax.png)

## <a name="enable-reverse-charge-mechanism-for-vatgst-scheme-feature"></a><a name="enable-reverse-charge"></a>Activer le mécanisme de la taxe au preneur pour la fonctionnalité de modèle TVA/TPS
Dans l’espace de travail **Rechercher la fonctionnalité**, recherchez la fonctionnalité et sélectionnez **Activer**.

Après avoir activé la fonctionnalité, l’onglet **Taxe au preneur** est disponible dans toutes les entités juridiques. Activez la fonctionnalité Taxe au preneur pour une entité juridique en définissant l’option **Activer la Taxe au preneur** sur **Oui**.

Les pages et éléments de menu suivants liés à la configuration des fonctionnalités seront disponibles :
 - **Groupes d’articles de Taxe au preneur** (**Taxe** > **Configurer** > **Taxe** > **Groupes d’articles de Taxe au preneur**). Pour plus d’informations, voir la section [Paramétrage des groupes d’élément de Taxe au preneur](#reverse-charge-item-group).
 - **Règles de Taxe au preneur** (**Taxe** > **Configurer** > **Taxe** > **Règles de Taxe au preneur**). Voir [Définir les règles sur la taxe au preneur](#reverse-charge-rules).
 - **Paramètres du commerce extérieur** (**Taxe** > **Configurer** > **Taxe** > **Commerce extérieur** > **Paramètres du commerce extérieur**). Voir [Configurer les propriétés de pays/régions](#Set-up-Country/region-properties).

La case à cocher **Taxe au preneur** sera disponible sur les pages **Groupe de taxes** et **Taxe validée**. Pour plus d’informations, consultez les sections, [Configurer des groupes de taxes et des groupes de taxe d’article](#sales-tax-item-sales-tax-groups), [Taxe au preneur sur une facture de vente](#reverse-charge-sale), et [Taxe au preneur sur une facture d’achat](#reverse-charge-purchase).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]