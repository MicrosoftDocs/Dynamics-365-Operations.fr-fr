---
title: "Contenu Power BI pour la gestion des crédits et des relances"
description: "Cette rubrique décrit les données incluses dans le contenu Power BI de gestion des crédits et des relances. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations. Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 7aec3d81fca86abdab4f5fcee54f832f917ffe92
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="credit-and-collections-management-power-bi-content"></a>Contenu Power BI pour la gestion des crédits et des relances

Cette rubrique décrit les données incluses dans le contenu Power BI **Gestion des crédits et des relances**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Vue d'ensemble

Le contenu Power BI **Gestion des crédits et des relances** a été créé pour les responsables des crédits et des relances, ainsi que les agents de recouvrement. Il fournit des mesures importantes sur les crédits et relances, comme les ventes quotidiennes restantes, le solde en retard, l'exposition au crédit et les clients qui dépassent leur limite de crédit autorisé. Il utilise des données transactionnelles et fournit une vue agrégée des crédits et relances dans toutes les sociétés. Il fournit également une répartition par société, groupe de clients et client.

Ce contenu Power BI se compose de 10 pages d'état :

- Deux pages de vue d'ensemble (une page pour l'aperçu des crédits et une page pour l'aperçu des relances)
- Huit pages de détails qui fournissent des détails sur les mesures des crédits et des relances qui sont tranchées et découpées en différentes dimensions

Tous les montants sont indiqués dans la devise système. Vous pouvez définir la devise du système dans la page **Paramètres système**.

Par défaut, les données liées aux crédits et aux relances pour la société actuelle s'affichent. Pour afficher les données entre toutes les sociétés, affectez le droit **CustCollectionsBICrossCompany** au rôle.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI
Si vous utilisez Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (Juillet 2017), le contenu Power BI **Gestion des crédits et des relances** s'affiche dans l'espace de travail **Crédits et relances client**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le contenu Power BI

Le contenu Power BI **CustCollectionsBICrossCompany** inclut un état composé d'un ensemble de mesures. Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux. Le tableau suivant donne une vue d'ensemble des visualisations dans le contenu Power BI **CustCollectionsBICrossCompany**.

| Page d'état                 | Visualisation |
|-----------------------------|---------------|
| Vue d'ensemble des relances        | <ul><li>Clients en retard</li><li>Clients dépassant la limite de crédit</li><li>DSO 30 jours</li><li>Dossiers ouverts</li><li>Nombre moyen de jours avant de clôturer le dossier</li><li>Activités en cours</li><li>Nombre moyen de jours avant de clôturer les activités</li><li>Notes d'intérêt en cours</li><li>Ouvrir les lettres de relance</li><li>Client en attente</li><li>Ventes en attente</li><li>Soldes chronologiques</li><li>Montants de statut des relances</li><li>Montants de code des relances</li><li>Motif d'annulation</li><li>Solde dû par région</li><li>Paiements attendus</li></ul> |
| Vue d'ensemble de crédit             | <ul><li>Clients en retard</li><li>Limite de crédit et solde dû</li><li>Clients dépassant la grille limite de crédit</li><li>Clients dépassant la limite de crédit par société</li><li>Crédit utilisé et limite de crédit total</li><li>Limite de crédit et crédit utilisé par région</li><li>Clients par degré de solvabilité</li></ul> |
| Limite de crédit                | <ul><li>Limite de crédit</li><li>Détails relatifs à la limite de crédit</li><li>Limite de crédit par client</li><li>Limite de crédit par groupe de clients</li><li>Limite de crédit par degré de solvabilité par société</li><li>Limite de crédit et crédit utilisé par région</li></ul> |
| Clients dépassant la limite de crédit | <ul><li>Clients dépassant la limite de crédit</li><li>Détails sur les clients dépassant la limite de crédit</li><li>Clients dépassant la limite de crédit par société</li><li>Client dépassant la limite de crédit par groupe de clients</li><li>Clients dépassant la limite de crédit par région</li></ul> |
| Clients en retard          | <ul><li>Clients en retard</li><li>Détails sur les factures client en retard</li><li>Retard client par société</li><li>Client en retard par groupe de clients</li><li>Client en retard par région</li></ul> |
| Soldes chronologiques               | <ul><li>Soldes chronologiques</li><li>Détails relatifs aux soldes échus</li><li>Soldes chronologiques par société</li><li>Soldes chronologiques par groupe de clients</li></ul> |
| Paiements attendus           | <ul><li>Paiements attendus</li><li>Détails sur les paiements attendus</li><li>Paiements attendus par société</li><li>Paiements attendus par groupe de clients</li><li>Paiements attendus par région</li></ul> |
| Annulations                  | <ul><li>Annulations par région</li><li>Détails sur les annulations</li><li>Annulations par compte principal</li><li>Annulations par société</li><li>Annulations par groupe de clients</li><li>Annulations par région</li></ul> |
| Statut des recouvrements          | <ul><li>Litigieux</li><li>Promesse de paiement interrompue</li><li>Promesse de payer</li><li>Détails sur le statut des relances</li><li>Montants de statut des relances</li><li>Dossiers ouverts</li><li>Activités en cours</li></ul> |
| Lettres de relance         | <ul><li>Montants de code relance</li><li>Détails sur les montants de code relance</li><li>Montants de lettres de relance par société</li><li>Montant de lettres de relance par groupe de clients</li><li>Montant de lettres de relance par région</li></ul> |

