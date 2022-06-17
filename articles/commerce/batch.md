---
title: Gestion améliorée des articles suivis par lots
description: Cet article décrit les améliorations apportées à la gestion des articles suivis par lots pendant le processus de validation des relevés dans Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 736ab8dd21f04d7119cca6d53bfeb5e408b8cbd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881876"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Gestion améliorée des articles suivis par lots

[!include [banner](includes/banner.md)]

Cet article décrit les améliorations apportées à la gestion des articles suivis par lots pendant le processus de validation des relevés dans Microsoft Dynamics 365 Commerce.

Dans le point de vente (PDV) Dynamics 365 Commerce, les numéros de lot ne peuvent pas être capturés pour les articles suivis par lots au moment de la vente. Toutefois, pour des configurations spécifiques, lorsque les ventes sont validées dans Comme Headquarters au moyen des commandes client ou de la validation des relevés, Commerce nécessite que des numéros de lot valides soient disponibles pour les articles suivis par lots et qu’ils soient utilisés pendant le processus de facturation.

Si des numéros de lot valides sont disponibles pour les produits, le processus de facturation des commandes client et le processus de facturation des commandes client au moyen de la validation des relevés les utilisent. Si des numéros de lot valides ne sont pas disponibles pour les produits, le processus de facturation de la commande client ne peut pas être validé et l’utilisateur du PDV reçoit un message d’erreur. La validation du relevé passe alors à un état d’erreur, même si un stock négatif a été activé pour les produits.

Les améliorations apportées à Commerce garantissent qu’en cas d’activation d’un stock négatif pour les articles suivis par lots, la facturation des commandes client et la facturation des commandes client au moyen de la validation des relevés ne sont pas bloquées pour ces articles si le stock est égal à 0 (zéro) ou un numéro de lot n’est pas disponible. La fonctionnalité améliorée utilise un ID de lot par défaut pour les lignes de vente lorsque les numéros de lot ne sont pas disponibles.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>Définition de l’ID de lot par défaut utilisé pour les commandes client

Pour définir l’ID de lot par défaut utilisé pour les commandes client, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**.
1. Sur l’onglet **Commandes client**, sur le raccourci **Commande**, entrez une valeur dans le champ **ID de lot par défaut**.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>Définition de l’ID de lot par défaut utilisé pour la facturation des commandes client au moyen de la validation du relevé

Pour définir de l’ID de lot par défaut utilisé pour la facturation des commandes client au moyen de la validation du relevé, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres commerciaux**.
1. Sur l’onglet **Validation**, sur le raccourci **Mise à jour du stock**, entrez une valeur dans le champ **ID de lot par défaut**.

> [!NOTE]
> - La fonctionnalité ID de lot par défaut est disponible uniquement lorsque l’entreposage avancé est activé pour l’entrepôt et les articles spécifiques en magasin. Dans une version ultérieure, la fonctionnalité d’ID de lot par défaut sera également prise en charge pour les scénarios où la gestion avancée des entrepôts n’est pas activée.
> - La prise en charge de la gestion améliorée des articles suivis par lots pendant la validation des relevés pour les scénarios de gestion des entrepôts non avancés a été introduite dans le lancement de la version 10.0.5 de Commerce.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
