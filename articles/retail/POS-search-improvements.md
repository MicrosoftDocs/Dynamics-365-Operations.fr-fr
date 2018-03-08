---
title: Recherche de produits et recherche de clients dans un Point de vente (PDV)
description: "Cette rubrique fournit une vue d'ensemble des améliorations apportées à la fonctionnalité de recherche de produits et de clients dans Dynamics 365 for Retail."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 08/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 5f6f9a02b20549a75941d367c1b46e3439360078
ms.contentlocale: fr-fr
ms.lasthandoff: 01/19/2018

---

# <a name="overview-of-product-and-customer-search-in-point-of-sale"></a>Vue d'ensemble de la recherche de produits et de clients dans un point de vente

[!include[banner](includes/banner.md)]

Le point de vente moderne (MPOS) et le point de vente cloud (CPOS) fournissent des fonctionnalités de recherche faciles à utiliser qui permettent aux employés de magasin de rechercher rapidement des produits et des clients. La barre de recherche s'affiche toujours en haut du point MPOS et du point CPOS, afin que les employés puissent trouver rapidement des produits et des clients.

Les employés peuvent rechercher des produits dans les assortiments et catalogues associés au magasin actuel, mais aussi dans les assortiments et les catalogues qui sont associés à un autre magasin de la société. Par conséquent, les caissiers peuvent vendre et resoumettre des produits en dehors de l'assortiment du magasin. De même, les employés peuvent rechercher les clients associés au magasin actuel ou tout autre magasin de la société. En outre, les employés peuvent rechercher les clients associés à une société différente de l'organisation parente.

## <a name="product-search"></a>Recherche du produit 

Par défaut, une recherche de produit est effectuée sur l'assortiment de magasin. Ce type de recherche est appelé *recherche de produit locale*. Toutefois, les employés peuvent facilement basculer vers tout catalogue associé au magasin actuel, ou ils peuvent les consulter dans un autre magasin. Ce type de recherche est appelé *recherche de produit à distance*. Pour modifier le catalogue, sélectionnez le bouton **Catégories** à gauche de la page. En haut du volet qui apparaît, sélectionnez le bouton **Modifier le catalogue**, puis sélectionnez l'un des catalogues disponibles pour y accéder. Le système recherche les produits dans le catalogue sélectionné.

Dans la page **Modifier le catalogue**, les employés peuvent facilement sélectionner n'importe quel magasin, ou ils peuvent rechercher des produits dans tous les magasins.

![Modification du catalogue](./media/Changecatalog.png "Modification du catalogue")
 
Une recherche locale permet d'effectuer une recherche de produit dans les propriétés de produit suivantes :

- Numéro de produit
- Nom du produit
- Description 
- Dimensions
- Code-barres
- Nom de recherche

### <a name="enhancements-to-local-product-searches"></a>Améliorations apportées aux recherches de produits locales

L'expérience en matière de recherche de produit locale a été rendue plus conviviale. Les modifications suivantes ont également été apportées :

