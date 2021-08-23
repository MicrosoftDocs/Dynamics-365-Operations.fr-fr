---
title: Recherche de produits et de clients dans le point de vente (PDV)
description: Cette rubrique fournit une vue d’ensemble des améliorations apportées à la fonctionnalité de recherche de produits et de clients dans Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 03/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: 043a630408d6b03e528f0afd5443de73ad5f3802c968b9d9bd7a5c51bfe1fb03
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716393"
---
# <a name="product-search-and-customer-search-in-the-point-of-sale-pos"></a>Recherche de produits et de clients dans le point de vente (PDV)

[!include [banner](includes/banner.md)]

Modern Point of Sale (MPOS) et Cloud Point of Sale (CPOS) fournissent des fonctionnalités de recherche faciles à utiliser pour les produits et les clients. Comme la barre de recherche s’affiche toujours en haut de la fenêtre MPOS et de la fenêtre CPOS, les employés peuvent rechercher rapidement des produits et des clients.

Les employés peuvent rechercher des produits dans les assortiments et les catalogues associés au magasin actuel. Ils peuvent également rechercher dans les assortiments et les catalogues associés à un autre magasin de la société. Par conséquent, les caissiers peuvent vendre et resoumettre des produits en dehors de l’assortiment du magasin. De même, les employés peuvent rechercher les clients associés au magasin actuel ou tout autre magasin de la société. En outre, les employés peuvent rechercher les clients associés à une société différente de l’organisation parente.

## <a name="product-search"></a>Recherche du produit

Par défaut, les recherches de produits sont effectuées sur l’assortiment de magasin. Ce type de recherche est appelé *recherche de produit locale*. Toutefois, les employés peuvent facilement basculer vers tout catalogue associé au magasin actuel, ou ils peuvent les consulter dans un autre magasin. Ce type de recherche est appelé *recherche de produit à distance*. Pour modifier le catalogue, sélectionnez le bouton **Catégories** à gauche de la page. En haut du volet qui apparaît, sélectionnez le bouton **Modifier le catalogue**, puis sélectionnez l’un des catalogues disponibles pour y accéder. Le système recherche les produits dans le catalogue sélectionné.

Dans la page **Modifier le catalogue**, les employés peuvent facilement sélectionner n’importe quel magasin, ou ils peuvent rechercher des produits dans tous les magasins.

![Modification du catalogue.](./media/Changecatalog.png "Modification du catalogue")

Une recherche locale permet d’effectuer une recherche de produit dans les propriétés de produit suivantes :

- Numéro de produit
- Nom du produit
- Description
- Dimensions
- Code-barres
- Nom de recherche

### <a name="additional-local-product-search-capabilities"></a>Fonctionnalités supplémentaires de recherche de produits locale

- Pour les recherches de plusieurs mots clés (c’est-à-dire, pour les recherches qui utilisent des critères de recherche), les détaillants peuvent configurer si les résultats de la recherche correspondent à *certains* termes de recherche ou uniquement ceux correspondant à *tous* les termes de recherche. Le paramètre pour cette fonctionnalité est disponible dans le profil de fonctionnalité du PDV, dans un nouveau groupe nommé **Recherche du produit**. Le paramètre par défaut est **Mettre en correspondance certains termes de recherche**. Ce paramètre est également le paramètre recommandé. Lorsque le paramètre **Mettre en correspondance certains termes de recherche** est utilisé, tous les produits qui correspondent partiellement ou complètement à un ou plusieurs termes de la recherche sont retournés comme résultats. Ces résultats sont triés automatiquement dans l’ordre croissant des produits dont la plupart des mots clés correspondent (complètement ou partiellement).

    Le paramètre **Mettre en correspondance tous les termes de recherche** ne renvoie que les produits qui correspondent à tous les critères de recherche (complète ou partielle). Ce paramètre est utile lorsque les noms de produit sont très longs, et que les employés souhaitent afficher uniquement les produits limités dans les résultats de la recherche. Toutefois, ce type de recherche a deux restrictions :

    - La recherche est effectuée sur plusieurs propriétés de produit. Par exemple, seuls les produits qui ont des mots clés recherchés dans au moins une propriété de produit sont retournés.
    - Les dimensions ne sont pas recherchées.

- Les détaillants peuvent configurer la recherche de produits pour afficher des suggestions de recherche sous la forme de noms de produit de type utilisateurs. Un nouveau paramètre pour cette fonctionnalité est disponible dans le profil de fonctionnalité du PDV, dans un nouveau groupe nommé **Recherche du produit**. Le paramètre est appelé **Afficher des suggestions de recherche lors de la saisie**. Cette fonctionnalité peut aider les employés à rechercher rapidement le produit pour lequel il effectue une recherche, car ils ne doivent pas entrer le nom entier manuellement.
- Désormais, l’algorithme de la recherche de produit recherche également les critères de recherche contenus dans la propriété **Nom de recherche** du produit.

