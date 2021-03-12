---
title: Créer un client par défaut
description: Cette rubrique décrit comment créer un client par défaut à utiliser lors de la création d'un canal dans Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 1dd4dfc5b8ca7af66941d081b4c20be0f5d6001d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993398"
---
# <a name="create-a-default-customer"></a>Créer un client par défaut


[!include [banner](includes/banner.md)]

Cette rubrique décrit comment créer un client par défaut à utiliser lors de la création d'un canal dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d'ensemble

Lors de la création d'un canal, vous devrez indiquer un client par défaut. Un client par défaut peut facilement être créé après avoir d'abord créé le groupe de clients et le carnet d'adresses client.

## <a name="create-a-customer-group"></a>Création d'un groupe de clients

Si aucun groupe de clients n'existe encore, vous pouvez en créer. Les exemples peuvent être des groupes pour représenter différents groupes de clients, tels que la vente en gros, la vente au détail, Internet, les employés, etc.

Pour créer un groupe de clients, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Clients \> Groupes de clients**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la zone **Groupe de clients**, entrez un ID groupe de clients.
1. Entrez une description adéquate dans la zone **Description**.
1. Entrez une valeur adéquate dans la zone **Conditions de paiement**.
1. Dans la zone **Intervalle entre la date d'échéance de la facture et le paiement**, entrez une valeur appropriée.
1. Dans la zone **Groupe de taxes par défaut**, entrez un groupe de taxes, le cas échéant.
1. Cochez la case **Prix, taxe incluse** le cas échéant.
1. Dans la zone **Motif d'annulation par défaut**, entrez une valeur appropriée, le cas échéant.

L'image suivante montre plusieurs groupes de clients configurés.

![Groupes de clients](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a>Créez un carnet d'adresses clients.

Un client doit être associé à un carnet d'adresses. Si ça n'est pas déjà fait, vous devrez en créer un.

Pour créer un carnet d'adresses clients, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Paramétrage du canal \> Carnets d'adresses**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la zone **Nom**, entrez un nom.
1. Entrez une description dans la zone **Description**.
1. Dans le volet Actions, sélectionnez **Enregistrer**.

L'image suivante présente un exemple de carnet d'adresses.

![Carnet d'adresses](media/address-book.png)

## <a name="create-a-default-customer"></a>Créer un client par défaut

Pour créer un client par défaut, procédez comme suit.

1. Dans le volet de navigation, accédez à **Modules \> Commerce et vente au détail \> Clients \> Tous les clients**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la liste déroulante **Type**, sélectionnez « Personne ».
1. Dans la liste déroulante **Compte client**, sélectionnez ou entrez un numéro de compte (par exemple, « 100001 »).
1. Dans la liste déroulante **Prénom**, sélectionnez ou entrez un nom (par exemple, « Par défaut »).
1. Dans la liste déroulante **Deuxième prénom**, sélectionnez ou entrez un nom (par exemple, « Vente au détail »).
1. Dans la liste déroulante **Nom**, sélectionnez ou entrez un nom (par exemple, « Client »).
1. Dans la liste déroulante **Devise**, sélectionnez ou entrez une devise (par exemple, « USD »).
1. Dans la liste déroulante **Devise**, sélectionnez le groupe de clients créé précédemment.
1. Dans la liste déroulante **Carnets d'adresses**, sélectionnez un carnet d'adresses client existant.
1. Sélectionnez **Sauvegarder** pour enregistrer et revenir à l'écran des détails du client pour le nouveau client.

> [!NOTE]
> Il n'est pas nécessaire d'ajouter une adresse pour un client par défaut.

L'image suivant présente un exemple de création de client.

![Création de client par défaut](media/default-customer-creation.png)

L'image suivante montre une configuration client par défaut.

![Exemple de configuration client](media/default-customer-configuration1.png)

La plupart des valeurs par défaut sur l'écran des détails client peuvent rester, mais deux valeurs doivent être modifiées.

1. Sur l'écran des détails du client, développez **Valeurs par défaut de commande client**.
1. Dans la liste déroulante **Site**, sélectionnez ou entrez un site préconfiguré.
1. Dans la liste déroulante **Entrepôt**, sélectionnez ou entrez un entrepôt préconfiguré.

L'image suivant présente un exemple de configuration client.

![Exemple de configuration client](media/default-customer-configuration2.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Présentation des canaux](channels-overview.md)

[Conditions préalables au paramétrage du canal](channels-prerequisites.md)
