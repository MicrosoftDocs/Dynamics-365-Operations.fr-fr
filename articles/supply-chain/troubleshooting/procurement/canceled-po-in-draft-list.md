---
title: Les commandes fournisseur annulées apparaissent dans la liste des brouillons de l’espace de travail
description: Les commandes fournisseur annulées apparaissent dans la liste des brouillons de l’espace de travail Préparation de la commande fournisseur
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f1dc23cd7e5b4b99cb7a9440d7d4666d8396511f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476358"
---
# <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-workspace"></a>Les commandes fournisseur annulées apparaissent dans la liste des brouillons de l’espace de travail

## <a name="symptoms"></a>Symptômes

Une que vous avez annulé les commandes fournisseur qui étaient dans un état *Confirmé*, les commandes fournisseur annulées apparaissent toujours dans la liste des brouillons de commande fournisseur dans l’espace de travail **Préparation de la commande fournisseur**.

## <a name="resolution"></a>Résolution

Ce problème se produit uniquement pour les commandes fournisseur faisant l’objet d’une gestion des modifications. Cela se produit parce que l’annulation est considérée comme un changement qui doit être approuvé. L’approbation peut être effectuée automatiquement par le système. Par conséquent, le processus consiste à soumettre la commande fournisseur annulée au workflow d’approbation afin qu’elle puisse passer à l’état *Approuvé*. À ce stade, la commande fournisseur n’apparaîtra plus dans la liste des brouillons de commande fournisseur dans l’espace de travail **Préparation de la commande fournisseur**.
