---
title: Rapprochement du fret dans la gestion du transport
description: Cette rubrique décrit le processus de rapprochement du fret.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1794c297bef86a62ff5dc24524332df07ea26f39
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345280"
---
# <a name="reconcile-freight-in-transportation-management"></a>Rapprochement du fret dans la gestion du transport

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le processus de rapprochement du fret.

Le rapprochement du fret peut être effectué manuellement, ou il peut être configuré pour se produire automatiquement. Pour utiliser le rapprochement du fret automatique, vous devez paramétrer les données principales d’audit pour définir des critères qui déterminent les factures de transport qui sont automatiquement mis en correspondance.

## <a name="the-freight-reconciliation-process"></a>Processus de rapprochement du fret

Les frais de transport sont calculés par le moteur de frais qui est associé au transporteur correspondant. Lorsque vous confirmez une charge, une facture de fret est générée et les taux de fret sont transférés. Les taux de fret sont répartis en tant que frais divers sur le document source correspondant (commande, commande client et/ou ordre de transfert), en fonction de la configuration qui est utilisée pour le processus de facturation régulier. Le processus de rapprochement des frais de transport (aussi appelé processus de mise en correspondance) peut commencer dès la réception de la facture de transport du transporteur. La facture peut être reçue par voie électronique ou sur papier. Si la facture est reçue sur papier, vous pouvez générer une facture électronique à l’aide de la facture de transport en tant que modèle.

[![Processus de rapprochement du transport.](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Rapprochement manuel

Si vous rapprochez manuellement le fret, vous devez faire correspondre chaque ligne de facture avec la ou les lignes de facturation de fret pour la charge en cours de facturation. Vous effectuez cette correspondance sur la page **Facture des frais de transport et rapprochement de factures**. Si le montant de la ligne de facture ne correspond pas au montant de la facture de transport, vous devez sélectionner un motif de rapprochement de la différence. S’il existe plusieurs motifs pour le rapprochement, vous pouvez répartir le montant qui ne correspond pas entre eux. Le motif du rapprochement détermine comment les montants de différence sont validés dans la comptabilité. Lorsque le rapprochement de l’intégralité du montant de la facture est comptabilisé, il est soumis pour approbation, et ensuite le journal est validé. La figure suivante indique comment générer une facture de transport et exécuter le rapprochement du fret.

[![Tâches de rapprochement du transport.](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>Rapprochement automatique

Pour utiliser le rapprochement automatique, vous devez spécifier la planification du rapprochement et les factures et les transporteurs à utiliser. La mise en correspondance des lignes de facture et des factures de transport s’effectue en fonction du paramétrage des données principales d’audit et du type de facture de transport. Après avoir exécuté le rapprochement automatique, vous devez gérer toutes les factures que le système ne peut pas faire correspondre. Vous devez traiter ces factures manuellement avant de pouvoir valider toutes les factures à des fins de paiement.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>Mettre en correspondre les factures de frais de transport et les factures de transport à l’aide du rapprochement automatique ou manuel

La *Mise en correspondance* est le processus de recherche des factures de frais de transport correspondant à chaque facture de transport. Elle peut être effectuée en mettant en correspondre les lignes de facture une par une (correspondance manuelle), ou en mettant en correspondance toutes les factures disponibles en même temps (correspondance automatique).

### <a name="auto-matching"></a>Correspondance automatique

Lors de la mise en correspondance de plusieurs factures de transport avec la même facture de frais de transport, le processus de correspondance automatique fonctionne comme suit :

1. Toutes les factures de transport qui ne sont pas mises en correspondance sont triées par montant, le montant le plus élevé en premier.
1. Les factures de transport sont mises en correspondance une par une, jusqu’à ce que la facture de frais de transport ne présente plus de montant positif restant.
1. Selon la configuration des données principales d’audit et le montant restant des factures de transport, le montant restant est défini.

### <a name="manual-matching"></a>Correspondance manuelle

Toutes les factures de frais de transport avec des montants positifs seront disponibles pour la correspondance. Comme pour la correspondance automatique, l’utilisateur ne pourra mettre en correspondre que les factures de transport avec des montants négatifs avec les factures de frais de transport qui ne sont pas entièrement mises en correspondance.

### <a name="example"></a>Exemple

Supposons que vous ayez une facture de frais de transport (FB) d’un montant de 1 500 et que vous ayez créé trois factures de transport pour la facture de frais de transport avec une ligne de facture pour chaque facture avec les paramètres suivants :

- Facture de frais de transport d’original (FB) : montant 1 500
- Facture 1 (Inv1) : montant 1 000
- Facture 2 (Inv2) : montant 600
- Facture 3 (Inv3) : montant -100

#### <a name="automatic-matching-result"></a>Résultat de la correspondance automatique

La correspondance automatique s’exécutera dans l’ordre suivant :

1. Triez toutes les factures de transport dans l’ordre décroissant par montant : Inv1 -> Inv2 -> Inv3.
1. Mettez en correspondance Inv1 avec FB. Inv1 a 1000 correspondances et FB a un montant restant de 500, donc le statut est défini sur *Correspondance partielle*.
1. Mettez en correspondance Inv2 avec FB. Inv2 a 500 correspondances et FB a un montant restant de 0, donc le statut est défini sur *Correspondance totale*.
1. Comme FB est maintenant entièrement mis en correspondance, Inv3 ne sera pas traité.

#### <a name="manual-matching-result"></a>Résultat de la correspondance manuelle

Pour la correspondance manuelle, les résultats varient selon l’ordre de la correspondance, comme illustré dans les exemples de scénarios suivants.

##### <a name="manual-matching-case-1"></a>Scénario de correspondance manuelle 1

Une façon d’effectuer une correspondance manuelle pour cet exemple est de procéder comme suit :

1. Mettez en correspondance FB avec Inv1. FB a un montant restant de 500, donc le statut est défini sur *Correspondance partielle*.
1. Mettez en correspondance Inv2 avec FB. Inv2 a 500 correspondances et FB a un montant restant de 0, donc le statut est défini sur *Correspondance totale*.
1. Lors de la correspondance manuelle de Inv3, vous ne trouverez aucune facture de frais de transport sans correspondance.

Ce scénario est essentiellement le même que la correspondance automatique

##### <a name="manual-matching-case-2"></a>Scénario de correspondance manuelle 2

Une autre façon d’effectuer une correspondance manuelle pour cet exemple est de procéder comme suit :

1. Mettez en correspondance Inv3 avec FB. Maintenant FB a un montant restant de 1 600, ce qui revient à soustraire moins 100 sur 1 500. FB et Inv3 ont une quantité correspondante de -100.
1. Mettez en correspondance Inv1 et Inv2 avec FB l’un après l’autre. FB est entièrement mis en correspondance.

Comme le montre cet exemple, la mise en correspondance des factures de frais de transport avec des montants négatifs ne doit être effectuée que manuellement. Cela garantit qu’il est toujours possible de mettre en correspondre les factures de frais de transport avec des montants négatifs avec une facture de transport qui n’est pas entièrement mise en correspondance, car cela vous permet de contrôler la séquence de correspondance.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]