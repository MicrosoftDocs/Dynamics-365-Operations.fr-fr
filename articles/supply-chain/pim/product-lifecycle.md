---
title: Vue d’ensemble de l’état du cycle de vie des produits
description: L’état du cycle de vie des produits documente l’état du cycle de vie d’un produit ou d’une variante de produit lancé.
author: t-benebo
ms.date: 01/06/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 5d1ea1517c75393b1c8d7c95c8aa2405042b4532
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850639"
---
# <a name="product-lifecycle-state-overview"></a>Vue d’ensemble de l’état du cycle de vie des produits

[!include [banner](../includes/banner.md)]

L’état du cycle de vie des produits documente l’état du cycle de vie d’un produit ou d’une variante de produit lancé. Les états du cycle de vie des produits sont définis par l’utilisateur, généralement un responsable de produit ou un responsable des données principales de produit. Des processus d’entreprise spécifiques, tels que la planification, peuvent être affectés par un état spécifique du cycle de vie.

Un produit ou une variante de produit lancé peut être associé à un état du cycle de vie des produits qui documente dans quel état du cycle de vie se trouve actuellement un produit ou une variante de produit spécifique. Vous pouvez définir plusieurs états du cycle de vie des produits en affectant un nom et une description. Vous pouvez sélectionner un état du cycle de vie comme valeur par défaut pour les nouveaux produits lancés. Les variantes de produit lancé héritent leur état de cycle de vie de leur produit générique lancé lors de la création. Lors de la modification de l’état du cycle de vie d’un produit générique lancé, vous pouvez choisir de mettre à jour toutes les variantes existantes qui ont le même état initial.  

## <a name="create-a-new-product-lifecycle-state"></a>Créer un état du cycle de vie des produits

- Pour créer un état du cycle de vie des produits, voir [Créer un état du cycle de vie des produits](tasks/new-product-lifecycle-state.md).

- Pour créer un état du cycle de vie des produits par défaut, voir [Créer un état du cycle de vie par défaut des produits](tasks/default-product-lifecycle-state.md).

## <a name="associate-product-lifecycle-states-to-released-products"></a>Associer les états du cycle de vie des produits aux produits lancés  

Il existe plusieurs méthodes pour associer un état du cycle de vie des produits aux produits ou variantes de produit lancés.

- Lors de la création d’un produit lancé, l’**État du cycle de vie des produits** par défaut est automatiquement affecté.
- Lors du lancement d’un produit dans une entité juridique, l’**État du cycle de vie des produits** par défaut est automatiquement affecté.
- Lors du lancement d’une variante de produit dans une entité juridique, l’**État du cycle de vie des produits** associé au produit générique lancé dans cette entité juridique est automatiquement affecté à la nouvelle variante.

Vous pouvez mettre à jour manuellement l’état du cycle de vie des produits à l’aide de :

- La page de liste **Produits lancés** ou la **Vue Détails**.
- La page de liste **Variantes de produit lancé** ou la **Vue Détails**.
- Recherchez les produits ou les variantes de produit obsolètes en fonction de la demande et associez un état du cycle de vie.  

Plus d’informations :

- Pour associer un état du cycle de vie des produits à un produit générique lancé, voir [Affecter un état du cycle de vie des produits à un produit générique lancé](tasks/product-lifecycle-state-released-product-master.md).

- Pour associer un état du cycle de vie des produits à un produit lancé, voir [Affecter un état du cycle de vie des produits à un produit générique lancé](tasks/product-lifecycle-state-released-product.md).

## <a name="impact-on-master-planning"></a>Impact sur la planification

L’état du cycle de vie des produits ne comporte qu’un seul indicateur de contrôle : **Est actif pour la planification**. Par défaut, il est défini sur **Oui** pour tous les états de cycle de vie de produit créés, mais il peut être modifié sur **Non**. Lorsqu’il est défini sur **Non**, les produits ou les variantes de produit lancés associés sont :

- Exclus de la planification.
- Exclus du calcul au niveau de la nomenclature.

Pour des informations détaillées sur l’utilisation de l’état du cycle de vie des produits pour exclure des produits de la planification et du calcul au niveau de la nomenclature, voir [Créer un état du cycle du vie des produits pour exclure des produits de la planification](tasks/exclude-products-master-planning.md)

