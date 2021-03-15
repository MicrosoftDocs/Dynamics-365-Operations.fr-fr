---
title: Remises fournisseur
description: Cette rubrique fournit une vue d'ensemble des tâches les plus courantes que vous souhaitez peut-être effectuer lorsque vous utilisez des remises fournisseur. Les remises fournisseur aident au mieux les sociétés à gérer leurs programmes de remise fournisseur en automatisant les tâches nécessaires afin d'administrer, de suivre et de réclamer les remises dues.
author: omulvad
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: 46d6beb287f7d034c6fde09999f7854695a4987c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966653"
---
# <a name="vendor-rebates"></a>Remises fournisseur

[!include [banner](../includes/banner.md)]

Les remises fournisseur aident au mieux les sociétés à gérer leurs programmes de remise fournisseur en automatisant les tâches nécessaires afin d'administrer, de suivre et de réclamer les remises dues.

Cette rubrique fournit une vue d'ensemble des tâches les plus courantes que vous souhaitez peut-être effectuer lorsque vous utilisez des remises fournisseur. La vue d'ensemble couvre les tâches suivantes :

- Détails de révision d'un accord de remise.
- Identifier les commandes concernées par les remises et générer des réclamations de remise.
- Réviser et approuver les réclamations.

## <a name="audience-and-purpose"></a>Public et objectif

Les informations de cette rubrique sont destinées aux décideurs dans les entreprises, notamment au niveau des postes de responsable des achats, de directeur financier et de responsable comptable, avec les responsabilités suivantes :

- Négocier le prix fournisseur, la remise et les accords de remise.
- Gérer le personnel qui traite les réclamations de remise et collecte les paiements.
- Commander du stock au meilleur prix.

Les personnes qui occupent ces postes recherchent des moyens d'atteindre divers objectifs. Voici quelques exemples :

- Adapter avec souplesse les différents types de programmes de promotion et conditions de remise fournisseur.
- Réduire la charge et les erreurs administratives associées à la surveillance des performances de promotion et au traitement des réclamations.
- Améliorer les prévisions de flux de trésorerie en comptabilisant les futures créances.
- Avoir une base quantifiée pour les négociations en cours et à venir avec les fournisseurs sur les remises.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>Détails de révision d'un accord de remise fournisseur

Un accord de remise fournisseur est un enregistrement d'un contrat avec un fournisseur qui spécifie les conditions négociées sous lesquelles la société bénéficie d'une récompense monétaire avec pour contrepartie d'accomplir les cibles d'achat prédéfinies. Les accords de remise fournisseur sont enregistrés sur la page **Accords de remise**.

Pour ouvrir la page **Accords de remise fournisseur**, sélectionnez **Approvisionnements** &gt; **Remises fournisseur** &gt; **Accords de remise**.

![Contrat d'achat](media/purchase-agreement.PNG)

Sur la page **Accords de remise fournisseur**, vous pouvez afficher les détails des conditions négociées d'un accord fournisseur.

L'en-tête de l'accord spécifie les conditions générales qui qualifient une société pour les remises. En effet, les informations d'en-tête indiquent qu'un fournisseur octroie une remise lorsqu'un produit spécifique est acheté dans une quantité spécifique. Dans l'en-tête, vous devez également spécifier l'option de remise de l'unité de mesure et le type de date de calcul.

- Sur l'onglet **Vue d'ensemble**, si vous avez des lignes avec **Code de l'article** défini sur *table* pour spécifier l'article, alors l'accord est pour cet article spécifique. Si vous avez des lignes avec **Code de l'article** défini sur *Groupe* ou *Tous* pour spécifier les articles, l'accord de remise fournisseur sera traité individuellement par article éligible pour le code article, et non pour tous les articles éligibles pour le code article.

- Dans l'onglet **Général**, dans le champ **Option de remise de l'unité de mesure**, vous pouvez définir si une unité de mesure doit être une condition pour que la ligne de commande fournisseur soit qualifiée pour une réclamation de remise.

    - **Convertir** – Une ligne de commande fournisseur bénéficie d'une remise fournisseur par accord de remise. Vous recevrez une remise indépendamment de l'unité de mesure appliquée à la ligne.
    - **Correspondance parfaite** – Pour bénéficier d'une remise, une ligne d'achat doit avoir la même unité de mesure que celle spécifiée dans l'accord.

- Dans l'onglet **Général**, dans le champ **Type de date de calcul**, sélectionnez la date utilisée pour déterminer si l'achat se produit dans la période de validité de l'accord de remise.

    - **Créé(e)** – Correspond à la date de création de la commande fournisseur.
    - **Livraison demandée** – Correspond à la date de livraison demandée.

Dans les lignes d'accord, vous pouvez spécifier l'accord de remise fournisseur en détail.

- Dans le champ **Cumuler les achats par**, vous pouvez définir le calcul de la réclamation de remise. Le montant peut être défini en fonction d'une période (semaine, mois, exercice ou période personnalisée). La valeur **Facture** indique qu'une réclamation de remise est déterminée à chaque fois qu'une ligne de commande fournisseur est facturée.
- Dans le champ **Provenant de**, vous pouvez spécifier la base du calcul de la remise.

    - **Brut** – La remise est calculée en fonction du prix brut de l'article.
    - **Net** – La remise est calculée en fonction du prix net de l'article (autrement dit, le prix après application d'autres remises).

