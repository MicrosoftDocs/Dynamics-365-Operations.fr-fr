---
title: Annuler des commandes de service
description: Vous pouvez annuler une commande de service ou une ligne de commande de service à partir de la commande de service elle-même ou annuler plusieurs commandes de service en exécutant une tâche périodique.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cca6c34bb43702e2c33935a73dc24f1a630065c0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571519"
---
# <a name="cancel-service-orders"></a>Annuler des commandes de service   

[!include [banner](../includes/banner.md)]


Vous pouvez annuler une commande de service ou une ligne de commande de service à partir de la commande de service elle-même ou annuler plusieurs commandes de service en exécutant une tâche périodique.


> [!NOTE]
> <P>Vous ne pouvez pas annuler une commande de service si son stade ne le permet pas, si elle contient des demandes d’articles ou si elle a déjà été validée.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>Annulation d’une commande de service dans l’écran Commandes de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**. Sélectionnez la commande de service, puis dans le volet Actions, cliquez sur **Annuler la commande**.

## <a name="cancel-a-service-order-line"></a>Annulation d’une ligne de commande de service

1.  Cliquez sur **Gestion des services** \> **Commun** \> **Commandes de service** \> **Commandes de service**. Double-cliquez sur la commande de service qui contient la ligne à annuler.

2.  Sélectionnez la ligne de commande de service à annuler, puis cliquez sur **Annuler la ligne de commande** pour modifier le statut de la ligne sur **Annulé**.


> [!TIP]
> <P>Pour inverser l’annulation d’une ligne de commande de service et rétablir son statut sur <STRONG>Créé</STRONG>, cliquez sur <STRONG>Annuler l’annulation</STRONG>.</P>


## <a name="cancel-multiple-service-orders"></a>Annulation de plusieurs commandes de service

1.  Cliquez sur **Gestion des services** \> **Périodique** \> **Commandes de service** \> **Annuler des commandes de service**.

2.  Cliquez sur le bouton **Sélectionner**.

3.  Dans l’écran **Recherche**, dans la colonne **Critères**, sélectionnez les commandes de service à annuler.

4.  Cliquez sur **OK** pour fermer l’écran **Recherche**.

5.  Activez la case à cocher **Afficher Infos** pour générer une fenêtre Infos répertoriant les commandes de service annulées.

6.  Activez la case à cocher **Annuler l’annulation** pour inverser le statut **Annulé** d’une commande de service.

7.  Cliquez sur **OK**.

Soit les commandes de service sélectionnées sont annulées, soit leur statut de progression **Annulé** a été rétabli sur **En cours**.


> [!NOTE]
> <P>Si vous activez la case à cocher <STRONG>Annuler l’annulation</STRONG>, les commandes de service dont le statut de progression est <STRONG>Annulé</STRONG> sont rétablies et celles dont le statut de progression est <STRONG>En cours</STRONG> ne sont pas annulées.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]