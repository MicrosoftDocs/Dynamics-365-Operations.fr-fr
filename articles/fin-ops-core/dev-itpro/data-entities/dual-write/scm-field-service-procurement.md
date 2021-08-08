---
title: Intégrer l’approvisionnement entre Supply Chain Management et Field Service
description: Cette rubrique décrit comment l’intégration de la double écriture prend en charge la création de commandes fournisseur et les mises à jour à partir de Supply Chain Management et Field Service.
author: RamaKrishnamoorthy
ms.date: 11/11/2020
ms.topic: article
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c29efb885babea833e3c3fde0155e3722f8b77e9
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542389"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>Intégrer l’approvisionnement entre Supply Chain Management et Field Service

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management fournit une fonctionnalité d’approvisionnement robuste. Dynamics 365 Field Service offre une fonctionnalité similaire qui prend en charge les processus d’achat associés au processus de service. La fonctionnalité de ces deux applications est intégrée via la double écriture, et les scénarios d’utilisation interfonctionnels résultants sont activés via les mappages de table, la logique de la solution, les vues et les formulaires.

Cette intégration prend en charge la création de commandes fournisseur et, dans la plupart des cas, les mises à jour à partir des deux applications. Cependant, Supply Chain Management contrôle les prix, les adresses et les accusés de réception de marchandises. Plusieurs scénarios d’utilisation interfonctionnels puissants sont activés pour les organisations qui utilisent à la fois Field Service et Supply Chain Management. Ces scénarios d’utilisation permettent de lancer et de suivre les achats sur les deux systèmes.

L’illustration suivante montre les tables des deux systèmes et la manière dont elles sont mappées entre elles. Les commandes fournisseur dans Field Service font référence à une ligne de *compte*, tandis que les commandes fournisseur dans Supply Chain Management font référence à une ligne de *fournisseur*. Pour résoudre l’intégration, la double écriture utilise une référence pour lier les lignes de *fournisseur* aux lignes de *compte*. Pour plus d’informations, voir [Données principales fournisseur intégrées](vendor-mapping.md).

