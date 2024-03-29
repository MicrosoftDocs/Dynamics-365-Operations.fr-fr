---
title: Basculement hors ligne transparent pour les opérations de cartes cadeaux et d’avoirs
description: Cet article fournit une vue d’ensemble des améliorations permettant un basculement transparent en mode hors connexion pour des types de paiement spécifiques.
author: BrianShook
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: e0416a61bd5fd3b875b427ad8a6313d0e9936f0d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869159"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>Basculement transparent en mode hors connexion pour les opérations par carte cadeau et avoir

[!include [banner](../includes/banner.md)]

Si un appareil de point de vente (PDV) perd sa connexion à la base de données du canal, la plupart des opérations et transactions du PDV qui étaient en cours peuvent se poursuivre une fois que le caissier reçoit un message d’avertissement concernant la perte de connectivité. Cependant, dans certains cas, les transactions ont des éléments qui dépendent du service en temps réel, et ces éléments ne sont pas pris en charge lorsque le PDV est hors connexion. Cet article décrit certaines fonctionnalités qui aident à réduire l’impact de la perte de connectivité dans ces scénarios.

## <a name="completing-gift-card-transactions-in-offline-mode"></a>Exécution de transactions par carte cadeau en mode hors connexion

Les cartes cadeaux internes dépendent du service en temps réel, car leur solde doit être géré de manière centralisée dans Microsoft Dynamics 365 Commerce Headquarters. Pour éviter toute fraude ou d’autres problèmes de synchronisation, les cartes cadeaux sont verrouillées dès qu’elles sont ajoutées à une transaction. La fonction de verrouillage garantit qu’une carte cadeau ne peut pas être utilisée sur plusieurs terminaux en même temps. Lorsqu’une transaction est terminée, la carte cadeau est mise à jour et déverrouillée.

Cependant, si le PDV perd la connectivité après l’ajout d’une carte cadeau à une transaction, la carte cadeau peut devenir inutilisable. Pour éviter cette situation, Dynamics 365 Commerce a un paramètre qui permet d’exécuter les transactions incluant une ligne de carte cadeau lorsque le PDV est hors connexion. Lorsque ce paramètre est activé, les transactions par carte cadeau qui sont forcées en mode hors connexion seront enregistrées avec les transactions hors connexion, et elles seront synchronisées avec Commerce Headquarters lors de la synchronisation des transactions hors connexion. La synchronisation déverrouillera également la carte cadeau afin qu’elle puisse être utilisée sur un autre terminal.

Pour activer la fonctionnalité permettant de conclure des transactions par carte cadeau après le basculement en mode hors connexion, accédez à l’onglet **Validation** dans la page **Paramètres Commerce**. Dans cet onglet, recherchez le raccourci **Carte cadeau** et définisez **Autoriser la conclusion des transactions par carte cadeau en mode hors connexion** sur **Oui**.

![Configuration d’une carte cadeau en mode hors connexion.](../media/gift.png)

Les paramètres Commerce sont généralement mis en cache. Par conséquent, une fois que la configuration de ce paramètre a été mise à jour et que le programme de distribution est lancé pour synchroniser les modifications avec le canal, les modifications peuvent prendre jusqu’à 24 heures pour prendre effet. Pour que les modifications prennent effet immédiatement, réinitialisez Microsoft Internet Information Services (IIS).

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>Exécution de transactions par avoir en mode hors connexion

Comme les cartes cadeaux internes, les avoirs sont centralisés dans Commerce Headquarters. Commerce a un paramètre qui permet d’exécuter les transactions par avoir lorsque POS est hors connexion. Ce paramètre fonctionne comme le paramètre de carte cadeau mentionné dans la section précédente. Lorsque le paramètre est activé, les transactions par avoir qui sont forcées en mode hors connexion seront resynchronisées avec la base de données du canal, ainsi que les autres transactions qui étaient exécutées lorsque le PDV était en mode hors connexion.

Pour activer la fonctionnalité permettant de conclure des transactions par avoir après le basculement en mode hors connexion, accédez à l’onglet **Validation** dans la page **Paramètres commerciaux**. Dans cet onglet, recherchez le raccourci **Avoir** et définisez **Autoriser la conclusion des transactions par avoir en mode hors connexion** sur **Oui**.

![Configuration d’un avoir en mode hors connexion.](../media/creditmemo.png)

Les paramètres Commerce sont généralement mis en cache. Par conséquent, une fois que la configuration de ce paramètre a été mise à jour et que le programme de distribution est lancé pour synchroniser les modifications avec le canal, les modifications peuvent prendre jusqu’à 24 heures pour prendre effet. Pour que les modifications prennent effet immédiatement, réinitialisez IIS.

## <a name="related-articles"></a>Articles connexes

- [Fonctionnalité de point de vente (PDV) en mode hors connexion](../pos-offline-functionality.md)
- [Opérations du point de vente (PDV), en ligne et hors connexion](../pos-operations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]