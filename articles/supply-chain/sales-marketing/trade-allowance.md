---
title: Gestion des reprises
description: Cette rubrique décrit la gestion des reprises pour Dynamics 365 Supply Chain Management.
author: t-benebo
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MCRBrokerClaims, MCRBrokerWriteOffReasonPrompt, MCRRoyaltyVendTable, MCRRoyaltyVendTrans, PdsCustRebateGroup, PdsRebateAgreement, TAMCopyTradePromotions, TAMDeduction, TAMDeductionCreate, TAMDeductionDenyReason, TAMDeductionParmDeny, TAMDeductionParmMassUpdate, TAMDeductionParmMatch, TAMDeductionParmSplit, TAMDeductionParmWriteOff, TAMDeductionType, TAMDeductionWriteOffReason, TAMFundManagement, TAMFundUsage, TAMListPage, TAMMarketingObjective, TAMMerchEventType, TAMOneTimePromotion, TAMPromoCompareGraph, TAMPromoStatistic, TAMPromotionAnalysisSummary, TAMPromotionParameters, TAMPromotionPeriod, TAMTemplateListPage, TAMTradePromotionAnalysis, TAMTradePromotions, TAMWhatIfPromotionAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2018-01-31
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 15c003109814d9b4dc2857910e69754e5927ec11138d215056be64424998bf00
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771273"
---
# <a name="trade-allowance-management"></a>Gestion des reprises

[!include [banner](../includes/banner.md)]

La gestion des reprises aide les sociétés à gérer des programmes de promotion des ventes qui offrent des récompenses monétaires selon le principe de la « rémunération au rendement » aux clients qui atteignent leurs objectifs en termes de volume et de comportement. Les capacités de la fonctionnalité sont conçues pour les sociétés qui sont axées sur les processus complets visant à promouvoir les profits, depuis la budgétisation et l’allocation de fonds de promotion à la création de contrats d’allocation, en passant par la création et le traitement des réclamations, le traitement des paiements et l’analyse de l’efficacité de la promotion.


Cet article donnera un aperçu général de la fonctionnalité Gestion des reprises et permettra de vous familiariser avec l’ensemble spécifique de tâches impliquées dans la gestion d’un programme de promotion des ventes. Plusieurs types d’utilisateurs qui ont des responsabilités opérationnelles et décisionnaires devraient utiliser cette fonctionnalité pour atteindre leurs objectifs respectifs :

- Allocation de fonds discrétionnaires aux comptes sélectionnés et création d’accords de reprise pour les promotions, basés sur les factures rétroactives et les paiements forfaitaires (pour un service convenu)
- Exécution des contrats de promotion négociés par le biais de ventes continues et génération des réclamations de facture rétroactive
- Calcul, approbation et traitement des réclamations générées et transfert à la Comptabilité client en tant que déductions pour le règlement des paiements
- Rapprochement entre le paiement partiel du client et la déduction due
- Suivi de l’utilisation du fonds de promotion, et évaluation de la rentabilité et de l’efficacité du programme

## <a name="audience-and-purpose"></a>Public et objectif

Les informations de ce document sont destinées aux décideurs dans les entreprises, notamment au niveau des postes de responsable des achats, de directeur financier et de responsable comptable, avec les responsabilités suivantes :

- Budgets généraux et allocation de fonds
- Planification et analyse des promotions des ventes
- Gestion du personnel qui traite les réclamations de facture rétroactive, exécute les paiements basés sur des événements de promotion des ventes et règle les paiements partiels et les déductions

Les personnes affectés à ces rôles recherchent des moyens d’atteindre les objectifs suivants :

- Mieux utiliser les fonds de promotion marketing.
- Adapter avec souplesse les différents types de programmes de promotion et de reprises.
- Réduire la charge et les erreurs administratives associées à la surveillance des performances de promotion et au traitement des réclamations.
- Améliorer les prévisions de flux de trésorerie en comptabilisant le futur passif.
- Avoir une base quantifiée pour les négociations en cours et à venir avec les clients sur les promotions.

## <a name="promotional-fund-and-trade-allowance-agreement"></a>Fonds de promotion et accord de reprise

Un accord de reprise est un programme d’incitation dans lequel des récompenses monétaires selon le principe de la rémunération au rendement sont offertes aux clients qui atteignent des objectifs spécifiques en termes de volume et/ou de comportement. Les fonds de promotion sont des dépenses budgétées. Ainsi, les campagnes promotionnelles peuvent être capturées.

### <a name="promotional-fund"></a>Fonds de promotion

Les fonds alloués aux accords de reprise sont enregistrés sur la page **Fonds**. Pour ouvrir la page **Fonds**, sélectionnez **Ventes et marketing** \> **Reprises** \> **Fonds** \> **Fonds**.

