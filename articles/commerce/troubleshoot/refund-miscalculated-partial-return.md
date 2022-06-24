---
title: Les frais remboursables sont calculés de manière incorrecte en fonction de la quantité retournée
description: Cet article fournit des conseils de dépannage qui peuvent aider lorsque les caissiers constatent que les frais remboursables sont incorrects pour la quantité d’articles retournés au point de vente (PDV).
author: gvrmohanreddy
ms.date: 03/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 7a84207f587a826b9acdfd818c64220c5327bde1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890241"
---
# <a name="refundable-charges-are-miscalculated-based-on-the-quantity-returned"></a>Les frais remboursables sont calculés de manière incorrecte en fonction de la quantité retournée

[!include [banner](../../includes/banner.md)]

Cet article fournit des conseils de dépannage qui peuvent aider lorsque les caissiers constatent que les frais remboursables sont incorrects pour la quantité d’articles retournés au point de vente (PDV).

## <a name="description"></a>Description

Un client retourne une quantité partielle des articles achetés pour une commande client comportant des frais remboursables au niveau de la ligne. Cependant, au lieu d’afficher un remboursement partiel, le PDV affiche tous les frais comme remboursables.

Par exemple, un client achète une quantité de cinq articles à 5 USD par article, pour des frais totaux de 25 USD. Le client retourne alors trois des cinq articles. Cependant, le caissier voit des frais remboursables de 25 USD au PDV, au lieu de 15 USD de frais remboursables attendus pour les trois articles retournés.

## <a name="resolution"></a>Résolution

### <a name="turn-on-the-enable-refunding-charges-based-on-the-refunded-quantity-feature"></a>Activer la fonctionnalité Activer les frais de remboursement en fonction de la quantité remboursée

À partir de Microsoft Dynamics 365 Commerce version 10.0.26, la fonctinnalité **Activer les frais de remboursement en fonction de la quantité remboursée** permet de calculer les frais remboursables au niveau de la ligne en fonction de la quantité d’articles retournés.

Pour activer la fonctionnalité **Activer les frais de remboursement en fonction de la quantité remboursée** dans Commerce Headquarters, procédez comme suit.

1. Ouvrez l’espace de travail **Gestion des fonctionnalités** (**Administrateur système \> Espaces de travail \> Gestion des fonctionnalités**).
1. Dans la liste des fonctionnalités disponibles, recherchez et sélectionnez la fonctionnalité **Activer les frais de remboursement en fonction de la quantité remboursée**.
1. Dans le volet droit, sélectionnez **Activer maintenant**.
