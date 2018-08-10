---
title: Identificateurs du produit
description: "Cette rubrique fournit des informations sur les différents types d'identificateurs de produit et explique comment vous pouvez ajouter des identificateurs de produit à vos données de produit."
auhor: cvocph
manager: AnnBe
ms.date: 03/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductEntityIdentifierCode
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: conradv
ms.dyn365.ops.version: 7.3
ms.search.validFrom: 2017-12-31
ms.translationtype: HT
ms.sourcegitcommit: 19cc8f92b5bb6d9ddfdc77785e48de17ed005703
ms.openlocfilehash: afd542a652abdf6e45c83a6097dc8f0d36efa905
ms.contentlocale: fr-fr
ms.lasthandoff: 03/23/2018

---

# <a name="product-identifiers"></a>Identificateurs du produit 

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les différents types d'identificateurs de produit et explique comment vous pouvez ajouter des identificateurs de produit à vos données de produit.

Lorsque vous travaillez avec des produits dans l'atelier ou dans un entrepôt avec Microsoft Dynamics ERP ou Microsoft Dynamics CRM, vous devez disposer d'une bonne stratégie pour identifier ces produits et variantes de produit.

## <a name="unique-product-numberproduct-id"></a>Numéro de produit/ID de produit unique

Dans Microsoft Dynamics 365 for Finance and Operations, l'identificateur principal d'un produit est le numéro de produit (c'est-à-dire, l'ID de produit unique). Ce numéro peut être généré automatiquement par une souche de numéros, ou il peut être associé manuellement à un produit. Pour les variantes de produit, les numéros peuvent être définis à l'aide du modèle de nomenclature produit.

Dans de nombreux cas, le numéro de produit n'est pas créé initialement dans Finance and Operations. Au lieu de cela, il est associé à un produit dans un système de gestion des cycles de vie des produits ou un système de gestion d'informations sur les produits. Dans ce cas, vous utilisez des entités de données pour importer les produits et les variantes de produit. Finance and Operations utilise ensuite les numéros dans toutes les opérations.

Lorsque vous implémentez Finance and Operations, vous devez accorder un soin particulier à votre stratégie relative aux numéros de produit. Un bon système de numérotation améliore les flux de logistique et permet d'éviter les erreurs. Un bon identificateur de produit comporte au maximum 15 caractères. Idéalement, il comporte moins de 10 caractères et n'inclut pas plus de cinq caractères de classification. Vous pouvez également utiliser des noms de recherche pour activer les recherches rapides. Un nom de recherche est un nom supplémentaire qui représente les classifications d'un produit.

Lorsque vous utilisez Common Data Service (CDS), le numéro de produit dans Finance and Operations est également le numéro de produit dans CDS. Les variantes de produit sont synchronisées avec CDS en tant que produits distincts.

## <a name="item-number-and-product-dimensions"></a>Numéro d'article et dimensions de produit

Le numéro d'article est l'identificateur de produit utilisé par une entité juridique spécifique. Idéalement, le numéro d'article doit être identique au numéro de produit. Si la nomenclature diffère selon l'entité juridique, il devient difficile de suivre un produit tout au long de la chaîne d'approvisionnement, et des processus fastidieux de réétiquetage et référencement doivent être mis en place. Pour des raisons de compatibilité avec des versions précédentes (c'est-à-dire, avec Microsoft Dynamics AX 2009 et versions antérieures), nous avons retenu ce modèle. Toutefois, il est recommandé d'éliminer les identificateurs spécifiques aux entités juridiques chaque fois que possible, et d'utiliser le numéro de produit unique comme identificateur principal à la place.

En outre, une variante de produit ne peut pas être identifié de façon unique par un numéro d'article. Elle nécessite toujours la combinaison d'un numéro d'article et de toutes les dimensions de produit qui sont définies sur le produit générique. Cette condition requise peut devenir encombrante et ralentir les processus d'identification. C'est pourquoi il est recommandé d'utiliser le numéro de produit unique à la place du numéro d'article chaque fois que possible.

