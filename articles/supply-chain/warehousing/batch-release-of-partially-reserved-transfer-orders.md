---
title: "Lancement par lots des ordres de transfert partiellement réservés"
description: "Cette rubrique explique comment configurer et appliquer le lancement par lots des ordres de transfert partiellement réservés à partir d'un appareil mobile."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 67e361aedf77166e01d9e7a5b9dcb19d08ea26bd
ms.openlocfilehash: a92a4f9eb6d7c62a9f895b18a13822480ecedbbd
ms.contentlocale: fr-fr
ms.lasthandoff: 10/05/2017

---

# <a name="batch-release-of-partially-reserved-transfer-orders"></a>Lancement par lots des ordres de transfert partiellement réservés

[!include[banner](../includes/banner.md)]

La fonctionnalité de lancement par lots des ordres de transfert partiellement réservés permet de lancer partiellement des ordres de transfert à l'attention à un entrepôt à l'aide d'un traitement par lots.
Comme vous avez la possibilité de lancer une quantité partielle, vous ne devez pas attendre que la quantité de la commande entière soit disponible dans l'entrepôt avant de lancer un ordre.

Le lancement des commandes à un entrepôt est un processus de gestion des entrepôts avancé. Ce processus implique des activités, comme le prélèvement, l'emballage et l'expédition, auxquelles un employé d'entrepôt peut procéder à l'aide d'un périphérique mobile.

## <a name="where-it-applies"></a>Dans ce cas

Pour cette fonctionnalité, les ordres de transfert sont lancés à un entrepôt à l'aide d'un traitement par lots. Cette fonctionnalité est utile si vous n'avez pas suffisamment de stock dans l'entrepôt, mais que vous souhaitez toujours transférer des articles d'un entrepôt à un autre.

## <a name="how-it-is-set-up"></a>Comment elle est paramétrée

### <a name="specify-fulfillment-criteria-for-transfer-orders-and-sales-orders"></a>Spécifier les critères d'exécution pour les ordres de transfert et les commandes client

Avant qu'un ordre puisse être partiellement lancé à un entrepôt dans un lot, les critères d'exécution doivent être remplis. Ces critères d'exécution sont déterminés par la stratégie d'exécution.

Les stratégies d'exécution pour les ordres de transfert et les commandes client sont spécifiées pour la société. En fonction du paramétrage de la stratégie d'exécution, le lancement des commandes dans un lot est accepté ou rejeté. Les commandes sont ensuite traitées en conséquence.

-   Pour créer des stratégies d'exécution pour les ordres de transfert et les commandes client, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Libérer dans l'entrepôt** \> **Stratégie d'exécution**, puis créez une stratégie d'exécution de commande en entrant un nom et une description.

-   Pour spécifier un taux d'exécution, un type de valeur et le message qui s'affichent si la stratégie d'exécution n'est pas respectée, cliquez sur **Gestion des entrepôts** \> **Paramétrage** \> **Libérer dans l'entrepôt** \> **Stratégie d'exécution**, puis définissez les champs **Taux d'exécution**, **Type de valeur** et **Message de violation d'exécution**.

### <a name="set-the-fulfillment-policies-for-transfer-orders-and-sales-orders"></a>Définir les stratégies d'exécution pour les ordres de transfert et les commandes client

-   Pour définir les stratégies d'exécution pour les ordres de transfert, cliquez sur **Gestion des stocks** \> **Paramétrage** \> **Paramètres de gestion des stocks et des entrepôts** \> **Ordres de transfert** \> **Gestion des entrepôts**, puis sélectionnez une stratégie d'exécution d'ordre de transfert.

-   Pour définir les stratégies d'exécution de commande pour les commandes client, cliquez sur **Ventes** \> **Paramétrage** \> **Paramètres des ventes** \> **Gestion des entrepôts**, puis sélectionnez une stratégie d'exécution de commande client.

## <a name="allow-release-in-a-batch-and-specify-the-quantity-that-should-be-release-in-a-batch"></a>Autoriser le lancement dans un lot et spécifier la quantité qui doit être lancée dans un lot

Un traitement par lots est utilisé pour lancer des ordres à un entrepôt dans un lot. Les paramètres qui distinguent les ordres qui doivent être exécutés dans un traitement par lots sont définis dans le traitement par lots lui-même.

Le paramètre **Quantité** spécifie si toute la quantité ou la quantité physiquement réservée doit être lancée dans le lot. Le paramètre **Autoriser la libération des commandes partiellement libérées** détermine si les ordres du lot doivent être acceptés ou rejetés s'ils ont été partiellement lancés précédemment.

-   Pour définir les paramètres **Quantité** et **Autoriser la libération des commandes partiellement libérées** pour les ordres de transfert, cliquez sur **Gestion des entrepôts** \> **Libérer dans l'entrepôt** \> **Lancement automatique des ordres de transfert**.

-   Pour définir les paramètres **Quantité** et **Autoriser la libération des commandes partiellement libérées** pour les commandes client, cliquez sur **Gestion des entrepôts** \> **Libérer dans l'entrepôt** \> **Lancement automatique de commandes client**.