- Les menus déroulants Produit et Client ont été ajoutés à la barre de recherche, afin que les employés puissent sélectionner **Produit** ou **Client** avant qu'ils effectuent la recherche. Par défaut, **Produit** est sélectionné, comme le montre l'illustration ci-après.
- Pour les recherches de plusieurs mots clés (c'est-à-dire, pour les recherches qui utilisent des critères de recherche), les détaillants peuvent configurer si les résultats de la recherche correspondent à un terme de recherche ou uniquement ceux correspondant à tous les termes de recherche. Ce paramètre est disponible dans le profil de fonctionnalité du PDV, sous un nouveau groupe nommé **Recherche du produit**. Le paramètre par défaut est **Mettre en correspondance certains termes de recherche**. Ce paramètre est également le paramètre recommandé. Lorsque le paramètre **Mettre en correspondance certains termes de recherche** est utilisé, tous les produits qui correspondent partiellement ou complètement à un ou plusieurs critères de recherche sont retournés, et les résultats sont triés automatiquement dans l'ordre croissant des produits qui comportent le plus de correspondances de mot clé (complètes ou partielles).

    Le paramètre **Mettre en correspondance tous les termes de recherche** ne renvoie que les produits qui correspondent à tous les critères de recherche (complète ou partielle). Ce paramètre est utile lorsque les noms de produit sont très longs, et que les employés souhaitent afficher uniquement les produits limités dans les résultats de la recherche. Toutefois, ce type de recherche a deux restrictions :

    - La recherche est effectuée sur plusieurs propriétés de produit. Par exemple, seuls les produits qui ont des mots clés recherchés dans au moins une propriété de produit sont retournés.
    - Les dimensions ne sont pas recherchées.

- Les détaillants peuvent désormais configurer la recherche de produit pour afficher des suggestions de recherche sous la forme de noms de produit de type utilisateurs. Un nouveau paramètre pour cette fonctionnalité est disponible dans le profil de fonctionnalité du PDV, sous un nouveau groupe nommé **Recherche du produit**. Le paramètre est appelé **Afficher des suggestions de recherche lors de la saisie**. Cette fonctionnalité peut aider les employés à rechercher rapidement le produit pour lequel il effectue une recherche, car ils ne doivent pas entrer le nom entier manuellement.
- Désormais, l'algorithme de la recherche de produit recherche également les critères de recherche contenus dans la propriété **Nom de recherche** du produit.

![Suggestions de produit](./media/Productsuggestions.png "Suggestions de produit")

## <a name="customer-search"></a>Recherche du client

La recherche de client est utilisée pour trouver des clients à différentes fins. Par exemple, les caissiers peuvent afficher la liste des souhaits d'un client ou l'historique de ses achats, ou encore ajouter le client à une transaction. Dans le cas de la recherche de plusieurs mots clés, l'algorithme de recherche de clients retourne tous les clients qui correspondent à l'un des mots clés recherchés. Cependant, les clients qui correspondent le plus aux mots-clés apparaissent en haut des résultats. Ce comportement est analogue à la manière dont les autres moteurs de recherche affichent les résultats. Ils affichent d'abord les résultats qui correspondent aux critères les plus recherchés, puis ils affichent les résultats qui correspondent partiellement aux mots clés de votre recherche. Cela aide les caissiers lorsqu'ils utilisent plusieurs mots clés pour leur recherche, mais qu'un des mots clés comporte une erreur d'orthographe.

Par défaut, une recherche de client est effectuée sur les carnets d'adresses du client associés au magasin. Ce type de recherche est appelé *recherche de client locale*. Toutefois, les employés peuvent également rechercher des clients globalement. Autrement dit, ils peuvent effectuer une recherche parmi les magasins de la société et dans toutes les autres entités juridiques. Ce type de recherche est appelé *recherche de client à distance*.

Pour effectuer une recherche globalement, les employés peuvent sélectionner le bouton **Filtrer les résultats** en bas de la page, puis sélectionner l'option **Rechercher tous les magasins**, comme le montre l'illustration ci-après. Dans ce cas, il n'y a pas que les clients qui sont retournés. Tous les types de parties composant un carnet d'adresses du siège sont également retournés. Ces parties incluent les collaborateurs, les fournisseurs, les contacts et les concurrents.

> [!NOTE]
> Au moins quatre caractères doivent être saisis pour qu'une recherche de client à distance génèrent des résultats.

Dans une recherche de client à distance, l'ID client n'est pas affiché pour les clients d'autres entités juridiques, car aucun ID client n'a été créé pour ces parties dans la société actuelle. Toutefois, si un employé ouvre la page de détails du client, le système génère automatiquement un ID client pour la partie et associe également les carnets d'adresses du client du magasin au client. Par conséquent, le client est visible dans les recherches de magasin locales qui sont effectuées ultérieurement.

![Recherche de client globale](./media/Globalcustomersearch.png "Recherche de client globale")

### <a name="enhancements-to-local-customer-searches"></a>Améliorations apportées aux recherches de clients locales

Les recherches de clients locales aident les employés à trouver rapidement des clients en fonction de leur numéro de téléphone. Les employés ne doivent pas saisir des caractères spéciaux ajoutés au numéro de téléphone d'un client, tels que des espaces, des tirets ou des parenthèses. Bien que les caissiers puissent enregistrer des numéros de téléphone dans n'importe quel format (par exemple, ils peuvent inclure des parenthèses, traits d'union, symboles, etc.), ils peuvent rechercher des clients en saisissant une partie du numéro de téléphone. Si un caissier a inclus des caractères spéciaux lorsqu'il a saisi un numéro de téléphone, d'autres caissiers peuvent trouver le client en saisissant les chiffres qui apparaissent après les caractères spéciaux. Par exemple, si un numéro de téléphone de client a été saisi sous la forme **123-456-7890**, le caissier peut rechercher le client en saisissant **123**, **456**, **7890**, ou **1234567890**, ou en saisissant partiellement les premiers chiffres du numéro de téléphone.