![Suggestions de produit.](./media/Productsuggestions.png "Suggestions de produit")

## <a name="customer-search"></a>Recherche de client

La recherche de client est utilisée pour trouver des clients à différentes fins. Par exemple, les caissiers peuvent afficher la liste des souhaits d’un client ou l’historique de ses achats, ou encore ajouter le client à une transaction. L’algorithme de recherche fait correspondre les termes de la recherche avec les valeurs qui sont présentes dans les propriétés suivantes du client :

- Nom
- Adresse e-mail
- Numéro de téléphone
- Numéro de la carte de fidélité
- Adresse
- Numéro de compte

Parmi ces propriétés, le nom offre la plus grande flexibilité pour les recherches par plusieurs mots clés, car l’algorithme renvoie tous les clients qui correspondent à l’un des mots clés recherchés. Les clients qui correspondent le plus aux mots clés apparaissent en haut des résultats. Ainsi, cela aide les caissiers lorsqu’ils effectuent une recherche en saisissant le nom entier, mais lorsque le nom de famille et le prénom ont été ignorés pendant la saisie initiale des données. Toutefois, pour des raisons de performances, toutes les autres propriétés conservent l’ordre des mots clés de votre recherche. Par conséquent, si l’ordre des mots clés de la recherche ne correspond pas à l’ordre dans lequel les données sont stockées, aucun résultat ne sera retourné.

Par défaut, une recherche de client est effectuée sur les carnets d’adresses du client associés au magasin. Ce type de recherche est appelé *recherche de client locale*. Toutefois, les employés peuvent également rechercher des clients globalement. Autrement dit, ils peuvent effectuer une recherche parmi les magasins de la société et dans toutes les autres entités juridiques. Ce type de recherche est appelé *recherche de client à distance*.

Pour effectuer une recherche globalement, les employés peuvent sélectionner le bouton **Filtrer les résultats** en bas de la page, puis sélectionner l’option **Rechercher tous les magasins**, comme le montre l’illustration ci-après. Dans ce cas, il n’y a pas que les clients qui sont retournés. Tous les types de parties composant un carnet d’adresses du siège sont également retournés. Ces parties incluent les collaborateurs, les fournisseurs, les contacts et les concurrents.

> [!NOTE]
> Au moins quatre caractères doivent être saisis pour qu’une recherche de client à distance génèrent des résultats.

L’ID client n’est pas affiché pour les clients demandés à partir d’autres entités juridiques, car aucun ID client n’a été créé pour ces parties dans la société actuelle. Toutefois, si un employé ouvre la page de détails du client, le système génère automatiquement un ID client pour la partie et associe également les carnets d’adresses du client du magasin au client. Par conséquent, le client est visible dans les recherches de magasin locales qui sont effectuées ultérieurement.

![Recherche de clients globale.](./media/Globalcustomersearch.png "Recherche de clients globale")

### <a name="additional-local-customer-search-capabilities"></a>Fonctionnalités supplémentaires de recherche de clients locale

Lorsque l’utilisateur recherche un numéro de téléphone, le système ignore les caractères spéciaux (tels que les espaces, les traits d’union et les parenthèses) qui peuvent avoir été ajoutés lorsque le client les a créés. Par conséquent, les caissiers ne doivent pas s’inquiéter du format du numéro de téléphone lorsqu’ils effectuent une recherche. Par exemple, si un numéro de téléphone de client a été saisi sous la forme **123-456-7890**, le caissier peut rechercher le client en saisissant **1234567890** ou en saisissant les premiers chiffres du numéro de téléphone.

> [!NOTE]
> Un client peut avoir plusieurs numéros de téléphone et plusieurs e-mails. L’algorithme de recherche client recherche également ces e-mails et numéros de téléphone secondaires, mais la page de résultats de recherche client n’affiche que l’adresse e-mail et le numéro de téléphone principaux. Cela peut entraîner une certaine confusion car les résultats client renvoyés n’afficheraient pas l’e-mail ou le numéro de téléphone recherché. Dans une prochaine version, nous prévoyons d’améliorer l’écran des résultats de recherche de clients pour afficher ces informations.

La recherche traditionnelle de client peut être un processus relativement long, car elle recherche parmi les plusieurs champs. Au lieu de cela, les caissiers peuvent rechercher dans une propriété de client simple, comme le nom, l’adresse e-mail, ou le numéro de téléphone. Les propriétés que l’algorithme de recherche du client utilise sont collectivement désignées comme *critères de recherche du client*. L’administrateur système peut facilement configurer un ou plusieurs critères comme raccourcis qui figurent dans le PDV. Comme la recherche est limitée à un critère unique, seuls les résultats de la recherche appropriés sont affichés, et les performances sont supérieures aux performances d’une recherche client standard. L’illustration suivante montre les raccourcis de la recherche de client dans le PDV.

