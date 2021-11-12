---
title: Générez des lignes de facture lorsque vous importez des factures fournisseur
description: Cette rubrique décrit la fonctionnalité permettant de générer automatiquement des lignes de facture sur les factures fournisseur lors de l’importation des factures.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 87dec3c142ae296975ab98432421be4548085c80
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647887"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Générez des lignes de facture lorsque vous importez des factures fournisseur

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique décrit la fonctionnalité permettant de générer automatiquement des lignes de facture sur les factures fournisseur lors de l’importation des factures.

Parfois, les factures fournisseur contiennent des informations limitées, telles que des informations sur les destinataires et des sous-totaux. Cependant, elles ne contiennent aucune information pour les éléments de ligne. Lorsque vous importez des factures, le système peut générer automatiquement des lignes de facture, en fonction des informations de la commande fournisseur correspondante.

Pour activer la création automatique de lignes de facture, procédez comme suit.

1.  Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
2.  Dans l’onglet **Automatisation des factures fournisseur**, sous **Création automatique de lignes pour les factures importées**, définissez l’option **Créer automatiquement des lignes de facture** sur **Oui**. 
4.  Dans le champ **Choisir la quantité par défaut pour la création automatique de lignes de facture**, sélectionnez la quantité que le système doit utiliser pour générer automatiquement des lignes de facture :

    - **Quantité commandée** – Le système générera des lignes à partir des lignes de commande fournisseur. Cette valeur est la valeur par défaut.
    - **Quantité de l’accusé de réception de marchandises** – Le système utilisera les numéros de commande fournisseur pour trouver les accusés de réception de marchandises pertinents. Il utilisera ensuite les quantités de l’accusé de réception de marchandises pour générer des lignes de facture.

## <a name="data-entity-changes"></a>Modifications de l’entité de données

Pour prendre en charge les fonctionnalités décrites dans cette rubrique, l’entité de données **En-tête de facture fournisseur** a été améliorée. Trois champs ont été ajoutés :

- **HeaderOnlyImport** – Ce champ doit être défini sur **Oui** pour que le système génère des lignes pour les en-têtes de facture.
- **PurchIdRange** – Liste des numéros de commandes fournisseur. Les numéros de facture peuvent être une plage, par exemple **INV0001..INV0009** (où deux points séparent le début et la fin de la plage) ou des valeurs séparées, telles que **INV0001, INV0003, INV0006**. Toutes les commandes fournisseur doivent appartenir au même compte fournisseur sur l’en-tête de la facture. Sinon, vous recevrez le message d’erreur suivant : « Impossible de générer des lignes de facture. Les commandes fournisseur ont des comptes fournisseur différents. »
- **PackingslipRange** – Liste des numéros d’accusé de réception de marchandises. Les lignes de facture fournisseur peuvent être créées à partir des accusés de réception de marchandises. Cependant, les numéros d’accusé de réception de marchandises ne sont généralement pas inclus sur les factures fournisseur. N’entrez les numéros d’accusé de réception de marchandises dans ce champ que si vous pouvez clairement identifier quels accusés de réception de marchandises correspondent à quelles factures spécifiques. Les lignes de facture peuvent être générées à partir des accusés de réception de marchandises. Et si ce champ est utilisé, le paramètre du champ **Choisir la quantité par défaut pour la création automatique de lignes de facture** sur la page **Paramètres de la comptabilité fournisseur** est ignoré. 

**Limitation** : Si vous saisissez plusieurs numéros d’accusé de réception de marchandises, plusieurs factures fournisseur en attente seront créées avec le même numéro de facture. Vous devez les consolider manuellement avant de poursuivre le traitement de la facture. Dans les prochaines versions, nous prévoyons de permettre au système de consolider les factures automatiquement, ce qui permettra de lever la limitation.

Tous les accusés de réception de marchandises doivent appartenir au même compte fournisseur sur l’en-tête de la facture.

## <a name="result"></a>Résultat

Si le système génère avec succès des lignes, le message suivant est enregistré dans l’historique d’automatisation des factures fournisseur : « Créer automatiquement des lignes de facture : Réussite ».

Si le système ne parvient pas à générer des lignes, le message d’erreur suivant est enregistré : « Créer automatiquement des lignes de facture : Échec ».
