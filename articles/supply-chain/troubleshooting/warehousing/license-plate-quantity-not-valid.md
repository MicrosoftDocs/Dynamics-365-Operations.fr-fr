---
title: La quantité n'est pas valide lors de l'enregistrement des commandes entrantes
description: "Si la quantité allouée pour un contenant dépasse la quantité qui doit encore être reçue, vous recevez le message d’erreur suivant : « La quantité n'est pas valide »."
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5099b320447bf59c72f5017564ea660f19c690a5
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476376"
---
# <a name="license-plate-quantity-is-not-valid-when-registering-inbound-orders"></a>La quantité du contenant n'est pas valide lors de l'enregistrement des commandes entrantes

## <a name="symptoms"></a>Symptômes

Lors de l'enregistrement de commandes entrantes, vous pouvez recevoir le message d’erreur suivant :

> La quantité n'est pas valide.

Si le champ **Stratégie de regroupement de contenants** est défini sur *Défini par l’utilisateur* pour un élément de menu de l’appareil mobile utilisé pour enregistrer les commandes entrantes, vous recevez ce message d’erreur et vous ne pouvez pas terminer l’enregistrement.

## <a name="cause"></a>Cause

Lorsque l’option *Défini par l’utilisateur* est utilisé comme stratégie de regroupement de contenants, le système divise l’inventaire entrant en contenants distincts, comme indiqué par le groupe de séquences d’unités. Si des numéros de lot ou de série sont utilisés pour suivre l’article qui est reçu, les quantités de chaque lot ou série doivent être spécifiées pour chaque contenant enregistré. Si la quantité spécifiée pour un contenant dépasse la quantité qui doit encore être reçue pour les dimensions actuelles, vous recevez ce message d’erreur.

## <a name="resolution"></a>Résolution

Lorsque vous enregistrez un article à l’aide d’un élément de menu d’appareil mobile où le champ **Stratégie de regroupement de contenants** est défini sur *Défini par l’utilisateur*, le système peut exiger que vous confirmiez ou saisissiez des numéros de contenant, des numéros de lot ou des numéros de série.

Sur la page de confirmation du contenant, le système affichera la quantité allouée pour le contenant actuel. Sur les pages de confirmation de lot ou de série, le système affichera la quantité qui doit encore être reçue sur le contenant actuel. Il comprendra également un champ dans lequel vous pourrez saisir la quantité à enregistrer pour cette combinaison de contenant et de numéro de lot ou de série. Dans ce cas, assurez-vous que la quantité enregistrée pour le contenant ne dépasse pas la quantité qui doit encore être reçue.

Sinon, si trop de contenants sont générés lors de l’enregistrement de la commande entrante, la valeur du champ **Stratégie de regroupement des contenants** peut être changée en *Regroupement de contenants*, un nouveau groupe de séquences d’unités peut être affecté à l’article, ou l’option **Regroupement de contenants** pour le groupe de séquences d’unités peut être désactivée.
