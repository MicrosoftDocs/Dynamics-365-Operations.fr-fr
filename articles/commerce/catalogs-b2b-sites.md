---
title: Créer des catalogues Commerce pour les sites B2B
description: Cet article décrit comment créer des catalogues Commerce pour les sites interentreprises (B2B) dans Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 07/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 7d4ed3e2a76924c2c3c0ba55e21ba648e8da7b76
ms.sourcegitcommit: d1491362421bf2fcf72a81dc2dc2d13d3b98122b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2022
ms.locfileid: "9136824"
---
# <a name="create-commerce-catalogs-for-b2b-sites"></a>Créer des catalogues Commerce pour les sites B2B

[!include [banner](includes/banner.md)]

Cet article décrit comment créer des catalogues de produits Commerce pour les sites interentreprises (B2B) dans Microsoft Dynamics 365 Commerce. Pour obtenir des réponses aux questions fréquemment posées sur les catalogues Commerce pour les sites B2B, consultez [FAQ des Catalogues Commerce pour B2B](catalogs-b2b-sites-FAQ.md).

> [!NOTE]
> Cet article s’applique à Dynamics 365 Commerce version 10.0.27 et versions ultérieures.

Vous pouvez utiliser les catalogues Commerce pour identifier les produits que vous souhaitez proposer dans vos magasins en ligne B2B. Quand vous créez un catalogue, identifiez les magasins en ligne dans lesquels les produits sont proposés, ajoutez les produits souhaités et améliorez les offres de produit en ajoutant des détails de vente. Vous pouvez créer plusieurs catalogues pour chaque boutique en ligne B2B, comme indiqué dans l’illustration suivante.

![Aperçu des catalogues de produits commerciaux.](./media/Commerce_Catalogs.png)

Les catalogues de produits Commerce vous permettent de définir les informations suivantes :

- **Type de catalogue** – Configurez la valeur comme **B2B**. Vous pouvez définir des propriétés spécifiques au catalogue B2B telles qu’une hiérarchie de navigation, une hiérarchie client et des métadonnées d’attribut pour le catalogue. 
- **Hiérarchie de navigation spécifique au catalogue** – Les organisations peuvent créer une structure de catégorie distincte pour leur catalogue spécifique.
- **Métadonnées d’attributs spécifiques au catalogue** – Les attributs contiennent des détails sur un produit. En affectant des attributs à une catégorie de la hiérarchie de navigation, vous pouvez définir des valeurs pour ces attributs au niveau des produits affectés à cette catégorie. Le organisations peuvent ensuite effectuer les tâches suivantes :

    - Définir les valeurs d’attribut spécifiques au catalogue.
    - Contrôler la visibilité des attributs au niveau du catalogue.
    - Sélectionner les affinements spécifiques à un catalogue individuel.