De nombreuses pages comportent toujours le numéro d'article et les dimensions de produit comme identificateurs principaux. Toutefois, les numéros de produit peuvent être utilisés pour les recherches. Dans **Ventes et marketing** &gt; **Paramétrage** &gt; **Recherche** &gt; **Paramètres de recherche**, vous pouvez modifier la recherche afin qu'elle utilise des numéros de produit au lieu de numéros d'article comme principale stratégie de recherche. Si vous définissez l'option **Activer la recherche pour la recherche de produit** sur **Oui**, la recherche affiche non seulement les produits génériques, mais aussi les variantes de produit. Pour plus d'informations, consultez [Rechercher des produits et des variantes de produits lors de la saisie de commande](search-products-product-variants.md).

En outre, vous pourrez rechercher et filtrer par numéro de produit, par nom du produit et description, et par ID de dimensions de produit de la variante de produit. Lorsque vous sélectionnez une variante, le numéro d'article associé et tous les ID des dimensions de produit sont sélectionnés. Par conséquent, vous pouvez trouver et sélectionner plus facilement la variante correcte. Ce paramètre est fortement recommandé si vous utilisez les variantes de produit et le numéro de produit unique comme principaux identificateurs pour les produits. La seule exception peut être le secteur de la mode, où les processus d'entreprise nécessitent souvent que vous sélectionniez le générique avant de sélectionner une variante. Vous devez évaluer soigneusement cette option avant de mettre en œuvre le système de numérotation.

## <a name="product-name-and-description"></a>Nom et description du produit

Le nom et la description du produit sont les identificateurs contrôlable de visu d'un produit et peuvent être tenus à jour dans de nombreuses langues. Par défaut, le client Finance and Operations affiche toutes les informations sur le produit dans la langue par défaut de la société, pas dans la langue de l'utilisateur. Toutefois, les noms et les descriptions de produit traduits sont utilisés dans toute les communications avec les clients et les fournisseurs. Les traductions sont basées sur le code langue des comptes client et fournisseur.

Pour les variantes de produit, le nom du produit peut être généré à l'aide du modèle de nomenclature produit. Comme il n'existe aucune condition requise selon laquelle les noms du produit doivent être uniques, vous pouvez rechercher plusieurs produits portant le même nom.

## <a name="product-and-item-search-names"></a>Noms de recherche de produit et d'article

Finance and Operations fournit un nom de recherche secondaire pour les produits ainsi que pour les articles (produits lancés). Ce nom de recherche ne doit pas être unique, et il peut être modifié après la création d'un produit ou d'une variante de produit. Il est recommandé d'utiliser le nom de recherche pour rechercher des produits par catégories. Les noms de recherche permet d'effectuer des recherches rapides, en particulier dans les processus de ventes et d'achat.

Le nom de recherche peut également contenir un ID produit de client ou fournisseur, ou un autre ID produit externe, si cet ID externe est le principal critère de recherche d'un produit.

## <a name="external-product-identifiers-customer-and-vendor-identifiers"></a>Identificateurs de produit externes (identificateurs clients et fournisseurs)

Pour les produits lancés, vous pouvez tenir à jour les numéros d'article, les noms d'article et les descriptions d'article utilisés par le client ou le fournisseur. Les références sont affichées sur les documents externes, tels que les commandes client, les commandes fournisseur, les bons de livraison et les factures. Dans la version actuelle de Finance and Operations, les références externes ne sont pas affichées dans les pages des opérations principales. La seule exception est le numéro d'article fournisseur. Ce numéro est affiché dans la boîte de dialogue **Informations sur le produit** si un fournisseur par défaut est défini pour le produit lancé.

Vous pouvez tenir à jour les identificateurs de produit externes par produit lancé, par variante de produit lancé, par client ou groupe de clients, ou par fournisseur ou groupe de fournisseurs.

