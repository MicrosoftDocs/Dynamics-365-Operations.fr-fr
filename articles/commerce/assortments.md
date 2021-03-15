---
title: Gestion des assortiments
description: Cette rubrique explique les concepts fondamentaux relatifs à la gestion des assortiments dans Dynamics 365 Commerce et fournit des considérations pour la mise en œuvre de votre projet.
author: jblucher
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: jeffbl
ms.search.validFrom: 2017-11-21
ms.dyn365.ops.version: Application update 5
ms.openlocfilehash: 981d1c604a7ed461f207e78c8c7f073aff03be9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979996"
---
# <a name="assortment-management"></a>Gestion des assortiments

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Présentation

Dynamics 365 Commerce fournit des *assortiments* vous permettant de gérer la disponibilité des produits entre plusieurs canaux. Les assortiments déterminent les produits disponibles dans des magasins spécifiques et pendant une période spécifique.

Dans Commerce, un assortiment est une mise en correspondance d'un ou de plusieurs canaux (ou de groupes de canaux, lorsque des hiérarchies d'organisation sont utilisées) avec un ou plusieurs produits (ou groupes de produits, lorsque des hiérarchies de catégories sont utilisées).

Le mélange global de produits d'un canal est déterminé par les assortiments publiés affectés au canal. Par conséquent, vous pouvez configurer plusieurs assortiments actifs par canal.

### <a name="basic-assortment-setup"></a>Paramétrage de base des assortiments

Dans l'exemple suivant, un seul assortiment est configuré pour chaque magasin. Dans ce cas, seul le produit 1 est disponible dans le magasin 1, et seul le produit 2 est disponible dans le magasin 2.

![Chaque produit est disponible dans un magasin](./media/Managing-assortments-figure1.png)

Pour rendre le produit 2 disponible dans le magasin 1, vous pouvez ajouter le produit à l'assortiment 1.