![Raccourcis de la recherche de clients.](./media/SearchShortcutsPOS.png "Raccourcis de la recherche de clients")

Pour définir des critères de recherche en tant que raccourcis, l’administrateur doit ouvrir la page **Paramètres de commerce**, puis, dans l’onglet **Critères de recherche POS**, sélectionnez tous les critères à afficher en tant que raccourcis.

![Configurer les raccourcis de la recherche.](./media/ConfigureShortcutsAX.png "Configurer les raccourcis de la recherche")

> [!NOTE]
> Si vous ajoutez un trop grand nombre de raccourcis, le menu déroulant de la barre de recherche du PDV est surchargé, et l’expérience de recherche de l’employé peut en être affectée. Il est recommandé d’ajouter uniquement autant de raccourcis que nécessaire.

Le champ **Ordre d’affichage** détermine l’ordre dans lequel les raccourcis sont affichés dans le PDV. Les critères affichés sont les propriétés prêtes à l’emploi que l’algorithme de recherche du client utilise pour rechercher des clients. Toutefois, les partenaires peuvent ajouter des propriétés personnalisées comme raccourcis de recherche. Pour ajouter des propriétés personnalisées comme raccourcis de recherche, l’administrateur système doit étendre l’énumération extensible (enum) utilisée pour les critères de recherche de client puis marquer les propriétés personnalisées du partenaire comme raccourcis. Les partenaires sont responsables d’écrire le code pour rechercher des résultats lorsque leurs raccourcis personnalisés sont utilisés pour des recherches.

> [!NOTE]
> Une propriété personnalisée qui est ajoutée à l’énumération n’affecte pas l’algorithme de recherche du client standard. En d’autres termes, l’algorithme de recherche du client ne recherche pas dans la propriété personnalisée. Les utilisateurs peuvent utiliser une propriété personnalisée pour les recherches uniquement si cette propriété personnalisée est ajoutée comme raccourci, ou si l’algorithme de recherche par défaut est remplacé.

Les détaillants peuvent également définir le mode de recherche de clients par défaut dans le PDV sur **Rechercher dans tous les magasins**. Cette configuration peut être utile dans les cas où les clients qui ont été créés en dehors des PDV doivent être recherchés immédiatement (par exemple, avant même d’exécuter la tâche de distribution). Pour ce faire, le revendeur doit activer l’option **Mode de recherche de clients par défaut** dans le profil de fonctionnalité du PDV. Lorsque le paramètre est **Oui**, chaque tentative de recherche d’un client effectuera un appel en temps réel au siège.

Pour empêcher les problèmes inattendus de performances, cette configuration est masquée derrière un indicateur de version d’évaluation nommé **CUSTOMERSEARCH_ENABLE_DEFAULTSEARCH_FLIGHTING**. Par conséquent, pour afficher le paramètre **Mode de recherche de client par défaut** dans l’interface utilisateur (IU), le détaillant doit créer un ticket de support pour ses environnements de test d’acceptation par l’utilisateur (UAT) et de production. Une fois le ticket réceptionné, l’équipe d’ingénierie collaborera avec le détaillant pour s’assurer que celui-ci effectue le test dans un environnement autre que de production afin de pouvoir évaluer les performances et de mettre en œuvre toutes les optimisations requises.

## <a name="cloud-powered-customer-search"></a>Recherche de clients dans le cloud

La version préliminaire de la fonctionnalité de recherche de clients à l’aide du service de recherche cognitive Azure a été publiée dans le cadre de la version 10.0.18 de Commerce. En plus des améliorations de performances, les utilisateurs du service bénéficient également d’un affinement enrichi et de capacités de pertinence améliorées. Les améliorations de performances sont particulièrement évidentes lorsque la fonction de recherche globale (« Rechercher dans tous les magasins ») du PDV est utilisée. En effet, les résultats de la recherche sont extraits de l’index de recherche Azure au lieu d’être interrogés à partir des données de Commerce Headquarters. 

### <a name="enable-the-cloud-powered-search-feature"></a>Activer la fonction de recherche dans le cloud

> [!NOTE]
> Il est nécessaire que Commerce Headquarters et Commerce Scale Unit soient mis à jour vers la version 10.0.18. La mise à jour du PDV n’est pas requise.

Pour activer la fonctionnalité de recherche dans le cloud dans Commerce Headquarters, procédez comme suit.