- Les champs **Compte de régularisation du programme de remise** et **Compte de dépenses du programme de remise** spécifient les numéros de compte qui reçoivent les montants de régularisation de remise au stade intermédiaire entre l'approbation et le traitement.
- Lorsque l'option **Approbation obligatoire** est définie sur **Oui**, la réclamation de remise doit être approuvée pour pouvoir être provisionnée ou payée.
- Le champ **Type de saut de ligne de remise** indique la base de calcul des remises.

    - **Quantité** – Les remises sont basées sur un volume.
    - **Montant** – Les remises sont basées sur un montant.

- Dans l'organisateur **Lignes**, vous pouvez voir comment différents niveaux de quantité peuvent être paramétrés pour accorder des remises. Par exemple, dans l'illustration précédente, les champs **Valeur de début** et **Valeur de fin** indiquent qu'une quantité de produits entre 10 et 19 unités permet d'obtenir une remise de 15 EUR par unité.

    > [!NOTE]
    > La **Valeur de début** est inclusive, tandis que la valeur **Valeur de fin** est exclusive. Par exemple, le champ **Type de saut de ligne de remise** est défini sur **Quantité**, puis entrez **1** dans le champ **Valeur de début** et **3** dans le champ **Valeur de fin**. Dans ce cas, le montant de remise s'applique lorsque vous achetez un ou deux articles, mais pas lorsque vous achetez trois articles.

- Dans le champ **Statut de l'approbation du workflow**, la valeur **Approbation** indique que l'accord peut être appliqué aux commandes fournisseur qui répondent aux conditions de l'accord.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>Identifier les commandes concernées par les remises et générer des réclamations de remise

Lorsque des commandes fournisseur sont passées par un fournisseur avec lequel la société possède un accord de remise, le programme identifie les futurs paiements de crédit fournisseur. Si les commandes fournisseur peuvent bénéficier d'une remise, une réclamation de remise est générée pour chaque ligne de commande dès qu'une facture d'achat est validée. Ce processus est automatique. Ensuite, vous pouvez examiner les remises prévues et voir l'impact de ces remises sur le coût et la marge bénéficiaire du produit.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>Afficher les détails des remises appliquées à une ligne de commande fournisseur par accord de remise fournisseur

1. Sur la page **Commande fournisseur**, sélectionnez une ligne de commande, puis sélectionnez &gt; **Ligne de commande fournisseur** **Affichage** &gt; **Détails de prix**.
2. Sur la page **Détails de prix**, sélectionnez l'organisateur **Remises**.

Les informations de remise s'affichent également dans le champ **Remise fournisseur** dans la section **Estimation de marge** de la page **Détails de prix**.

> [!NOTE]
> Sur la page **Paramètres d'approvisionnement**, sous l'onglet **Prix**, vérifiez que l'option **Activer les détails de prix** est définie sur **Oui**. Si l'option est définie sur **Non**, vous ne pourrez pas afficher les remises.

## <a name="review-and-approve-claims"></a>Réviser et approuver les réclamations

Les réclamations de remise générées représentent les futurs paiements qui peuvent être attendus du fournisseur. Avant qu'un avoir ne soit émis au fournisseur, le propriétaire de l'accord veut généralement examiner les réclamations et les approuver. Toutefois, notez que le statut d'une réclamation détermine si la réclamation est prête à passer par le processus d'approbation.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>Statut des réclamations et effet sur le processus d'approbation

Lorsqu'une réclamation est générée, son statut est défini sur **À calculer** si la remise est accordée sur une base cumulative ou **Calculé** si la remise est octroyée par facture. Si le statut d'une réclamation est **À calculer**, la réclamation doit passer par un processus de calcul qui est assuré par la fonction Cumuler. Seules les réclamations qui ont un statut **Calculé** peuvent être incluses dans le processus d'approbation.

> [!NOTE]
> Si l'option **Approbation obligatoire** sur un accord de remise du fournisseur est définie sur **Non**, toutes les réclamations générées auront un statut **Approuvé**. L'approbation est obligatoire pour les réclamations qui sont octroyées sur une base cumulative.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>Approuver les réclamations et afficher les validations et détails de facture