![Page Fonds.](./media/trade-allowance-management-funds-page.png "Page Fonds")

Dans la page **Fonds**, vous pouvez afficher les détails des fonds de promotion.

L’organisateur **Général** indique la période de validité du fonds et son montant budgété. Pour que le fonds soit alloué à l’accord de promotion, le champ **Statut** doit avoir la valeur **Approuvé**.

L’organisateur **Clients** affiche la hiérarchie des clients. Pour sélectionner les clients ciblés par le fonds, faites-les glisser pour les déplacer vers la zone **Clients du fonds**. Cet organisateur indique également la répartition du montant total du fonds.

L’organisateur **Articles** indique les articles inclus dans la promotion.

### <a name="trade-allowance-agreement"></a>Accord de reprise

Une fois que la définition du fonds est en place, l’étape suivante de la planification de la promotion consiste à enregistrer les contrats de promotion (qui sont appelés accords de reprise), à allouer des fonds et à définir des objectifs de performances pour chaque événement de promotion des ventes.

Les accords de reprise sont enregistrés sur la page **Accords de reprise**. Pour ouvrir la page **Accords de reprise**, sélectionnez **Ventes et marketing** \> **Reprises** \> **Accords de reprise**.

![Page Accords de reprise.](./media/trade-allowance-management-agreements-page.png "Page Accords de reprise")

#### <a name="header"></a>En-tête

Sélectionnez **En-tête** pour passer à la vue En-tête.

Dans l’organisateur **Général**, les champs **Destination de la commande** et **Origine de la commande** définissent la période de validité de l’accord. Le statut d’approbation **Approbation interne** pour l’accord indique que l’accord n’est pas encore valide et ne peut pas être appliqué pendant le traitement de la commande client.

La section **Analyse** de l’organisateur **Général** contient des champs importants qui définissent les quantités et les coûts utilisés pour l’évaluation de la promotion :

- Le champ **Unités de base** spécifie la quantité de produits qui doivent être vendus aux clients sélectionnés pour que la promotion soit appliquée.
- La valeur **Quantité à expédier calculée** est calculée en fonction de la valeur **Pourcentage de hausse**, qui est une augmentation cible prévue pour cette promotion.
- Le champ **Coût de la reprise** est calculé en fonction des quantités des différents événements dans l’accord de reprise.

Dans l’organisateur **Clients**, dans la liste à gauche, vous pouvez sélectionner et afficher des groupes de clients, qui sont paramétrés comme hiérarchies prédéfinies. Vous pouvez ensuite sélectionner l’ensemble de la hiérarchie ou des comptes spécifiques comme cibles pour l’accord de reprise.

Dans l’organisateur **Articles**, tout comme dans l’organisateur **Articles** de la page **Fonds**, des produits sont ajoutés à l’accord pour associer les ventes à la reprise convenue.

Dans l’organisateur **Fonds**, vous pouvez afficher les fonds de promotion associés à ce contrat. Vous pouvez également afficher la répartition des coûts de l’événement du contrat. Une répartition des coûts de l’événement de 100 % signifie que cette promotion sera financée exclusivement à partir d’un fonds. Sinon, un accord de promotion peut se baser sur plusieurs fonds, et peut utiliser la répartition à pourcentage égal ou différentiel.

#### <a name="lines"></a>Lignes

Ensuite, sélectionnez **Lignes** pour passer à la vue Lignes.

L’onglet **Événements de promotion des ventes** indique les types d’événements couverts par un accord. Il existe trois types : facture rétroactive, montant forfaitaire et hors facture.

Lorsque vous sélectionnez l’événement de promotion des ventes, puis sélectionnez l’onglet **Montants**, les détails de l’événement s’affichent.

![Lignes de l’accord de reprise.](./media/trade-allowance-management-agreements-lines.png "Lignes de l’accord de reprise")

Dans la section **Lignes de reprise**, spécifiez les plages de quantité ou de montant que le client doit atteindre pour les définitions pour obtenir les récompenses.

Dans le cas d’un événement de promotion des ventes du type **Facture rétroactive**, la section supérieure de l’onglet **Montants** définit les règles selon lesquelles la facture rétroactive sera appliquée, générée et payée. Par exemple, les règles peuvent spécifier les conditions suivantes pour la réclamation de facture rétroactive :

