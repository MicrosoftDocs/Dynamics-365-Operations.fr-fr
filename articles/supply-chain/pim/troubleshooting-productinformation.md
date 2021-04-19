---
title: Résoudre les problèmes d’informations sur le produit
description: Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des informations sur le produit.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a05e9957363ef6a659e25ceba84a168507cd641a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841525"
---
# <a name="troubleshoot-product-information"></a>Résoudre les problèmes d’informations sur le produit

Cette rubrique décrit comment résoudre les problèmes que vous pourriez rencontrer lors de l’utilisation des informations sur le produit.

## <a name="i-cant-delete-a-released-product"></a>Je ne peux pas supprimer un produit lancé.

### <a name="issue-description"></a>Description du problème

Vous pouvez supprimer un produit lancé et toutes ses variantes uniquement si le produit lancé ne comporte aucune transaction associée.

### <a name="issue-resolution"></a>Résolution du problème

Suivez ces étapes pour supprimer un produit lancé ou un produit générique.

1. Fermez toutes les transactions ouvertes pour les articles.
1. Réduisez le stock à 0 (zéro).
1. Effectuer la clôture des stocks.
1. Supprimez toutes les variantes de produit pour le produit générique que vous souhaitez supprimer.

## <a name="can-i-change-the-item-number-of-a-released-product"></a>Puis-je modifier le numéro d’article d’un produit lancé ?

