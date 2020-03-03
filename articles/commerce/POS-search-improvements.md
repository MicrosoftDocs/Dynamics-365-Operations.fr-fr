---
title: Recherche de produits et de clients dans le point de vente (PDV)
description: Cette rubrique fournit une vue d'ensemble des améliorations apportées à la fonctionnalité de recherche de produits et de clients dans Dynamics 365 Commerce.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 2b4c17b41056a35c2d2caaedb4f52998179b3c3e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022466"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Recherche de produits et de clients dans le point de vente (PDV)

[!include [banner](includes/banner.md)]

Modern Point of Sale (MPOS) et Cloud Point of Sale (CPOS) fournissent des fonctionnalités de recherche faciles à utiliser pour les produits et les clients. Comme la barre de recherche s'affiche toujours en haut de la fenêtre MPOS et de la fenêtre CPOS, les employés peuvent rechercher rapidement des produits et des clients.

Les employés peuvent rechercher des produits dans les assortiments et les catalogues associés au magasin actuel. Ils peuvent également rechercher dans les assortiments et les catalogues associés à un autre magasin de la société. Par conséquent, les caissiers peuvent vendre et resoumettre des produits en dehors de l'assortiment du magasin. De même, les employés peuvent rechercher les clients associés au magasin actuel ou tout autre magasin de la société. En outre, les employés peuvent rechercher les clients associés à une société différente de l'organisation parente.

## <a name="product-search"></a>Recherche du produit

Par défaut, les recherches de produits sont effectuées sur l'assortiment de magasin. Ce type de recherche est appelé *recherche de produit locale*. Toutefois, les employés peuvent facilement basculer vers tout catalogue associé au magasin actuel, ou ils peuvent les consulter dans un autre magasin. Ce type de recherche est appelé *recherche de produit à distance*. Pour modifier le catalogue, sélectionnez le bouton **Catégories** à gauche de la page. En haut du volet qui apparaît, sélectionnez le bouton **Modifier le catalogue**, puis sélectionnez l'un des catalogues disponibles pour y accéder. Le système recherche les produits dans le catalogue sélectionné.

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

L'expérience en matière de recherche de produit locale est devenue plus conviviale. Les modifications suivantes ont également été apportées :

