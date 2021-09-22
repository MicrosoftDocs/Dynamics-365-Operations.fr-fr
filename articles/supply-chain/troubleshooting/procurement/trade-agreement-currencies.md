---
title: Problèmes de conversion de devises avec les accords commerciaux
description: Les prix des accords commerciaux ne sont pas recalculés en fonction de la devise lorsque la devise diffère sur une commande fournisseur.
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
ms.openlocfilehash: 1b6dc36c5f5ee6b611eebd81f378399ce1748c63
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476300"
---
# <a name="trade-agreement-currency-conversion-issues"></a>Problèmes de conversion de devises avec les accords commerciaux

## <a name="symptoms"></a>Symptômes

Les prix des accords commerciaux ne sont pas recalculés en fonction de la devise lorsque la devise diffère sur une commande fournisseur.

## <a name="resolution"></a>Résolution

La fonction *Devise générique* vous permet de définir les prix et les remises dans une seule devise. Vous pouvez ensuite convertir vers d’autres devises selon vos besoins. En outre, une fois la conversion terminée, la fonction peut automatiquement appliquer un arrondi intelligent.