Lorsque des réclamations ont été approuvées, elles peuvent être traitées par le service Comptabilité fournisseur. Un avoir (facture fournisseur) pour le montant de réclamation de remise est généré automatiquement. Le crédit peut ensuite être ajouté au solde fournisseur, et l'équipe du service Comptabilité fournisseur peut l'inclure dans le processus de règlement habituel.

1. Sélectionnez **Approvisionnements** &gt; **Remises fournisseur** &gt; **Réclamations de remise** pour ouvrir une réclamation de remise.
2. Clôturez la réclamation de remise.
3. Cochez la réclamation, puis dans le volet Actions, sélectionnez **Approuver**.
4. Sur la page de demande, dans le champ **Fournisseur**, sélectionnez le fournisseur pour lequel vous êtes autorisé à recevoir une remise, puis sélectionnez **OK**.

    Un journal de régularisation des remises est validé pour le montant de réclamation. Cette validation débite le compte devant recevoir les remises fournisseur provisionnées pour le crédit fournisseur prévu et crédite le compte devant recevoir les remises fournisseur provisionnées provisoires pour le gain attendu.

    ![Message](media/message.png)

5. Dans la liste des remises, sélectionnez la ligne, puis dans le volet Actions, sélectionnez **Transactions de remise** pour voir et accéder au numéro de lot de journal correspondant à cette validation de régularisation des remises.

    Pour déplacer les réclamations vers le processus du service Comptabilité fournisseur habituel, l'agent de ce service doit désormais exécuter le traitement de la réclamation de remise lors de l'exécution de la fonction de traitement.

6. Dans le volet Actions, sélectionnez **Processus**, puis sélectionnez **Filtrer**. Dans le champ **Critères** pour le champ **Compte fournisseur**, sélectionnez le fournisseur pour lequel traiter les réclamations de remise, sélectionnez les autres filtres appropriés, puis sélectionnez **OK**.

    Les barres de message et le fait que le statut passe à **Terminé** indiquent que les événements suivants se sont produits :

    - Une validation du journal de régularisation de remise a contrepassé les montants intermédiaires précédents sur les comptes des ventes et des dépenses de régularisation.
    - Une facture fournisseur (avoir) pour le montant de la remise a été créée.

        > [!NOTE]
        > Le paramètre de l'option **Validation de facture manuelle** dans l'onglet **Programme de la remise** de la page **Paramètres d'approvisionnement** détermine si une facture fournisseur est validée manuellement ou automatiquement dans le cadre du traitement de la réclamation.

    - Lorsque la facture fournisseur est validée, automatiquement ou manuellement, le compte Achats du fournisseur est débité, et le compte Remises et reprises est crédité.

        > [!NOTE] 
        > Le numéro du compte Remises et reprises est spécifié pour la catégorie d'approvisionnement utilisée sur la ligne de facture d'achat pour la remise. La catégorie d'approvisionnement, elle-même, est définie sur l'onglet **Programme de la remise** de la page **Paramètres d'approvisionnement**.

7. Dans la liste des remises, sélectionnez la ligne, puis dans le volet Actions, sélectionnez **Transactions de remise** pour voir et accéder au numéro de lot de journal correspondant à cette validation de régularisation des remises, et également le numéro de la facture fournisseur.
8. Sélectionnez la ligne pour la transaction de facture fournisseur, puis, dans le volet Actions, sélectionnez **Facture fournisseur**. Si la facture fournisseur a été validée, vous verrez le journal des factures. Sinon, vous consulterez la facture fournisseur sous la forme d'une facture fournisseur en attente qui requiert une validation manuelle.

    La ligne de facture indique les détails de la facture fournisseur pour la catégorie d'approvisionnement **Commissions et remises**.

9. Sur la page **Tous les fournisseurs**, sélectionnez le fournisseur qui vous émet une remise, puis dans le volet Actions, sélectionnez **Transactions**. Recherchez la ligne de la facture. Le montant de la remise est désormais ajouté au solde fournisseur.

## <a name="summary"></a>Synthèse

Le processus de gestion des remises fournisseur implique plusieurs tâches de suivi manuelles qui sont souvent pénibles. En automatisant ces tâches, la fonctionnalité de gestion des remises fournisseur peut vous aider à effectuer les processus suivants :

- Génération de réclamations de remise précises
- Accumulation de la créance et du gain intermédiaire attendus dans la comptabilité
- Mise à jour du solde fournisseur et du compte de résultat avec la réduction due


[!INCLUDE[footer-include](../../includes/footer-banner.md)]