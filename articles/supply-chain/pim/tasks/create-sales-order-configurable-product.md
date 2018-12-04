--- 
title: "Créer une commande client pour un produit configurable"
description: "Cette procédure explique comment appliquer un modèle de configuration à un produit dans une commande client."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 646606237f593d24792a0ae072948f2e12782283
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Créer une commande client pour un produit configurable

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure explique comment appliquer un modèle de configuration à un produit dans une commande client. Cet exemple utilise le modèle de haut-parleur D0006 dans les données de démonstration de la société fictive USMF. Généralement, un processeur de commande client utilise cette procédure.


## <a name="create-a-sales-order"></a>Créer une commande client
1. Cliquez sur Traitement et recherche de commande client.
2. Cliquez sur Nouveau.
3. Cliquez sur Commande client.
4. Dans le champ Compte client, sélectionnez US-001. 
5. Cliquez sur OK.
6. Sélectionnez D0006 dans le champ Numéro d'article.
    * Pour cette tâche, vous devez sélectionner un produit configurable.  
7. Cliquez sur Produit et approvisionnement.
8. Cliquez sur Configurer la ligne.
    * Notez que le prix a été modifié sur la base de la configuration sélectionnée et que le champ Inclure le câble est désormais défini sur True.  
    * Notez le prix par défaut et les paramètres sélectionnés pour le câble.  
9. Cliquez sur Charger un modèle.
    * Cet exemple décrit comment appliquer un modèle pour sélectionner une configuration prédéfinie. Si vous utilisez cette procédure comme guide de tâche et souhaitez afficher les autres valeurs d'attribut disponibles, vous devez cliquer sur le bouton Déverrouiller.  
10. Cliquez sur OK.
11. Cliquez sur OK.
12. Développez la section Détails de ligne.
13. Cliquez sur l'onglet Produit.
    * La configuration de l'article est maintenant répertoriée sous les dimensions de produit.  
14. Fermez la page.

## <a name="select-the-product-configuration"></a>Sélectionner la configuration du produit


