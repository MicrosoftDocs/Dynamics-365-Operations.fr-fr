---
title: Le propriétaire du stock n'est pas autorisé lors du traitement des mouvements
description: Vous pouvez recevoir l'erreur « Le propriétaire du stock %1 n'est pas autorisé. » Les processus de gestion des entrepôts ne prennent en charge que les stocks appartenant à l’entité juridique.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 4ee29cfc7bad990cd1ee5deaa98fca217af772ed
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476312"
---
# <a name="inventory-owner-not-allowed-when-processing-movements-in-the-warehouse-app"></a>Le propriétaire du stock n'est pas autorisé lors du traitement des mouvements dans l'application de gestion des entrepôts

## <a name="symptoms"></a>Symptômes

Lorsque vous traitez des mouvements dans l’application mobile Warehouse Management, vous pouvez recevoir le message d’erreur suivant :

> Le propriétaire du stock %1 n'est pas autorisé dans ce processus.

## <a name="cause"></a>Cause

Cela se produit parce que la dimension de suivi **Propriétaire** est manquante lorsque l’application mobile Warehouse Management est utilisée pour effectuer des mouvements. Un journal de transfert d’inventaire régulier du client Supply Chain Management semble fonctionner comme prévu et ne peut être enregistré que si la dimension **Propriétaire** est remplie.

## <a name="resolution"></a>Résolution

Microsoft a évalué ce problème et a déterminé qu’il s’agissait d’une limitation de fonctionnalité. Actuellement, les processus de gestion des entrepôts ne prennent en charge que les stocks appartenant à l’entité juridique.
