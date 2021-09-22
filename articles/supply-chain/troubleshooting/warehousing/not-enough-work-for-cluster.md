---
title: Pas assez de travail trouvé pour le groupement après la configuration du profil
description: Si vous configurez un profil de groupement, vous pouvez recevoir un message d'erreur indiquant qu'il n'y a pas assez de travail. Modifiez le profil et définissez Activer les postes sur Non.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 139fd72e571c8ef83af2fd0e497cf334b6ef0ea4
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476302"
---
# <a name="not-enough-work-found-for-cluster-when-using-system-directed-cluster-picking"></a>Pas assez de travail trouvé pour le groupement lors de l'utilisation de la sélection de groupements dirigée par le système

## <a name="symptoms"></a>Symptômes

Lorsque vous utilisez le processus *Sélection de groupement dirigée par le système*, si vous configurez un profil de groupement où, par exemple, 10 postes peuvent être sélectionnés, le processus fonctionne comme prévu lorsqu’il y a suffisamment de travail pour sélectionner 10 postes. Cependant, s'il n'y a que huit postes à sélectionner, le message d'erreur suivant s'affiche :

> Travail insuffisant trouvé pour le groupement.

## <a name="resolution"></a>Résolution

Pour résoudre ce problème, modifiez le profil du groupement et définissez l’option **Activer les postes** sur *Non*.
