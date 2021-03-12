---
title: Résoudre des problèmes de configurateur de produit
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer avec le configurateur de produit.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e6cfeb6a2b4166dfa9a5a5cc1b7d3d913b865ce2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999604"
---
# <a name="troubleshoot-the-product-configurator"></a>Résoudre des problèmes de configurateur de produit

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer avec le configurateur de produit.

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a>Le texte de l'article est écrasé lorsque je configure un produit sur une ligne de commande client.

### <a name="issue-description"></a>Description du problème

Ce problème se produit lorsque vous créez une ligne de commande client pour un article configurable, puis que vous modifiez le texte de l'article. Lorsque vous configurez l'article, puis sélectionnez **OK**, le texte est écrasé par le texte standard.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est attendu. Le champ de texte comprend le nom de la variante, qui n'est renseigné qu'après avoir configuré la ligne. Par conséquent, vous devez modifier le texte après avoir configuré la ligne, pas avant.

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Les attributs entiers ne sont pas arrondis correctement lors du calcul des modèles de configuration de produit.

### <a name="issue-description"></a>Description du problème

Ce problème peut se produire lorsque vous effectuez la série d'actions suivante :

1. Configurez les attributs suivants sur un modèle de configuration de production :

    - Entrée (entier)
    - Pourcentage (décimal)
    - Résultat (entier)

2. Créez un calcul possédant les expressions suivantes :

    *Résultat* = *Entrée* × *Pourcentage* ÷ 100

Dans ce cas, le résultat entier n'est pas toujours correctement arrondi. Par exemple, l'entrée est 1 000 et le pourcentage est 2,40. Par conséquent, vous vous attendez à ce que le résultat entier soit 24, car 2,40 pourcent de 1 000 est 24 (ou 24,00 sous forme décimale). Au lieu de cela, le résultat est affiché comme 23. Cependant, lorsque le pourcentage est de 2,39, le calcul est arrondi à 24 au lieu de 23. Lorsque le pourcentage est de 2,50, le calcul est arrondi à 25 comme prévu.

### <a name="issue-resolution"></a>Résolution du problème

Ce problème se produit en raison de la façon dont Microsoft Solver Foundation représente en interne des nombres en utilisant des fractions. Pour l'exemple précédent, le résultat du calcul où le pourcentage est de 2,40 est représenté par 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Lorsque .NET convertit cette valeur sous forme d'entier, il renvoie 23.

Ce comportement ne sera pas modifié, car d'autres scénarios en dépendent. Pour l'exemple précédent, vous pouvez résoudre le problème en introduisant un attribut décimal supplémentaire et un calcul.

Par exemple, vous pouvez configurer les attributs suivants sur un modèle de configuration de production :

- Entrée (entier)
- Pourcentage (décimal)
- ResultDecimal (décimal)
- ResultInteger (entier)

Vous pouvez ensuite ajouter les calculs suivants :

- *ResultDecimal* = *Entrée* × *Pourcentage* ÷ 100
- *ResultInteger* = *ResultDecimal*
