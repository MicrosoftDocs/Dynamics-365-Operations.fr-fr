---
title: Moyenne mobile, séquence de coût de secours
description: Cet article fournit des informations sur les séquences de coût de secours pour déplacer les calculs de moyenne dans Microsoft Dynamics 365 Supply Chain Management.
author: JennySong-SH
ms.date: 03/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-03-25
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: ad67828e2608f4754a3dffd76c64292f6a91e95f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868012"
---
# <a name="moving-average-fallback-cost-sequence"></a>Moyenne mobile, séquence de coût de secours

[!include [banner](../includes/banner.md)]

Vous pouvez calculer le coût de votre stock en utilisant une _moyenne mobile_. Jusqu’à trois valeurs de coût peuvent être associées à chaque article en stock :

- **Dernière sortie** - Le dernier coût d’émission attribué avant que le stock ne devienne négatif
- **Coût actif** - Le dernier coût qui a été activé dans une version d’évaluation des coûts
- **Prix de l’article** - Le coût spécifié pour le produit lancé

Pour déterminer laquelle de ces valeurs de coût doit être utilisée dans les calculs de moyenne mobile, le système utilise une _séquence de coût de secours_ pour établir l’ordre de préférence des valeurs. Si la valeur de coût préférée n’est pas disponible, le système utilise la valeur préférée suivante, etc.

Dans les versions précédentes de Microsoft Dynamics 365 Supply Chain Management, le système a utilisé une séquence de coûts de secours fixe (_Dernière sortie - Coût actif - Prix de l’article_). Dans la version 10.0.11, cette séquence est toujours la séquence par défaut. Cependant, vous pouvez également activer une fonctionnalité qui vous permet de sélectionner parmi trois séquences de coût de secours disponibles. Cette fonctionnalité peut être particulièrement utile pour les organisations qui utilisent régulièrement des valeurs de stock négatives.

Pour rendre le sélecteur de la séquence de coût de secours disponible, vous (ou un administrateur) devez utiliser [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour activer la fonction nommée _Moyenne mobile, séquence de coût de secours_.

Pour sélectionner la séquence de coût de secours pour les calculs de moyenne mobile, procédez comme suit.

1. Ouvrez la page **Paramètres**.
2. Sur l’onglet **Comptabilité de stock**, dans la section **Moyenne mobile**, définissez le champ **Séquence de coût de secours** sur l’une des valeurs suivantes :

    - **Dernière sortie - Coût actif - Prix de l’article** - Cette séquence est la séquence par défaut. C’est la même séquence qui est utilisée si la fonctionnalité _Moyenne mobile, séquence de coût de secours_ n’est pas activée.
    - **Coût actif - Dernière sortie**
    - **Coût actif - Prix de l’article** - Les organisations peuvent rencontrer des problèmes de performances si elles utilisent des processus métier où le stock devient régulièrement négatif et si, en même temps, le volume de transactions est élevé. Ce paramètre peut aider à atténuer ces problèmes de performances.

![Paramètres de comptabilité de stock.](media/inventory-accounting-parameters.png "Paramètres de comptabilité de stock")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]