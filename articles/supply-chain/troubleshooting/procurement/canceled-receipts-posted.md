---
title: Les transactions peuvent être valisées sur un compte général suspendu
description: Si un accusé de réception de marchandises est annulé, le système autorise la validation des transactions sur les comptes généraux suspendus, même si les comptes principaux sont suspendus
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 20df0ee4107ad62bec0dd9a683660fe2375a3dd1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476384"
---
# <a name="transactions-can-be-posted-to-a-suspended-ledger-account"></a>Les transactions peuvent être valisées sur un compte général suspendu

## <a name="symptoms"></a>Symptômes

Si un accusé de réception de marchandises est annulé, le système autorise la validation des transactions sur les comptes généraux suspendus, même si les comptes principaux sont suspendus.

## <a name="reproduce-the-issue"></a>Reproduire le problème

La procédure suivante montre comment reproduire le problème.

1. Sur la page **Paramètres de la comptabilité fournisseur**, sur l’onglet **Général**, assurez-vous que l’option **Valider l’accusé de réception de marchandises dans la comptabilité** est définie sur *Oui*.
1. Créez une commande fournisseur et ajoutez une ligne de commande d’une quantité de *1 000* pour un produit.
1. Confirmez la commande fournisseur.
1. Validez l’accusé de réception de marchandises et vérifiez les bons.
1. Suspendez les comptes principaux concernés, *200140* et *140200*.
1. Annulez l’accusé de réception de marchandises validé.
1. Notez que les transactions peuvent être validées sur les comptes généraux suspendus.

## <a name="resolution"></a>Résolution

Les transactions peuvent être validées sur les comptes généraux suspendus lorsque les accusés de réception de marchandise sont annulés, car ce comportement permet des validations correctes.
