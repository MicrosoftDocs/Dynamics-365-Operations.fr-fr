---
title: La tâche de mise à jour des reçus de produits confirme les commandes non confirmées
description: Après avoir exécuté Mettre à jour les accusés de réception de produits, le système confirme les commandes non confirmées qui ont le statut Enregistré. Découvrez la fonctionnalité qui résout ce problème.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 171a978efc6b55b92f429381e72036cb1b3296c6
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476301"
---
# <a name="unconfirmed-purchase-orders-are-confirmed-after-running-update-product-receipts"></a>Après avoir exécuté Mettre à jour les reçus de produits, les commandes fournisseur non confirmées sont confirmées.

## <a name="symptoms"></a>Symptômes

Après avoir exécuté la tâche périodique *Mettre à jour les réceptions de produits*, le système confirme automatiquement les commandes fournisseur non confirmés dont le statut de transaction de stock est *Inscrit*.

## <a name="resolution"></a>Résolution

Une nouvelle fonctionnalité de gestion des charges entrantes, *À réception des quantités de chargement*, résout ce problème. Pour activer cette fonctionnalité, accédez à l’espace de travail [Gestion des fonctionnalités](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) et activez les fonctionnalités suivantes (dans l’ordre de la liste) :

1. Associer les mouvements de stock de commande fournisseur au chargement
2. Réception excédentaire des quantités de chargement

Pour plus d’informations, consultez [Afficher les quantités de produits enregistrées par rapport aux commandes fournisseur](/dynamics365/supply-chain/warehousing/inbound-load-handling).
