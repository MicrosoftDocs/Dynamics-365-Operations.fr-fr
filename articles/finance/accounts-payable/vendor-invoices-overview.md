---
title: Vue d'ensemble des factures fournisseur
description: Cette rubrique fournit des informations générales sur les factures fournisseur. Les factures fournisseur sont des demandes de paiement pour les biens et services reçus. Les factures fournisseur peuvent représenter une facture pour les services en cours, ou elles peuvent être basées sur des commandes fournisseur pour des articles et services spécifiques.
author: abruer
manager: AnnBe
ms.date: 07/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13971
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b9708c37f10cd08e6b98167fe24d9ae0380c3dac
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772166"
---
# <a name="vendor-invoices-overview"></a>Vue d'ensemble des factures fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations générales sur les factures fournisseur. Les factures fournisseur sont des demandes de paiement pour les biens et services reçus. Les factures fournisseur peuvent représenter une facture pour les services en cours, ou elles peuvent être basées sur des commandes fournisseur pour des articles et services spécifiques.

## <a name="vendor-invoices"></a>Factures fournisseur

Une facture fournisseur basée sur une commande fournisseur est une facture produite lorsque des produits ou des services sont reçus en fonction d'une commande fournisseur placée auprès d'un fournisseur. La facture fournisseur contient un en-tête et une ou plusieurs lignes pour des articles ou services. Une facture fournisseur termine le cycle de la commande fournisseur à la réception des produits et à la facture fournisseur.

Bien que certaines factures fournisseur soient liées à une commande fournisseur, les factures fournisseur peuvent également contenir des lignes qui ne correspondent pas aux lignes de commande fournisseur. Vous pouvez également créer des factures fournisseur qui ne sont associées à aucune commande fournisseur. Ces factures fournisseur peuvent représenter des services en cours, tels qu'une facture de service, et vous n'êtes pas obligé de référencer une commande fournisseur lorsque vous les ajoutez.

Il existe plusieurs manières d'entrer une facture fournisseur :

- Le registre des factures fournisseur permet d'entrer rapidement les factures qui ne font pas référence à une commande fournisseur, afin de pouvoir provisionner la dépense. À l'aide du journal des approbations de facture fournisseur, vous pouvez sélectionner ces factures et les valider dans le solde fournisseur pour contrepasser la provision.
- Le journal des factures fournisseur vous permet d'entrer rapidement des factures qui ne référencent pas une commande fournisseur, en une seule étape.
- Utilisé avec le regroupement des factures fournisseur, le registre des factures fournisseur vous permet d'entrer rapidement des factures pour provisionner la dépense. Vous pouvez ouvrir les commandes fournisseur associées ultérieurement afin de valider la facture par rapport au compte de dépenses.
- Les pages **Factures fournisseur en cours** et **Factures fournisseur en attente** vous permettent de créer des factures fournisseur à partir de commandes fournisseur confirmées.

La discussion suivante fournit davantage d'informations sur l'utilisation des pages **Factures fournisseur en cours** ou **Factures fournisseur en attente** pour créer une facture fournisseur à partir d'une commande fournisseur.

## <a name="understanding-invoice-line-quantities"></a>Présentation des quantités de ligne de facture

Lorsque vous ouvrez une facture fournisseur à partir d'une commande fournisseur associée, des lignes sont créées à partir de la commande fournisseur. Par défaut, les quantités sont tirées de la quantité de l'accusé de réception de marchandises. Toutefois, vous pouvez utiliser l'un des comportements par défaut suivants :