- Elle est basée sur la date de création de la commande client (la valeur **Type de date de calcul** est **Créé**).
- Elle est calculée en fonction du montant de la ligne de commande client avant les remises, et non le montant net, qui inclut les remises (la valeur **Provenant de** est **Brut**).
- Elle est basée sur le volume des produits vendus, et non le montant (la valeur **Type de saut de ligne de remise** est **Quantité**).
- Elle est calculée par période d’un mois (la valeur **Cumuler les ventes par** est **Mois**). 
- Elle est réglée en tant que déduction, et non à l’aide de la comptabilité fournisseur (la valeur **Type de paiement** est **Déductions client**).

Dans le cas d’un événement de promotion des ventes du type **Montant forfaitaire**, l’onglet **Montants** affiche la quantité qui sera payée au client sous forme de déduction lorsqu’il atteint des performances spécifiques. Le statut d’approbation **En cours** indique que le montant forfaitaire n’a pas encore été payé.

Pour appliquer l’accord aux commandes client qui répondent aux conditions de l’accord, son statut doit être **Confirmé**. 

## <a name="perform-sales-under-the-planned-merchandising-event-and-generate-bill-back-claims"></a>Réaliser des ventes dans le cadre de l’événement de promotion des ventes prévu et générer les réclamations de facture rétroactive

Lorsque vous créez une commande client dont les lignes répondent aux conditions de l’accord, vous pouvez afficher les informations associées sur la page **Commande client** en sélectionnant **Ligne de commande client** \> **Afficher** \> **Détails de prix**.

Dans la page **Détails de prix**, sous l’organisateur **Remises**, le commis aux ventes peut afficher une facture rétroactive à partir de l’accord de reprise valide (l’ID du programme de remise est affiché) et du montant total appliqué à la ligne. Ce montant est également affiché dans le champ **Montant de la remise** dans la section **Estimation de marge** de la page **Détails de prix**.

Lorsque la facture client est validée, une réclamation de facture rétroactive correspondante est générée pour chaque ligne de facture.

> [!NOTE]
> Pour afficher la page **Détails de prix**, dans la page **Paramètres de la comptabilité client**, sous l’onglet **Prix**, activez la case à cocher **Activer les détails de prix**. I

## <a name="process-claims-and-pass-them-as-deductions-to-ar"></a>Traiter les réclamations et les faire passer comme déductions dans la comptabilité client

Les étapes suivantes du processus de gestion des factures rétroactives consistent à vérifier, calculer et approuver les réclamations, puis à les convertir en déductions.

L’atelier de facturation rétroactive est l’endroit où le propriétaire de l’accord de promotion vérifie et traite régulièrement les réclamations générées. C’est également à cet endroit que l’administrateur de la comptabilité client convertit les réclamations approuvées en déductions ou paiements réguliers, selon le mode de paiement de la réclamation.

Dans la page **Atelier de facturation rétroactive**, vous pouvez vérifier les lignes de réclamation. Si le statut des réclamations est **Pour recalcul**, elles doivent être recalculées pour tout effet cumulatif.

### <a name="recalculate-claims"></a>Recalculer des réclamations

Pour recalculer les réclamations, dans le volet Actions, sélectionnez **Cumuler**. Ensuite, dans la boîte de dialogue **Cumuler des remises**, sélectionnez le client.

À l’issue du recalcul, le programme génère de nouvelles réclamations pour les montants pour ajuster les réclamations d’origine sur le montant de qualification par unité. Une réclamation d’ajustement est générée pour chaque combinaison unique d’un client, d’un article, d’une devise, d’une unité de mesure, de dimensions de stock, de dimensions financières et d’un groupe de taxe. Ces réclamations d’ajustement ont la même référence à la commande client et au numéro de facture que les réclamations ajustées (autrement dit, les réclamations initialement créées à partir du document de vente). Contrairement à la réclamation d’origine, la réclamation d’ajustement ne contient pas de valeurs dans les champs qui décrivent les montants et la quantité de la ligne de commande client initiale.

Une fois le recalcul effectué, le statut des réclamations est remplacé par **Calculé**. Pour approuver les réclamations, dans le volet Actions, sélectionnez **Approuver**.

### <a name="process-claims-and-pass-them-to-ar"></a>Traiter les réclamations et les transférer vers la comptabilité client

Les réclamations sont maintenant prêtes à être traitées dans la comptabilité client. Pour les traiter, dans le volet Actions, sélectionnez **Traiter**. 

Lors du traitement des réclamations, le statut est remplacé par **Marquer** et indique qu’une validation du journal (le journal validé est le journal de régularisation des remises, comme spécifié dans les paramètres de la comptabilité client) a déclenché les événements suivants : 

- Les réclamations ont été transférées vers le solde client temporaire en tant que déductions.
- Le compte de régularisation de remise a été crédité pour représenter le futur passif du client.
- Le compte de frais de remise a été débité pour représenter les coûts engagés dans le cadre de la vente.