Dans la page **Produits lancés**, suivez l'une des étapes suivantes.

- Pour les clients, sous l'onglet **Vendre**, dans le groupe **Informations associées**, sélectionnez **Description d'article externe**.
- Pour les fournisseurs, sous l'onglet **Acheter**, dans le groupe **Informations associées**, sélectionnez **Description d'article externe**.

Sur la page **Descriptions d'article externes**, vous pouvez associer le numéro d'article client ou fournisseur à un produit lancé. Cette association doit être effectuée pour chaque entité juridique. Les informations suivantes peuvent être capturées. Malheureusement, les libellés sont légèrement erronées dans la version actuelle de Finance and Operations. Toutefois, ces libellés peuvent être modifiés dans la prochaine version.

| Champ | Informations client correspondantes | Informations fournisseur correspondantes |
|-------|------------------------------------|----------------------------------|
| Numéro d'article externe | Numéro d'article client | Numéro d'article fournisseur |
| Description | Nom que le client associe à l'article | Nom que le fournisseur associe à l'article |
| Description d'article externe | Description de l'article client | Description de l'article fournisseur |

Si plusieurs clients ou fournisseurs utilisent les mêmes numéros d'article (dans le cas d'une association d'achat ou d'un groupe de vente au détail, par exemple), vous pouvez créer des groupes de clients ou de fournisseurs afin de simplifier la maintenance des informations sur le produit externe.

- Pour les groupes de clients, accédez à **Ventes** &gt; **Paramétrage** &gt; **Articles** &gt; **Description d'article externe** pour créer et tenir à jour les groupes et les numéros d'article associés. Pour associer des clients à un groupe, accédez à **Ventes** &gt; **Clients** &gt; **Tous les clients**, puis dans l'organisateur **Valeurs par défaut de commande client**, spécifiez une valeur dans le champ **Article - Groupe de clients**.
- Pour les groupes de fournisseurs, accédez à **Approvisionnements** &gt; **Paramétrage** &gt; **Groupe de descriptions d'article externes** pour créer et tenir à jour les groupes et les numéros d'article associés. Pour associer des fournisseurs à un groupe, accédez à **Comptabilité fournisseur** &gt; **Fournisseurs** &gt; **Tous les fournisseurs**, puis dans l'organisateur **Valeurs par défaut des commandes fournisseur**, spécifiez une valeur dans le champ **Article - Groupe de fournisseurs**.
 
## <a name="bar-codes"></a>Codes-barres

Si vous souhaitez utiliser un lecteur de codes-barres pour identifier des produits, l'identificateur de produit doit répondre aux besoins de la norme de code-barres utilisée. Par conséquent, les codes-barres ne contiennent généralement pas le numéro de produit brut mais un numéro généré spécifiquement pour la technologie de code-barres sélectionnée. Vous pouvez tenir à jour plusieurs codes-barres par type de code-barres. Vous pouvez même associer le même codes-barres à plusieurs produits, puis sélectionner l'association active réelle lors de l'analyse d'un code-barres.

Avant de définir des codes-barres, vous pouvez définir un ou plusieurs paramétrages de codes-barres. Les paramétrages des codes-barres permettent de valider que les codes-barres suivent les instructions requises, et qu'ils peuvent donc être imprimés et analysés de manière efficace. Vous pouvez également mettre à jour des codes-barres spéciaux pour des quantités de produits spécifiques.

Il est recommandé d'utiliser le paramétrage de code-barres pour gérer les codes de numéro d'article de commerce mondial (GTIN) ou de numéro international d'article (EAN).

Pour gérer les codes-barres, sur la page **Produits lancés**, sous l'onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **Codes-barres**.

## <a name="gtin-codes"></a>Codes GTIN