1. Accédez à **Administration système \> Espaces de travail \> Gestion des fonctionnalités**.
1. Trouvez et sélectionnez la fonctionnalité **(Version préliminaire) Recherche de clients dans le cloud**, puis sélectionnez **Activer maintenant**.
1. Accédez à **Retail et Commerce > Configuration du siège> Planificateur de Commerce > Initialiser le planificateur de Commerce** et sélectionnez **OK** pour afficher la nouvelle tâche **1010_CustomerSearch** sur le formulaire **Programme de distribution**.
1. Accédez à **Retail et Commerce > IT Retail et Commerce > Programme de distribution**.
1. Exécutez la tâche **1010_CustomerSearch**. Cette tâche publie la date dans l’index de recherche Azure. Une fois la publication de l’index terminée, le statut de la tâche sera défini sur **Appliqué**.
1. Une fois que le statut de la tâche **1010_CustomerSearch** est défini sur **Appliqué**, lancez la tâche **1110 - Configuration globale** pour mettre à jour les canaux de PDV de la fonctionnalité nouvellement activée dans **Gestion des fonctionnalités**.
1. Ensuite, exécutez la tâche **1010_CustomerSearch** à intervalles réguliers pour envoyer les mises à jour des clients à l’index de recherche.

> [!NOTE]
> Pour la publication initiale de l’index, la tâche **1010_CustomerSearch** peut prendre quelques heures, car elle enverra tous les enregistrements client à l’index de recherche Azure. Les mises à jour suivantes devraient prendre quelques minutes. Pendant la période où la fonctionnalité de recherche dans le cloud est activée mais que la publication de l’index n’est pas encore terminée, la recherche client à partir du PDV sera par défaut la recherche SQL existante. Cela garantit que les opérations de stockage ne sont pas interrompues.

### <a name="functional-differences-from-the-existing-search"></a>Différences fonctionnelles par rapport à la recherche existante

La liste suivante montre les différences entre la fonctionnalité de recherche de clients dans le cloud et la fonctionnalité de recherche existante. 

- Les clients créés et modifiés dans Commerce Headquarters sont envoyés à l’index de recherche Azure lorsque la tâche **1010_CustomerSearch** est exécutée. Ces mises à jour de l’index prennent au moins 15 à 20 minutes. Les utilisateurs du PDV pourront rechercher de nouveaux clients (ou effectuer une recherche en fonction d’informations mises à jour) environ 15 à 20 minutes après les mises à jour dans Commerce Headquarters. Si votre processus métier nécessite que les clients créés dans Commerce Headquarters soient immédiatement consultables dans le PDV, ce service peut ne pas être adapté à vos besoins.
- Les nouveaux clients créés dans PDV sont envoyés à l’index de recherche Azure à partir de Commerce Scale Unit et sont immédiatement consultables dans n’importe quel magasin. Cependant, si la fonctionnalité de création de client asynchrone est activée, les nouveaux enregistrements client ne seront pas publiés dans l’index de recherche Azure à partir de Commerce Scale Unit et ne pourront pas faire l’objet d’une recherche à partir du PDV tant que les informations client ne seront pas synchronisées avec Commerce Headquarters et que les ID client ne seront pas générés pour les clients asynchrones. La tâche **1010_CustomerSearch** sera alors en mesure d’envoyer les enregistrements de clients asynchrones à l’index de recherche Azure. En moyenne, 30 minutes s’écouleront avant que les clients asynchrones nouvellement créés puissent être recherchés sur le PDV. Cette estimation suppose que l’exécution des tâches **1010_CustomerSearch**, **Tâche P**, et **Synchroniser les clients et les partenaires commerciaux à partir du mode asynchrone** est programmée toutes les 15 minutes.
- La recherche dans le cloud recherche également les e-mails et les numéros de téléphone secondaires des clients, mais actuellement les résultats de recherche des clients affichent uniquement le numéro de téléphone principal et l’adresse e-mail principale des clients. À première vue, il peut sembler que des résultats de recherche non pertinents sont renvoyés, mais la vérification de l’adresse e-mail secondaire et du numéro de téléphone d’un client dans les résultats de recherche peut aider à vérifier si le mot-clé recherché a généré une correspondance client. Pour éviter une telle confusion, il est prévu d’améliorer la page de résultats de recherche afin de permettre aux utilisateurs de comprendre facilement pourquoi un résultat de recherche a été renvoyé.
- L’obligation de rechercher au moins 4 caractères dans une recherche globale (« Rechercher dans tous les magasins ») n’est pas applicable à ce service.

> [!NOTE]
> La fonctionnalité de recherche de clients à l’aide du service de recherche cognitive Azure est disponible dans certaines régions seulement pour la version préliminaire. La fonctionnalité de recherche de clients *n’est pas* disponible dans les régions suivantes :
> - Brésil
> - Inde
> - Canada
> - Royaume-Uni

[!INCLUDE[footer-include](../includes/footer-banner.md)]