![Produit 2 ajouté à l'assortiment 1](./media/Managing-assortments-figure2.png)

Sinon, vous pouvez ajouter le magasin 1 à l'assortiment 2.

![Magasin 1 ajouté à l'assortiment 2](./media/Managing-assortments-figure3.png)

### <a name="organization-hierarchies"></a>Hiérarchies de l'organisation

Dans les situations où plusieurs canaux partagent les mêmes assortiments de produits, vous pouvez configurer les assortiments à l'aide de la hiérarchie d'organisation d'assortiments Commerce. Lorsque des nœuds de cette hiérarchie sont ajoutés, tous les canaux de ce nœud et ses nœuds enfants sont inclus.

![Hiérarchie d'organisation](./media/Managing-assortments-figure4.png)

### <a name="product-categories"></a>Catégories de produits

De même, côté produit, vous pouvez inclure des groupes de produits à l'aide de hiérarchies de catégories de produits. Vous pouvez configurer des assortiments en incluant un ou plusieurs nœuds de hiérarchie de catégories. Dans ce cas, l'assortiment permet d'inclure tous les produits dans ce nœud de catégorie, ainsi que ses nœuds enfants.

![Catégories de produits](./media/Managing-assortments-figure5.png)

### <a name="excluded-products-or-categories"></a>Produits ou catégories exclus

En plus d'inclure des produits et des catégories dans les assortiments, vous pouvez utiliser l'option Exclure pour définir des produits ou des catégories spécifiques à exclure des assortiments. Dans l'exemple suivant, vous souhaitez inclure tous les produits dans une catégorie spécifique, sauf le produit 2. Dans ce cas, vous n'avez pas besoin de définir l'assortiment produit par produit ou de créer des nœuds de catégorie supplémentaires. Au lieu de cela, vous pouvez inclure simplement la catégorie mais exclure le produit.

> [!NOTE]
> Si un produit est inclus et exclu dans un ou plusieurs assortiments par définition, le produit sera toujours considéré comme exclu.

![Produit exclu](./media/Managing-assortments-figure6.png)

### <a name="global-and-released-products"></a>Produits globaux et lancés

Les assortiments sont définis à un niveau global et peuvent contenir des canaux de plusieurs entités juridiques. Les produits et les catégories inclus dans des assortiments sont également partagés entre plusieurs entités juridiques. Toutefois, un produit doit être lancé pour de pouvoir être vendu, commandée, calculé, ou reçu réellement dans le canal (par exemple, dans le point de vente \[PDV\]). Par conséquent, bien que deux magasins d'entités juridiques distinctes puissent partager un assortiment contenant les mêmes produits, ceux-ci ne sont disponibles que s'ils ont été lancés dans ces entités juridiques.

### <a name="dynamic-and-static-assortments"></a>Assortiments dynamiques et statiques

Les assortiments peuvent être définis avec des canaux et des produits spécifiques ou en incluant des unités et des catégories d'organisation. Les assortiments incluant des références à ces groupes sont considérés comme des assortiments dynamiques. Si la définition ou le contenu de ces groupes change alors que l'assortiment est actif, la définition de l'assortiment change également.

Par exemple, un assortiment est initialement défini et publié afin de faire référence à une catégorie de produits. Si des produits supplémentaires sont ajoutés ultérieurement à la catégorie, ces produits sont automatiquement inclus dans la définition de l'assortiment existant. Il n'est pas nécessaire d'ajouter manuellement les produits à l'assortiment. De même, si une unité d'organisation est ajoutée à un nœud différent, l'assortiment de l'unité d'organisation est automatiquement ajusté en fonction de cette définition.

### <a name="stopped-products"></a>Produits interrompus

Vous pouvez « interrompre » des produits lancés pour le processus de vente en activant un paramètre dans les paramètres **Commande par défaut**. Ce paramètre est le plus souvent utilisé lorsqu'un produit est à la fin de sa vie et ne doit être vendu dans aucun canal. Les assortiments respectent ce paramètre, et les produits interrompus ne sont pas assortis, indépendamment de la configuration de l'assortiment.

### <a name="blocked-products"></a>Produits bloqués

Outre l'interruption des ventes d'un produit, vous pouvez bloquer temporairement les ventes d'un produit. Vous pouvez configurer ce paramètre sous l'onglet **Commerce** d'un produit lancé. Les produits bloqués continuent d'être assortis, mais un message dans le PDV vous indique que ce produit ne peut pas être vendu.

### <a name="date-effectivity"></a>Prise d'effet de date

Les assortiments prennent effet par date. Par conséquent, les détaillants peuvent configurer quand les produits doivent ou ne doivent pas être disponibles par canal. Vous pouvez définir et publier des assortiments à l'avance, puis spécifier les dates de début et de fin. Les produits deviennent automatiquement disponibles ou non aux dates spécifiées.

### <a name="process-assortments-batch-job"></a>Traitement par lots des assortiments

Les assortiments définis dans Commerce doivent être traités avant qu'ils prennent effet. Ce traitement est effectué pour les raisons suivantes :

- Les définitions d'assortiments doivent être dénormalisées afin que les canaux puissent les consomment plus facilement. Un mélange de produits pour un canal peut être défini via plusieurs assortiments couvrant différentes plages de dates. Lorsque certaines de ces informations sont calculées en avance sur le serveur, les performances au niveau du canal sont améliorées.
- Les produits et les canaux de l'assortiment peuvent changer en dehors de l'assortiment lui-même. Les assortiments dynamiques qui contiennent des références à des catégories ou à des unités d'organisation doivent être traités périodiquement afin qu'ils incluent ou excluent des enregistrements, en fonction de leur affectation actuelle.

## <a name="implementation-considerations"></a>Considérations d'implémentation

Tenez compte des exigences de mise en œuvre suivantes lorsque vous planifiez et gérez les assortiments pour votre mise en œuvre Commerce :

- **Réplication de données et taille de la base de données** : bien que les assortiments permettent d'utiliser le besoin métier pour gérer la disponibilité de produit, ils constituent également un outil important pour gérer la taille du canal et des bases de données hors ligne. Les assortiments bien gérés permettent de réduire le volume de données devant être traitées et répliquées dans les bases de données de canaux et hors ligne. Ils permettent également de réduire le nombre d'enregistrements devant être rendus persistants. Moins d'enregistrements dans ces bases de données améliorera les performances lorsque vous ajouterez des articles à une transaction, rechercherez, puis parcourrez les produits.
- **Assortiments liés à une date d'effet/d'expiration** : l'un des outils les plus pertinents pour gérer le nombre de produits dans des bases de données de canaux et hors connexion est la prise d'effet de date des assortiments. Si vous laissez des assortiments ouverts (sans date d'expiration) pour des produits saisonniers ou des produits à la fin de leur vie, ces bases de données croîtront indéfiniment. Vous pouvez utiliser différentes approches pour gérer ces cas. Par exemple, vous pouvez tenir à jour des assortiments distincts pour les produits saisonniers et les produits qui sont toujours disponibles.
- **Ventes et retours en dehors des assortiments** : cette capacité permet aux détaillants de gérer efficacement leurs assortiments en leur laissant limiter le nombre de produits disponibles aux produits appartenant au mix produit de base du magasin. Cette capacité permet également aux détaillants de gérer les situations au cours desquelles un produit a été omis par erreur d'un assortiment, ou lorsqu'un produit a été retourné en dehors des dates d'effet de l'assortiment.

Si les données de produit n'existent pas dans la base de données du canal, le PDV effectue des appels en temps réel aux sièges sociaux pour récupérer les informations requises, de sorte que le produit pusse être vendu, retourné ou placé sur une commande client. Les informations sur le produit extraites de cette manière sont disponibles uniquement dans le cadre de cette transaction. Le produit n'est pas ajouté à la définition de l'assortiment. Par conséquent, les appels en temps réel consécutifs seront effectués au cas par cas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]