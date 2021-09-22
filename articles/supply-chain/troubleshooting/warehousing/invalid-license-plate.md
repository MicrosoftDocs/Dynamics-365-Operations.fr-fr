---
title: Contenant non valide lors de la numérisation de l'ID dans l'application mobile
description: Vous pouvez recevoir un message d’erreur lors de la numérisation de l'ID d'un contenant dans l’application mobile Warehouse Management. Cette page explique comment résoudre le problème.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b7cd6a2223dfe2c7be5324e3d2ca2ab3e9fb87a9
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476313"
---
# <a name="invalid-license-plate-error-when-scanning-license-plate-id-in-the-mobile-app"></a>Erreur de contenant non valide lors de la numérisation de l'ID du contenant dans l'application mobile

## <a name="symptoms"></a>Symptômes

Lorsque vous numérisez un ID de contenant dans l’application mobile Warehouse Management, vous pouvez recevoir le message d’erreur suivant :

> Contenant non valide.

## <a name="resolution"></a>Résolution

Assurez-vous que l’ID de contenant existe dans la table des contenants, et que les articles et les quantités du contenant sont disponibles (en d’autres termes, ils ne sont pas bloqués).