- Les menus déroulants Produit et Client ont été ajoutés à la barre de recherche, afin que les employés puissent sélectionner **Produit** ou **Client** avant qu'ils effectuent la recherche. Par défaut, **Produit** est sélectionné, comme le montre l'illustration ci-après.
- Pour les recherches de plusieurs mots clés (c'est-à-dire, pour les recherches qui utilisent des critères de recherche), les détaillants peuvent configurer si les résultats de la recherche correspondent à *certains* termes de recherche ou uniquement ceux correspondant à *tous* les termes de recherche. Le paramètre pour cette fonctionnalité est disponible dans le profil de fonctionnalité du PDV, dans un nouveau groupe nommé **Recherche du produit**. Le paramètre par défaut est **Mettre en correspondance certains termes de recherche**. Ce paramètre est également le paramètre recommandé. Lorsque le paramètre **Mettre en correspondance certains termes de recherche** est utilisé, tous les produits qui correspondent partiellement ou complètement à un ou plusieurs termes de la recherche sont retournés comme résultats. Ces résultats sont triés automatiquement dans l'ordre croissant des produits dont la plupart des mots clés correspondent (complètement ou partiellement).

    Le paramètre **Mettre en correspondance tous les termes de recherche** ne renvoie que les produits qui correspondent à tous les critères de recherche (complète ou partielle). Ce paramètre est utile lorsque les noms de produit sont très longs, et que les employés souhaitent afficher uniquement les produits limités dans les résultats de la recherche. Toutefois, ce type de recherche a deux restrictions :

    - La recherche est effectuée sur plusieurs propriétés de produit. Par exemple, seuls les produits qui ont des mots clés recherchés dans au moins une propriété de produit sont retournés.
    - Les dimensions ne sont pas recherchées.

- Les détaillants peuvent désormais configurer la recherche de produit pour afficher des suggestions de recherche sous la forme de noms de produit de type utilisateurs. Un nouveau paramètre pour cette fonctionnalité est disponible dans le profil de fonctionnalité du PDV, dans un nouveau groupe nommé **Recherche du produit**. Le paramètre est appelé **Afficher des suggestions de recherche lors de la saisie**. Cette fonctionnalité peut aider les employés à rechercher rapidement le produit pour lequel il effectue une recherche, car ils ne doivent pas entrer le nom entier manuellement.
- Désormais, l'algorithme de la recherche de produit recherche également les critères de recherche contenus dans la propriété **Nom de recherche** du produit.

![Suggestions de produit](./media/Productsuggestions.png "Suggestions de produit")

## <a name="customer-search"></a>Recherche du client

La recherche de client est utilisée pour trouver des clients à différentes fins. Par exemple, les caissiers peuvent afficher la liste des souhaits d'un client ou l'historique de ses achats, ou encore ajouter le client à une transaction. L'algorithme de recherche fait correspondre les termes de la recherche avec les valeurs qui sont présentes dans les propriétés suivantes du client :

- Nom
- Adresse e-mail
- Numéro de téléphone
- Numéro de la carte de fidélité
- Adresse
- Numéro de compte

Parmi ces propriétés, le nom offre la plus grande flexibilité pour les recherches par plusieurs mots clés, car l'algorithme renvoie tous les clients qui correspondent à l'un des mots clés recherchés. Les clients qui correspondent le plus aux mots clés apparaissent en haut des résultats. Ainsi, cela aide les caissiers lorsqu'ils effectuent une recherche en saisissant le nom entier, mais lorsque le nom de famille et le prénom ont été ignorés pendant la saisie initiale des données. Toutefois, pour des raisons de performances, toutes les autres propriétés conservent l'ordre des mots clés de votre recherche. Par conséquent, si l'ordre des mots clés de la recherche ne correspond pas à l'ordre dans lequel les données sont stockées, aucun résultat ne sera retourné.

Par défaut, une recherche de client est effectuée sur les carnets d'adresses du client associés au magasin. Ce type de recherche est appelé *recherche de client locale*. Toutefois, les employés peuvent également rechercher des clients globalement. Autrement dit, ils peuvent effectuer une recherche parmi les magasins de la société et dans toutes les autres entités juridiques. Ce type de recherche est appelé *recherche de client à distance*.

Pour effectuer une recherche globalement, les employés peuvent sélectionner le bouton **Filtrer les résultats** en bas de la page, puis sélectionner l'option **Rechercher tous les magasins**, comme le montre l'illustration ci-après. Dans ce cas, il n'y a pas que les clients qui sont retournés. Tous les types de parties composant un carnet d'adresses du siège sont également retournés. Ces parties incluent les collaborateurs, les fournisseurs, les contacts et les concurrents.

> [!NOTE]
> Au moins quatre caractères doivent être saisis pour qu'une recherche de client à distance génèrent des résultats.

Dans une recherche de client à distance, l'ID client n'est pas affiché pour les clients d'autres entités juridiques, car aucun ID client n'a été créé pour ces parties dans la société actuelle. Toutefois, si un employé ouvre la page de détails du client, le système génère automatiquement un ID client pour la partie et associe également les carnets d'adresses du client du magasin au client. Par conséquent, le client est visible dans les recherches de magasin locales qui sont effectuées ultérieurement.

![Recherche de clients globale](./media/Globalcustomersearch.png "Recherche de clients globale")

### <a name="enhancements-to-local-customer-search"></a>Améliorations apportées à la recherche de clients locale

Les recherches qui sont basées sur le numéro de téléphone ont été simplifiées. Ces recherches ignorent désormais les caractères spéciaux, tels que les espaces, les traits d'union et les parenthèses, qui peuvent avoir été ajoutés lorsque le client les a créés. Par conséquent, les caissiers ne doivent pas s'inquiéter du format du numéro de téléphone lorsqu'ils effectuent une recherche. Ils peuvent également rechercher des clients en entrant un numéro de téléphone partiel. Si un numéro de téléphone inclut des caractères spéciaux, il est également affiché en recherchant les numéros qui s'affichent après les caractères spéciaux. Par exemple, si un numéro de téléphone de client a été saisi sous la forme **123-456-7890**, le caissier peut rechercher le client en saisissant **123**, **456**, **7890**, ou **1234567890**, ou en saisissant les premiers chiffres du numéro de téléphone.

La recherche traditionnelle de client peut être un processus relativement long, car elle recherche parmi les plusieurs champs. Au lieu de cela, les caissiers peuvent désormais rechercher dans une propriété de client simple, comme le nom, l'adresse e-mail, ou le numéro de téléphone. Les propriétés que l'algorithme de recherche du client utilise sont collectivement désignées comme *critères de recherche du client*. L'administrateur système peut facilement configurer un ou plusieurs critères comme raccourcis qui figurent dans le PDV. Comme la recherche est limitée à un critère unique, seuls les résultats de la recherche appropriés sont affichés, et les performances sont supérieures aux performances d'une recherche client standard. L'illustration suivante montre les raccourcis de la recherche de client dans le PDV.

![Raccourcis de la recherche de clients](./media/SearchShortcutsPOS.png "Raccourcis de la recherche de clients")

Pour définir des critères de recherche en tant que raccourcis, l'administrateur doit ouvrir la page **Paramètres de commerce**, puis, dans l'onglet **Critères de recherche POS**, sélectionnez tous les critères à afficher en tant que raccourcis.

![Configurer les raccourcis de la recherche](./media/ConfigureShortcutsAX.png "Configurer les raccourcis de la recherche")

> [!NOTE]
> Si vous ajoutez un trop grand nombre de raccourcis, le menu déroulant de la barre de recherche du PDV est surchargé, et l'expérience de recherche de l'employé peut en être affectée. Il est recommandé d'ajouter uniquement autant de raccourcis que nécessaire.

Le champ **Ordre d'affichage** détermine l'ordre dans lequel les raccourcis sont affichés dans le PDV. Les critères affichés sont les propriétés prêtes à l'emploi que l'algorithme de recherche du client utilise pour rechercher des clients. Toutefois, les partenaires peuvent ajouter des propriétés personnalisées comme raccourcis de recherche. Pour ajouter des propriétés personnalisées comme raccourcis de recherche, l'administrateur système doit étendre l'énumération extensible (enum) utilisée pour les critères de recherche de client puis marquer les propriétés personnalisées du partenaire comme raccourcis. Les partenaires sont responsables d'écrire le code pour rechercher des résultats lorsque leurs raccourcis personnalisés sont utilisés pour des recherches.

> [!NOTE]
> Une propriété personnalisée qui est ajoutée à l'énumération n'affecte pas l'algorithme de recherche du client standard. En d'autres termes, l'algorithme de recherche du client ne recherche pas dans la propriété personnalisée. Les utilisateurs peuvent utiliser une propriété personnalisée pour les recherches uniquement si cette propriété personnalisée est ajoutée comme raccourci, ou si l'algorithme de recherche par défaut est remplacé.

Dans une prochaine version de Commerce, les détaillants pourront définir le mode de recherche de clients par défaut dans le PDV sur **Rechercher dans tous les magasins**. Cette configuration peut être utile dans les cas où les clients qui ont été créés en dehors des PDV doivent être recherchés immédiatement (par exemple, avant même d'exécuter la tâche de distribution). Une nouvelle option **Mode de recherche de client par défaut** sera disponible dans le profil de fonctionnalité du PDV. Définissez-la sur **Activé** pour définir le mode de recherche par défaut sur **Rechercher dans tous les magasins**. Chaque tentative de recherche d'un client effectuera alors un appel en temps réel au siège.

Pour empêcher les problèmes inattendus de performances, cette configuration est masquée derrière un indicateur de version d'évaluation nommé **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Par conséquent, pour afficher le paramètre **Mode de recherche de client par défaut** dans l'interface utilisateur (IU), le détaillant doit créer un ticket de support pour ses environnements de test d'acceptation par l'utilisateur (UAT) et de production. Une fois le ticket réceptionné, l'équipe d'ingénierie collaborera avec le détaillant pour s'assurer que celui-ci effectue le test dans un environnement autre que de production afin de pouvoir évaluer les performances et de mettre en œuvre toutes les optimisations requises.