Dans le commerce électronique, il est primordial que toutes les parties parlent une langue commune et fassent référence aux produits à l'aide d'un ensemble commun d'identificateurs. Par conséquent, certains secteurs s'appuient sur les [GTIN](https://www.gs1.org/id-keys/gtin), qui constituent un système de numéro d'article mondial facilité par GS1.

Dans Finance and Operations, il est recommandé de gérer le GTIN comme un codes-barres. Toutefois, vous pouvez également le tenir à jour sur la page **Article - GTIN**. Pour ouvrir cette page, sur la page **Produits lancés**, sous l'onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **Codes GTIN**. Notez que le GTIN n'est pas gérer comme un numéro mondial. Au lieu de cela, il est géré par entité juridique.

Dans Finance and Operations, vous définissez des variantes de packaging dans les opérations d'entrepôt en définissant des unités de mesure spécifiques. Par exemple, un article peut être stocké sous forme de pièces, par paquets de six, par bacs de 18, ou sur des palettes complètes. Une unité de mesure spécifique est définie pour chacune de ces variantes de packaging. Comme le GTIN est généralement associé à l'unité d'emballage d'un produit, la page **Article - GTIN** permet de gérer plusieurs codes GTIN par produit et unité de mesure. Toutefois, vous ne pouvez pas utiliser le même code GTIN plusieurs fois pour différents articles ou variantes de produit d'une entité juridique.

Pour gérer les **Codes GTIN**, sur la page **Produits lancés**, sous l'onglet **Gérer le stock**, dans le groupe **Entrepôt**, sélectionnez **GTIN**.

## <a name="external-codes"></a>Codes externes

Les codes externes peuvent être définis pour plusieurs entités dans Finance and Operations. Par exemple, vous pouvez définir des codes externes pour identifier des produits et des produits lancés. Ces codes externes peuvent être utilisés pour associer des codes statistiques ou des codes taxe à des produits lancés et des variantes de produit lancé. Les codes externes sont définis par entité juridique et par type de code. Ils doivent être uniques par entité juridique, type de code, référence de table.

Malheureusement, il n'existe aucune fonctionnalité standard qui vous permet de rechercher des produits par codes externes.

## <a name="data-entities-that-are-used-to-import-and-export-product-identifiers"></a>Entités de données utilisées pour importer et exporter des identificateurs de produit

| Nom d'entité | Identificateurs d'importation | Identificateurs d'exportation | Commentaires |
|-------------|--------------------|--------------------|----------|
| Produits V2 | Numéro du produit, nom de recherche du produit, nom du produit, description du produit | Numéro du produit, nom de recherche du produit, nom du produit, description du produit | En fonction des paramètres de l'entité et de la souche de numéros du numéro de produit, le numéro de produit peut être créé automatiquement lors de l'importation. |
| Variantes de produit | Numéro du produit, nom de recherche du produit, nom du produit, description du produit | Numéro du produit, nom de recherche du produit, nom du produit, description du produit | Selon le modèle de produit, le numéro de produit peut être créé automatiquement lors de l'importation. Toutefois, vous pouvez importer chaque numéro de produit unique, et ce numéro de produit ne doit pas suivre la structure des modèles de nomenclature produit. |
| Traductions de produit | Nom du produit, description du produit | Nom du produit, description du produit | Cette entité remplace la langue. Notez que lorsque le nom ou la description de la langue principale d'une entité juridique est ignorée, le nom et la description du produit lui-même sont modifiés. |
| Produits lancés V2 | Numéro d'article, numéro de produit, nom de recherche d'article| Numéro d'article, numéro de produit, nom de recherche d'article, nom de recherche de produit, nom du produit | Cette entité peut être un défi lorsque des souches de numéros sont utilisées lors de la création de nouveaux produits lancés. La souche de numéros **Numéro d'article** et la souche de numéros **Numéro de produit** ont une influence. Toutefois, la souche de numéros **Numéro d'article** est par entité juridique, alors que la souche de numéros **Numéro de produit** est globale. Par conséquent, il n'est pas recommandé d'utiliser la souche de numéros **Numéro d'article** lorsque vous déployez de nouveaux produits lancés. Évidemment, lorsque l'entité est utilisée pour lancer un produit existant, le numéro de produit doit être indiqué dans l'entité. Pour plus d'informations, voir la section « Souches de numéros de produit et d'article » dans cette rubrique. |
| Variantes de produit lancé | Numéro d'article, dimensions de produit, numéro de produit | Numéro du produit, nom de recherche du produit, nom du produit, description du produit, dimensions de produit | Comme l'entité **Variantes de produit**, cette entité peut être utilisée pour créer des produits qui suivent le modèle de nomenclature de produit ou utilisent leurs propres numéros de produit pour la variante. |
| Description d'article externe pour les clients | Numéro d'article client, nom d'article client, description du client, compte client | Numéro d'article client, nom d'article client, description du client, compte client | Un groupe de clients (par exemple, une association d'acheteurs) peut être agrégé dans un groupe à l'aide de l'entité **Groupes de clients pour les descriptions d'article externes**. |
| Description d'article externe pour les fournisseurs | Numéro d'article fournisseur, nom d'article fournisseur, description du fournisseur, compte fournisseur | Numéro d'article fournisseur, nom d'article fournisseur, description du fournisseur, compte fournisseur | Un groupe de fournisseurs (par exemple, une association de ventes ou une organisation sectorielle) peut être agrégé dans un groupe à l'aide de l'entité **Groupes de fournisseurs pour les descriptions d'article externes**. |
| Code-barres d'article | Code-barres | Code-barres | Notez que, lors de l'importation, vous devez faire référence à un paramétrage de code-barres défini dans le système cible. Les références de code-barres importées sont validées par rapport à ce paramétrage de codes-barres et sont rejetées si les codes-barres ne correspondent pas aux configurations requises définies dans ce paramétrage de codes-barres. |
| Codes externes pour les produits lancés | Code externe | Code externe, classes de code externe, numéro d'article | Les codes externes sont par entité juridique. Pour l'importation, vous devez faire référence à une classe de code définie. Importez les classes de code à l'aide l'entité **Classes de code externe pour les produits lancés**. |
| Codes externes pour les variantes de produits lancés | Code externe | Code externe, classes de code externe, numéro d'article, dimensions de produit | Les codes externes sont par entité juridique. Pour l'importation, vous devez faire référence à une classe de code définie. Importez les classes de code à l'aide l'entité **Classes de code externe pour les produits lancés**. Cette entité fait référence à des variantes de produit par numéro d'article et dimensions de produit. |
| Exporter les codes des variantes de produit lancé par identificateur du numéro de produit | Code externe | Code externe, classes de code externe, numéro de produit | Les codes externes sont par entité juridique. Pour l'importation, vous devez faire référence à une classe de code définie. Importez les classes de code à l'aide l'entité **Classes de code externe pour les produits lancés**. Cette entité fait référence à des variantes de produit par numéro de produit de la variante. (Dans la prochaine version majeure) |
| GTIN | Non applicable | Non applicable | Actuellement, il n'existe aucune entité spécifique utilisée pour importer et exporter des codes GTIN. Nous vous recommandons d'utiliser l'entité **Codes-barres d'article** à la place. |
| Entité d'identificateur du service de données communes d'entité de produit | Non applicable | Numéro d'article, nom de recherche d'article, nom de recherche de produit, numéro d'article fournisseur, le numéro d'article client, codes externes, codes GTIN, codes-barres | Cette entité consolide tous les identificateurs dans un seul modèle de données, de sorte qu'une seule interface puisse être utilisée pour exporter facilement tous les identificateurs et leurs types associés. Utilisez l'entité **Code d'identification d'entité de produit** pour exporter les codes et descriptions d'identificateur. Utlisez l'entité **Portée des identificateurs d'entité de produit** pour exporter des informations de portée supplémentaires vers un identificateur, telles que la partie, l'entité juridique, la quantité, ou l'unité. |

