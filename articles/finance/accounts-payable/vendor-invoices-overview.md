---
title: Vue d’ensemble des factures fournisseur
description: Cette rubrique fournit des informations générales sur les factures fournisseur.
author: abruer
ms.date: 02/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b54a60ac3b1868ea7cc5ed88d5a31203b4bd29d3
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358422"
---
# <a name="vendor-invoices-overview"></a>Vue d’ensemble des factures fournisseur

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Cette rubrique fournit des informations générales sur les factures fournisseur. Les factures fournisseur sont des demandes de paiement pour les biens et services. Les factures fournisseur peuvent représenter une facture pour les services en cours, ou elles peuvent être basées sur des commandes fournisseur pour des articles et services spécifiques.

## <a name="vendor-invoices"></a>Factures fournisseur

Une facture fournisseur basée sur une commande fournisseur est produite lorsque des produits ou des services sont reçus suite à une commande fournisseur passée auprès d’un fournisseur. La facture fournisseur contient un en-tête et une ou plusieurs lignes pour des articles ou services. Une facture fournisseur termine le cycle de la commande fournisseur à la réception des produits et à la facture fournisseur.

Bien que certaines factures fournisseur soient liées à une commande fournisseur, les factures fournisseur peuvent également contenir des lignes qui ne correspondent pas aux lignes de commande fournisseur. Vous pouvez également créer des factures fournisseur qui ne sont associées à aucune commande fournisseur. Ces factures fournisseur peuvent représenter des services en cours, comme une facture de service. Vous n’avez pas à référencer un bon de commande lorsque vous ajoutez un service en cours.

Il existe plusieurs manières d’entrer une facture fournisseur :

- Le registre des factures fournisseur permet d’entrer rapidement les factures qui ne font pas référence à une commande fournisseur, afin de pouvoir provisionner la dépense. À l’aide du journal des approbations de facture fournisseur, vous pouvez sélectionner ces factures et les valider dans le solde fournisseur pour contrepasser la provision.
- Le journal des factures fournisseur vous permet d’entrer rapidement des factures qui ne référencent pas une commande fournisseur, en une seule étape.
- Utilisé avec le regroupement des factures fournisseur, le registre des factures fournisseur vous permet d’entrer rapidement des factures pour provisionner la dépense. Vous pouvez ouvrir les commandes fournisseur associées ultérieurement afin de valider la facture par rapport au compte de dépenses.
- Les pages **Factures fournisseur en cours** et **Factures fournisseur en attente** vous permettent de créer des factures fournisseur à partir de commandes fournisseur confirmées.

La discussion suivante fournit davantage d’informations sur l’utilisation des pages **Factures fournisseur en cours** ou **Factures fournisseur en attente** pour créer une facture fournisseur à partir d’une commande fournisseur.

## <a name="understanding-invoice-line-quantities"></a>Présentation des quantités de ligne de facture

Lorsque vous ouvrez une facture fournisseur à partir d’une commande fournisseur associée, le système crée des lignes de facture à partir de la commande fournisseur. Par défaut, le système tire les quantités de l’accusé de réception de marchandises. Toutefois, vous pouvez utiliser l’un des comportements par défaut suivants :

- **Quantité à recevoir maintenant** – Utilisez cette option pour les expéditions partielles. Le système définit la valeur par défaut dans le champ **Quantité** à partir de la quantité spécifiée dans le champ **Recevoir maintenant** de la commande fournisseur.
- **Quantité commandée** – Utilisez cette option pour les expéditions complètes. Le système définit la valeur par défaut dans le champ **Quantité** à partir de la quantité spécifiée dans le champ **Commandé** de la commande fournisseur.
- **Quantité enregistrée** – Utilisez cette option si l’article requiert un enregistrement, tel que cela est spécifié sur la page **Groupes de modèles d’article**. La valeur par défaut du champ **Quantité** est la quantité physique mise à jour qui a été enregistrée.
- **Quantité de l’accusé de réception de marchandises** – Utilisez cette option si un accusé de réception de marchandises a déjà été reçu pour la commande. La valeur par défaut du champ **Quantité** est tirée de la quantité totale des accusés de réception de marchandises disponibles.
- **Quantité et services enregistrés** – Utilisez cette option si des quantités ont été enregistrées dans les journaux des arrivées pour des articles stockés ou non stockés. Cette option s’applique également aux services, qu’ils soient enregistrés ou non.

Si votre entité juridique utilise le rapprochement de factures, vous pouvez afficher les résultats du rapprochement de quantité dans la colonne **Correspondance de quantités des accusés de réception de marchandises**. Vous pouvez également utiliser le bouton **Détails de rapprochement** sous l’onglet **Revoir** du volet Action pour afficher les résultats du rapprochement de quantité.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Ajout d’une ligne qui ne figurait pas sur la commande fournisseur

