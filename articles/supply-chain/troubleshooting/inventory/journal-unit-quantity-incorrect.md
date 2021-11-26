---
title: L’unité et la quantité unitaire ne fonctionnent pas correctement dans le journal de stock
description: L’unité et la quantité unitaire ne fonctionnent pas correctement dans le journal de stock
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 074be71d7b6ec1acab6307a79e397c2a2a045c39
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2021
ms.locfileid: "7778423"
---
# <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>L’unité et la quantité unitaire ne fonctionnent pas correctement dans le journal de stock

## <a name="symptoms"></a>Symptômes

Vous pouvez rencontrer l’un ou les deux problèmes suivants lorsque vous utilisez des unités et des quantités dans un journal d’inventaire :

- Vous ne voyez pas les unités ou les quantités unitaires dans le journal d’inventaire lorsqu’une unité de conversion est configurée pour le produit lancé, et vous ne pouvez pas modifier l’unité dans le journal d’inventaire.
- Vous voyez les champs **Quantité** et **Unité** dans le journal d’inventaire, mais vous ne voyez pas le champ **Quantité unitaire**. Si vous modifiez l’unité, entrez une quantité et validez le journal, le journal affiche toujours l’unité de mesure d’origine pour cette quantité.

## <a name="resolution"></a>Résolution

Pour régler ce problème, procédez comme suit :

1. Dans l’espace de travail **Gestion des fonctionnalités**, assurez-vous que la fonctionnalité *Utilisation de l’unité de mesure et de la quantité unitaire dans les journaux d’inventaire* est activée. Cette fonctionnalité ajoute les champs **Unité** et **Quantité Unitaire** au journal. (Depuis la version 10.0.21 de Supply Chain Management, cette fonctionnalité est activée par défaut.)
1. Une fois la fonctionnalité activée, utilisez les champs **Quantité**, **Quantité Unitaire** et **Unité** de la manière suivante :

    - **Quantité** : indiquez la quantité en utilisant l’unité par défaut définie pour le produit lancé. Cependant, l’unité par défaut proprement dite n’est pas affichée ici. Si une conversion est configurée entre l’unité par défaut et l’unité sélectionnée dans le champ **Unité**, le champ **Quantité** est automatiquement mis à jour, en fonction des sélections dans les champs **Quantité unitaire** et **Unité**.
    - **Quantité unitaire** : spécifiez la quantité en utilisant l’unité sélectionnée dans le champ **Unité**.
    - **Unité** : sélectionnez l’unité à appliquer à la valeur dans le champ **Quantité Unitaire**.
