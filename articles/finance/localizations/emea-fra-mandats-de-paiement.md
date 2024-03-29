---
title: Mandats de paiement dans le secteur public en France
description: Le mandat de paiement est utilisé par le directeur pour aviser et autoriser le comptable à verser un montant déterminé à une autre entité.
author: brpotter
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: France
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 27231
ms.search.industry: Public sector
ms.openlocfilehash: 2a0a61157ec506191966adc1da5a045f8147b487
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9267100"
---
# <a name="mandats-de-paiement-in-the-public-sector-in-france"></a>Mandats de paiement dans le secteur public en France

[!include [banner](../includes/banner.md)]

Le mandat de paiement est utilisé par le directeur pour aviser et autoriser le comptable à verser un montant déterminé à une autre entité. Comme requis, le mandat permet de garantir une séparation nette entre le rôle opérationnel du directeur et le rôle comptable du comptable.

## <a name="directors-tasks"></a>Tâches du directeur

À partir de la page **Tenir à jour les mandats de paiement**, le directeur peut effectuer les tâches suivantes :

-   **Affecter des lignes de facture à un mandat de paiement.** Pour rechercher les lignes de facture qui n’ont pas encore été affectées à un mandat, utilisez la colonne **Mandat** pour filtrer les lignes récupérées.
-   **Autoriser le paiement des lignes de facture affectées à des mandats.** Les paiements peuvent également être autorisés à partir de l’onglet **Mandat de paiement** de la page **Facture fournisseur** ou la page **Transactions fournisseur**.
-   **Affecter des mandats à un bordereau de mandat.** Pour rechercher les lignes de facture qui n’ont pas encore été affectées à un bordereau de mandat, vous pouvez filtrer les lignes récupérées par la colonne **Bordereau de mandat**.
-   **Émettre un arrêté de réquisition.** Affectez la ligne de facture à un nouveau mandat avant de le soumettre au comptable en tant qu’arrêté de réquisition.

Pour soumettre des mandats au comptable pour paiement, le directeur recueille les mandats imprimés et leurs documents associés sous un bordereau de mandat.

-   Imprimez les mandats affectés à un bordereau à partir de l’organisateur **Enregistrements à inclure** de la page **État de mandat de paiement**.
-   Imprimez le bordereau à partir de l’organisateur **Enregistrements à inclure** de la page **État de bordereau de mandat**.

## <a name="accountants-tasks"></a>Tâches du comptable
Le comptable peut accepter, rejeter ou détenir des mandats à partir des endroits suivants :

  - Page **Tenir à jour les mandats de paiement**
  - Page **Factures fournisseur en attente**, sur l’onglet **Mandat de paiement**  
  - Page **Factures fournisseur ouvertes**, sur l’onglet **Mandat de paiement**
  
Lorsqu’un mandat est rejeté, le statut d’administrateur passe à **Non révisé(e)**. Les numéros de mandat et bordereau de mandat sont effacés.

## <a name="using-the-database-inquiry-page"></a>Utilisation de la page Recherche dans la base de données
Pour ouvrir la page **Recherche dans la base de données** à partir de la page **Tenir à jour les mandats de paiement**, spécifiez si vous souhaitez travailler avec des factures en attente ou validées. Indiquez la plage de dates à partir de laquelle vous souhaitez sélectionner les factures, puis sélectionnez **Récupérer des lignes**. La page **Recherche dans la base de données** s’ouvre et vous pouvez spécifier les critères pour les lignes de facture que vous souhaitez récupérer. Lorsque vous fermez la page, toutes les lignes de facture qui correspondent aux critères sélectionnés s’affichent dans la grille. Les lignes des factures qui sont en cours de modification ne sont pas récupérées. 

Utilisez les critères suivants dans la page de recherche dans la base de données pour récupérer des lignes.

- Lignes de facture qui n’ont pas été révisées par le directeur.

  | Enregistrement  | Table dérivée |             Champ             |    Critères    |
  |--------|---------------|-------------------------------|----------------|
  | Mandat |    Mandat     | Statut d’autorisation du directeur | « Non révisé(e) » |


- Lignes de facture des mandats qui ont été autorisés pour paiement par le directeur, mais pas encore approuvés par le comptable.

  | Enregistrement  | Table dérivée |             Champ             |    Critères    |
  |--------|---------------|-------------------------------|----------------|
  | Mandat |    Mandat     | Statut d’autorisation du directeur |  « Autorisé(e) »  |
  | Mandat |    Mandat     | Statut d’acceptation du comptable  | « Non révisé(e) » |


- Lignes de facture des mandats qui ont été rejetés par le comptable.

  | Enregistrement  | Table dérivée | Champ                        | Critères   |
  |--------|---------------|------------------------------|------------|
  | Mandat | Mandat        | Statut d’acceptation du comptable | « Rejeté(e) » |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
