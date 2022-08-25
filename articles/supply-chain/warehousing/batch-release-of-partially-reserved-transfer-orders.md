---
title: Lancement par lots d’ordres de transfert partiellement réservés
description: Cet article explique comment configurer et appliquer le lancement par lots des ordres de transfert partiellement réservés à partir d’un appareil mobile.
author: perlynne
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSFulfillmentPolicy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 741377a43e2bfe702b213647cc6460a3d6ad93fb
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218680"
---
# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Lancement par lots des ordres de transfert partiellement réservés

[!include [banner](../includes/banner.md)]

La fonctionnalité de lancement par lots des ordres de transfert partiellement réservés permet de lancer partiellement des ordres de transfert à l’attention à un entrepôt à l’aide d’un traitement par lots.
Comme vous avez la possibilité de lancer une quantité partielle, vous ne devez pas attendre que la quantité de la commande entière soit disponible dans l’entrepôt avant de lancer un ordre.

Le lancement des commandes à un entrepôt est un processus de gestion des entrepôts. Ce processus implique des activités, comme le prélèvement, l’emballage et l’expédition, auxquelles un employé d’entrepôt peut procéder à l’aide d’un périphérique mobile.

## <a name="where-it-applies"></a>Dans ce cas

Pour cette fonctionnalité, les ordres de transfert sont lancés à un entrepôt à l’aide d’un traitement par lots. Cette fonctionnalité est utile si vous n’avez pas suffisamment de stock dans l’entrepôt, mais que vous souhaitez toujours transférer des articles d’un entrepôt à un autre.

## <a name="how-it-is-set-up"></a>Comment elle est paramétrée

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Spécifier les critères d’exécution pour les ordres de transfert et les commandes client

Avant qu’un ordre puisse être partiellement lancé à un entrepôt dans un lot, les critères d’exécution doivent être remplis. Ces critères d’exécution sont déterminés par la stratégie d’exécution.

Les stratégies d’exécution pour les ordres de transfert et les commandes client sont spécifiées pour la société. En fonction du paramétrage de la stratégie d’exécution, le lancement des commandes dans un lot est accepté ou rejeté. Les commandes sont ensuite traitées en conséquence.

- Pour créer des stratégies d’exécution pour les ordres de transfert et les commandes client, accédez à **Warehouse Management \> Paramétrage \> Publier dans l’entrepôt \> Stratégies d’exécution**, puis créez une stratégie d’exécution de commande en entrant un nom et une description.
- Pour spécifier un taux d’exécution, un type de valeur et le message qui s’affichent si la stratégie d’exécution n’est pas respectée, accédez à **Warehouse Management \> Paramétrage \> Publier dans l’entrepôt \> Stratégies d’exécution** et définissez les champs **Taux d’exécution**, **Type de valeur** et **Message de violation d’exécution**.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Définir les stratégies d’exécution pour les ordres de transfert et les commandes client

- Pour définir les stratégies d’exécution pour les ordres de transfert, accédez à **Gestion des inventaires \> Paramétrage \> Paramètres de gestion des stocks et des entrepôts** puis, dans l’onglet **Ordres de transfert**, dans la section **Gestion des entrepôts**, sélectionnez une stratégie d’exécution d’ordre de transfert.
- Pour définir les stratégies d’exécution de commande pour les commandes client, accédez à **Comptabilité client \> Paramétrage \> Paramètres de comptabilité client** puis, dans l’onglet **Gestion des entrepôts**, sélectionnez une stratégie d’exécution de commande client.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-released-in-a-batch"></a>Autoriser le lancement dans un lot et spécifier la quantité qui doit être lancée dans un lot

Un traitement par lots est utilisé pour lancer des ordres à un entrepôt dans un lot. Les paramètres qui distinguent les ordres qui doivent être exécutés dans un traitement par lots sont définis dans le traitement par lots lui-même.

Le paramètre **Quantité** spécifie si toute la quantité ou la quantité physiquement réservée doit être lancée dans le lot. Le paramètre **Autoriser la libération des commandes partiellement libérées** détermine si les ordres du lot doivent être acceptés ou rejetés s’ils ont été partiellement lancés précédemment.

- Pour définir les paramètres **Quantité** et **Autoriser la libération des commandes partiellement libérées** pour les ordres de transfert, accédez à **Gestion des entrepôts \>Libérer dans l’entrepôt \> Lancement automatique des ordres de transfert**.
- Pour définir les paramètres **Quantité** et **Autoriser la libération des commandes partiellement libérées** pour les commandes client, accédez à **Gestion des entrepôts \> Libérer dans l’entrepôt \> Lancement automatique de commandes client**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
