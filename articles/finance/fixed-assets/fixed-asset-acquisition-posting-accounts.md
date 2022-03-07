---
title: Comptes de validation d’acquisition d’immobilisations
description: Cet article explique comment paramétrer les comtes de validation de la comptabilité afin d’acquérir des immobilisations.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7718ab6ad40dd135a79d2d07def19465aef68b33
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2021
ms.locfileid: "7675022"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a>Comptes de validation d’acquisition d’immobilisations

[!include [banner](../includes/banner.md)]

Cet article explique comment paramétrer les comtes de validation de la comptabilité afin d’acquérir des immobilisations.

Les comptes utilisés pour la validation des acquisitions d’immobilisations peuvent varier selon la méthode utilisée pour acquérir l’immobilisation. Dans la page des profils de validation d’immobilisation, sous l’onglet Comptes généraux, sélectionnez Acquisition et Ajustement d’acquisition pour paramétrer les comptes d’immobilisation à valider dans la comptabilité. 

Dans les journaux et les commandes fournisseur, le Compte général correspond généralement au compte de bilan, où la valeur d’acquisition de la nouvelle immobilisation est débitée. Ce compte n’est pas affiché dans le journal et ne peut pas être remplacé dans les transactions. 

Le Compte de contrepartie est également un compte de bilan. Dans le journal des opérations diverses et le journal des immobilisations, ce compte sera souvent le compte bancaire utilisé pour payer l’acquisition de l’immobilisation. Le compte de contrepartie est un compte par défaut, suggéré dans les journaux. Il peut être remplacé dans le journal par tout autre compte à partir du plan de comptes ou par un compte fournisseur, si l’immobilisation a été achetée à un fournisseur. 

Lorsque le Journal des factures ou les Commandes fournisseur du module Achats sont utilisés pour les acquisitions d’immobilisations, le compte de contrepartie de la transaction d’immobilisation est remplacé par le compte fournisseur sélectionné pour la transaction.

Pour les acquisitions validées à l’aide du journal Stock vers immobilisations dans le module Comptabilité, l’immobilisation n’est pas achetée à des sources externes, mais transférée depuis le propre stock de la société. Ainsi, le compte de contrepartie est un compte de sorties de stock pour l’article en stock dans le module Gestion des stocks.

Pour plus d’informations, voir [Acquérir les actifs via l’approvisionnement](acquire-assets-procurement.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