- **Quantité à recevoir maintenant** – Utilisez cette option pour les expéditions partielles. La valeur par défaut dans le champ **Quantité** est tirée de la quantité spécifiée dans le champ **Recevoir maintenant** de la commande fournisseur.
- **Quantité commandée** – Utilisez cette option pour les expéditions complètes. La valeur par défaut dans le champ **Quantité** est tirée de la quantité spécifiée dans le champ **Commandé** de la commande fournisseur.
- **Quantité enregistrée** – Utilisez cette option si l'article requiert un enregistrement, tel que cela est spécifié sur la page **Groupes de modèles d'article**. La valeur par défaut du champ **Quantité** est la quantité physique mise à jour qui a été enregistrée.
- **Quantité de l'accusé de réception de marchandises** – Utilisez cette option si un accusé de réception de marchandises a déjà été reçu pour la commande. La valeur par défaut du champ **Quantité** est tirée de la quantité totale des accusés de réception de marchandises disponibles.
- **Quantité et services enregistrés** – Utilisez cette option si des quantités ont été enregistrées dans les journaux des arrivées pour des articles stockés ou non stockés. Cette option s'applique également aux services, qu'ils soient enregistrés ou non.

Si votre entité juridique utilise le rapprochement de factures, vous pouvez afficher les résultats du rapprochement de quantité dans la colonne **Correspondance de quantités des accusés de réception de marchandises**. Vous pouvez également utiliser le bouton **Détails de rapprochement** sous l'onglet **Revoir** du volet Action pour afficher les résultats du rapprochement de quantité.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Ajout d'une ligne qui ne figurait pas sur la commande fournisseur

Vous pouvez ajouter à la facture fournisseur une ligne qui ne figurait pas sur la commande fournisseur. Vous devez sélectionner un numéro d'article ou une catégorie d'approvisionnement. Vous pouvez ensuite ajouter des quantités, des prix, et des montants à la ligne. La ligne est incluse uniquement dans les stratégies de rapprochement pour les totaux de la facture.

## <a name="submitting-a-vendor-invoice-for-review"></a>Soumission d'une facture fournisseur pour révision

Votre organisation peut utiliser des workflows pour gérer le processus de révision des factures fournisseur. La révision via workflow peut être nécessaire pour l'en-tête de facture, la ligne de facture ou les deux. Les contrôles de workflow s'appliquent à l'en-tête ou à la ligne, selon l'emplacement de la vue lorsque vous sélectionnez le contrôle. À la place du bouton **Valider**, vous verrez un bouton **Soumettre** qui vous permet d'envoyer la facture fournisseur dans le processus de révision.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Rapprochement des factures fournisseur avec les accusés de réception de marchandises

Vous pouvez entrer et enregistrer des informations pour les factures fournisseur et vous pouvez mettre en correspondance des lignes de facture avec des lignes d'accusé de réception de marchandises. Vous pouvez également rapprocher des quantités partielles pour une ligne.

Vous pouvez créer une facture fournisseur basée sur les lignes d'accusé de réception de marchandises qui ont été reçues jusqu'à la date actuelle, même si tous les articles d'une commande fournisseur spécifique n'ont pas encore été reçus. Vous pouvez utiliser cette option si, par exemple, un fournisseur envoie une facture par mois pour couvrir toutes les livraisons qu'il a expédiées au cours du mois. Chaque accusé de réception de marchandises représente une livraison partielle ou complète des articles de la commande fournisseur.

Lorsque vous validez la facture, la quantité **Solde de la facture** de chaque article est mise à jour avec le total des quantités reçues pour les accusés de réception de marchandises sélectionnés. Si la quantité **Solde de la facture** et la quantité **Livrer quantité restante** pour tous les articles de la commande fournisseur ont la valeur 0 (zéro), le statut de la commande fournisseur passe à **Facturé**. Si la quantité **Solde de la facture** n'a pas la valeur 0 (zéro), le statut de la commande fournisseur reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci.

Cette option suppose qu'au moins un accusé de réception de marchandises a été validé pour la commande fournisseur. La facture fournisseur a pour base ces accusés de réception de marchandises et reflète les quantités de ceux‑ci. Les informations financières pour la facture sont basées sur les informations entrées lors de la validation de la facture.