Les graphiques et les vignettes sur tous ces états peuvent être filtrés et épinglés au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Vous pouvez également utiliser la fonctionnalité Exporter les données sous-jacentes pour exporter les données sous-jacentes qui sont résumées dans une visualisation.

## <a name="extending-the-power-bi-content"></a>Extension du contenu Power BI
Grâce aux packs de contenu disponibles dans Microsoft Dynamics Lifecycle Services (LCS), vous pouvez fournir une analyse approfondie aux personnes qui ne se connectent pas à Finance and Operations. Vous pouvez modifier ces packs de contenu pour qu'ils permettent d'inclure d'autres rapports ou visuels, et de publier les packs de contenu via votre locataire Power BI.com pour analyse.

Le contenu Power BI **Gestion des crédits et des relances** se trouve dans la bibliothèque des actifs partagés dans LCS. Pour savoir comment télécharger le contenu et l'implémenter dans votre organisation, voir [Contenu Power BI dans LCS de Microsoft et de vos partenaires](../../dev-itpro/analytics/power-bi-content-microsoft-partners.md). Pour visionner une démonstration sur l'implémentation du contenu Power BI, voir la présentation Office Mix [Contenu Power BI de Microsoft et de vos partenaires dans Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office Mix.

Veillez à télécharger le contenu Power BI **Gestion des crédits et des relances** qui s'applique à la version de Finance and Operations que vous utilisez.

## <a name="understanding-the-data-model-and-entities"></a>Compréhension du modèle de données et des entités

Les données suivantes sont utilisées pour remplir les pages d'état dans le contenu Power BI **Gestion des crédits et des relances**. Ces données sont représentées sous la forme de mesures globales indexées dans le magasin des entités. Le magasin des entités est une base de données Microsoft SQL Server optimisée pour les analyses. Pour plus d'informations, voir [Vue d'ensemble de l'intégration de Power BI au magasin d'entité](../../dev-itpro/analytics/power-bi-integration-entity-store.md)

| Entité                                      | Mesures globales clés           | Source de données                                 | Champ                                                      | Description |
|---------------------------------------------|--------------------------------------|---------------------------------------------|------------------------------------------------------------|-------------|
| CustCollectionsBIActivitiesAverageCloseTime | NumOfActivities, AveragecClosedTime  | smmActivities                               | AverageOfChildren(AverageClosedTime) Count(ActivityNumber) | Le nombre d'activités fermées et le temps moyen pour fermer ces activités. |
| CustCollectionsBIActivitiesOpen             | ActivityNumber                       | smmActivities                               | Count(ActivityNumber)                                      | Le nombre d'activités en cours. |
| CustCollectionsBIAgedBalances               | AgedBalances                         | CustCollectionsBIAgedBalancesView           | Sum(SystemCurrencyBalance)                                 | Somme des soldes chronologiques. |
| CustCollectionsBIBalancesDue                | SystemCurrencyAmount                 | CustCollectionsBIBalanceDueView             | Sum(SystemCurrencyAmount)                                  | Montants en retard. |
| CustCollectionsBICaseAverageCloseTIme       | NumOfCases, CaseAverageClosedTime    | CustCollectionsCaseDetail                   | AverageOfChildren(CaseAverageClosedTime) Count(NumOfCases) | Le nombre de dossiers clôturés et le temps moyen pour fermer ces dossiers. |
| CustCollectionsBICasesOpen                  | CaseId                               | CustCollectionsCaseDetail                   | Count(CaseId)                                              | Le nombre de dossiers en cours. |
| CustCollectionsBICollectionLetter           | CollectionLetterNum                  | CustCollectionLetterJour                    | Count(CollectionLetterNum)                                 | Nombre de lettres de relances en cours. |
| CustCollectionsBICollectionLetterAmount     | CollectionLetterAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Solde des lettres de relance validées. |
| CustCollectionsBICollectionStatus           | CollectionStatusAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Solde des transactions avec le statut de relance. |
| CustCollectionsBICredit                     | CreditExposed, AmountOverCreditLimit | CustCollectionsBICreditView                 | Sum(CreditExposed), Sum(AmountOverCreditLimit)             | Somme de l'exposition au crédit et montants que les clients dépassent par rapport à leur limite de crédit autorisé. |
| CustCollectionsBICustOnHold                 | Bloqué                              | CustCollectionsBICustTable                  | Count(Blocked)                                             | Nombre de clients qui sont en attente. |
| CustCollectionsBIDSO                        | DSO30                                | CustCollectionsBIDSOView                    | AverageOfChildren(DSO30)                                   | Ventes quotidiennes restantes pendant 30 jours. |
| CustCollectionsBIExpectedPayment            | ExpectedPayment                      | CustCollectionsBIExpectedPaymentView        | Sum(SystemCurrencyAmounts)                                 | Somme des paiements attendus dans l'année suivante. |
| CustCollectionsBIInterestNote               | InterestNote                         | CustInterestJour                            | Count(InterestNote)                                        | Nombre de notes d'intérêt qui ont été créées. |
| CustCollectionsBISalesOnHold                | SalesId                              | SalesTable                                  | Count(SalesId)                                             | Nombre total de commandes client qui sont en attente. |
| CustCollectionsBIWriteOff                   | WriteOffAmount                       | CustCollectionsBIWriteOffView               | Sum(SystemCurrencyAmount)                                  | Somme des transactions annulées. |

