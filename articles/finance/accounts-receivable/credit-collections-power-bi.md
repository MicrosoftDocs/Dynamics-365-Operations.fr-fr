---
title: Contenu Power BI Gestion des crédits et des relances
description: Cette rubrique décrit les données incluses dans le contenu Power BI de gestion des crédits et des relances. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 6d6880e258510a79cdd5937f96af28e5ae148292
ms.sourcegitcommit: 219aa992b1f4c913f26243eeb7e40a383fa1ca67
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4443355"
---
# <a name="credit-and-collections-management-power-bi-content"></a>Contenu Power BI Gestion des crédits et des relances

[!include [banner](../includes/banner.md)]

Cette rubrique décrit les données incluses dans le contenu Power BI de **gestion des crédits et des relances**. Elle explique également comment accéder aux états Power BI, et fournit des informations sur le modèle de données et les entités qui permettent de créer le contenu.

## <a name="overview"></a>Présentation

Le contenu Power BI **Gestion des crédits et des relances** a été créé pour les responsables des crédits et des relances, ainsi que les agents de recouvrement. Il fournit des mesures importantes sur les crédits et relances, comme les ventes quotidiennes restantes, le solde en retard, l’exposition au crédit et les clients qui dépassent leur limite de crédit autorisé. Il utilise des données transactionnelles et fournit une vue agrégée des crédits et relances dans toutes les sociétés. Il fournit également une répartition par société, groupe de clients et client.

Ce contenu Power BI se compose de 10 pages d’état :

- Deux pages de vue d’ensemble (une page pour l’aperçu des crédits et une page pour l’aperçu des relances)
- Huit pages de détails qui fournissent des détails sur les mesures des crédits et des relances qui sont tranchées et découpées en différentes dimensions

Tous les montants sont indiqués dans la devise système. Vous pouvez définir la devise du système dans la page **Paramètres système**.

Par défaut, les données liées aux crédits et aux relances pour la société actuelle s’affichent. Pour afficher les données entre toutes les sociétés, affectez le droit **CustCollectionsBICrossCompany** au rôle.

## <a name="setup-needed-to-view-power-bi-content"></a>Paramétrage requis pour afficher le contenu de Power BI

Le paramétrage suivant doit être réalisé pour que les données s’affichent dans les visuels **Crédits et relances client** de Power BI.

1. Accédez à **Administration système > Paramétrage > Paramètres système** pour définir la **Devise système** et le **Taux de change système**.
2. Accédez à **Comptabilité > Calendriers > Calendriers fiscaux** pour valider les dates du calendrier fiscal affecté à la période active.
3. Accédez à **Comptabilité > Configuration > Comptabilité** et définissez la **Devise comptable** et le **Type de taux de change**.
4. Définissez les taux de change entre les devises de transaction et la devise comptable, la devise comptable et la devise système. Pour ce faire, accédez à **Comptabilité > Devises > Taux de change des devises**.
5. Accédez à **Administration système > Paramétrage > Magasin des entités** pour actualiser la mesure de regroupement **CustCollectionsBIMeasurementsV2**.

>[!NOTE] 
> Les définitions des plages âgées doivent être définies dans **Paramètres de la comptabilité client > Recouvrements > Valeurs par défaut des relances** pour activer les données âgées dans le contenu Power BI.

## <a name="accessing-the-power-bi-content"></a>Accès au contenu Power BI

Le contenu Power BI **Gestion des crédits** et des relances s’affiche dans l’espace de travail **Crédits et relances client**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>États inclus dans le pack de contenu Power BI

Le contenu Power BI **CustCollectionsBICrossCompany** inclut un état composé d’un ensemble de mesures. Ces mesures sont visualisées sous forme de graphiques, vignettes et tableaux. Le tableau suivant donne une vue d’ensemble des visualisations dans le contenu Power BI **CustCollectionsBICrossCompany**.

| Page d’état                 | Visualisation |
|-----------------------------|---------------|
| Vue d’ensemble des relances        | <ul><li>Clients en retard</li><li>Clients dépassant la limite de crédit</li><li>DSO 30 jours</li><li>Dossiers ouverts</li><li>Nombre moyen de jours avant de clôturer le dossier</li><li>Activités en cours</li><li>Nombre moyen de jours avant de clôturer les activités</li><li>Notes d’intérêt en cours</li><li>Ouvrir les lettres de relance</li><li>Client en attente</li><li>Ventes en attente</li><li>Soldes chronologiques</li><li>Montants de statut des relances</li><li>Montants de code des relances</li><li>Motif d’annulation</li><li>Solde dû par région</li><li>Paiements attendus</li></ul> |
| Vue d’ensemble de crédit             | <ul><li>Clients en retard</li><li>Limite de crédit et solde dû</li><li>Clients dépassant la grille limite de crédit</li><li>Clients dépassant la limite de crédit par société</li><li>Crédit utilisé et limite de crédit total</li><li>Limite de crédit et crédit utilisé par région</li><li>Clients par degré de solvabilité</li></ul> |
| Limite de crédit                | <ul><li>Limite de crédit</li><li>Détails relatifs à la limite de crédit</li><li>Limite de crédit par client</li><li>Limite de crédit par groupe de clients</li><li>Limite de crédit par degré de solvabilité par société</li><li>Limite de crédit et crédit utilisé par région</li></ul> |
| Clients dépassant la limite de crédit | <ul><li>Clients dépassant la limite de crédit</li><li>Détails sur les clients dépassant la limite de crédit</li><li>Clients dépassant la limite de crédit par société</li><li>Client dépassant la limite de crédit par groupe de clients</li><li>Clients dépassant la limite de crédit par région</li></ul> |
| Clients en retard          | <ul><li>Clients en retard</li><li>Détails sur les factures client en retard</li><li>Retard client par société</li><li>Client en retard par groupe de clients</li><li>Client en retard par région</li></ul> |
| Soldes chronologiques               | <ul><li>Soldes chronologiques</li><li>Détails relatifs aux soldes échus</li><li>Soldes chronologiques par société</li><li>Soldes chronologiques par groupe de clients</li></ul> |
| Paiements attendus           | <ul><li>Paiements attendus</li><li>Détails sur les paiements attendus</li><li>Paiements attendus par société</li><li>Paiements attendus par groupe de clients</li><li>Paiements attendus par région</li></ul> |
| Annulations                  | <ul><li>Annulations par région</li><li>Détails sur les annulations</li><li>Annulations par compte principal</li><li>Annulations par société</li><li>Annulations par groupe de clients</li><li>Annulations par région</li></ul> |
| Statut des recouvrements          | <ul><li>Litigieux</li><li>Promesse de paiement interrompue</li><li>Promesse de payer</li><li>Détails sur le statut des relances</li><li>Montants de statut des relances</li><li>Dossiers ouverts</li><li>Activités en cours</li></ul> |
| Lettres de relance         | <ul><li>Montants de code relance</li><li>Détails sur les montants de code relance</li><li>Montants de lettres de relance par société</li><li>Montant de lettres de relance par groupe de clients</li><li>Montant de lettres de relance par région</li></ul> |

Les graphiques et les vignettes sur tous ces états peuvent être filtrés et épinglés au tableau de bord. Pour savoir comment filtrer et épingler dans Power BI, voir [Créer et configurer un tableau de bord](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Vous pouvez également utiliser la fonctionnalité Exporter les données sous-jacentes pour exporter les données sous-jacentes qui sont résumées dans une visualisation.