- **Canaux** – Les organisations peuvent associer plusieurs canaux en ligne B2B à un catalogue. La prise en charge de bout en bout des catalogues n’est actuellement disponible que pour les boutiques en ligne B2B.
- **Hiérarchies des clients** – Pour un canal B2B donné, les organisations peuvent mettre un catalogue spécifique à la disposition de partenaires B2B sélectionnés en associant des hiérarchies de clients à ce catalogue.
- **Groupes de prix** – Vous pouvez configurer des prix et des promotions spécifiques à un catalogue donné. Cette capacité est une raison essentielle pour définir un catalogue pour un canal B2B. Les groupes de prix pour les catalogues permettent aux organisations de mettre des produits à la disposition de leurs organisations B2B prévues et d’appliquer leurs prix et remises préférés. Les clients B2B qui commandent à partir d’un catalogue configuré peuvent bénéficier de prix spéciaux et de promotions après s’être connectés à un site Commerce B2B. Pour configurer des prix spécifiques au catalogue, sélectionnez **Groupes de prix** sur l’onglet **Catalogues** pour associer un ou plusieurs groupes de prix au catalogue. Les accords commerciaux, les journaux d’ajustement de prix et les remises avancées associés au même groupe de prix sont appliqués quand les clients passent une commande à partir de ce catalogue. (Les remises avancées incluent les remises de seuil, de quantité et de combinaison.) Pour plus d’informations sur les groupes de prix, voir [Groupes de prix](price-management.md#price-groups).

> [!NOTE]
> Cette fonctionnalité est disponible à partir de la version 10.0.27 de Dynamics 365 Commerce. Pour configurer des configurations spécifiques au catalogue telles que la hiérarchie de navigation et la hiérarchie des clients, dans Commerce headquarters, accédez à l’espace de travail **Gestion des fonctionnalités** (**Administration système \> Espaces de travail \> Gestion des fonctionnalités**), activez la fonctionnalité **Activer l’utilisation de plusieurs catalogues sur les canaux de vente au détail**, puis exécutez la tâche **1110 CDX**. Lorsque vous activez cette fonctionnalité, tous les catalogues existants utilisés pour les points de vente ou un centre d’appels seront marqués comme **Type de catalogue = B2C** sur la page **Catalogues**. Seuls les catalogues existants et nouveaux marqués comme **Type de catalogue = B2C** sont applicables aux points de vente et à un centre d’appels. 

## <a name="b2b-catalog-process-flow"></a>Flux de processus du catalogue B2B

Le processus de création et de traitement d’un catalogue comporte quatre étapes générales. Chaque étape est expliquée en détail dans la section suivante.

> [!NOTE]
> Avant de continuer, assurez-vous que le catalogue est marqué comme **Type de catalogue = B2B**.

1. **[Configuration](#configure-the-catalog)**

    - Associez la hiérarchie de navigation.
    - Spécifiez les dates d’effet et d’expiration, si elles sont applicables.
    - Ajoutez et catégorisez les produits.
    - Associez les groupes de prix.
    - Associez une hiérarchie client spécifique à vos organisations B2B. 
    - Associez un groupe d’attributs de dimension par défaut pour les affinements tels que la taille, le style et la couleur.
    - Paramétrer les métadonnées d’attribut.

1. **[Validation](#validate-the-catalog)** – Dans cette étape, vous exécutez des règles de validation qui appliquent un comportement spécifique. Voici quelques exemples :

    - Assurez-vous qu’il n’y a pas de produits non classés.
    - Assurez-vous que tous les articles qui sont assortis à chaque canal sont associés à un catalogue.

1. **[Approbation](#approve-the-catalog)**
1. **[Publication](#publish-the-catalog)**

## <a name="set-up-the-catalog"></a>Paramétrage du catalogue

Utilisez les informations de cette section pour configurer votre catalogue.

### <a name="configure-the-catalog"></a>Configurer le catalogue

Dans Commerce headquarters, accédez à **Retail et Commerce \> Catalogues et assortiments \> Tous les catalogues** pour configurer votre catalogue.

Quand vous créez un catalogue, vous devez d’abord l’associer à un ou plusieurs canaux. Seuls les articles liés aux [assortiments](/dynamics365/unified-operations/retail/assortments) du canal sélectionné peuvent être utilisés à la création du catalogue. Pour associer le catalogue à un ou plusieurs canaux, sélectionnez **Ajouter** sur le raccourci **Canaux Commerce** de la page **Configuration du catalogue**. Veillez à ce que le catalogue soit marqué comme **Type de catalogue = B2B**.

#### <a name="associate-the-navigation-hierarchy"></a>Associez la hiérarchie de navigation

Pour ajouter des produits à un catalogue, sélectionnez une hiérarchie de navigation. La hiérarchie de navigation prend en charge la structure de catégories pour le catalogue. Vous devez sélectionner l’une des hiérarchies de navigation associées aux canaux sélectionnés dans le raccourci **Canaux Commerce** de la page **Catalogue**. Pour associer une hiérarchie de navigation par défaut à chacun de vos canaux, rendez-vous sur **Retail et Commerce \> Configuration du canal \> Catégories de canaux et attributs de produits**.

#### <a name="specify-time-effective-and-expiration-dates"></a>Spécifiez les dates d’effet et d’expiration

Pour spécifier les dates d’effet et d’expiration d’un catalogue, sélectionnez le nœud supérieur de la hiérarchie du catalogue pour revenir à la vue d’en-tête du catalogue principal. Ensuite, sous l’organisateur **Général**, configurez les dates d’effet et d’expiration au besoin.

#### <a name="add-and-categorize-products"></a>Ajoutez et catégorisez les produits

Pour configurer les produits à ajouter au catalogue, dans Commerce headquarters, accédez à **Retail et Commerce \> Catalogues et assortiments \> Tous les catalogues**. Ensuite, dans l’onglet **Catalogues**, sélectionnez **Ajouter des produits**.

Sinon, vous pouvez également sélectionner un nœud dans la hiérarchie de navigation. Vous pourrez alors ajouter des produits directement à une catégorie du catalogue.

#### <a name="associate-price-groups"></a>Associez les groupes de prix

Pour configurer les produits à ajouter au catalogue, dans Commerce headquarters, accédez à **Retail et Commerce \> Catalogues et assortiments \> Tous les catalogues**. Ensuite, dans l’onglet **Catalogues**, sélectionnez **Ajouter des produits**. 

Produits qui ont été ajoutés à un catalogue à partir du nœud racine de la hiérarchie de navigation en sélectionnant **Ajouter des produits** dans le volet Actions hériteront de leurs catégories si la hiérarchie de navigation source est également associée au catalogue. Les modifications apportées aux catégories dans la hiérarchie de navigation source seront immédiatement répercutées dans les catalogues. Vous devez republier les catalogues pour mettre à jour les chaînes.

Vous pouvez également sélectionner un nœud dans la hiérarchie de navigation et ajouter des produits directement à une catégorie sélectionnée dans le catalogue. 

Lorsque vous ajoutez des produits, l’option **Inclure automatiquement toutes les variantes lorsque seul le produit principal est sélectionné** sera disponible. Pour empêcher l’inclusion de toutes les variantes, sélectionnez au moins une variante pour le produit générique. 

> [!NOTE]
> Si vous choisissez d’inclure automatiquement toutes les variantes dans une grande sélection de produits génériques, vous risquez de rencontrer des délais de traitement plus longs. Pour les grandes sélections, nous vous recommandons de sélectionner **Inclure toutes les variantes** dans le volet Actions de la page des catalogues pour exécuter l’opération en mode batch. Si vous avez inclus uniquement le produit générique dans le catalogue et n’avez inclus aucune variante, le sélecteur de variante peut ne pas être disponible lorsque vous accédez à une page de détails de produit. 

Pour configurer des prix spécifiques au catalogue, vous devez lier un ou plusieurs groupes de prix au catalogue. Pour associer des groupes de prix à un catalogue, dans Commerce headquarters, accédez à **Retail et Commerce \> Catalogues et assortiments \> Tous les catalogues**. Ensuite, sur l’onget **Catalogues**, sous **Tarification**, sélectionner **Groupes de prix**. Les accords commerciaux, les journaux d’ajustement de prix et les remises avancées (seuil, quantité et remises mix and match) qui ont été associés au même groupe de prix sont appliqués quand les clients passent une commande à partir du catalogue.

Pour plus d’informations sur les groupes de prix, voir [Groupes de prix](price-management.md#price-groups).

> [!NOTE]
> Vous ne pouvez pas créer de groupe de prix à partir de la page **Tous les catalogues**. Au lieu de cela, vous devez le créer à partir de la page **Tous les groupes de prix**. Vous devez ensuite l’associer au catalogue sur la page **Tous les catalogues**.

#### <a name="associate-a-customer-hierarchy"></a>Associer une hiérarchie client

Pour associer des hiérarchies client, dans Commerce headquarters, accédez à **Retail et Commerce \> Catalogues et assortiments \> Tous les catalogues**. Ensuite, sur l’onglet **Catalogues**, sous **Hiérarchie des clients**, sélectionner **Attribuer des hiérarchies** pour lier une ou plusieurs hiérarchies de clients au catalogue.

> [!NOTE]
> Vous ne pouvez pas créer de hiérarchie de clients à partir de la page **Tous les catalogues**. Au lieu de cela, vous devez le créer à partir de la page **Hiérarchies des clients**. Vous devez ensuite l’associer au catalogue sur la page **Tous les catalogues**.

#### <a name="associate-default-dimension-attribute-group-for-refiners-such-as-size-style-and-color"></a>Associez un groupe d’attributs de dimension par défaut pour les affinements tels que la taille, le style et la couleur

Pour associer un groupe d’attributs de dimension par défaut pour les affinements tels que la taille, le style et la couleur, dans Commerce headquarters, accédez à **Retail et Commerce \> Catalogues et assortiments \> Tous les catalogues**. Ensuite, sur l’onget **Catalogues**, sous **Attributs**, sélectionner **Groupes d’attributs**.

#### <a name="set-attribute-metadata"></a>Paramétrer les métadonnées d’attribut

Pour configurer les métadonnée d’attribut, dans Commerce headquarters, accédez à **Retail et Commerce \> Catalogues et assortiments \> Tous les catalogues**. Ensuite, sur l’onget **Catalogues**, sous **Attributs**, sélectionner **Définir les métadonnées d’attribut**. Pour sélectionner les attributs qui doivent être visualisables et affinables, sélectionnez une catégorie dans la hiérarchie de navigation spécifique au catalogue associée, puis, sous **Attributs des produits du catalogue**, sélectionnez un attribut. Ensuite, sélectionnez **Afficher l’attribut sur le canal**. Par défaut, tous les attributs visibles sont également consultables. Pour éventuellement rendre les attributs affinables, sélectionnez **Peut être affiné**.

### <a name="validate-the-catalog"></a>Validation du catalogue

Avant qu’un nouveau catalogue puisse être utilisé, il doit être validé et publié.

Pour valider un catalogue, procédez comme suit.

1. Sur l’onglet **Catalogues** de la page **Tous les catalogues**, sous **Valider**, sélectionnez **Valider le catalogue** pour exécuter une validation. Cette étape est obligatoire. Elle permet de valider que le paramétrage requis est exact.
1. Sélectionnez **Afficher les résultats** pour afficher les détails de la validation. Si des erreurs sont détectées, vous devez corriger les données et réexécuter ensuite la validation jusqu’à ce qu’elle réussisse.

> [!NOTE]
> Si **Type de catalogue = B2B**, la validation échouera si vous avez ajouté des points de vente ou un centre d’appels au catalogue. Les catalogues B2B ne doivent être associés qu’à des canaux en ligne B2B. La validation échouera également si aucune hiérarchie client n’est associée à un catalogue B2B. 

### <a name="approve-the-catalog"></a>Approuver le catalogue

Une fois un catalogue validé, il doit être approuvé.

Pour démarrer le workflow d’approbation de catalogue, procédez comme suit.

1. Sur le volet Actions de la page **Tous les catalogues**, sélectionnez **Workflow \> Envoyer**.
1. Accédez à **Retail et Commerce \> Configuration du siège \> Workflows Commerce** pour configurer les étapes et les utilisateurs autorisés pour le workflow. Le workflow définit les étapes obligatoires pour faire passer le catalogue au statut **Approuvé**.

### <a name="publish-the-catalog"></a>Publiez le catalogue

Une fois qu’un catalogue est dans un statut **Approuvé**, vous pouvez le publier en sélectionnant **Publier** sur le menu **Catalogues**. Une fois que le catalogue est à l’état **Publié**, il peut être utilisé dans les processus d’envoi du catalogue et de saisie de commande dans le centre d’appels. Vous pouvez publier un catalogue manuellement ou via un processus de traitement par lots. La date d’effet que vous avez définie pour le catalogue détermine le moment où les produits sont disponibles dans le magasin en ligne. La date d’expiration que vous avez définie détermine le moment où les produits sont retirés du magasin en ligne.

> [!NOTE]
> Vous pouvez publier un catalogue qui contient des produits avec des avertissements. Toutefois, ces produits ne figurent pas dans le magasin en ligne.

## <a name="additional-resources"></a>Ressources supplémentaires

[Impact d’extensibilité des catalogues Commerce pour les personnalisations B2B](catalogs-b2b-sites-dev.md)

[FAQ sur les catalogues Commerce pour le B2B](catalogs-b2b-sites-FAQ.md)

[Module de sélection de catalogue](catalog-picker.md)