### <a name="product-and-item-number-sequences"></a>Souches de numéros de produit et d'article

Dans Finance and Operations, vous pouvez définir deux souches de numéros différentes :

- La souche de numéros **Numéro de produit** pour le numéro de produit global.
- La souche de numéros **Numéro d’article** pour le numéro d'article par entité juridique

> [!NOTE]
> Vous devez utiliser le numéro d'article comme identificateur distinct uniquement lorsque vous migrez différentes entités juridiques depuis différentes sources ayant eu différents systèmes de numérotation. Vous devez toujours tenter d'utiliser un identificateur de produit unique entre toutes les entités juridiques. Par conséquent, vous devez définir l'option **Manuelle** sur **Oui** pour la souche de numéros **Numéro d'article**. Ainsi, le numéro d'article suit le numéro de produit à la création. Si Finance and Operations n'est pas le système principal pour les nouveaux numéros de produit, vous devez définir l'option **Manuelle** sur **Oui** pour les souches de numéros **Numéro d'article** et **Numéro de produit**.

Lorsque vous utilisez l'entité **Produit lancé V2** pour créer des produits, plusieurs paramètres peuvent affecter la manière dont les souches de numéros sont utilisées pour créer le numéro de produit et le numéro d'article :

- Paramètres de la souche de numéros **Numéro de produit**
- Paramètres de la souche de numéros **Numéro d'article**
- Mappage du numéro de l'article 
- Mappage du numéro de produit