Dans la plupart des cas, vous ne pouvez pas modifier les numéros d’article des produits lancés, car cette modification entraînera la corruption des données. Vous ne pouvez modifier le numéro d’article que si vous devez réparer la corruption des données causée par un précédent changement de nom de la clé primaire de ce produit lancé, comme indiqué dans la liste des [fonctionnalités supprimées ou obsolètes pour Finance and Operations 10.0.0 avec Platform Update 24](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md#finance-and-operations-1000-with-platform-update-24).

Si vous souhaitez pouvoir modifier les numéros d’article des produits lancés, [votez pour cette idée dans le portail des idées](https://experience.dynamics.com/ideas/idea/?ideaid=660fcb15-875d-ea11-b698-0003ff68bc25).

## <a name="the-default-flushing-principle-from-the-product-isnt-being-entered-on-the-bill-of-materials-line"></a>Le principe d’effacement par défaut du produit n’est pas entré dans la ligne de nomenclature.

### <a name="issue-description"></a>Description du problème

Lorsque vous ajoutez un article à une ligne de nomenclature (BOM), le système n’utilise pas les informations de principe de rinçage par défaut qui sont configurées pour l’article. En d’autres termes, le principe d’effacement de l’article n’apparaît pas sur la page **Ligne de nomenclature**.

### <a name="issue-resolution"></a>Résolution du problème

Si vous spécifiez un principe d’effacement sur une ligne de nomenclature, il s’appliquera à cette ligne de nomenclature. Cependant, si le principe d’effacement est vide ou s’il n’est pas défini sur une ligne de nomenclature, le principe d’effacement défini sur l’article s’appliquera toujours à cette ligne de nomenclature, même s’il n’est pas affiché sur la ligne de nomenclature.

La logique par défaut pour les autres fonctionnalités de Microsoft Dynamics 365 Supply Chain Management ne fonctionne généralement pas de cette manière. Cependant, le comportement actuel ne peut pas être modifié. Sinon, certaines personnalisations existantes qui en dépendent pourraient être interrompues.

## <a name="the-system-lets-me-save-duplicate-bar-codes-for-different-items-or-for-the-same-item-that-has-different-dimensions"></a>Le système me permet d’enregistrer des codes à barres en double pour différents articles ou pour le même article qui a des dimensions différentes.

Le système n’applique actuellement pas de codes à barres uniques et l’ajout de cette restriction constituerait un changement radical. En fait, Microsoft a la preuve que certaines installations client existantes seraient interrompues par ce changement. Cependant, nous envisagerons un changement de conception plus large pour activer cette fonctionnalité à l’avenir.

## <a name="i-receive-the-following-error-message-when-i-edit-item-record-templates-the-warehouse-location-cannot-be-created-because-the-item-is-not-stocked-to-stock-items-the-stocked-product-option-on-the-associated-item-model-group-must-be-selected"></a>Je reçois le message d’erreur suivant lorsque je modifie des modèles d’enregistrement d’article : "L’emplacement de l’entrepôt ne peut pas être créé car l’article n’est pas stocké. Pour stocker des articles, l’option Produit en stock du groupe de modèles d’articles associé doit être sélectionnée. »

### <a name="issue-description"></a>Description du problème

Ce problème se produit si vous suivez ces étapes pour essayer de créer un modèle pour un article qui n’est pas stocké.

1. Ouvrez un produit lancé qui n’est pas en stock.
1. Dans le volet Actions, sous l’onglet **Options**, sélectionnez **Infos sur l’enregistrement**.
1. Dans la boite de dialogue **Infos sur l’enregistrement**, sélectionnez **Modèle de comptes d’entreprise**.

Dans ce cas, vous recevez le message d’erreur suivant :

> L’emplacement de l’entrepôt ne peut pas être créé car l’article n’est pas stocké. Pour stocker des articles, l’option Produit en stock du groupe de modèles d’articles associé doit être sélectionnée.

### <a name="issue-resolution"></a>Résolution du problème

Le processus de création de modèles de produit nécessite une logique supplémentaire spécifique au produit. Par conséquent, vous ne pouvez pas utiliser le bouton **Modèle de comptes d’entreprise** générique à cet effet. À la place, procédez comme suit.

1. Ouvrez un produit lancé.
1. Sur le volet Actions, sous l’onglet **Produit**, dans le groupe **Nouveau**, cliquez sur **Modèle \> Créer un modèle partagé**.

## <a name="default-help-text-that-is-added-in-product-attributes-isnt-entered-in-a-released-product"></a>Le texte d’aide par défaut ajouté dans les attributs de produit n’est pas entré dans un produit lancé.

Une description et un texte d’aide ajoutés dans les attributs du produit ne sont pas visibles ou saisis par défaut dans les produits lancés. Ce comportement est fait exprès.

## <a name="the-default-quantity-that-is-entered-differs-when-its-registered-from-a-bom-and-when-its-registered-from-a-bom-version"></a>La quantité par défaut saisie diffère lorsqu’elle est enregistrée à partir d’une nomenclature et lorsqu’elle est enregistrée à partir d’une version de nomenclature.

### <a name="issue-description"></a>Description du problème

Par défaut, lorsque vous ajoutez un article à une nomenclature, la quantité est définie sur 1 au lieu de la quantité définie dans le champ **Quantité de commande min.** sur la page **Paramètres de commande par défaut** pour un produit sélectionné. Cependant, lorsque vous ajoutez un article à partir d’une version de nomenclature et que l’article et la variante sont sélectionnés, la quantité saisie par défaut prend en compte la quantité minimale définie dans les paramètres de commande par défaut pour les dimensions spécifiques.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est attendu. Cependant, le fait que la logique diffère dans la nomenclature et la version de la nomenclature est un problème connu. Néanmoins, ce comportement ne sera pas modifié, car un changement pourrait affecter de nombreux scénarios clients différents.

## <a name="in-the-released-product-details-i-cant-change-the-attached-images-that-were-uploaded-from-the-product-document-attachments-data-entity"></a>Dans les détails du produit publié, je ne peux pas modifier les images jointes qui ont été chargées à partir de l’entité de données de pièces jointes du document Produit.

### <a name="issue-description"></a>Description du problème

Ce problème peut se produire lorsque vous joignez une image à un article à l’aide de l’entité de données *Pièces jointes aux documents de produit*. Dans ce cas, l’image de l’article est affichée pour l’article. Cependant, si vous sélectionnez **Modifier l’image**, rien n’est affiché dans la liste des images chargées. De plus, aucune pièce jointe n’est affichée pour l’article.

### <a name="issue-resolution"></a>Résolution du problème

L’entité *EcoResProductDocumentAttachmentEntity* (*Pièces jointes aux documents de produit*) importe les pièces jointes pour *des produits* mais pas pour des *produits lancés*. (Les produits commercialisés sont également connus sous le nom d’*articles*.) Pour afficher les pièces jointes d’un article sur la page **Détails du produit publié**, vous devez utiliser l’entité *EcoResReleasedProductDocumentAttachmentEntity* (*Pièces jointes de document de produit publié*) à l place.

## <a name="the-microsoft-flow-connector-shows-the-following-error-message-update-not-allowed-for-field-productnumber"></a>Le connecteur Microsoft Flow affiche le message d’erreur suivant : « Mise à jour non autorisée pour le champ ’ProductNumber’. »

### <a name="issue-description"></a>Description du problème

Ce problème se produit si vous essayez de mettre à jour le champ **Numéro de produit** en utilisant l’entité *Produits lancés* V2 et Microsoft Flow.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est attendu. La possibilité de modifier le numéro de produit d’un produit lancé a été supprimée dans Dynamics 365 Finance and Operations 10.0.0 avec Platform Update 24 pour éviter la corruption des données. Dan sdes cas exceptionnels, où vous devez réparer une corruption des données causée par un précédent changement de nom de la clé primaire d’un produit publié, vous pouvez demander au Support Microsoft de supprimer temporairement cette restriction.

## <a name="i-cant-create-a-released-product-variant-in-another-legal-entity"></a>Je ne peux pas créer une variante de produit lancée dans une autre entité juridique.

### <a name="issue-description"></a>Description du problème

Si vous essayez de publier un produit générique sans variantes, puis que vous créez les variantes dans chaque entité juridique (société) au fur et à mesure qu’elles sont nécessaires, vous ne pourrez pas valider les variantes à l’aide de suggestions de variantes. Vous ne pourrez pas non plus créer manuellement les variantes.

### <a name="issue-resolution"></a>Résolution du problème

Ce comportement est fait exprès. Les relations d’un produit générique et les dimensions que le générique peut prendre sont conservées à un niveau partagé. Par conséquent, vous ne pouvez pas créer les dimensions disponibles pour un produit générique partagé dans l’entité juridique spécifique où ces dimensions sont lancées, puis répliquer le processus dans chaque entité juridique où les dimensions sont requises. Au lieu de cela, vous devez modifier votre processus de publication pour vous adapter au processus conçu.

Voici le processus de sortie des produits.

1. Créez le produit générique et les dimensions partagés qui peuvent être validés pour les entités juridiques.
1. Libérez les produits pour les entités juridiques en utilisant des suggestions de variantes ou en ajoutant manuellement les combinaisons à publier.

Vous pouvez également créer directement le produit lancé.

## <a name="when-i-release-a-variant-in-another-company-i-receive-the-following-error-message-product-variant-with-specified-dimensions-has-already-been-created"></a>Lorsque je publie une variante dans une autre société, je reçois le message d’erreur suivant : « La variante de produit avec des dimensions spécifiées a déjà été créée. »

### <a name="issue-description"></a>Description du problème

Si une variante de produit a déjà été lancée dans une entreprise A et que vous essayez de la lancer dans l’entreprise B en utilisant le bouton **Nouveau** sur la page **Variantes de produits lancées**, vous recevrez le message d’erreur suivant :

> Il existe déjà une variante de produit comportant les dimensions spécifiées.

### <a name="issue-resolution"></a>Résolution du problème

Le bouton **Nouveau** sur la page **Variantes de produits lancées** crée la variante et la libère dans le contexte de l’entreprise. Si la variante a déjà été créée, vous ne pouvez pas utiliser le bouton **Nouveau** pour le libérer dans une autre entreprise.

Pour résoudre le problème, ouvrez la page **Produit générique** et sélectionnez **Publier le produit** pour libérer la variante existante dans l’entreprise souhaitée.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]