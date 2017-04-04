---
title: "Vue d&quot;ensemble personnalisée de recommandations de produit"
description: "Dans Dynamics 365 pour les opérations, les recommandations de produit peuvent être affichées {{sur:on_the_point_of}} {{le:on_the_point_of}} {{point:on_the_point_of}} du périphérique de (POS) de vente. Les recommandations sont des articles que le client peut être intéressé $ selon leur historique d&quot;achat, articles dans sa liste de souhait, et articles que d&quot;autres clients ont acheté en ligne et dans les magasins de brique-et- physiques. Pour les détaillants avec des catalogues, les recommandations permettent le client à la découverte de produit. Sur présentation de les produits visés aux intérêts d&quot;un client et aux habitudes d&quot;achats, les recommandations de produit peuvent aider les détaillants avec la - vente et la vente croisée, et peuvent améliorer la rétention client. Dans Dynamics 365 pour les opérations, les recommandations de produit sont actionnées par l&quot;apprentissage azuré cognitif de services et de machine Microsoft."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: af1f4ba1ed5efe0e35d08d37d09e7ada4a4c1b7a
ms.lasthandoff: 03/31/2017


---

# <a name="personalized-product-recommendations-overview"></a>Vue d'ensemble personnalisée de recommandations de produit

Dans Dynamics 365 pour les opérations, les recommandations de produit peuvent être affichées {{sur:on_the_point_of}} {{le:on_the_point_of}} {{point:on_the_point_of}} du périphérique de (POS) de vente. Les recommandations sont des articles que le client peut être intéressé $ selon leur historique d'achat, articles dans sa liste de souhait, et articles que d'autres clients ont acheté en ligne et dans les magasins de brique-et- physiques. Pour les détaillants avec des catalogues, les recommandations permettent le client à la découverte de produit. Sur présentation de les produits visés aux intérêts d'un client et aux habitudes d'achats, les recommandations de produit peuvent aider les détaillants avec la - vente et la vente croisée, et peuvent améliorer la rétention client. Dans Dynamics 365 pour les opérations, les recommandations de produit sont actionnées par l'apprentissage azuré cognitif de services et de machine Microsoft.

<a name="scenarios"></a>Scénarios
---------

Des recommandations de produit sont activées pour les scénarios suivants du PDV. Elles sont disponibles dans POS de cloud ou le Modern POS (MPOS).

1.  Sous ** détails des produits ** la page :

-   Si un Associé du magasin peut que a ** détails des produits ** page en regardant les transactions précédentes entre différents canaux, le moteur de recommandation suggère les articles supplémentaires qui sont susceptibles d'être achetés ensemble.
-   Si l'associer de magasin ajoute un client à la transaction puis visite a ** détails des produits ** page, le moteur de recommandation fournit des recommandations personnalisées dans l'historique de la transaction du client.

[proddetails d'![] (. /media/proddetails.png)](. /media/proddetails.png)

1.  Sous ** transaction ** la page :

-   Le moteur de recommandation suggère des articles selon la liste entière d'articles du panier.
-   Si l'associer de magasin ajoute un client à la transaction, le moteur de recommandation fournit des recommandations personnelles dans l'historique de la transaction du client et la liste des articles du panier.

** Note ** pour afficher les recommandations sur ** transaction ** la page, le détaillant doit mettre la mise en page de l'écran à jour dans Dynamics 365 pour les opérations. ** Recommandations ** le contrôle doit être déposé en fonction ** transaction ** à la page. ![transactionscreenmultipleproductslargemessengersbag-5 [] (. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

1.  Sous ** détails sur le client ** la page :
    -   Le moteur de recommandation suggère des articles de l'ID utilisateur et des articles de la liste des souhait du client.

[customerdetailsrecommendations d'![] (. /media/customerdetailsrecommendations.png)](. /media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Configurent Dynamics 365 pour les opérations proposer des recommandations de PDV
Pour paramétrer des recommandations de produit, procédez comme suit.

1.  Vérifiez que vous avez sélectionné le bon ** entité juridique **.
2.  Naviguez jusqu'à ** magasin d'entité **, sélectionnez ** des ventes au détail **, puis cliquez sur ** l'actualisez **. ** ** Elle utilise les données de démonstration (ou vos données) de votre base de données opérationnelle et les déplacera au magasin d'entité.
3.  Facultatif : Pour afficher les recommandations dans l'écran de transaction, allez dans ** mise en page de l'écran, ** effectuent une mise en page de l'écran, l'interrogation ** concepteur de mise en page de l'écran **, ** ** puis d'activer la fonction glisser-déplacer ** contrôle de recommandations ** où nécessaire.
4.  Atteindre ** les paramètres des ventes au détail **, sélectionnez ** Machine- apprentissage **, sélectionnez Oui ** ** sous ** activez les recommandations du PDV **.
5.  Pour afficher les recommandations sur le POS, tâche globale de configuration Runtime ** 1110 **. Pour refléter les modifications est effectuée au concepteur de mise en page de l'écran du PDV, exécutez la tâche de configuration des canaux ** 1070 **.

## <a name="how-does-it-work"></a>[] () mode d'emploi ?
Lorsque vous actualisez ** magasin d'entité ** l'entité, les actions suivantes ont lieu.

-   Les données au format requis par les services cognitifs sont extraites de Dynamics 365 pour la base de données opérationnelle d'opérations et envoyées au magasin d'entité.
-   Les données sont utilisées par l'usine azurée (ADF) de données pour nettoyer les données à l'aide de les scripts de ruche dans le cadre de les activités de radiogoniomètre automatique. Les données nettoyées sont enregistrées en stock d'objet blob.
-   Les données du stockage d'objet blob sont utilisées par l'API cognitive de services pour former un modèle de recommandation.

Lorsque vous activez ** activez les recommandations ** et exécutez les tâches de configuration, les actions suivantes ont lieu.

-   Les informations d'identification et l'ID modèles sont prélevés de l'API et enregistrés dans Dynamics 365 pour la base de données opérationnelle d'opérations, dans le web.config pour l'AOS, ainsi que le serveur de vente au détail.
-   Les informations d'identification et l'ID modèles sont mis disponible au CRT afin que les appels pour les recommandations de produit du PDV de cloud et le MPOS en mode en ligne puissent être réglés.


<a name="see-also"></a>Voir également :
--------

[Ajoutez un contrôle de recommandations à la page de transaction sur un périphérique du PDV] (add-recommendations-control-pos-screen.md)