Le tableau suivant fournit une vue d'ensemble des résultats de l'importation et de la création manuelle avec des combinaisons de paramètres spécifiques de mise en correspondance de souche de numéros et de champ.

| Souche de numéros du numéro de produit | Souche de numéros du numéro d'article | Mappage du numéro d'article | Mappage du numéro de produit | Résultat de l'importation d'entité | Résultat de la création manuelle | Conclusion |
|--------------------------------|-----------------------------|----------------------------|-------------------------------|-------------------------|----------------------------|-----------|
| Manuelle = Non | Manuelle = Non | Aucune mise en correspondance | Aucune mise en correspondance | Les numéros de produit utilisent la souche de numéros **Numéro de produit**. Les numéros d'article utilisent la souche de numéros **Numéro d'article**. | Les numéros de produit utilisent la souche de numéros **Numéro de produit**. Les numéros d'article utilisent la souche de numéros **Numéro d'article**. | Ces paramètres peuvent être utilisés si vous avez besoin d'un autre numéro pour les produits et les articles. Toutefois, il n'est pas recommandé d'utiliser des numéros différents pour les articles et les produits. |
| Manuelle = Non | Manuelle = Oui | Autogénérer | Aucune mise en correspondance | Les numéros de produit et les numéros d'article utilisent la souche de numéros **Numéro d'article**. | Les numéros de produit et les numéros d'article utilisent la souche de numéros **Numéro de produit**. | Ces paramètres ne sont pas recommandés. L'importation et la création manuelle fonctionnent différemment. |
| Manuelle = Non | Manuelle = Oui | Aucune mise en correspondance | Aucune mise en correspondance | Les numéros de produit et les numéros d'article utilisent la souche de numéros **Numéro de produit**. | Les numéros de produit et les numéros d'article utilisent la souche de numéros **Numéro de produit**. | Ces paramètres sont recommandés si les produits doivent comporter une numérotation automatique cohérente, indépendamment de l'importation ou de la création manuelle. |
| Manuelle = Oui | Non applicable | Non applicable | Autogénérer | Vous recevez le message d'erreur suivant : « La souche de numéros ne peut pas être détectée. » | Selon la souche de numéros **Numéro d'article** | Ce paramètre n'est pas pris en charge pour l'importation. |

