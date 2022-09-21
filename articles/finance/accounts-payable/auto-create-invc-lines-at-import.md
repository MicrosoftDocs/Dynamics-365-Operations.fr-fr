---
title: Générez des lignes de facture lorsque vous importez des factures fournisseur
description: Cet article décrit la fonctionnalité permettant de générer automatiquement des lignes de facture sur les factures fournisseur lors de l’importation des factures.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5cb2c1234de03e9777921c18e4cbb81eec7feef9
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462272"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Générez des lignes de facture lorsque vous importez des factures fournisseur

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article décrit la fonctionnalité permettant de générer automatiquement des lignes de facture sur les factures fournisseur lors de l’importation des factures.

Parfois, les factures fournisseur contiennent des informations limitées, telles que des informations sur les destinataires et des sous-totaux. Cependant, elles ne contiennent aucune information pour les éléments de ligne. Lorsque vous importez des factures, le système peut générer automatiquement des lignes de facture, en fonction des informations de la commande fournisseur correspondante.

Pour activer la création automatique de lignes de facture, procédez comme suit.

1.  Allez dans **Comptabilité fournisseur \> Paramètres \> Paramètres de la comptabilité fournisseur**.
2.  Dans l’onglet **Automatisation des factures fournisseur**, sous **Création automatique de lignes pour les factures importées**, définissez l’option **Créer automatiquement des lignes de facture** sur **Oui**. 
4.  Dans le champ **Choisir la quantité par défaut pour la création automatique de lignes de facture**, sélectionnez la quantité que le système doit utiliser pour générer automatiquement des lignes de facture :

    - **Quantité commandée** – Les lignes sont générées à partir des lignes de commande fournisseur. Cette valeur est la valeur par défaut.
    - **Quantité de l’accusé de réception de marchandises** – Le système utilisera le numéro de commande fournisseur pour trouver les accusés de réception de marchandises pertinents. Il utilisera ensuite les quantités de l’accusé de réception de marchandises pour générer des lignes de facture.

## <a name="data-entity-changes"></a>Modifications de l’entité de données

Pour prendre en charge les fonctionnalités décrites dans cet article, l’entité de données **En-tête de facture fournisseur** a été améliorée. Trois champs ont été ajoutés :

- **HeaderOnlyImport** – Ce champ doit être défini sur **Oui** pour générer des lignes pour les en-têtes de facture.
- **PurchIdRange** – Liste des numéros de commandes fournisseur. Les numéros de facture peuvent être une plage, par exemple **PO0001..PO0009** (où deux points séparent le début et la fin de la plage) ou des valeurs séparées, telles que **PO0001, PO0003, PO0006**. Toutes les commandes fournisseur doivent appartenir au même compte fournisseur sur l’en-tête de la facture. Sinon, vous recevrez le message d’erreur suivant : « Impossible de générer des lignes de facture. Les commandes fournisseur ont des comptes fournisseur différents. »
- **PackingslipRange** – Liste des numéros d’accusé de réception de marchandises. Les lignes de facture fournisseur peuvent être créées à partir des accusés de réception de marchandises. Cependant, les numéros d’accusé de réception de marchandises ne sont généralement pas inclus sur les factures fournisseur. N’entrez les numéros d’accusé de réception de marchandises dans ce champ que si vous pouvez clairement identifier quels accusés de réception de marchandises correspondent à quelles factures spécifiques. Les lignes de facture peuvent être générées à partir des accusés de réception de marchandises. Si ce champ est utilisé, le paramètre du champ **Choisir la quantité par défaut pour la création automatique de lignes de facture** sur la page **Paramètres de la comptabilité fournisseur** est ignoré. 

**Limitation** : Si vous saisissez plusieurs numéros d’accusé de réception de marchandises, plusieurs factures fournisseur en attente seront créées avec le même numéro de facture. Vous devez les consolider manuellement avant de poursuivre le traitement de la facture. Dans les prochaines versions, nous prévoyons de consolider les factures automatiquement, ce qui permettra de lever la limitation.

Tous les accusés de réception de marchandises doivent appartenir au même compte fournisseur sur l’en-tête de la facture.

## <a name="result"></a>Résultat

Si les lignes sont bien générées, le message suivant est enregistré dans l’historique d’automatisation des factures fournisseur : « Créer automatiquement des lignes de facture : Réussite ».

Si les lignes ne sont pas générées, le message d’erreur suivant est enregistré : « Créer automatiquement des lignes de facture : Échec ».