Pour terminer le processus, le commis à la comptabilité client doit maintenant gérer les déductions de régularisation en les transférant vers le solde client en tant qu’avoir (passif). 

Pour démarrer la tâche, dans le volet Actions de la page **Client**, sélectionnez **Collecter** \> **Régler les transactions**. Ensuite, dans la page **Régler les transactions**, sélectionnez **Fonctions** \> **Programme de facturation rétroactive**. Cette page de remise affiche toutes les réclamations de facture rétroactive qui ont été précédemment traitées.

Si vous souhaitez créer un avoir, activez la case à cocher **Marquer** pour toutes les lignes, puis sélectionnez **Fonctions** \> **Créer un avoir**.

Lors de la création d’un avoir, un journal est validé. (Le journal validé est le journal de consommation de la comptabilité client, comme spécifié dans les paramètres de la comptabilité client). Par conséquent, le montant (crédit) de passif réel a été déplacé vers le solde client. Financièrement, cette situation implique que les événements suivants se sont produits :

- Le compte débiteur du client a été crédité.
- Le compte de régularisation de remise a été débité.

Pour approuver un événement de promotion des ventes du type **Montant forfaitaire**, sélectionnez l’événement dans la page **Accords de reprise**, puis, sous l’onglet **Montant**, sélectionnez **Approuver**.

## <a name="settle-the-deduction-that-is-due-and-the-customer-short-pay-by-using-the-deduction-workbench"></a>Régler la déduction due et le paiement partiel du client à l’aide de l’atelier de déduction

Souvent, en prévision des facturations rétroactives, les clients choisissent d’effectuer un paiement partiel pour les factures sélectionnées. Pour éviter les problèmes de rapprochement des paiements à l’avenir, le commis à la comptabilité client enregistre ces paiements partiels comme déductions lorsqu’il enregistre les paiements client réels. Ensuite, dans l’atelier de déduction, ces déductions client peuvent facilement être réglées avec les montants de réclamation dûs par la société.

Pour enregistrer le paiement partiel d’un client dans le journal des paiements, sélectionnez **Comptabilité client** \> **Paiements** \> **Journal des paiements**, puis créez un journal des paiements. Ensuite, dans le volet Actions, sélectionnez **Déductions**. Dans la page **Déduction**, vous pouvez créer et suivre le montant qui a été partiellement payé.

Le responsable de collection est maintenant chargé de régler la transaction d’avoir en cours et la transaction de paiement partiel l’une en fonction de l’autre dans l’atelier de déduction.

Pour gérer les déductions, sélectionnez **Ventes et marketing** \> **Reprises** \> **Déductions** \> **Atelier de déduction**. La section supérieure de la page contient des lignes qui représentent les paiements partiels du client. La section inférieure de la page contient les transactions de crédit en cours du client. 

Pour régler la déduction sur la transaction en cours, marquez la ligne de déduction, puis, sous l’onglet Transactions en cours, marquez la ligne. Dans le volet Actions, cliquez sur Tenir à jour > Correspondance.

Le statut des réclamations d’origine est maintenant défini sur **Terminé**.

## <a name="analyze-the-effectiveness-of-the-promotion-and-fund-consumption"></a>Analyser l’efficacité de la promotion et la consommation du fonds

Pour obtenir une vue d’ensemble de l’utilisation du fonds et des statistiques clés du programme, vous pouvez utiliser plusieurs états et vues analytiques disponibles dans le module Gestion des reprises.

Dans la page **Activité de reprise**, l’onglet **Vue d’ensemble** affiche les principaux détails de l’accord de reprise. Les autres onglets contiennent des détails plus spécifiques sur les documents, les paiements et autres événements associés au programme.

L’onglet **Synthèse** affiche la quantité totale de produits vendus dans le cadre de la promotion, le montant des ventes facturé ainsi que les factures rétroactives et les montants forfaitaires payés.

L’onglet **Crédits de facturation rétroactive** contient les détails des différentes factures rétroactives qui ont été créditées au client.

Pour obtenir une vue d’ensemble plus analytique des différentes mesures de performances pour la promotion, vous pouvez utiliser la vue Analyse. Pour accéder à la vue Analyse, cliquez sur **Ventes et marketing** \> **Reprises** \> **Accords de reprise**. Dans le volet Actions, cliquez sur **Analyse**.  

Pour obtenir une vue d’ensemble plus analytique des différentes mesures de performances pour la promotion, vous pouvez utiliser la vue Analyse. Pour accéder à la vue Analyse, cliquez sur **Ventes et marketing** \> **Reprises** \> **Accords de reprise**. Dans le volet Actions, cliquez sur **Analyse**. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]