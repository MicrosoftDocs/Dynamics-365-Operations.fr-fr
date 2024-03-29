---
title: Configurer et traiter un échange suite à un ordre de retour
description: Cet article explique comment configurer un échange suite à un retour dans Dynamics 365 Commerce.
author: josaw1
ms.date: 07/28/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f33c674e4110b4e45ac58e499a65da2509b00046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845790"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>Configurer et traiter un échange suite à un ordre de retour

[!include [banner](includes/banner.md)]

Dans les versions antérieures de Dynamics 365 Commerce, les retours suite à des commandes client étaient traités à l’aide du document d’ordre de retour dans Headquarters. Toutefois, un document d’ordre de retour peut être utilisé pour traiter uniquement les produits retournés. Les produits retournés sont signalés par une quantité négative dans les lignes de l’ordre de retour. Les ventes sont en revanche indiquées par une quantité positive. Toutefois, le document d’ordre de retour ne prend pas en charge les quantités positives. En raison de cette limitation, les versions précédentes de l’application ne prenaient pas en charge les scénarios où les échanges de produit étaient effectués à l’aide du document d’ordre de retour.

Toutefois, une fonctionnalité a été ajoutée pour prendre en charge les scénarios au cours desquels les échanges sont effectués avec des ordres de retour. Commerce utilise désormais le document de commande client au lieu du document d’ordre de retour pour traiter ces transactions.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>Configurer Commerce pour prendre en charge les échanges suite aux ordres de retour

> [!NOTE]
> Dans la version 10.0.20 et les versions ultérieures de Commerce, une nouvelle fonctionnalité appelée « Expérience unifiée du traitement des retours dans PDV » est disponible. Si vous activez cette fonctionnalité, les étapes de configuration ci-dessous ne sont pas nécessaires. **Traiter les retours en tant que commandes client** devient un paramètre configuré de manière permanente et vous ne pourrez plus le modifier.

Suivez ces étapes pour configurer le système de façon à prendre en charge les échanges sur les ordres de retour (si vous n’avez pas activé la fonctionnalité **Expérience unifiée du traitement des retours dans PDV**).

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**. Dans le raccourci **Commandes client**, définissez l’option **Traiter les ordres de retour en tant que commandes client** sur **Activé**.
2. Exécutez la tâche **Programme de distribution de la configuration globale** (**1110**).

## <a name="make-an-exchange"></a>Effectuer un échange

Une fois le système configuré comme décrit dans la section précédente, l’utilisateur du point de vente sélectionne toujours une commande client ou une facture client pour traiter un retour, comme dans les versions précédentes de l’application. Toutefois, une fois les articles retournés ajoutés au chariot, l’utilisateur peut ajouter de nouvelles lignes de vente.

Pour ces nouvelles lignes de vente, l’utilisateur doit définir tous les attributs nécessaires afin de traiter une ligne de commande client. Ces attributs comprennent l’emplacement d’exécution et le mode de livraison. Le paiement dû pour la transaction sera la montant net des lignes d’ordre de retour et des lignes de commande client. Lorsque le paiement est fourni pour la transaction, l’ordre de retour sera validé comme document de commande client dans Headquarters et le système facturera immédiatement les lignes de retour.

Pour fournir une meilleure visibilité sur les différents montants du chariot, trois nouveaux champs de montant ont été ajoutés dans celui-ci. Vous pouvez utiliser le concepteur de l’écran pour rendre ces nouveaux champs disponibles dans l’interface utilisateur (UI) du point de vente.

- **Dépôt appliqué** : Montant du dépôt qui est appliqué sur une transaction lorsque l’utilisateur effectue un prélèvement de commande client. S’il n’y a aucun remplacement de dépôt et qu’un dépôt de 10 % est configuré, le montant de ce champ correspond à 90 % du montant total de la commande client.
- **Exécuter le montant** : Montant total des lignes dans lesquelles le mode de livraison a été défini sur **Exécuter** lorsque la commande client a été créée ou modifiée, ou lors d’un échange de commande client. Le montant de ce champ inclut des taxes et des frais.
- **Montant du retour** : Montant total des lignes ayant des quantités négatives lors de l’échange de la commande client. Le montant de ce champ inclut des taxes et des frais.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
