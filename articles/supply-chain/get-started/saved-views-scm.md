---
title: Vues enregistrées standard pour Supply Chain Management
description: Cette rubrique décrit les vues enregistrées standard disponibles et explique comment les activer.
author: kamaybac
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0709574ea44fcf841321044da31781862fcf1420
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103686"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Vues enregistrées standard pour Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management comprend plusieurs vues enregistrées que vous pouvez activer et utiliser selon vos besoins. Certaines de ces vues enregistrées standard sont optimisées et nommées pour un rôle ou une tâche spécifique (par exemple, « Contrôle qualité » ou « Réception »). D’autres sont optimisées pour n’inclure que les champs et les paramètres les plus souvent utilisés par les clients selon les statistiques d’utilisation de Microsoft. Ces vues enregistrées sont généralement appelées vues *simplifiées*. Cette rubrique décrit les vues enregistrées standard disponibles et explique comment les activer et les personnaliser.

Pour obtenir des informations complètes sur l’utilisation des vues enregistrées, y compris les vues enregistrées standard, une fois que vous les avez activées, voir [Vues enregistrées](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Personnalisation des vues enregistrées standard

Vous pouvez personnaliser les vues enregistrées standard, tout comme vous pouvez personnaliser vos propres vues enregistrées. Cependant, lorsque vous personnalisez une vue enregistrée standard, il est vivement recommandé d’enregistrer votre version personnalisée sous un nouveau nom. Sinon, vos personnalisations peuvent être remplacées lorsque vous mettez à jour Supply Chain Management.

Pour plus d’informations sur la personnalisation et l’attribution d’un nouveau nom aux vues enregistrées, voir [Vues enregistrées](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Vues enregistrées disponibles et procédure d’activation

Pour utiliser la fonctionnalité de vues enregistrées, que vous utilisiez ou non les vues enregistrées standard, vous devez activer la fonctionnalité *Vues enregistrées* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (à partir de la version 10.0.21, cette fonctionnalité est activée par défaut).

Les autres sections de cette rubrique fournissent des tableaux qui décrivent les vues enregistrées standard actuellement disponibles pour chaque module pertinent. Chaque tableau affiche le nom de chaque vue enregistrée, la page dans laquelle vous pouvez la trouver et une description de celle-ci. Chaque tableau indique également le nom de la fonctionnalité incluant la vue enregistrée. Pour afficher une vue enregistrée standard dans votre système, vous devez activer la fonctionnalité spécifiée dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). À partir de la version 10.0.25, toutes les vues répertoriées sont activées par défaut.

## <a name="saved-views-for-the-inventory-management-module"></a>Vues enregistrées pour le module Gestion des stocks

Le tableau suivant décrit les vues enregistrées disponibles pour le module Gestion des stocks.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Liste disponible | Finances | Cette vue simplifiée vous permet de vous concentrer sur les informations financières tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Liste disponible | Contrôle de la qualité | Cette vue simplifiée vous permet de vous concentrer sur le contrôle qualité tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Liste disponible | Réception | Cette vue simplifiée vous permet de vous concentrer sur les opérations de réception tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Liste disponible | Expédition | Cette vue simplifiée vous permet de vous concentrer sur les opérations d’expédition tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Transactions | Simplifié | Cette vue simplifiée vous permet de réviser le statut du stock sans être distrait par les informations financières et d’autres champs moins souvent utilisés. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Ordres de transfert | Expédition | Cette vue simplifiée vous permet de vous concentrer sur les opérations d’expédition tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Ordres de transfert | Réception | Cette vue simplifiée vous permet de vous concentrer sur les opérations de réception tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Ordres de transfert | Contrôle de la qualité | Cette vue simplifiée vous permet de vous concentrer sur le contrôle qualité tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Ordres de transfert | Finances | Cette vue simplifiée vous permet de vous concentrer sur les informations financières tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks<br><br>(Activé par défaut à partir de la version 10.0.21) |

## <a name="saved-views-for-the-master-planning-module"></a>Vues enregistrées pour le module Planification générale

Le tableau suivant décrit les vues enregistrées disponibles pour le module Planification générale.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Ordres prévisionnels : page de détails de l’ordre prévisionnel | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour travailler avec les détails d’un ordre prévisionnel unique. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées des ordres prévisionnels<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Ordres prévisionnels : page de liste d’ordres prévisionnels | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour travailler avec la liste des ordres prévisionnels. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées des ordres prévisionnels<br><br>(Activé par défaut à partir de la version 10.0.25) |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Vues enregistrées pour le module Approvisionnements

Le tableau suivant décrit les vues enregistrées disponibles pour le module Approvisionnements.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Détails de la commande fournisseur | Création de commande | Cette vue simplifiée est optimisée pour la création de nouvelles commandes fournisseur. | Vues enregistrées pour les commandes fournisseur<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Détails de la commande fournisseur | Gestion des stocks | Cette vue simplifiée est optimisée pour exécuter des activités liées au stock, telles que le suivi du stock reçu, la réception du stock, la vérification des besoins nets et l’ajustement des quantités en commande. | Vues enregistrées pour les commandes fournisseur<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Détails de la commande fournisseur | Gestion financière | Cette vue simplifiée est optimisée pour exécuter des activités liées aux finances, telles que la facturation et la vérification des prix, totaux et frais. | Vues enregistrées pour les commandes fournisseur<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Détails de la commande fournisseur | Approbation commande | Cette vue simplifiée est optimisée pour l’approbation de nouvelles commandes fournisseur. | Vues enregistrées pour les commandes fournisseur<br><br>(Activé par défaut à partir de la version 10.0.25) |

## <a name="saved-views-for-the-product-information-management-module"></a>Vues enregistrées pour le module Gestion des informations sur les produits

Le tableau suivant décrit les vues enregistrées disponibles pour le module Gestion des informations sur les produits.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Liste Produits lancés | Création de produits | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la création de produits. | Vues enregistrées pour les produits lancés<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Détails des produits lancés | Création de produits | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la création de produits. | Vues enregistrées pour les produits lancés<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Détails des produits lancés | Gestion des informations logistiques | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la gestion des informations logistiques des produits. | Vues enregistrées pour les produits lancés<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Détails des produits lancés | Gestion des informations sur l’achat | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la gestion des informations sur l’achat des produits. | Vues enregistrées pour les produits lancés<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Détails des produits lancés | Gestion des informations sur les ventes | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la gestion des informations liées aux ventes des produits. | Vues enregistrées pour les produits lancés<br><br>(Activé par défaut à partir de la version 10.0.21) |

## <a name="saved-views-for-the-production-control-module"></a>Vues enregistrées pour le module Contrôle de la production

Le tableau suivant décrit les vues enregistrées disponibles pour le module Contrôle de la production.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Page de nomenclature de l’ordre de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Page de détails de l’ordre de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Page de liste de prélèvements de l’ordre de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production<br><br>(Activé par défaut à partir de la version 10.0.21) |
| Page de liste d’ordres de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production<br><br>(Activé par défaut à partir de la version 10.0.21) |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Vues enregistrées pour le module Vente et marketing

Le tableau suivant décrit les vues enregistrées disponibles pour le module Vente et marketing.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Journal des bons de livraison | Révision du journal | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour réviser les journaux de bon de livraison. | Vues enregistrées pour la vente et le marketing<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Commande de vente | Création de commande | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour créer des commandes client. | Vues enregistrées pour la vente et le marketing<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Commande de vente | Révision de la commande | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour réviser des commandes client. | Vues enregistrées pour la vente et le marketing<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Devis de vente | Création de devis | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour créer des devis de vente. | Vues enregistrées pour la vente et le marketing<br><br>(Activé par défaut à partir de la version 10.0.25) |

## <a name="saved-views-for-the-warehouse-management-module"></a>Vues enregistrées pour le module Gestion des entrepôts

Le tableau suivant décrit les vues enregistrées disponibles pour le module Gestion des entrepôts.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Toutes les charges | Traitement entrant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les chargements entrants. | Vues enregistrées pour le traitement du chargement<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Toutes les charges | Traitement sortant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les chargements sortants. | Vues enregistrées pour le traitement du chargement<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Toutes les expéditions | Traitement entrant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les expéditions entrantes. | Vues enregistrées pour le traitement de l’expédition<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Toutes les expéditions | Traitement sortant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les expéditions sortantes. | Vues enregistrées pour le traitement de l’expédition<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Toutes les vagues | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vue enregistrée pour le traitement de la vague<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Atelier de planification des chargements | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vue enregistrée pour l’atelier de planification des chargements<br><br>(Activé par défaut à partir de la version 10.0.25) |
| Détails du travail | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vue enregistrée pour la page des détails du travail<br><br>(Activé par défaut à partir de la version 10.0.25) |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]