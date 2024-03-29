---
title: Créer une commande client pour un produit configurable
description: Cette procédure explique comment appliquer un modèle de configuration à un produit dans une commande client.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e42f121d1efa66f85a3dd811606962b907ed177d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570583"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Créer une commande client pour un produit configurable

[!include [banner](../../includes/banner.md)]

Cette procédure explique comment appliquer un modèle de configuration à un produit dans une commande client. Cet exemple utilise le modèle de haut-parleur D0006 dans les données de démonstration de la société fictive USMF. Généralement, un processeur de commande client utilise cette procédure.

## <a name="create-a-sales-order"></a>Créer une commande client

1. Accédez à **Ventes et marketing \> Espaces de travail \> Traitement et recherche de commande client**.
1. Sélectionnez **Nouveau**.
1. Sélectionnez **Commandes client**.
1. Dans le champ **Compte client**, sélectionnez *US-001*. 
1. Cliquez sur **OK**.
1. Dans le champ **Numéro d’article**, sélectionnez *D0006*.
    * Pour cette tâche, vous devez sélectionner un produit configurable.  
1. Sélectionnez **Produit et approvisionnement**.
1. Sélectionnez **Configurer la ligne**.
    * Notez que le prix a été modifié sur la base de la configuration sélectionnée et que le champ **Inclure le câble** est désormais défini sur *True*.  
    * Notez le prix par défaut et les paramètres sélectionnés pour le câble.  
1. Sélectionnez **Charger un modèle**.
    * Cet exemple décrit comment appliquer un modèle pour sélectionner une configuration prédéfinie. Si vous utilisez cette procédure comme guide de tâche et souhaitez afficher les autres valeurs d’attribut disponibles, vous devez cliquer sur le bouton **Déverrouiller**.  
1. Cliquez sur **OK**.
1. Cliquez sur **OK**.
1. Développez la section **Détails de ligne**.
1. Sélectionnez l'onglet **Produit**.
    * La configuration de l’article est maintenant répertoriée sous les dimensions de produit.  
1. Fermez la page.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]