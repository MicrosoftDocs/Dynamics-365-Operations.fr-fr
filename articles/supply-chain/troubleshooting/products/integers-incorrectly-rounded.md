---
title: Entiers incorrectement arrondis dans les calculs du modèle de configuration du produit
description: Les résultats entiers ne sont pas toujours arrondis correctement lors du calcul des modèles de configuration de produit. Résolvez le problème avec un attribut décimal et un calcul ajoutés.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b17145d7d17cb784fe11b3fbf65ddf5aa5530f27
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476355"
---
# <a name="integers-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Les entiers ne sont pas arrondis correctement lors du calcul des modèles de configuration de produit

## <a name="symptoms"></a>Symptômes

Ce problème peut se produire lorsque vous effectuez la série d’actions suivante :

1. Configurez les attributs suivants sur un modèle de configuration de production :

    - Entrée (entier)
    - Pourcentage (décimal)
    - Résultat (entier)

2. Créez un calcul possédant les expressions suivantes :

    *Résultat* = *Entrée* × *Pourcentage* ÷ 100

Dans ce cas, le résultat entier n’est pas toujours correctement arrondi. Par exemple, si l'entrée est 1 000 et que le pourcentage est 2,40, vous vous attendez à ce que le résultat entier soit 24, car 2,40 % de 1 000 est 24 (ou 24,00 sous forme décimale). Au lieu de cela, le résultat est affiché comme 23. Cependant, lorsque le pourcentage est de 2,39, le calcul est arrondi à 24 au lieu de 23. Lorsque le pourcentage est de 2,50, le calcul est arrondi à 25 comme prévu.

## <a name="cause"></a>Cause

Ce problème se produit en raison de la façon dont Microsoft Solver Foundation représente en interne des nombres en utilisant des fractions. Pour l’exemple précédent, le résultat du calcul où le pourcentage est de 2,40 est représenté par 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Lorsque .NET convertit cette valeur sous forme d’entier, il renvoie 23.

## <a name="resolution"></a>Résolution

Ce comportement ne sera pas modifié car d’autres scénarios en dépendent. Pour l’exemple précédent, vous pouvez résoudre le problème en introduisant un attribut décimal et des calculs supplémentaires.

Par exemple, configurez les attributs suivants sur un modèle de configuration de production :

- Entrée (entier)
- Pourcentage (décimal)
- ResultDecimal (décimal)
- ResultInteger (entier)

Vous pouvez ensuite ajouter les calculs suivants :

- *ResultDecimal* = *Entrée* × *Pourcentage* ÷ 100
- *ResultInteger* = *ResultDecimal*
