---
title: Calcul TDS sur les transactions intersociétés
description: Cet article décrit le processus utilisé pour calculer la taxe déduite à la source (TDS) sur les transactions intersociétés par phases.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: c27bea997804f2c5eff6be2b20064b272ccd062f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888971"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>Calcul TDS sur les transactions intersociétés

[!include [banner](../includes/banner.md)]

Cet article décrit le processus utilisé pour calculer la taxe déduite à la source (TDS) sur les transactions intersociétés par phases.

Lorsqu’une commande fournisseur ou une commande client intersociétés est créée, le groupe TDS par défaut défini pour le client ou le fournisseur est utilisé pour calculer le montant TDS. Le montant TDS est imputé aux comptes récupérables ou à payer après la validation de la facture.

Une commande client intersociétés ou une commande fournisseur est automatiquement créée pour la commande fournisseur ou la commande client d’origine. Le groupe TDS par défaut est affiché sur la commande intersociétés, afin que TDS puisse être calculé. Vous pouvez modifier le groupe TDS. La facture ne peut être validée que si le montant net de la facture de la commande intersociétés créée automatiquement correspond au montant net de la facture de la commande d’origine. (Le montant net est le montant de la facture après déduction de TDS.)

Par exemple, une facture de vente est créée pour 50 000 et le groupe TDS **10 %** y est attaché. Le montant de la facture validée est de 45 000 et le montant TDS validé pour la facture de vente est de 5 000. Une commande fournisseur est automatiquement créée pour la commande client intersociétés et le groupe TDS **10 %** y est attaché. Si vous modifiez le groupe TDS à **15%**, vous ne pouvez pas valider la facture, car le montant net de la facture de la commande client intersociétés créée automatiquement ne correspond pas au montant net de la facture de la commande client d’origine.

Un journal des paiements créé pour une facture intersociétés est automatiquement validé. Ce journal des paiements ne peut être validé que si le montant net du paiement qu’il contient correspond au montant net du paiement indiqué dans le journal des paiements d’origine.
