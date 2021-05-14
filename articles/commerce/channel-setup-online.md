---
title: Paramétrer un canal en ligne
description: Cette rubrique décrit comment créer un canal en ligne dans Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: f0f1e0f3e7145c66b8f2b082b44ad7035c57d947
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936942"
---
# <a name="set-up-an-online-channel"></a>Paramétrer un canal en ligne


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer un canal en ligne dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Dynamics 365 Commerce prend en charge plusieurs canaux de vente au détail. Ces canaux de vente au détail comprennent les magasins en ligne, les centres d’appels et les magasins de vente au détail (également appelés magasins traditionnels). Les magasins en ligne donnent aux clients la possibilité d’acheter des produits dans le magasin en ligne du détaillant, en plus de ses magasins de vente au détail.

Pour créer un magasin en ligne dans Commerce, vous devez d’abord créer un canal en ligne. Avant de créer un nouveau canal en ligne, assurez-vous d’avoir rempli la [Configuration requise de paramétrage de canaux](channels-prerequisites.md).

Avant de pouvoir créer un site, au moins un magasin en ligne doit être créé dans Commerce. Pour plus d’informations, voir [Créer un site de commerce électronique](create-ecommerce-site.md).

## <a name="create-and-configure-a-new-online-channel"></a>Créer et configurer un canal en ligne

Pour créer et configurer un canal en ligne, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Canaux \> Magasins en ligne**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le champ **Nom**, fournissez un nom pour le nouveau canal.
1. Dans la liste déroulante **Entité juridique**, entrez l’entité juridique appropriée.
1. Dans la liste déroulante **Entrepôt**, entrez l’entrepôt approprié.
1. Dans le champ **Fuseau hoaraire du magasin**, sélectionnez le fuseau horaire adéquat.
1. Sélectionnez la devise adéquate dans le champ **Devise**.
1. Dans le champ **Client par défaut**, indiquez un client par défaut valide.
1. Dans le **Carnet d’adresses client**, fournissez un carnet d’adresses valide.
1. Dans le champ **Profil de la fonctionnalité**, sélectionnez un profil de fonctionnalité le cas échéant.
1. Dans le champ **Profil de notification par e-mail**, fournissez un profil de notification par e-mail valide.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante montre la création d’un canal en ligne.

![Nouveau canal en ligne](media/channel-setup-online-1.png)

L’image suivante présente un exemple de canal en ligne.

![Exemple de canal en ligne](media/channel-setup-online-2.png)

## <a name="set-up-languages"></a>Configurer les langues

Si votre site de commerce électronique prend en charge plusieurs langues, développez la section **Langues** et ajoutez des langues, selon les besoins.

## <a name="set-up-payment-account"></a>Configurer un compte de paiement

Depuis la section **Compte de paiement**, vous pouvez ajouter un fournisseur de paiement tiers. Pour plus d’informations sur la configuration d’un connecteur de paiement Adyen, consultez [Connecteur de paiement Dynamics 365 pour Adyen](./dev-itpro/adyen-connector.md).

## <a name="additional-channel-setup"></a>Configuration de canal supplémentaire

Les tâches supplémentaires qui sont requises pour la configuration du canal en ligne comprennent la configuration des modes de paiement, des modes de livraison et l’affectation du groupe d’exécution.

L’image suivante montre les options de configuration **Modes de livraison**, **Modes de paiement** et **Affectation du groupe d’exécution** de l’onglet **Configurer**.

![Actions supplémentaires de configuration de canal en ligne](media/channel-setup-online-3.png)

### <a name="set-up-payment-methods"></a>paramétrer les modes de paiement ;

Pour configurer des modes de paiement, pour chaque type de paiement pris en charge sur ce canal, procédez comme suit.

1. Dans le volet Actions, sélectionnez l’onglet **Configurer**, puis **Modes de paiement**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans le volet de navigation, sélectionnez un mode de paiement souhaité.
1. Dans la section **Général**, fournissez un **Nom de l’opération** et configurez tous les autres paramètres souhaités.
1. Configurez tous les autres paramètres requis pour le type de paiement.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante présente un exemple de mode de paiement au comptant.

![Exemple de modes de paiement](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Paramétrer des modes de livraison

Vous pouvez voir les modes de livraison configurés en sélectionnant **Modes de livraison** dans l’onglet **Paramétrer** du **Volet Actions**.  

Pour modifier ou ajouter un mode de livraison, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Gestion des stocks \> Modes de livraison**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour créer un mode de livraison ou sélectionnez un mode existant.
1. Dans la section **Canaux de vente au détail**, sélectionnez **Ajouter une ligne** pour ajouter le canal. L’ajout de canaux à l’aide de nœuds d’organisation au lieu d’ajouter chaque canal individuellement peut rationaliser l’ajout de canaux.

L’image suivante présente un exemple de mode de livraison.

![Paramétrer des modes de livraison](media/channel-setup-retail-7.png)

### <a name="set-up-a-fulfillment-group-assignment"></a>Paramétrer une affectation de groupe d’exécution

Pour paramétrer une affectation de groupe d’exécution, procédez comme suit.

1. Dans le volet Actions, sélectionnez l’onglet **Paramétrer**, puis **Affectation du groupe d’exécution**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la liste déroulante **Groupe d’exécution**, sélectionnez un groupe d’exécution.
1. Dans la liste déroulante **Description**, entrez une description.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L’image suivante montre un exemple de configuration d’affectation de groupe d’exécution.

![Configurer l’affectation du groupe d’exécution](media/channel-setup-retail-9.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des canaux](channels-overview.md)

[Configuration requise pour le paramétrage de canaux](channels-prerequisites.md)

[Paramétrer un canal de vente au détail](channel-setup-retail.md)

[Paramétrer un canal de centre d’appels](channel-setup-callcenter.md)

[Connecteur de paiement Dynamics 365 pour Adyen](./dev-itpro/adyen-connector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]