---
title: Quantité non valable pour le travail de prélèvement avec plusieurs contenants
description: Dans le cas d'un travail de prélèvement avec plusieurs contenants à un seul emplacement, la quantité n'est pas valide pour l'unité ea. Vérifiez que les champs suivants sont corrects.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5b245f71e80339fee3e42cfffa0396078a56926e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476295"
---
# <a name="quantity-not-valid-when-theres-picking-work-with-multiple-lps-in-one-location"></a>La quantité n'est pas valide lorsqu'il y a du travail de prélèvement avec plusieurs contenants au même emplacement

## <a name="symptoms"></a>Symptômes

Dans le cas d'un travail de prélèvement avec plusieurs contenants à un seul emplacement, la quantité n'est pas valide pour l'unité *ea*, et vous recevez le message d'erreur suivant :

> La quantité n'est pas valide pour l'unité 1%.

## <a name="resolution"></a>Résolution

Vérifiez que les champs **ID du groupe de séquences d’unités** et **Conversions d’unités** du produit lancé ou de la variante de produit sont correctement définis.

Notez que le message d’erreur a été amélioré dans la version 10.0.15 pour afficher la quantité prévue (voir [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)). Le nouveau message d'erreur est :

> La quantité n'est pas valide. Prévu %1 %2.
