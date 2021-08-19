---
title: Les paramètres de principe d'effacement sur les lignes de nomenclature ne sont pas respectés
description: Les paramètres de principe d'effacement sur les lignes de nomenclature (BOM) ne sont pas respectés
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ee40eff53efd920ebe43a7b2dd28129f01e6ebb5e75bd480a91f758529f77fc5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716954"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a>Les paramètres de principe d'effacement sur les lignes de nomenclature ne sont pas respectés

Numéro de la base de connaissances : 4612725

## <a name="symptoms"></a>Symptômes

Ce problème se produit lorsque le champ **Consommation de nomenclature automatique** dans l'onglet **Mise à jour automatique** de la page **Paramètres de contrôle de production** est définie sur *Principe d'effacement*. Ce paramètre indique que toutes les lignes de nomenclature (BOM) doivent être automatiquement consommées lors de la réception d'une commande d'achat. Si le champ **Principe d'effacement** sur les lignes de nomenclature est explicitement défini sur *Manuel*, vous pouvez vous attendre à ce que les lignes de nomenclature ne soient pas automatiquement consommées. Toutefois, lorsque ce problème se produit, les lignes de nomenclature où le champ **Principe d'effacement** est défini sur *Manuel* sont automatiquement consommés de toute façon.

## <a name="resolution"></a>Résolution

Si vous rencontrez ce problème, vos paramètres de contrôle de production peuvent être configurés pour remplacer le paramètre **Principe d'effacement** sur les lignes de nomenclature. Sur la page **Paramètres de contrôle de production**, dans l'onglet **Mise à jour automatique**, vérifiez la valeur du champ **Consommation de nomenclature automatique**. S'il est paramétré sur *Toujours*, le système ignorera le **Principe d'effacement** sur toutes les lignes de nomenclature et effacera toujours les lignes. Pour que le système respecte le paramètre **Principe d'effacement** sur les lignes de nomenclature, modifiez la valeur du champ **Consommation de nomenclature automatique** sur *Principe d'effacement*.