![Mappages de l’approvisionnement.](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>Conditions préalables

Pour intégrer Supply Chain Management à Field Service, vous devez installer les composants suivants :

- Field Service version 8.8.31.60 ou versions ultérieures, pour une intégration complète des commandes fournisseur
- Supply Chain Management version 10.0.14 ou versions ultérieures
- Double écriture, pour exécuter la solution OneFSSCM

## <a name="installation-guidelines"></a>Instructions d’installation

### <a name="prerequisites"></a>Conditions préalables

- **Double écriture** : pour plus d’informations, consultez la [Page d’accueil de la double écriture](dual-write-home-page.md#dual-write-setup).
- **Dynamics 365 Field Service** : pour plus d’informations, voir [Procédure d’installation de Dynamics 365 Field Service](/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service).

Lorsqu’ils sont activés dans Microsoft Dataverse, la double écriture et Field Service introduisent plusieurs couches de solution qui étendent l’environnement avec de nouvelles métadonnées, formulaires, vues et logique. Ces solutions peuvent être activées dans n’importe quel ordre, mais vous les installez généralement dans l’ordre indiqué ici :

1. **Field Service Common** : Field Service Common est installé lorsque Field Service est installé dans l’environnement.
2. **Field Service (Anchor)**  : Field Service (Anchor) est installé lorsque Field Service est installé dans l’environnement. 
3. **Supply Chain Management Extended** – Supply Chain Management Extended est automatiquement installé lorsque la double écriture est activée dans un environnement. 
4. **Solution OneFSSCM** : OneFSSCM est automatiquement installé par la solution (Field Service ou Supply Chain Management) installée en dernier.

    - Si Field Service est déjà installé dans l’environnement et que vous activez la double écriture, qui installe Supply Chain Management Extended, OneFSSCM est installé.
    - Si Supply Chain Management Extended est déjà installé dans l’environnement et que vous installez Field Service, OneFSSCM est installé.

## <a name="initial-synchronization"></a>Synchronisation initiale

Pour créer de nouvelles commandes fournisseur et utiliser des commandes fournisseur existantes, vous devez synchroniser les données de référence entre Supply Chain Management et Dataverse. La fonctionnalité d’écriture initiale permet de détecter les relations de table et de rechercher les tables que vous devez activer pour une mappage donné.

Vous devez synchroniser les tables suivantes :

- Modèles de produit

    Lorsque vous exécutez l’écriture initiale, vous obtenez une liste complète des tables requises. Voici quelques exemples de ces modèles :

    - Tous les produits
    - Produits lancés V2
    - Produits distincts lancés pour Dataverse

- Sites
- Entrepôts
- Modèles de catégories d’approvisionnement

    Voici quelques exemples de ces modèles :

    - Catégories d’approvisionnement
    - Pro
    - Hiérarchie de catégories de produit
    - Affectations de catégorie de produit

- Modèles de fournisseur, tels que Fournisseur V2
- Modèles de contact, tels que Contacts Dataverse V2
- Modèles de collaborateur, tels que Collaborateur

La synchronisation des tables garantit que tous les documents (commandes fournisseur et accusés de réception de marchandises) dans Supply Chain Management sont disponibles dans Dataverse.

### <a name="account-and-vendor-tables"></a>Tables de compte et de fournisseur

Les commandes fournisseur dans Field Service reposent sur la table Compte pour suivre les fournisseurs. Par conséquent, les tables de Dataverse pour les commandes fournisseur utilisent les comptes pour suivre les fournisseurs. Pour tenir compte de cette différence essentielle, les quatre flux de travail suivants doivent être activés pour assurer la synchronisation entre les comptes et les fournisseurs : 

- Créer des fournisseurs dans la table Comptes
- Créer des fournisseurs dans la table Fournisseurs
- Mettre à jour les fournisseurs dans la table Comptes
- Mettre à jour les fournisseurs dans la table Fournisseurs

Si OneFSSCM est installé, comme Field Service et Supply Chain Management Extended sont installés, ces workflows sont automatiquement activés. Si Field Service n’est pas installé, mais vous souhaitez intégrer les tables de commande fournisseur avec Dataverse, vous devez activer ces workflows. Dans les deux cas, à moins de partir de zéro, vous devrez peut-être vous assurer que tous les fournisseurs sont créés en tant que comptes dans Dataverse avant de créer des commandes fournisseur. Sinon, des erreurs peuvent se produire.

### <a name="initial-synchronization"></a>Synchronisation initiale

Une fois toutes les conditions préalables en place, si vous souhaitez que les commandes fournisseur et les accusés de réception de marchandises existants soient disponibles dans les deux systèmes, vous devez effectuer une synchronisation initiale des modèles suivants :

- En-tête de commande fournisseur V2
- Ligne de commande fournisseur de CDS
- Suppression temporaire de la ligne de commande fournisseur de CDS
- Accusé de réception de la commande fournisseur
- Produit d’accusé de réception de la commande fournisseur

## <a name="mappings-with-logic"></a>Mappages avec logique

L’intégration de l’approvisionnement étend le mappage de produit avec la logique suivante pour garantir que la colonne **Type de produit Field Service** est correctement définie dans la table de produits de Dataverse :

- Si **Type de produit** est défini sur *Produit* et **Groupe de modèles d’article, produit stocké** est défini sur *Vrai*, **Type de produit Field Service** est défini sur *Stock*.
- Si **Type de produit** est défini sur *Produit* et **Groupe de modèles d’article, produit stocké** est défini sur *False*, **Type de produit Field Service** est défini sur *Hors stock*.
- Si **Type de produit** est défini sur *Service*, **Type de produit Field Service** est défini sur *Service*.

En outre, Dataverse inclut une logique qui mappe les fournisseurs avec leurs comptes associés. Cette logique définit le compte fournisseur de factures par défaut. Lors de la création, la logique du plug-in côté serveur définit le compte fournisseur de factures par défaut du fournisseur associé au compte. Le fournisseur a une référence au compte de factures utilisé pour définir cette valeur.

## <a name="supported-scenarios"></a>Scénarios pris en charge

- Les commandes fournisseur peuvent être créées et mises à jour par les utilisateurs de Dataverse. Cependant, le processus et les données sont contrôlés par Supply Chain Management. Les contraintes des mises à jour des colonnes de la commande fournisseur dans Supply Chain Management s’appliquent lorsque les mises à jour proviennent de Field Service. Par exemple, vous ne pouvez pas mettre à jour une commande fournisseur si elle a été finalisée. 
- Si la commande fournisseur est contrôlée par la gestion des modifications dans Supply Chain Management, un utilisateur de Field Service ne peut mettre à jour la commande fournisseur que lorsque le statut d’approbation de Supply Chain Management est *Brouillon*.
- Plusieurs colonnes ne sont gérées que par Supply Chain Management et ne peuvent pas être mises à jour dans Field Service. Pour savoir quelles colonnes ne peuvent pas être mises à jour, consultez les tables de mappage du produit. Par souci de simplicité, la plupart de ces colonnes sont définies en lecture seule sur les pages de Dataverse. 

    Par exemple, les colonnes d’informations tarifaires sont gérées par Supply Chain Management. Supply Chain Management a des accords commerciaux dont Field Service peut bénéficier. Les colonnes telles que **Prix unitaire**, **Remise** et **Montant net** ne proviennent que de Supply Chain Management. Pour vous assurer que le prix est synchronisé avec Field Service, vous devez utiliser la fonctionnalité **Synchroniser** sur les pages **Commande fournisseur** et **Produit de la commande fournisseur** de Dataverse lorsque les données de la commande fournisseur ont été entrées. Pour plus d’informations, voir [Synchronisation à la demande avec les données d’approvisionnement de Dynamics 365 Supply Chain Management](#sync-procurement).

- La colonne **Totaux** n’est disponible que dans Field Service, car il n’y a pas de totaux à jour de la commande fournisseur dans Supply Chain Management. Les totaux dans Supply Chain Management sont calculés en fonction de plusieurs paramètres qui ne sont pas disponibles dans Field Service.
- Les lignes de commande fournisseur dans lesquelles une seule catégorie d’approvisionnement est spécifiée, ou dans lesquelles le produit spécifié est un article du type de produit *Service* ou du type de produit Field Service, ne peuvent être lancées que dans Supply Chain Management. Les lignes sont ensuite synchronisées avec Dataverse et sont visibles dans Field Service.
- Si seul Field Service est installé, et non Supply Chain Management, la colonne **Entrepôt** est obligatoire sur la commande fournisseur. Cependant, si Supply Chain Management est installé, cette obligation est assouplie, car Supply Chain Management autorise les lignes de commande fournisseur dans lesquelles aucun entrepôt n’est spécifié dans certaines situations.
- Les accusés de réception de marchandises (accusés de réception de commande fournisseur dans Dataverse) sont gérés par Supply Chain Management et ne peuvent pas être créés à partir de Dataverse si Supply Chain Management est installé. Les accusés de réception de marchandises de Supply Chain Management sont synchronisés de Supply Chain Management vers Dataverse.
- Les sous-livraisons sont autorisées dans Supply Chain Management. La solution OneFSSCM ajoute une logique de sorte que, lorsque la ligne d’accusé de réception de marchandises (ou le produit de l’accusé de réception de la commande fournisseur dans Dataverse) est créée ou mise à jour, une ligne de journal de stock est créée dans Dataverse pour ajuster la quantité restante en commande pour les scénarios de sous-livraison.

## <a name="unsupported-scenarios"></a>Scénarios non pris en charge

- Field Service empêche l’ajout de lignes à une commande fournisseur annulée dans Supply Chain Management. Pour contourner ce problème, vous pouvez modifier le statut système de la commande fournisseur dans Field Service, puis ajouter la nouvelle ligne dans Field Service ou Supply Chain Management.
- Bien que les lignes d’approvisionnement affectent les niveaux de stock dans les deux systèmes, cette intégration ne garantit pas l’alignement du stock dans Supply Chain Management et Field Service. Field Service et Supply Chain Management ont d’autres processus qui mettent à jour les niveaux de stock. Ces processus n’entrent pas dans le cadre de l’approvisionnement.

## <a name="status-management"></a>Gestion des statuts

Les statuts des commandes fournisseur dans Field Service diffèrent des statuts dans Supply Chain Management.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Statuts de commande fournisseur et de produit de commande fournisseur dans Field Service

| En-tête : statut du système | En-tête : statut d’approbation | Statut de l’article |
|---|---|---|
| <ul><li>Brouillon</li><li>Soumis</li><li>Annulé(e)</li><li>Produit reçu</li><li>Facturé</li></ul> | <ul><li>Null</li><li>Approuvé/e</li><li>Rejeté</li></ul> | <ul><li>Facture en attente</li><li>Reçue(s)</li><li>Annulé(e)</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Statuts de commande fournisseur et de ligne de commande fournisseur dans Supply Chain Management

Les statuts d’approbation de ligne ne sont actifs que lorsqu’il existe un workflow de ligne.

| En-tête : statut de documents | En-tête : statut d’approbation | Statut de ligne | Statut d’approbation de ligne |
|---|---|---|---|
| <ul><li>Commande en cours (reliquat)</li><li>Reçue(s)</li><li>Facturée</li><li>Annulé(e)</li></ul> | <ul><li>Brouillon</li><li>En cours de révision</li><li>Approuvé/e</li><li>Rejeté</li><li>En cours de révision externe</li><li>Confirmée</li><li>Finalisé</li></ul> | <ul><li>Commande en cours (reliquat)</li><li>Reçue(s)</li><li>Facturée</li><li>Annulé(e)</li></ul> | <ul><li>Non envoyé</li><li>En cours de révision</li><li>Approuvé/e</li><li>Rejeté</li></ul> |

Les règles suivantes sont appliquées aux colonnes de statut :

- Le statut dans Supply Chain Management ne peut pas être mis à jour à partir de Field Service. Cependant, dans certains cas, le statut dans Field Service est mis à jour lorsque le statut de la commande fournisseur dans Supply Chain Management est modifié.
- Si une commande fournisseur dans Supply Chain Management est en cours de gestion des modifications et qu’une modification est en cours de traitement, le statut d’approbation est *Brouillon* ou *En cours de révision*. Dans ce cas, le statut d’approbation de Field Service est défini sur *Nul*.
- Si le statut d’approbation de la commande fournisseur dans Supply Chain Management est défini sur *Approuvé*, *En cours de révision externe*, *Confirmé* ou *Finalisé*, le statut d’approbation de la commande fournisseur dans Field Service est défini sur *Approuvé*.
- Si le statut d’approbation de la commande fournisseur dans Supply Chain Management est défini sur *Rejeté*, le statut d’approbation de la commande fournisseur dans Field Service est défini sur *Rejeté*.
- Si le statut de l’en-tête de document dans Supply Chain Management est modifié en *Commande en cours (reliquat)* et le statut de la commande fournisseur dans Field Service est *Brouillon* ou *Annulé*, le statut de la commande fournisseur dans Field Service est modifié en *Envoyé*.
- Si le statut de l’en-tête de document dans Supply Chain Management est modifié en *Annulé* et aucun produit de l’accusé de réception de la commande fournisseur dans Field Service n’est associé à la commande fournisseur (via les produits de la commande fournisseur), le statut du système dans Field Service est défini sur *Annulé*.
- Si le statut de la ligne de commande fournisseur dans Supply Chain Management est *Annulé*, le statut du produit de la commande fournisseur dans Field Service est défini sur *Annulé*. En outre, si le statut de la ligne de commande fournisseur dans Supply Chain Management est modifié de *Annulé* en *Reliquat*, le statut de l’article de la commande fournisseur dans Field Service est défini sur *En attente*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Synchronisation à la demande avec les données d’approvionnement de Supply Chain Management

Supply Chain Management comprend des données d’approvisionnement qui gèrent les accords commerciaux, les remises et d’autres scénarios qui reposent sur des processus secondaires dans Supply Chain Management. Le moteur d’approvisionnement utilise des règles complexes pour déterminer le meilleur prix pour une commande fournisseur donnée. Lorsque vous utilisez la double écriture, les données ne sont pas toujours synchronisées dans les deux environnements, en particulier dans les scénarios où la ligne a été créée ou mise à jour à partir de Dataverse et peut déclencher des processus de suivi dans Supply Chain Management.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Synchroniser les données d’approvionnement de Supply Chain Management

1. Dans Dataverse, accédez à **Stock \> Commande fournisseur**.
2. Sélectionnez **Nouveau** pour créer une commande fournisseur, ou sélectionnez la ligne d’une commande fournisseur existante.
3. À partir de la commande fournisseur ou de la ligne de commande fournisseur.
4. Dans le volet Actions, sélectionnez **Synchroniser**.

Toutes les colonnes de Dataverse et Field Service qui sont partagés par Supply Chain Management sont synchronisées.

Voici les situations dans lesquelles vous pouvez utiliser la fonction **Synchroniser** :

- Si vous apportez plusieurs modifications successives à la même ligne dans Dataverse, exécutez la fonction **Synchroniser**.
- Si vous n’êtes pas sûr qu’un changement soit le deuxième changement successif dans Dataverse, il peut être utile d’exécuter la fonction **Synchroniser**.
- Si vous recevez un message d’erreur concernant la mise à jour d’une valeur dans Supply Chain Management, exécutez la fonction **Synchroniser**, puis recommencez la mise à jour dans Dataverse.

## <a name="cancelling-the-posting-process"></a>Annulation du processus de publication

Si le processus de validation de l’accusé de réception de marchandises est annulé pendant le traitement, la double écriture peut créer une ligne d’accusé de réception de marchandises dans Dataverse, mais pas dans Supply Chain Management. Cette situation se produit car la double écriture ne prend pas en charge les transactions distribuées.

## <a name="templates"></a>Modèles

Les modèles suivants sont disponibles pour l’intégration des documents liés à l’approvisionnement.

| Gestion de la chaîne d’approvisionnement | Field Service | Description |
|---|---|---|
| [En-tête de commande fournisseur V2](mapping-reference.md#183) | msdyn\_Purchaseorders | Cette table contient les colonnes qui représentent l’en-tête de commande fournisseur. |
| [Entité de ligne de commande fournisseur](mapping-reference.md#181) | msdyn\_PurchaseOrderProducts | Cette table contient les lignes qui représentent les lignes d’une commande fournisseur. Le numéro de produit est utilisé pour la synchronisation. Cela identifie le produit comme une unité de gestion de stock (SKU), y compris les dimensions du produit. Pour plus d’informations sur l’intégration de produit avec Dataverse, voir [Expérience produit uniformisée](product-mapping.md). |
| [En-tête d’accusé de réception des marchandises](mapping-reference.md#185) | msdyn\_purchaseorderreceipts | Cette table contient les en-têtes d’accusé de réception de marchandises créés lorsqu’un accusé de réception de marchandises est enregistré dans Supply Chain Management. |
| [Lignes d’accusé de réception des marchandises](mapping-reference.md#184) | msdyn\_purchaseorderreceiptproducts | Cette table contient les lignes d’accusé de réception de marchandises créées lorsqu’un accusé de réception de marchandises est enregistré dans Supply Chain Management. |
| [Entité de suppression temporaire de ligne de commande fournisseur](mapping-reference.md#182) | msdyn\_purchaseorderproducts | Ce tableau contient des informations sur les lignes de commande fournisseur qui sont supprimées de manière temporaire. Une ligne de commande fournisseur dans Supply Chain Management ne peut être supprimée de manière temporaire que lorsque la commande fournisseur a été confirmée ou approuvée, si la gestion des modifications est activée. La ligne existe dans la base de données de Supply Chain Management et est marquée comme **IsDeleted**. Comme Dataverse n’a pas de concept de suppression temporaire, il est important que ces informations soient synchronisées avec Dataverse. De cette manière, les lignes supprimées de manière temporaire dans Supply Chain Management peuvent être automatiquement supprimées de Dataverse. Dans ce cas, la logique de suppression d’une ligne dans Dataverse se trouve dans Supply Chain Management Extended. |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
