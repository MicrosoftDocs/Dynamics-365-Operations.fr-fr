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
ms.openlocfilehash: 2544591773bea7d54b4da4ac25ed3fed3f9e3594c5f791a0975c0349583b695c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728625"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Vues enregistrées standard pour Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management comprend plusieurs vues enregistrées que vous pouvez activer et utiliser selon vos besoins. Certaines de ces vues enregistrées standard sont optimisées et nommées pour un rôle ou une tâche spécifique (par exemple, « Contrôle qualité » ou « Réception »). D’autres sont optimisées pour n’inclure que les champs et les paramètres les plus souvent utilisés par les clients selon les statistiques d’utilisation de Microsoft. Ces vues enregistrées sont généralement appelées vues *simplifiées*. Cette rubrique décrit les vues enregistrées standard disponibles et explique comment les activer et les personnaliser.

Pour obtenir des informations complètes sur l’utilisation des vues enregistrées, y compris les vues enregistrées standard, une fois que vous les avez activées, voir [Vues enregistrées](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Personnalisation des vues enregistrées standard

Vous pouvez personnaliser les vues enregistrées standard, tout comme vous pouvez personnaliser vos propres vues enregistrées. Cependant, lorsque vous personnalisez une vue enregistrée standard, il est vivement recommandé d’enregistrer votre version personnalisée sous un nouveau nom. Sinon, vos personnalisations peuvent être remplacées lorsque vous mettez à jour Supply Chain Management.

Pour plus d’informations sur la personnalisation et l’attribution d’un nouveau nom aux vues enregistrées, voir [Vues enregistrées](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Vues enregistrées disponibles et procédure d’activation

Pour utiliser la fonctionnalité de vues enregistrées, que vous utilisiez ou non les vues enregistrées standard, vous devez activer la fonctionnalité *Vues enregistrées* dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Les autres sections de cette rubrique fournissent des tableaux qui décrivent les vues enregistrées standard actuellement disponibles pour chaque module pertinent. Chaque tableau affiche le nom de chaque vue enregistrée, la page dans laquelle vous pouvez la trouver et une description de celle-ci. Chaque tableau indique également le nom de la fonctionnalité incluant la vue enregistrée. Pour afficher une vue enregistrée standard dans votre système, vous devez activer la fonctionnalité spécifiée dans [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="saved-views-for-the-inventory-management-module"></a>Vues enregistrées pour le module Gestion des stocks

Le tableau suivant décrit les vues enregistrées disponibles pour le module Gestion des stocks.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Liste disponible | Finances | Cette vue simplifiée vous permet de vous concentrer sur les informations financières tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks |
| Liste disponible | Contrôle de la qualité | Cette vue simplifiée vous permet de vous concentrer sur le contrôle qualité tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks |
| Liste disponible | Réception | Cette vue simplifiée vous permet de vous concentrer sur les opérations de réception tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks |
| Liste disponible | Expédition | Cette vue simplifiée vous permet de vous concentrer sur les opérations d’expédition tout en gérant le stock disponible. | Vues enregistrées pour la gestion des stocks |
| Transactions | Simplifié | Cette vue simplifiée vous permet de réviser le statut du stock sans être distrait par les informations financières et d’autres champs moins souvent utilisés. | Vues enregistrées pour la gestion des stocks |
| Ordres de transfert | Expédition | Cette vue simplifiée vous permet de vous concentrer sur les opérations d’expédition tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks |
| Ordres de transfert | Réception | Cette vue simplifiée vous permet de vous concentrer sur les opérations de réception tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks |
| Ordres de transfert | Contrôle de la qualité | Cette vue simplifiée vous permet de vous concentrer sur le contrôle qualité tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks |
| Ordres de transfert | Finances | Cette vue simplifiée vous permet de vous concentrer sur les informations financières tout en gérant les ordres de transfert. | Vues enregistrées pour la gestion des stocks |

## <a name="saved-views-for-the-master-planning-module"></a>Vues enregistrées pour le module Planification générale

Le tableau suivant décrit les vues enregistrées disponibles pour le module Planification générale.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Ordres prévisionnels : page de détails de l’ordre prévisionnel | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour travailler avec les détails d’un ordre prévisionnel unique. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées des ordres prévisionnels |
| Ordres prévisionnels : page de liste d’ordres prévisionnels | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour travailler avec la liste des ordres prévisionnels. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées des ordres prévisionnels |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Vues enregistrées pour le module Approvisionnements

Le tableau suivant décrit les vues enregistrées disponibles pour le module Approvisionnements.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Détails de la commande fournisseur | Création de commande | Cette vue simplifiée est optimisée pour la création de nouvelles commandes fournisseur. | Vues enregistrées pour les commandes fournisseur |
| Détails de la commande fournisseur | Gestion des stocks | Cette vue simplifiée est optimisée pour exécuter des activités liées au stock, telles que le suivi du stock reçu, la réception du stock, la vérification des besoins nets et l’ajustement des quantités en commande. | Vues enregistrées pour les commandes fournisseur |
| Détails de la commande fournisseur | Gestion financière | Cette vue simplifiée est optimisée pour exécuter des activités liées aux finances, telles que la facturation et la vérification des prix, totaux et frais. | Vues enregistrées pour les commandes fournisseur |
| Détails de la commande fournisseur | Approbation de commande | Cette vue simplifiée est optimisée pour l’approbation de nouvelles commandes fournisseur. | Vues enregistrées pour les commandes fournisseur |

## <a name="saved-views-for-the-product-information-management-module"></a>Vues enregistrées pour le module Gestion des informations sur les produits

Le tableau suivant décrit les vues enregistrées disponibles pour le module Gestion des informations sur les produits.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Liste Produits lancés | Création de produits | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la création de produits. | Vues enregistrées pour les produits lancés |
| Détails des produits lancés | Création de produits | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la création de produits. | Vues enregistrées pour les produits lancés |
| Détails des produits lancés | Gestion des informations logistiques | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la gestion des informations logistiques des produits. | Vues enregistrées pour les produits lancés |
| Détails des produits lancés | Gestion des informations sur l’achat | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la gestion des informations sur l’achat des produits. | Vues enregistrées pour les produits lancés |
| Détails des produits lancés | Gestion des informations sur les ventes | Vue de page simplifiée qui inclut uniquement les champs les plus utilisés lors de la gestion des informations liées aux ventes des produits. | Vues enregistrées pour les produits lancés |

## <a name="saved-views-for-the-production-control-module"></a>Vues enregistrées pour le module Contrôle de la production

Le tableau suivant décrit les vues enregistrées disponibles pour le module Contrôle de la production.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Page de nomenclature de l’ordre de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production |
| Page de détails de l’ordre de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production |
| Page de liste de prélèvements de l’ordre de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production |
| Page de liste d’ordres de fabrication | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vues enregistrées pour le contrôle de la production |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Vues enregistrées pour le module Vente et marketing

Le tableau suivant décrit les vues enregistrées disponibles pour le module Vente et marketing.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Journal des bons de livraison | Révision du journal | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour réviser les journaux de bon de livraison. | Vues enregistrées pour la vente et le marketing |
| Commandes client | Création de commande | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour créer des commandes client. | Vues enregistrées pour la vente et le marketing |
| Commandes client | Révision de la commande | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour réviser des commandes client. | Vues enregistrées pour la vente et le marketing |
| Devis de vente | Création de devis | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour créer des devis de vente. | Vues enregistrées pour la vente et le marketing |

## <a name="saved-views-for-the-warehouse-management-module"></a>Vues enregistrées pour le module Gestion des entrepôts

Le tableau suivant décrit les vues enregistrées disponibles pour le module Gestion des entrepôts.

| Page | Nom de vue | Afficher la description | Nom de la fonction |
|---|---|---|---|
| Toutes les charges | Traitement entrant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les chargements entrants. | Vues enregistrées pour le traitement du chargement |
| Toutes les charges | Traitement sortant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les chargements sortants. | Vues enregistrées pour le traitement du chargement |
| Toutes les expéditions | Traitement entrant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les expéditions entrantes. | Vues enregistrées pour le traitement de l’expédition |
| Toutes les expéditions | Traitement sortant | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés pour traiter les expéditions sortantes. | Vues enregistrées pour le traitement de l’expédition |
| Toutes les vagues | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vue enregistrée pour le traitement de la vague |
| Atelier de planification des chargements | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vue enregistrée pour l’atelier de planification des chargements |
| Détails du travail | Simplifié | Cette vue simplifiée ne comprend que les champs les plus souvent utilisés. De cette manière, elle offre une vue d’ensemble plus rapide et un processus de travail simplifié. | Vue enregistrée pour la page des détails du travail |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]