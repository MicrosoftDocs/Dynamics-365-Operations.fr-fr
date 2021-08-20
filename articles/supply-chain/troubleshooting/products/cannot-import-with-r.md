---
title: Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2
description: Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2.
author: t-benebo
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: EcoResProductDetailsExtended, DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: efd773313f89784d8fca6b37d867e204cb2d06ab29694a19cbec7eed107a8019
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764690"
---
# <a name="you-cant-import-an-item-by-using-the-released-products-v2-entity"></a>Vous ne pouvez pas importer un article à l'aide de l'entité Produits lancés V2

Numéro de la base de connaissances : 4611825

## <a name="symptoms"></a>Symptômes

Lorsque vous essayez d'importer un élément à l'aide de l'entité *Produits lancés V2*, vous recevez un message d'erreur semblable à l'exemple suivant :

> Impossible de créer un enregistrement dans les éléments - groupes de dimensions de suivi (EcoResTrackingDimensionGroupItem). Numéro de l'article : 2040663, Lot. L'enregistrement existe déjà.

## <a name="resolution"></a>Résolution

Pour importer de nouveaux produits lancés, vous devez utiliser l'entité *Sortie de la création de produit V2* au lieu de l'entité *Produits lancés V2*.
