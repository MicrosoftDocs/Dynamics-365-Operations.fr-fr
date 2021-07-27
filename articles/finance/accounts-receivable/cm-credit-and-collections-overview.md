---
title: Vue d’esemble des crédits et relances
description: Cette rubrique fournit un aperçu des fonctionnalités des crédits et des relances.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.custom: intro-internal
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 81518cf7e70e8283d55e0b031bb1c48f1fad840f
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6337277"
---
# <a name="credit-and-collections-overview"></a>Vue d’esemble des crédits et relances

[!include [banner](../includes/banner.md)]

Vous pouvez gérer les limites de crédit pour vos clients et effectuer des activités de collecte lorsqu’elles deviennent nécessaires.

## <a name="credit-management"></a>Gestion du crédit

La gestion du crédit client vous permet de gérer les limites de crédit et de contrôler le flux des commandes client via le processus de validation en fonction des règles de crédit que vous créez.

Le processus de gestion des crédits peut inclure n’importe laquelle des étapes suivantes :

- Mettre à jour des attributs de crédit pour des clients afin de fournir des informations supplémentaires sur leur solvabilité.
- Créer des limites de crédit pour les clients à l’aide d’ajustements de limite de crédit.
- Créer des limites de crédit temporaires pour les clients à l’aide d’ajustements de limite de crédit. De cette façon, vous pouvez augmenter ou diminuer temporairement les limites de crédit client, en fonction des besoins de l’entreprise.
- Ajouter des informations qui peuvent affecter la limite de crédit, telles que des informations sur les assurances et les garanties.
- Créer des groupes de crédit client qui relient les clients afin qu’ils puissent partager une seule limite de crédit.
- Attribuer des scores de risque aux clients, puis utiliser les scores pour générer automatiquement des limites de crédit pour ces clients via des ajustements de limite de crédit.
- Créer des règles de blocage qui mettent une commande en attente pendant un ou plusieurs processus de validation en fonction de facteurs tels que le risque, les modalités de paiement, les limites de crédit, les montants en souffrance et le pourcentage de la limite de crédit utilisée.
- Gérer une liste des commandes client en attente, examiner les motifs de la suspension et atténuer les problèmes.
- Libérer des commandes client afin qu’elle poursuivent le processus de validation.
- Paramétrer un workflow pour gérer l’approbation des modifications de limites de crédit et des validations de commandes client.

## <a name="collections-management"></a>Gestion des recouvrements

La page **Recouvrements** fournit une vue centralisée de l’emplacement où sont gérées les informations de recouvrements des comptes clients. Les directeurs des recouvrements peuvent utiliser cette vue centralisée pour gérer les recouvrements. Les agents de recouvrement peuvent lancer le processus de recouvrement soit à partir des listes de clients générées à l’aide de critères de recouvrement prédéfinis, soit à partir de la page **Clients**.

Avant de commencer à paramétrer ou utiliser des recouvrements, vous devez comprendre les concepts suivants :

- Les instantanés de balance âgée des clients contiennent des informations sur les balances âgées à un moment donné.
- Les regroupements de clients de recouvrement vous aident à organiser votre travail.
- Les agents de recouvrement peuvent avoir leurs propres regroupements de clients.
- Les pages de liste permettent d’organiser les clients, les activités et les demandes de devis de recouvrement.
- Toutes les informations de recouvrement d’un client sont indiquées sur une seule page qui vous permet d’effectuer diverses opérations.
- Les intérêts et commissions peuvent être exonérés, rétablis ou contrepassés en une seule étape.
- Des transactions d’annulation peuvent être créées en une seule étape.
- Les paiements de fonds insuffisants peuvent être traités en une seule étape.

Pour une description de ces concepts, voir [Concepts clés de la gestion des recouvrements](./cm-collections-concepts.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Paramétrage de la gestion du crédit client](./cm-credit-mgmt-setup.md)

[Informations sur le paramétrage de la gestion du crédit client](./cm-setup-information.md)

[Ajout d’informations sur la gestion du crédit pour un client](./cm-add-credit-mgmt-information-customer.md)

[Groupes de créditer du client](./cm-customer-credit-groups.md)

[Ajustements de limite de crédit client](./cm-credit-limit-adjustments.md)

[Blocages pour les commandes client](./cm-sales-order-credit-holds.md)

[Tâches périodiques de gestion des crédits client](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]