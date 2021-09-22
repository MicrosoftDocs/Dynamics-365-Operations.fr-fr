---
title: Les commandes fournisseur importées affichent des numéros de ligne incorrects
description: Lorsque des commandes fournisseur sont importées via la gestion des données, les numéros de ligne de commande fournisseur ne suivent pas l’incrément défini dans les paramètres système
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
ms.openlocfilehash: e1cf5cf1d04824213f495ac3ebf556796c96611a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476291"
---
# <a name="imported-purchase-orders-show-incorrect-line-numbers"></a>Les commandes fournisseur importées affichent des numéros de ligne incorrects

## <a name="symptoms"></a>Symptômes

Par défaut, les numéros de ligne générés automatiquement pour les lignes de commande fournisseur importées via l’entité de données *Lignes de commandes fournisseur V2* n’utilisent pas l’incrément de numéro de ligne système spécifié dans les paramètres système. Si vous créez manuellement une commande fournisseur et ajoutez des lignes via l’interface utilisateur (UI), les numéros de ligne sont incrémentés correctement. Cependant, si vous utilisez Data Management Framework (DMF), ils ne sont pas incrémentés correctement.

Ce problème se produit car, lorsque vous importez des lignes via DMF, si les numéros de ligne ne sont pas déjà affectés dans l’entité importée, le système utilise la méthode du DMF pour les affecter. Cette méthode incrémente toujours les numéros de ligne de Un.

## <a name="workaround"></a>Solution de contournement

Assurez-vous que les numéros de ligne souhaités sont déjà indiqués dans les champs de numéro de ligne d’entité de données lorsque vous importez les lignes de commande fournisseur. Dans ce cas, DMF n’écrasera pas les numéros de ligne.
