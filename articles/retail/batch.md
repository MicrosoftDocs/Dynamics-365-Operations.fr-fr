---
title: Gestion améliorée des articles suivis par lots
description: Cette rubrique décrit les améliorations qui ont été apportées à la gestion des lots pour les articles suivis par lots pendant le processus de validation des relevés de vente au détail.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 35823efa2844898d3eecbf91624b3e37d308b63c
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025792"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Gestion améliorée des articles suivis par lots

Dans le point de vente (PDV) Retail, les numéros de lot ne peuvent pas être capturés pour les articles suivis par lots au moment de la vente. Toutefois, pour des configurations spécifiques, lorsque les ventes sont validées dans le siège par le biais des commandes client ou de la validation des relevés, le système Microsoft Dynamics s'attend à ce que des numéros de lot valides soient disponibles pour les articles suivis par lots et qu'ils soient utilisés pendant le processus de facturation.

Si des numéros de lot valides sont disponibles pour les produits, le processus de facturation des commandes client et le processus de facturation des commandes client par le biais de la validation des relevés les utilisent. Sinon, le processus de facturation des commandes client ne peut pas être validé et l'utilisateur POS reçoit un message d'erreur. La validation des relevés passe ensuite à l'état d'erreur. Cet état d'erreur se produit même si un stock négatif a été activé pour les produits.

Les améliorations qui ont été apportées à Retail version 10.0.4 et ultérieure garantissent qu'en cas d'activation d'un stock négatif pour les articles suivis par lots, la facturation des commandes client et la facturation des commandes client par le biais de la validation des relevés ne sont pas bloquées pour ces articles si le stock est égal à 0 (zéro) ou un numéro de lot n'est pas disponible. La nouvelle fonctionnalité utilise un ID de lot par défaut pour les lignes de vente lorsque les numéros de lot ne sont pas disponibles.

Pour définir l'ID de lot par défaut utilisé pour les commandes client, dans la page **Paramètres des ventes au détail**, sous l'onglet **Commandes client**, dans le raccourci **Commande**, définissez le champ **ID de lot par défaut**.

Pour définir l'ID de lot par défaut utilisé pour la facturation des commandes client par le biais de la validation des relevés, dans la page **Paramètres des ventes au détail**, sous l'onglet **Validation**, dans le raccourci **Mise à jour du stock**, définissez le champ **ID de lot par défaut**.

> [!NOTE]
> Cette fonctionnalité est disponible uniquement lorsque l'entreposage avancé est activé pour l'entrepôt et les articles spécifiques. Dans une version ultérieure, la fonctionnalité sera également prise en charge pour les scénarios où la gestion avancée des entrepôts n'est pas utilisée.
