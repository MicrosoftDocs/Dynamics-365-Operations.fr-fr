---
title: Configurer un canal de centre d'appels
description: Cette rubrique décrit comment créer un canal de centre d'appels dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6ec42ab920868f541eeac54556f4f24cb1efaa3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002448"
---
# <a name="set-up-a-call-center-channel"></a>Configurer un canal de centre d'appels


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer un canal de centre d'appels dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Dans Dynamics 365 Commerce, un centre d'appels est un type de canal de vente au détail qui peut être défini dans l'application. La définition d'un canal pour vos entités de centre d'appels permet au système de lier des données spécifiques et des valeurs par défaut de traitement des commandes aux commandes client. Une société peut définir plusieurs canaux pour les centres d'appels dans Commerce. 

Avant de créer un centre d'appel, assurez-vous d'avoir rempli la [Configuration requise de paramétrage de canaux](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Créer et configurer un centre d'appels

Pour créer et configurer un centre d'appels, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Canaux \> Centre d'appels \> Tous les centres d'appels**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom**, fournissez un nom pour le nouveau canal.
1. Sélectionnez l'**Entité juridique** adéquate dans la liste déroulante.
1. Sélectionnez l'emplacement **Entrepôt** adéquat dans la liste déroulante.
1. Dans le champ **Client par défaut**, indiquez un client par défaut valide.
1. Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.
1. Fournissez un code info **Prix manuel**. Notez que vous devrez peut-être d'abord créer un code info.
1. Fournissez un code info **Code de blocage**. Notez que vous devrez peut-être d'abord créer un code info.
1. Fournissez un code info **Crédit**. Notez que vous devrez peut-être d'abord créer un code info.
1. Sélectionnez **Enregistrer**.

L'image suivante montre la création d'un canal de centre d'appels.

![Nouveau canal de centre d'appels](media/channel-setup-callcenter-1.png)

L'image suivante présente un exemple de canal de centre d'appels.

![Exemple de canal de centre d'appels](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Configuration de canal supplémentaire

Les tâches supplémentaires requises pour la configuration du canal de centre d'appels comprennent la configuration des modes de paiement et des modes de livraison.

L'image suivante montre les options de configuration **Modes de livraison** et **Modes de paiement** de l'onglet **Configurer**.

![Actions supplémentaires de configuration de canal de centre d'appels](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>paramétrer les modes de paiement ;

Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.

1. Dans le volet Actions, sélectionnez l'onglet **Configurer**, puis **Modes de paiement**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le volet de navigation, sélectionnez un mode de paiement souhaité.
1. Dans la section **Général**, fournissez un **Nom de l'opération** et configurez tous les autres paramètres souhaités.
1. Configurez tous les autres paramètres requis pour le type de paiement.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L'image suivante présente un exemple de mode de paiement au comptant.

![Exemple de modes de paiement](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Paramétrer des modes de livraison

Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l'onglet **Paramétrer** du **Volet Actions**.  

Pour modifier ou ajouter un mode de livraison, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.
1. Dans la section **Canaux de vente au détail**, sélectionnez **Ajouter une ligne** pour ajouter le canal. L'ajout de canaux à l'aide de nœuds d'organisation au lieu d'ajouter chaque canal individuellement peut rationaliser l'ajout de canaux.

L'image suivante présente un exemple de mode de livraison.

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Configuration requise pour le paramétrage de canaux](channels-prerequisites.md)

[Fonctionnalité de vente du centre d'appels](call-center-functionality.md)

[Configurer des options de traitement de commandes de centre d'appels](set-up-order-processing-options.md)

[Catalogues de centre d'appels](call-center-catalogs.md)

[Paramétrer et utiliser les alertes pour fraude](set-up-fraud-alerts.md)

[Paramétrer des programmes périodiques pour les centres d'appels](set-up-continuity-program.md)
