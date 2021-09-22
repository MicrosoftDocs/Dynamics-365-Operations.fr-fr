---
title: Les conditions des accords commerciaux ne s’appliquent pas aux lignes de commande importées
description: Les prix et les remises des accords commerciaux ne sont pas appliqués aux lignes de commande fournisseur ou client importées via la gestion des données.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: fef38819efaff2f2a927cf09fc7f469490149574
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476364"
---
# <a name="trade-agreement-conditions-arent-applied-to-imported-order-lines"></a>Les conditions des accords commerciaux ne s’appliquent pas aux lignes de commande importées

## <a name="symptoms"></a>Symptômes

Les accords commerciaux qui sont applicables aux lignes de commande fournisseur ou client ne sont pas appliqués sur les lignes importées via la gestion des données. Cependant, les mêmes accords commerciaux sont appliqués sur les lignes de commande client ou fournisseur créées manuellement.

## <a name="cause"></a>Cause

Si les lignes de commande fournisseur importées via la gestion des données incluent déjà des informations de prix, l’accord commercial ne sera pas réévalué pour ces lignes. Par exemple, si **Pourcentage de remise de ligne** ou l’une des valeurs de prix et de remise est définie pour une ligne, les accords commerciaux ne seront pas recherchés pour cette ligne.

## <a name="workaround"></a>Solution de contournement

Ce comportement est attendu et est similaire pour les commandes client et les commandes fournisseur.

Pour contourner le problème, importez les lignes de commande fournisseur sans définir aucune information de prix. Les accords commerciaux seront alors appliqués et les lignes de commande fournisseur seront mises à jour en fonction des accords commerciaux définis.