> [!NOTE]
> Pour des raisons de performances, il est fortement recommandé d’associer les produits ou les variantes de produit lancés obsolètes, surtout lorsque vous travaillez avec des variantes de configuration de produit non réutilisables, avec un état du cycle de vie des produits qui est désactivé pour la planification.  

## <a name="default-migration-import-and-export"></a>Migration, importation et exportation par défaut

Les états du cycle de vie des produits sont pris en charge par les entités de données, et l’état du cycle de vie peut être défini sur un état variable via les entités de données de produits lancés ou les entités de données de variantes publiées.

## <a name="find-obsolete-products-and-products-variants"></a>Rechercher des produits et des variantes de produit obsolètes

Vous pouvez exécuter une analyse de simulation pour rechercher les produits ou les variantes de produit lancés obsolètes et mettre à jour le statut de leur cycle de vie. Pour rechercher des produits obsolètes, voir [Rechercher des variantes de produit obsolètes et affecter un état du cycle de vie des produits](tasks/obsolete-product-variants.md). Cet article décrit comment rechercher des produits ou des variantes de produits lancés obsolètes et comment associer un état du cycle de vie des produits aux produits obsolètes. Il explique également comment afficher les résultats de la simulation et évaluer le nombre de produits et de variantes de produit à associer à un nouvel état du cycle de vie des produits lors de l’exécution de la mise à jour sans simulation.  

En exécutant l’analyse en mode de simulation, les produits et les variantes de produit identifiés comme obsolètes sont affichés dans un écran spécifique, où ils peuvent facilement être examinés. L’analyse recherche des transactions et des données principales spécifiques pour identifier les produits sans demande dans une période variable et sans données principales pouvant entraîner une demande. Les nouveaux produits lancés dans une période variable peuvent être exclus de l’analyse. Lorsque la simulation de l’analyse renvoie le résultat attendu, l’utilisateur peut exécuter l’analyse et définir un nouvel état du cycle de vie pour tous les produits identifiés comme obsolètes par l’analyse.  

> [!NOTE]
> Notez que toutes les analyses et mises à jour doivent être effectuées dans la même entité juridique.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Critères de sélection et de mise à jour des produits ou des variantes de produit lancés

Utilisez les critères suivants pour sélectionner et mettre à jour les produits et les variantes de produit lancés :

- L’état du cycle de vie du produit ou de la variante de produit doit être différent du nouvel état souhaité.
- Le produit ou la variante de produit a été créé il y a quelques jours en fonction du nombre de jours saisis dans la boîte de dialogue de sélection.
- Il n’existe aucun ordre de fabrication en cours (= statut < terminé) pour le produit ou la variante de produit.
- Il n’existe aucune transaction de stock en cours (= sortie de statut ReservPhysical sur QuotationIssue ou réception de statut Registrered sur QuotationReceipt) pour le produit ou la variante de produit.
- Il n’existe aucune transaction de stock au cours des derniers jours pour le produit ou la variante de produit.
- Il n’existe aucune demande future ou prévision d’approvisionnement pour le produit ou la variante de produit.  
- Aucun niveau de stock minimal n’a été défini dans la couverture d’article pour le produit ou la variante de produit.
- Aucune règle de kanban à quantité fixe active pour le produit ou la variante de produit.  
- Aucune ligne de commande de service pour le produit ou la variante de produit.
- Aucune ligne de contrat de vente ou d’achat active ou future pour le produit ou la variante de produit.
- Le produit ou la variante de produit n’est pas utilisé dans une nomenclature associée à une version de nomenclature approuvée non expirée pour un produit ou une variante qui est actif pour la planification.

## <a name="related-articles"></a>Articles connexes

- [Créer un état du cycle de vie des produits](tasks/new-product-lifecycle-state.md)
- [Créer un état du cycle de vie des produits par défaut](tasks/default-product-lifecycle-state.md)
- [Affecter un état du cycle de vie des produits à un produit générique lancé](tasks/product-lifecycle-state-released-product-master.md)
- [Affecter un état du cycle de vie des produits à un produit lancé](tasks/product-lifecycle-state-released-product.md)
- [Rechercher des variantes de produit obsolètes et affecter un état du cycle de vie des produits](tasks/obsolete-product-variants.md)
- [Créer un état du cycle de vie des produits pour exclure des produits de la planification](tasks/exclude-products-master-planning.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]