---
title: "Vue d'ensemble des recommandations produit personnalisées"
description: "Dans Dynamics 365 for Retail, les recommandations de produits peuvent être affichées sur le point de vente (PDV). Les recommandations sont des articles susceptibles d'intéresser les clients en fonction de leur historique d'achat, des articles de leur liste de souhaits et des articles achetés par d'autres clients en ligne ou dans des magasins traditionnels. Pour les détaillants ayant de gros catalogues, les recommandations personnalisées aident le client à découvrir les produits proposés. En mettant en avant des produits ciblés selon les intérêts et les habitudes d'achat des clients, les recommandations de produit peuvent aider les détaillants à réaliser des ventes de gamme supérieure/croisée, et à accroître la conservation des clients. Dans Dynamics 365 for Retail, les recommandations de produit sont fondées sur le Machine learning et les Cognitive Services de Microsoft Azure."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core, UnifiedOperations
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d727718442f94a2a78a3864741e93439d7c36473
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="personalized-product-recommendations-overview"></a>Vue d'ensemble des recommandations produit personnalisées

[!include[banner](includes/banner.md)]


> [!NOTE]
> Cette fonctionnalité est actuellement disponible uniquement sur les topologies de déploiement sandbox et de production (haute disponibilité). 

Dans Dynamics 365 for Retail, les recommandations de produits peuvent être affichées sur le point de vente (PDV). Les recommandations sont des articles susceptibles d'intéresser les clients en fonction de leur historique d'achat, des articles de leur liste de souhaits et des articles achetés par d'autres clients en ligne ou dans des magasins traditionnels. Pour les détaillants ayant de gros catalogues, les recommandations personnalisées aident le client à découvrir les produits proposés. En mettant en avant des produits ciblés selon les intérêts et les habitudes d'achat des clients, les recommandations de produit peuvent aider les détaillants à réaliser des ventes de gamme supérieure/croisée, et à accroître la conservation des clients. Dans Dynamics 365 for Retail, les recommandations de produit sont fondées sur le Machine learning et les Cognitive Services de Microsoft Azure.


<a name="scenarios"></a>Scénarios
---------

Les recommandations de produit sont activées pour les scénarios de PDV suivants. Elles sont disponibles dans le Cloud POS ou Modern POS (MPOS).

1.  Sur la page **Détails de produit** :

-   Si un associé du magasin visite une page **Détails de produit** lorsque vous regardez des transactions antérieures sur différents canaux, le moteur de recommandation propose des éléments supplémentaires susceptibles d'être achetés ensemble.
-   Si l'associé du magasin ajoute un client à la transaction et qu'il visite une page **Détails de produit**, le moteur de recommandation fournit des recommandations personnalisées à l'aide de l'historique des transactions du client.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  Sur la page **Transaction** :

-   Le moteur de recommandation suggère des articles selon la liste entière d'articles du panier.
-   Si l'associé du magasin ajoute un client à la transaction, le moteur de recommandation fournit des recommandations personnelles en utilisant l'historique des transactions du client et la liste des éléments dans le panier.

> [!NOTE]
> Pour afficher les recommandations sur la page **Transaction**, le détaillant doit actualiser la mise en page de l'écran dans Dynamics 365 for Retail. Le contrôle **Recommandations** doit être déposé sur la page **Transaction**. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  Sur la page **Détails du client** :
    -   Le moteur de recommandation propose des éléments basés sur l'ID utilisateur et les éléments dans la liste de souhaits du client.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a>Configurer Dynamics 365 for Retail pour proposer des recommandations de PDV
Pour paramétrer des recommandations de produit, procédez comme suit.

1.  Vérifiez que vous avez sélectionné la bonne **entité juridique**.
2.  Accédez au **Magasin des entités**, sélectionnez **Ventes au détail**, puis cliquez sur **Actualiser**. Les données (ou vos données) de démonstration issues de votre base de données opérationnelle seront utilisées et déplacées vers le magasin des entités.
3.  Facultatif : Pour afficher les recommandations dans l'écran de transaction, allez dans **Mise en page de l'écran**, choisissez une mise en page d'écran, lancez le **Concepteur de mise en page de l'écran**, puis faites glisser-déplacer le contrôle de **recommandations** à l'emplacement souhaité.
4.  Accédez à **Paramètres des ventes au détail**, sélectionnez **Machine-learning**, sélectionnez **Oui** sous **Accepter des recommandations de PDV**.
5.  Pour afficher les recommandations sur le PDV, exécutez une tâche de configuration globale **1110**. Pour refléter les modifications effectuées dans le concepteur de mise en page de l'écran du PDV, exécutez la tâche de configuration des canaux **1070**.

## <a name="how-does-it-work"></a>[]()Comment ça fonctionne ?
Lorsque vous actualisez l'entité **Magasin des entités**, les actions suivantes ont lieu.

-   Les données au format requis par les services cognitifs sont extraites de la base de données Dynamics 365 for Retail et envoyées au magasin des entités.
-   Les données sont utilisées par Azure Data Factory (ADF) pour nettoyer les données à l'aide des scripts de ruche dans le cadre des activités ADF. Les données nettoyées sont enregistrées en stock d'objets blob.
-   Les données du stockage d'objets blob sont utilisées par l'API de Microsoft Cognitive Services pour tester un modèle de recommandation.

Lorsque vous sélectionnez **Activer les recommandations** et exécutez les tâches de configuration, les actions suivantes ont lieu.

-   Les informations d'identification et l'ID du modèle sont prélevés de l'API et enregistrés dans la base de données Dynamics 365 for Retail, dans le web.config pour AOS, ainsi que le serveur de vente au détail.
-   Les informations d'identification et l'ID du modèle sont mis à la disposition de CRT afin que les appels de recommandations de produits de Cloud POS et MPOS en mode en ligne puissent être respectés.


<a name="see-also"></a>Voir également :
--------

[Ajouter un contrôle de recommandations à la page de transaction sur un périphérique de PDV](add-recommendations-control-pos-screen.md)