Vous pouvez ajouter à la facture fournisseur une ligne qui ne figurait pas sur la commande fournisseur. Vous devez sélectionner un numéro d’article ou une catégorie d’approvisionnement. Vous pouvez ensuite ajouter des quantités, des prix, et des montants à la ligne. La ligne est incluse uniquement dans les stratégies de rapprochement pour les totaux de la facture.

## <a name="submitting-a-vendor-invoice-for-review"></a>Soumission d’une facture fournisseur pour révision

Votre organisation peut utiliser des workflows pour gérer le processus de révision des factures fournisseur. La révision via workflow peut être nécessaire pour l’en-tête de facture, la ligne de facture ou les deux. Les contrôles de workflow s’appliquent à l’en-tête ou à la ligne, selon l’emplacement de la vue lorsque vous sélectionnez le contrôle. À la place du bouton **Valider**, un bouton **Soumettre** s’affiche et permet d’envoyer la facture fournisseur dans le processus de révision.

### <a name="preventing-invoice-from-being-submitted-to-workflow"></a>Empêcher la soumission de la facture au flux de travail 

Voici plusieurs façons d’empêcher une facture d’être soumise à un flux de travail.

- **Le total de la facture et le total enregistré ne sont pas identiques.** La personne qui a soumis la facture recevra une alerte indiquant que les totaux ne sont pas égaux. L’alerte offre la possibilité de corriger les soldes avant de soumettre à nouveau la facture au workflow. Cette fonction est disponible si le paramètre **Interdire la soumission au flux de travail lorsque le total de la facture et le total de la facture enregistrée ne sont pas identiques** sur la page **Gestion des fonctionnalités** est activé. 
- **La facture contient des frais non alloués.** La personne qui a soumis la facture recevra une alerte indiquant que la facture a des frais non attribués afin de pouvoir corriger la facture avant de la soumettre à nouveau au flux de travail. Cette fonction est disponible si le paramètre **Interdire la soumission au flux de travail en cas de charges non attribuées sur une facture fournisseur** de la page **Gestion des fonctionnalités** est activé.
- **La facture contient le même numéro de facture qu’une autre facture validée.** La personne qui a envoyé la facture recevra un message indiquant qu’une facture avec un numéro en double a été trouvée. Le numéro en double peut être corrigé avant d’envoyer à nouveau la facture au flux de travail. Cette alerte s’affiche lorsque le paramètre **Vérifier le numéro de facture utilisé** de la Comptabilité fournisseur est défini sur **Rejeter le doublon**. Cette fonction est disponible si le paramètre **Interdire la soumission au flux de travail lorsque le numéro de facture existe déjà sur une facture validée et lorsque votre système n’est pas configuré pour accepter les numéros de facture en double** sur la page **Gestion des fonctionnalités** est activé.
- **La facture contient une ligne où la quantité de la facture est inférieure à la quantité correspondante de l’accusé de réception de marchandises.** La personne qui envoie la facture ou tente de la publier recevra un message indiquant que les quantités ne sont pas égales. Ce message offre la possibilité de corriger les valeurs avant de renvoyer la facture au flux de travail. Cette fonctionnalité est disponible si le paramètre **Bloquer la publication et l’envoi de factures fournisseur au flux de travail** dans la page **Gestion des fonctionnalités** est activé et le paramètre **Bloquer la publication et l’envoi au flux de travail** dans la page **Paramètres de la comptabilité fournisseur** est activé.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Rapprochement des factures fournisseur avec les accusés de réception de marchandises

Vous pouvez entrer et enregistrer des informations pour les factures fournisseur et vous pouvez mettre en correspondance des lignes de facture avec des lignes d’accusé de réception de marchandises. Vous pouvez également rapprocher des quantités partielles pour une ligne.

Vous pouvez créer une facture fournisseur basée sur les lignes d’accusé de réception de marchandises qui ont été reçues jusqu’à la date actuelle, même si tous les articles d’une commande fournisseur spécifique n’ont pas encore été reçus. Vous pouvez utiliser cette option si, par exemple, un fournisseur envoie une facture par mois pour couvrir toutes les livraisons qu’il a expédiées au cours du mois. Chaque accusé de réception de marchandises représente une livraison partielle ou complète des articles de la commande fournisseur.

