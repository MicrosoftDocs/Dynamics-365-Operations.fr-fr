---
title: Réservations budgétaires générales
description: Cette rubrique fournit des informations sur les réservations budgétaires générales pour le secteur public.
author: TaylorVH
ms.date: 08/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetReservation_PSN
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: fad1bb06063ac8fa04b93fb36e2f157f0d1d30a7
ms.sourcegitcommit: 81bc42551e6c9af6ad38908afb606ee1f8d3c44b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2021
ms.locfileid: "7473393"
---
# <a name="general-budget-reservations"></a>Réservations budgétaires générales

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Une *réservation budgétaire générale* est un document qui est parfois également appelé un *engagement*. Les entités du secteur public utilisent souvent ce document pour répartir ou réserver des fonds budgétés afin qu’ils soient disponibles pour d’autres fins. Généralement, ces réservations sont effectuées avant que des fournisseurs aient été sélectionnés pour l’achat. En utilisant les réservations budgétaires générales, une organisation peut explicitement suivre les dépenses prévues à des fins de gestion et de génération d’états. Chaque demande d’achat, commande fournisseur ou facture fournisseur générée peut être associée à au moins une réservation budgétaire générale.

Les réservations budgétaires générales ne sont disponibles que si les conditions suivantes sont remplies :

- Vous avez la version 8.1 ou ultérieure.
- Les clés de configuration **Secteur public**, **Processus d’engagement** et **Processus d’engagement préalable** sont activées.
- Vous utilisez des définitions de validation. (Toutefois, vous n’avez pas besoin d’utiliser des définitions de validation si vous n’activez pas la comptabilité d’engagements.)
- La configuration du contrôle budgétaire est activée et configurée, et le contrôle budgétaire est activé.

Les réservations budgétaires générales contiennent des lignes qui fournissent des détails sur l’objectif de la réservation et les fonds réservés prévus. Ces détails incluent les dates de début et de fin de la réservation. Il est possible d’ajouter, de modifier et de supprimer des lignes. Vous pouvez également spécifier plusieurs détails, tels que l’article demandé, la devise, le prix unitaire, la quantité et le montant total. Les réservations budgétaires générales sont conçues pour être utilisées par les entités du secteur public.

Les entités du secteur privé utilisent l’expression *réservation budgétaire* pour parler d’engagements ou d’engagements préalables. Toutefois, contrairement aux réservations budgétaires générales, ces réservations budgétaires ne sont pas des documents.

Vous pouvez créer différents types de réservation budgétaire générale pour spécifier plusieurs caractéristiques et exigences, selon vos besoins d’achat. Les caractéristiques incluent le workflow utilisé pour la réservation, et les valeurs par défaut. Par exemple, vous pouvez créer trois types de réservations. Vous utilisez un type pour les demandes d’achat, un autre type pour les commandes fournisseur, et encore un autre type pour les factures fournisseur.

Dans la réservation budgétaire générale, vous pouvez également afficher les répartitions comptables et les lignes du journal de comptabilité auxiliaire pour la transaction.

> [!NOTE]
> Les comptes généraux utilisés sur les réservations budgétaires générales doivent être inclus dans le contrôle budgétaire. Si ces comptes ne sont pas inclus dans le contrôle budgétaire, ce qui suit se produira. 
>- La réservation budgétaire générale et ses documents de consommation ne seront ni grevés ni pré-grevés. 
>- Les opérations de report ne créeront pas d'écritures dans le registre budgétaire. 
>- L'annulation et la finalisation des réservations budgétaires générales ne réduiront pas le report de budget.
>- Les comptes généraux ne seront pas inclus dans l'analyse budgétaire ni les études statistiques du contrôle budgétaire.

Si vous utilisez la comptabilité de projet, vous pouvez activer le suivi des coûts engagés pour les réservations budgétaires générales.

Vous pouvez reporter les réservations budgétaires générales d’un exercice au suivant. Vous pouvez également clôturer ou finaliser une réservation budgétaire générale terminée ou expirée à la fin de l’exercice.

Une réservation budgétaire générale est exonérée différemment, en fonction du document qui la référence :

- Si le document est une commande fournisseur, la réservation est exonérée lorsque la commande fournisseur est *confirmée*.
- Si le document est une facture et qu’il ne référence pas une commande fournisseur ou un contrat d’achat, la réservation budgétaire générale est exonérée lorsque la facture est *validée*.
- Si le document est une demande d’achat, la réservation est exonérée lorsque la demande d’achat est *approuvée*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
