---
title: Mises en attente du paiement d&quot;une facture fournisseur dans le secteur public en France
description: "Les processus standard liés aux mises en attente de paiement d&quot;une facture fournisseur dans Microsoft Dynamics « AX 7 » ont été étendus pour les entités françaises du secteur public. Cette rubrique décrit la fonctionnalité de mises en attente de paiement d&quot;une facture fournisseur utilisée par le secteur public en France."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27331
ms.assetid: 09ece137-e8fd-41ec-ae46-dc922b327999
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 4dc3457160a7ab2656517301a473b6f79539d237
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="vendor-invoice-payment-holds-in-the-public-sector-in-france"></a>Mises en attente du paiement d'une facture fournisseur dans le secteur public en France

[!include[banner](../includes/banner.md)]


Les processus standard liés aux mises en attente de paiement d'une facture fournisseur dans Microsoft Dynamics 365 for Operations ont été étendus pour les entités françaises du secteur public. Cette rubrique décrit la fonctionnalité de mises en attente de paiement d'une facture fournisseur utilisée par le secteur public en France.

<a name="set-up-rules-for-vendor-invoice-payment-holds"></a>Définition de règles pour les mises en attente de paiement d'une facture fournisseur
---------------------------------------------

Les règles pour la mise en attente du paiement d'une facture fournisseur sont paramétrées dans l'organisateur **Bloquer** de la page **Conditions de paiement**. Chaque règle est constituée de trois parties :

-   Un rôle utilisateur, tel que comptable, gestionnaire comptable ou contrôleur. Seuls les utilisateurs dotés du rôle spécifié peuvent mettre en attente ou lancer un paiement sous les conditions de paiement spécifiées.
-   Le nombre de jours minimal à ajouter à la date d'échéance du paiement de la facture lorsqu'un utilisateur doté du rôle sélectionné met fin à la mise en attente.
-   Le nombre maximal de fois où un utilisateur doté du rôle spécifié peut mettre en attente un paiement sur chaque facture. **Conseil** : pour autoriser un nombre illimité de mises en attente, entrez un nombre important, tel que 9999.

Par exemple, sur les conditions de paiement Net 30, vous pouvez créer deux règles : une pour les comptables et une pour les directeurs. La règle pour les comptables ajoute un minimum de 30 jours à la date d'échéance de paiement de la facture lorsque la mise en attente prend fin, et autorise un maximum de 3 mises en attente sur une facture. La règle pour les directeurs ajoute un minimum de 15 jours à la date d'échéance de paiement de la facture, avec un maximum de 10 mises en attente sur une facture.

## <a name="when-can-i-place-and-release-vendor-invoice-payment-holds"></a>Quand puis-je créer et supprimer des mises en attente de paiement d'une facture fournisseur ?
Des mises en attente de paiement peuvent être effectuées ou supprimées dans les conditions suivantes :

-   Pour pouvoir effectuer une mise en attente de paiement, il faut que des conditions de paiement aient été définies pour la facture fournisseur concernée ou pour toutes les factures fournisseur associées au fournisseur concerné.
-   Pour créer une mise en attente de paiement ou la supprimer, vous devez être affecté à un rôle d'utilisateur pour lequel des règles ont été définies pour les mises en attente de paiement.
-   Si une mise en attente est activée pour un fournisseur, il est impossible de procéder à la mise en attente d'une facture du même fournisseur. Vous devez d'abord supprimer la mise en attente du fournisseur.
-   Seul l'utilisateur qui a procédé à la mise en attente ou les utilisateurs qui assument le même rôle que ce dernier sont habilités à supprimer la mise en attente.
-   Il est impossible de valider une facture fournisseur dont le paiement a été mis en attente. Il convient d'abord de supprimer la mise en attente.

## <a name="where-do-i-place-and-release-vendor-invoice-payment-holds"></a>Où dois-je créer et supprimer des mises en attente de paiement d'une facture fournisseur ?
### <a name="for-a-vendor"></a>Pour un fournisseur
Créez ou supprimez une mise en attente de paiement pour toutes les factures d'un fournisseur sélectionné sur la page **Transactions fournisseur** ou sur la page **Règlement des transactions**. Si vous appliquez une mise en attente de paiement à un fournisseur, cette dernière concernera toutes les factures de ce fournisseur. Si vous supprimez la mise en attente de paiement appliquée à un fournisseur, les mises en attente ne seront supprimées que sur les factures fournisseur qui n'ont pas été mises en attente individuellement. Par exemple, vous procédez à des mises en attente de paiement individuelles de deux factures fournisseur différentes, concernant le même fournisseur. Ultérieurement, vous appliquez une mise en attente de paiement au fournisseur. Lorsque vous supprimerez la mise en attente de paiement appliquée au fournisseur, les mises en attente individuelles des deux factures ne seront pas supprimées.

### <a name="for-a-vendor-invoice"></a>Pour une facture fournisseur

Créez ou supprimez une mise en attente de paiement une facture unique sur la page **Facture fournisseur** ou sur la page **Règlement des transactions**.

### <a name="for-a-posted-vendor-invoice"></a>Pour une facture fournisseur validée

Créez ou supprimez une mise en attente de paiement pour une facture fournisseur validée sur la page **Journal des factures**.

### <a name="for-all-vendor-invoices-associated-with-a-purchase-order"></a>Pour toutes les factures fournisseur associées à une commande fournisseur.

Créez ou supprimer une mise en attente de paiement pour toutes les factures fournisseur qui sont associées à une commande fournisseur sur la page **Règlement des transactions**.

## <a name="can-i-settle-an-invoice-that-is-on-hold"></a>Puis-je régler une facture qui est en attente ?
Si vous assumez le même rôle utilisateur que la personne qui a créé la mise en attente, vous pouvez y mettre fin à partir de la page**Règlement des transactions** et régler la facture fournisseur. Lorsque vous créez une mise en attente de paiement, l'option **Blocage de paiement de facture** est automatiquement sélectionnée sous l'onglet **Paiement** de la page **Règlement des transactions**. Cela permet d'empêcher qu'une facture fournisseur ne soit réglée avant la suppression de la mise en attente.




