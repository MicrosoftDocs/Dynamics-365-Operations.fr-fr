---
title: Quantité de stock non mise à jour en raison de transactions insuffisantes
description: La quantité de stock -1% ne peut pas être mise à jour car il n’y a pas suffisamment de transactions de stock pour l'article %2 ayant les dimensions spécifiées.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 88130a969039dd741c8ea4fbaabe81acf0e6fb6a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476287"
---
# <a name="system-cant-update-inventory-quantity-because-of-insufficient-transactions"></a>Le système ne peut pas mettre à jour la quantité de stock en raison de transactions insuffisantes

## <a name="symptoms"></a>Symptômes

Ce problème peut se produire si le système ne peut pas mettre à jour une quantité de stock car il n’y a pas suffisamment de transactions de stock qui ont les dimensions spécifiées. Vous recevrez le message d’erreur suivant :

> Quantité de stock -%1 n’a pas pu être mis à jour en raison de transactions de stock insuffisantes pour l’article %2 avec dimensions Taille=%3, Couleur=%4, Ajouts=%5, Site=%6, Entrepôt=%7, Emplacement=%8, Statut du stock=Disponible, Contenant=%9, Numéro de lot=%10 pour l’ID de référence %11 sur l’ID de lot %12.

## <a name="resolution"></a>Résolution

Assurez-vous qu’aucune transaction de stock ne réserve physiquement la quantité. Par exemple, ces transactions peuvent ouvrir des commandes de qualité, des enregistrements de blocage des stocks ou des commandes de sortie.