Lorsqu’une facture se trouve dans le workflow, l’approbateur peut mettre à jour les quantités afin qu’elles correspondent à la valeur du champ **Quantité de l’accusé de réception de marchandises à mettre en correspondance**. Pour ce faire, sélectionnez la fonctionnalité **Mettre à jour les quantités facturées pour qu’elles correspondent aux quantités de produit reçues dans le workflow** dans l’espace de travail **Gestion des fonctionnalités** et sélectionnez **Activer**. Si un approbateur dans le processus de workflow a supprimé toutes les correspondances de tous les accusés de réception de marchandises de la ligne de facture, elle sera supprimée. Lorsque cette fonctionnalité n’est pas activée, les quantités facturées ne sont pas mises à jour pour les factures dans le workflow.

Lorsque vous validez la facture, la quantité **Solde de la facture** de chaque article est mise à jour avec le total des quantités reçues pour les accusés de réception de marchandises sélectionnés. Si la quantité **Solde de la facture** et la quantité **Livrer quantité restante** pour tous les articles de la commande fournisseur ont la valeur 0 (zéro), le statut de la commande fournisseur passe à **Facturé**. Si la quantité **Solde de la facture** n’a pas la valeur 0 (zéro), le statut de la commande fournisseur reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci.

Cette option suppose qu’au moins un accusé de réception de marchandises a été validé pour la commande fournisseur. La facture fournisseur a pour base ces accusés de réception de marchandises et reflète les quantités de ceux‑ci. Les informations financières pour la facture sont basées sur les informations entrées lors de la validation de la facture.

Pour plus d’informations, voir [Enregistrer la facture fournisseur et la mettre en correspondance avec la quantité reçue](../accounts-payable/tasks/record-vendor-invoice-match-against-received-quantity.md).

## <a name="configure-an-automated-task-for-vendor-invoice-workflow-to-post-the-vendor-invoice-using-a-batch-job"></a>Configurer une tâche automatisée pour le flux de travail de facture fournisseur pour valider la facture fournisseur à l’aide d’un traitement par lots

Vous pouvez ajouter une tâche de validation automatisée au flux de travail de facture fournisseur afin que les factures soient traitées dans un lot. L’enregistrement de factures dans un lot permet au processus de flux de travail de continuer sans avoir à attendre la fin de l’enregistrement, ce qui améliore les performances globales de toutes les tâches soumises au flux de travail.

Pour enregistrer une facture fournisseur dans un lot, sur la page **Gestion des fonctionnalités**, activez le paramètre **Validation des lots de facture fournisseur**. Les flux de travail de facturation fournisseur sont configurés en accédant à **Comptabilité fournisseur > Configuration > Flux de travail de la Comptabilité fournisseur**.

Vous pouvez voir la tâche **Valider la facture fournisseur à l’aide d’un lot** dans l’éditeur de flux de travail, indépendamment du fait que le paramètre de fonctionnalité, **Validation des lots de factures fournisseur**, est activée. Lorsque le paramètre de fonctionnalité n’est pas activé, une facture qui contient le **Valider la facture fournisseur à l’aide d’un traitement par lots** ne sera pas traitée dans le flux de travail tant que le paramètre n’est pas activé. La tâche **Valider la facture fournisseur à l’aide d’un lot** ne doit pas être utilisée dans le même flux de travail que la tâche automatisée **Valider les factures fournisseur**. En outre, la tâche **Valider la facture fournisseur à l’aide d’un lot** doit être le dernier élément de la configuration du flux de travail.

Vous pouvez spécifier le nombre de factures à inclure dans le lot et le nombre d’heures à attendre avant de replanifier un lot, en allant sur **Comptabilité fournisseur > Configuration> Paramètres de comptabilité fournisseur > Facture> Flux de travail de facture**. 

## <a name="working-with-multiple-invoices"></a>Utilisation de plusieurs factures

Vous pouvez utiliser plusieurs factures à la fois et les valider toutes à la fois. Si vous devez créer plusieurs factures, utilisez la page **Factures fournisseur en attente**. Si vous devez valider et imprimer plusieurs factures fournisseur, utilisez le **journal d’approbation des factures**. Si vous utilisez le **journal d’approbation des factures**, au moins un accusé de réception de marchandises doit être validé pour la commande fournisseur, et une facture pour la commande fournisseur doit être validée dans un registre des factures. Les informations financières pour la facture viennent de la facture qui a été validée dans le registre.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Récupération de factures fournisseur en cours d’utilisation

Quand une facture fournisseur est utilisée, elle ne peut pas être modifiée par un autre utilisateur. Toutefois, l’état d’une facture peut parfois indiquer que la facture est en cours d’utilisation, même si elle n’est pas activement modifiée. Par exemple, l’application peut avoir cessé de répondre pendant la modification de la facture, ou un utilisateur peut avoir par inadvertance laissé la facture ouverte dans l’application.