Pour plus d'informations, voir [Enregistrer la facture fournisseur et la mettre en correspondance avec la quantité reçue](../accounts-receivable/tasks/record-vendor-invoice-match-against-received-quantity.md).

## <a name="working-with-multiple-invoices"></a>Utilisation de plusieurs factures

Vous pouvez utiliser plusieurs factures à la fois et les valider toutes à la fois. Si vous devez créer plusieurs factures, utilisez la page **Factures fournisseur en attente**. Si vous devez valider et imprimer plusieurs factures fournisseur, utilisez le journal d'approbation des factures. Si vous utilisez journal d'approbation des factures, au moins un accusé de réception de marchandises doit être validé pour la commande fournisseur, et une facture pour la commande fournisseur doit être validée dans un registre des factures. Les informations financières pour la facture viennent de la facture qui a été validée dans le registre.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Récupération de factures fournisseur en cours d'utilisation

Quand une facture fournisseur est utilisée, elle ne peut pas être modifiée par un autre utilisateur. Toutefois, l'état d'une facture peut parfois indiquer que la facture est en cours d'utilisation, même si elle n'est pas activement modifiée. Par exemple, l'application peut avoir cessé de répondre pendant la modification de la facture, ou un utilisateur peut avoir par inadvertance laissé la facture ouverte dans l'application.

Vous pouvez utiliser la page **Récupérer les factures fournisseur** pour récupérer ou libérer les factures fournisseur qui ont été utilisée pendant plus de quatre heures, afin qu'elles puissent être modifiées. Vous pouvez ouvrir cette page à partir de l'écran **Tâche périodique** ou d'une vignette de l'espace de travail **Saisie de facture fournisseur**. Une fois qu'une facture a été récupérée, elle est disponible à la modification dans la page **Facture fournisseur**.

Vous pouvez accéder à la page **Récupérer les factures fournisseur** uniquement si vous disposez du privilège et du droit de sécurité **Récupérer les factures fournisseur en cours de utilisation**. En outre, le paramètre **Autoriser la récupération des factures fournisseur** de la page **Paramètres de la comptabilité fournisseur** doit être activé.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Réinitialiser le statut de workflow pour les factures fournisseur d'Irrécupérable à Brouillon

Une instance de workflow arrêtée en raison d'une erreur irrécupérable aura le statut de workflow de **Irrécupérable**. Lorsque le statut d'un workflow de facture fournisseur est **Irrécupérable**, vous pouvez le réinitialiser sur **Brouillon** en sélectionnant **Rappeler**. Vous pouvez ensuite modifier la facture fournisseur. Cette fonctionnalité est disponible que si le paramètre **Réinitialiser le statut de workflow pour les factures fournisseur d'Irrécupérable à Brouillon** sur la page **Gestion des fonctionnalités** est activé.

Vous pouvez utiliser la page **Historique du workflow** pour réinitialiser le statut du workflow sur **Brouillon**. Vous pouvez ouvrir cette page à partir de **Facture fournisseur** ou de **Commun > Recherches > Workflow**. Pour réinitialiser le statut du workflow sur **Brouillon**, sélectionnez **Rappeler**. Vous pouvez également réinitialiser le statut du workflow sur Brouillon en sélectionnant l'action **Rappeler** dans la page **Facture fournisseur** ou **Factures fournisseur en attente**. Une fois le statut du workflow réinitialisé sur **Brouillon**, il devient disponible pour modifier sur la page **Facture fournisseur**.



## <a name="additional-resources"></a>Ressources supplémentaires

- [Paramétrer des stratégies de facture fournisseur](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Données de facture clés dans le système de comptabilité fournisseur à l'aide de la facture fournisseur](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un journal d'approbation](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [Indexer les données de facturation dans la comptabilité fournisseur à l'aide d'un registre de factures](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Enregistrer une facture fournisseur dans le journal des factures](tasks/record-vendor-invoice-invoice-journal.md)
