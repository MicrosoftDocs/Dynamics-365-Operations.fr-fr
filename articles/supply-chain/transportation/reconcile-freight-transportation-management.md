---
title: Rapprochement du fret dans la gestion du transport
description: Cette rubrique décrit le processus de rapprochement du fret.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSFBDetailReconcile, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8472094ba532d531b15dc4e9f120646b2c3bbe96
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017297"
---
# <a name="reconcile-freight-in-transportation-management"></a>Rapprochement du fret dans la gestion du transport

[!include [banner](../includes/banner.md)]

Cette rubrique décrit le processus de rapprochement du fret.

Le rapprochement du fret peut être effectué manuellement, ou il peut être configuré pour se produire automatiquement. Pour utiliser le rapprochement du fret automatique, vous devez paramétrer les données principales d'audit pour définir des critères qui déterminent les factures de transport qui sont automatiquement mis en correspondance.

## <a name="the-freight-reconciliation-process"></a>Processus de rapprochement du fret
Les frais de transport sont calculés par le moteur de frais qui est associé au transporteur correspondant. Lorsque vous confirmez une charge, une facture de fret est générée et les taux de fret sont transférés. Les taux de fret sont répartis en tant que frais divers sur le document source correspondant (commande, commande client et/ou ordre de transfert), en fonction de la configuration qui est utilisée pour le processus de facturation régulier. Le processus de rapprochement des frais de transport (aussi appelé processus de mise en correspondance) peut commencer dès la réception de la facture de transport du transporteur. La facture peut être reçue par voie électronique ou sur papier. Si la facture est reçue sur papier, vous pouvez générer une facture électronique à l’aide de la facture de transport en tant que modèle. 

[![Processus de rapprochement du fret](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Rapprochement manuel
Si vous rapprochez manuellement le fret, vous devez faire correspondre chaque ligne de facture avec la ou les lignes de facturation de fret pour la charge en cours de facturation. Vous effectuez cette correspondance sur la page **Facture des frais de transport et rapprochement de factures**. Si le montant de la ligne de facture ne correspond pas au montant de la facture de transport, vous devez sélectionner un motif de rapprochement de la différence. S’il existe plusieurs motifs pour le rapprochement, vous pouvez répartir le montant qui ne correspond pas entre eux. Le motif du rapprochement détermine comment les montants de différence sont validés dans la comptabilité. Lorsque le rapprochement de l’intégralité du montant de la facture est comptabilisé, il est soumis pour approbation, et ensuite le journal est validé. La figure suivante indique comment générer une facture de transport et exécuter le rapprochement du fret. 
[![Tâches de rapprochement des frais de transport](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Rapprochement automatique
Pour utiliser le rapprochement automatique, vous devez spécifier la planification du rapprochement et les factures et les transporteurs à utiliser. La mise en correspondance des lignes de facture et des factures de transport s’effectue en fonction du paramétrage des données principales d’audit et du type de facture de transport. Après avoir exécuté le rapprochement automatique, vous devez gérer toutes les factures que le système ne peut pas faire correspondre. Vous devez traiter ces factures manuellement avant de pouvoir valider toutes les factures à des fins de paiement.