Vous pouvez utiliser la page **Récupérer les factures fournisseur** pour récupérer ou libérer les factures fournisseur qui ont été utilisée pendant plus de quatre heures, afin qu’elles puissent être modifiées. Vous pouvez ouvrir cette page à partir de l’écran **Tâche périodique** ou d’une vignette de l’espace de travail **Saisie de facture fournisseur**. Une fois qu’une facture a été récupérée, elle est disponible à la modification dans la page **Facture fournisseur**.

Vous pouvez accéder à la page **Récupérer les factures fournisseur** uniquement si vous disposez du privilège et du droit de sécurité **Récupérer les factures fournisseur en cours de utilisation**. En outre, le paramètre **Autoriser la récupération des factures fournisseur** de la page **Paramètres de la comptabilité fournisseur** doit être activé.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Réinitialiser le statut de workflow pour les factures fournisseur d’Irrécupérable à Brouillon

Une instance de workflow arrêtée en raison d’une erreur irrécupérable aura le statut de workflow de **Irrécupérable**. Lorsque le statut d’un workflow de facture fournisseur est **Irrécupérable**, vous pouvez le réinitialiser sur **Brouillon** en sélectionnant **Rappeler**. Vous pouvez ensuite modifier la facture fournisseur. Cette fonctionnalité est disponible que si le paramètre **Réinitialiser le statut de workflow pour les factures fournisseur d’Irrécupérable à Brouillon** sur la page **Gestion des fonctionnalités** est activé.

Vous pouvez utiliser la page **Historique du workflow** pour réinitialiser le statut du workflow sur **Brouillon**. Vous pouvez ouvrir cette page à partir de **Facture fournisseur** ou de **Commun > Recherches > Workflow**. Pour réinitialiser le statut du workflow sur **Brouillon**, sélectionnez **Rappeler**. Vous pouvez également réinitialiser le statut du workflow sur Brouillon en sélectionnant l’action **Rappeler** dans la page **Facture fournisseur** ou **Factures fournisseur en attente**. Une fois le statut du workflow réinitialisé sur **Brouillon**, il devient disponible pour modifier sur la page **Facture fournisseur**.

## <a name="viewing-the-invoice-total-on-the-pending-vendor-invoices-page"></a>Affichage du total de la facture sur la page Factures fournisseur en attente

Vous pouvez consulter le total de la facture sur la page **Factures fournisseur en attente** en activant le paramètre **Afficher le total de la facture sur la liste des factures fournisseur en attente** sur la page **Paramètres des comptes fournisseurs**. 

## <a name="vendor-open-transactions-report"></a>État des transactions en cours fournisseur

Le rapport **Transactions ouvertes par le fournisseur** fournit des informations détaillées sur les transactions en cours pour chaque fournisseur à la date que vous spécifiez. Ce rapport est souvent utilisé lors de la procédure d’audit pour vérifier les soldes entre les transactions du livre du fournisseur et les transactions du compte du grand livre.

Pour chaque transaction, l’état comprend les détails suivants :

- Numéro de facture
- Date de la transaction
- N° document
- Montant de la transaction dans la devise de transaction et la devise comptable
- Solde créditeur dans la devise de transaction et la devise comptable
- Solde débiteur dans la devise de transaction et la devise comptable
- Montant du sous-total dans la devise comptable
- Date d’échéance du paiement

### <a name="filter-the-data-on-the-report"></a>Filtrer les données sur l’état

Lorsque vous générez l’état **Transactions ouvertes par le fournisseur**, les paramètres par défaut suivants sont disponibles. Vous pouvez les utiliser pour filtrer les données qui seront incluses dans le rapport.

- **Exclure le règlement futur** – Cochez cette case pour exclure les transactions réglées après la date saisie dans le champ **Transactions ouvertes par**.
- **Transactions ouvertes par** – Saisissez une date pour inclure les transactions ouvertes à cette date. Si vous ne saisissez pas de date, ce champ est défini sur la date maximale. (La date maximale est la dernière date que le système acceptera, le 31 décembre 2154.) Par défaut, la prochaine fois que le rapport sera exécuté, ce champ sera défini comme la dernière date qui y a été entrée.

Vous pouvez utiliser les filtres sous le champ **Enregistrement à inclure** pour limiter davantage les données de transaction incluses dans le rapport.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Paramétrer des stratégies de facture fournisseur](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Données de facture clés dans le système de comptabilité fournisseur à l’aide de la facture fournisseur](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Indexer les données de facturation dans la comptabilité fournisseur à l’aide d’un journal d’approbation](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [Indexer les données de facturation dans la comptabilité fournisseur à l’aide d’un registre de factures](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Enregistrer une facture fournisseur dans le journal des factures](tasks/record-vendor-invoice-invoice-journal.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
