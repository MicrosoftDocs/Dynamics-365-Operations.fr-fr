---
title: Le nom de livraison n’est pas synchronisé après avoir modifié l’adresse de livraison d'une commande fournisseur
description: Après avoir modifié l’adresse de livraison sur un en-tête de commande fournisseur, le nom de livraison n’est pas synchronisé
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
ms.openlocfilehash: 588d1ef6250d249aa4fc9da4f5125e9a34c0255f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476304"
---
# <a name="the-delivery-name-isnt-synced-after-changing-a-purchase-order-delivery-address"></a>Le nom de livraison n’est pas synchronisé après avoir modifié l’adresse de livraison d'une commande fournisseur

## <a name="symptoms"></a>Symptômes

L’adresse figurant dans l’en-tête d’une commande fournisseur est mise à jour sur une adresse qui n’est pas une adresse de livraison. Bien que l’adresse soit mise à jour sur la commande fournisseur, le nom de livraison n’est pas mis à jour en fonction de l’adresse mise à jour.

## <a name="resolution"></a>Résolution

Ce comportement est fait exprès. L’adresse sélectionnée doit être classée comme adresse de livraison. Sinon, le nom de livraison n’est pas mis à jour en fonction de l’adresse sélectionnée.