## <a name="product-entity-identifier-export-all-product-identifiers"></a>Identificateur d'entité de produit (Exporter tous les identificateurs de produit)

Le modèle d'identificateur d'entité de produit a été créé pour activer la version 1.0 de CDS à provisionner avec tous les identificateurs utilisés pour faire référence à un produit. Pour simplifier cette tâche, tous les identificateurs sont regroupés dans une table globale d'identificateurs, de sorte qu'ils puissent être exportés en tant que modèle unique. Notez que cette version de CDS n'utilise pas de modèle d'identificateurs de produit. Par conséquent, l'entité **Entité d'identificateur du service de données communes d'entité de produit** et ce processus ont une utilisation pratique limitée et sont soumis vraisemblablement à une future modification.

La table d'identificateurs de produit est une table globale renseignée par toutes les tables de référence de l'entité juridique principale via un traitement par lots récurrent. Vous devez sélectionner une entité juridique et une hiérarchie de catégories de produit comme définition de la portée de produit générique globale. La génération de la table d'identificateurs de produit globale est limitée aux produits lancés dans l'entité juridique sélectionnée et aux produits membres de la hiérarchie de produits sélectionnée pour le rôle **Common data service** dans la hiérarchie de catégories de produits.

Cette procédure suppose que les données de produit générique sont principalement tenues à jour dans une seule entité juridique centrale. (Toutefois, cette entité juridique peut être une entité juridique virtuelle utilisée pour tenir à jour uniquement les données principales globales.)

Procédez comme suit pour configurer l'environnement.

1. Sélectionner la hiérarchie de catégories de CDS. Sur la page **Associations de rôles de hiérarchie de catégories**, si aucune hiérarchie n'est associée au rôle **Common data service**, vous devez créer une association. Sélectionnez le rôle **Common data service**, puis associez la hiérarchie de catégories qui représente le portefeuille de produits qui doit être synchronisé sur CDS.
2. Sélectionnez l'entité juridique pour les données principales du produit globales. Sur la page **Paramètres de gestion des informations sur les produits**, sous l'onglet **Attributs de produit**, sélectionnez la société principale où les identificateurs de produit et d'article sont généralement gérés.
3. Définissez les types de codes d'identificateur et les codes à exporter. Accédez à **Gestion des informations sur les produits** &gt; **Paramétrage** &gt; **Codes d'identificateur de produit**. Pour générer les types de codes d'identificateur, sélectionnez **Générer des codes**. Une entrée de type de code est générée pour chaque type d'identificateur indiqué dans l'entité juridique sélectionnée.

    Notez que, pour les codes-barres, un type de code est généré pour chaque paramétrage de code-barres. Pour les codes-barres externes, un type de code est généré pour chaque classe de code-barres externe.

    Vous pouvez désormais tenir à jour la liste des types de codes. Vous pouvez modifier le code, le nom et la description. Vous pouvez également supprimer les types de codes. Les types de code que vous supprimer ne seront pas utilisés pour renseigner les tables d'identificateur d'entité de produit globales.

4. Lorsque vous avez fini de définir les types de codes d'identificateur de produit, vous pouvez créer des identificateurs dans la table globale en lançant la tâche **Créer des identificateurs d'entité de produit** sur la page **Codes d'identification d'entité de produit**. Vous devez exécuter cette tâche sous forme de traitement par lot. Cette tâche doit être paramétrée en tant que traitement par lots périodique de sorte que la table soit remplie selon les nouvelles entrées.

Vous pouvez désormais utiliser s entités de données **Entité d'identificateur du service de données communes d'entité de produit**, **Codes d'identification d'entité de produit** et **Portée des identificateurs d'entité de produit** pour exporter les identificateurs de tout système cible.

## <a name="related-topic"></a>Rubrique connexe

[Rechercher des produits et des variantes de produits lors de la saisie de commande](search-products-product-variants.md)

