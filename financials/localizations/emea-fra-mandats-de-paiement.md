---
title: Mandats de paiement dans le secteur public en France
description: "Le mandat de paiement est utilisé par le directeur pour informer le comptable que l&quot;organisation doit payer un montant donné à une autre entité et pour autoriser le comptable à payer ledit montant. Le mandat permet de garantir une séparation nette obligatoire entre le rôle opérationnel du directeur et le rôle comptable du comptable."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27231
ms.assetid: e63d4d9d-27d4-42c9-ad87-66040b8680db
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 0a034a282f0406f36443d93d753c5a55a65eac0b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="mandats-de-paiement-in-the-public-sector-in-france"></a>Mandats de paiement dans le secteur public en France

[!include[banner](../includes/banner.md)]


Le mandat de paiement est utilisé par le directeur pour informer le comptable que l'organisation doit payer un montant donné à une autre entité et pour autoriser le comptable à payer ledit montant. Le mandat permet de garantir une séparation nette obligatoire entre le rôle opérationnel du directeur et le rôle comptable du comptable.

<a name="directors-tasks"></a>Tâches du directeur
----------------

À partir de la page **Tenir à jour les mandats de paiement**, le directeur peut effectuer les tâches suivantes :

-   **Affecter des lignes de facture à un mandat de paiement.** Pour rechercher les lignes de facture qui n'ont pas encore été affectées à un mandat, vous pouvez filtrer les lignes récupérées par la colonne **Mandat**.
-   **Autoriser le paiement des lignes de facture affectées à des mandats.** Cela peut également être effectué à partir de l'onglet **Mandat de paiement** de la page de facture fournisseur ou la page de transactions fournisseur.
-   **Affecter des mandats à un bordereau de mandat.** Pour rechercher les lignes de facture qui n'ont pas encore été affectées à un bordereau de mandat, vous pouvez filtrer les lignes récupérées par la colonne **Bordereau de mandat**.
-   **Émettre un arrêté de réquisition.** Affectez la ligne de facture à un nouveau mandat avant de le soumettre au comptable en tant qu'arrêté de réquisition.

Pour soumettre des mandats au comptable pour paiement, le directeur recueille les mandats imprimés et leurs documents associés sous un bordereau de mandat.

-   Imprimez les mandats affectés à un bordereau à partir de l'organisateur **Enregistrements à inclure** de la page **État de mandat de paiement**.
-   Imprimez le bordereau à partir de l'organisateur **Enregistrements à inclure** de la page **État de bordereau de mandat**.

## <a name="accountants-tasks"></a>Tâches du comptable
À partir de la page **Tenir à jour les mandats de paiement** ou de l'onglet **Mandat de paiement** de la page des factures fournisseur en attente ou de la page des factures fournisseur en cours, le comptable peut accepter, rejeter ou mettre en attente les mandats. Lorsqu'un mandat est rejeté, le statut du directeur est remplacé par **Non vérifié** et les numéros du mandat et du bordereau de mandat sont effacés.

## <a name="using-the-database-inquiry-page"></a>Utilisation de la page de recherche dans la base de données
Pour ouvrir la page de recherche dans la base de données à partir de la page **Tenir à jour les mandats de paiement**, spécifiez si vous souhaitez travailler avec des factures en attente ou validées et la plage de dates dans laquelle vous souhaitez sélectionner des factures. Cliquez ensuite sur **Récupérer les lignes**. Cela ouvre la page de **recherche dans** **la base de donnée**, sur laquelle vous pouvez spécifier les critères pour les lignes de facture que vous souhaitez récupérer. Lorsque vous fermez l'écran, toutes les lignes de facture qui correspondent aux critères sélectionnés s'affichent dans la grille. Les lignes des factures qui sont en cours de modification ne sont pas récupérées. **Conseil** : utilisez les critères suivants dans la page de recherche dans la base de données pour récupérer des lignes.

-   Lignes de facture qui n'ont pas été révisées par le directeur.
    | Enregistrement  | Table dérivée | Champ                         | Critères       |
    |--------|---------------|-------------------------------|----------------|
    | Mandat | Mandat        | Statut d'autorisation du directeur | « Non révisé(e) » |

-   Lignes de facture des mandats qui ont été autorisés pour paiement par le directeur, mais pas encore approuvés par le comptable.
    | Enregistrement  | Table dérivée | Champ                         | Critères       |
    |--------|---------------|-------------------------------|----------------|
    | Mandat | Mandat        | Statut d'autorisation du directeur | « Autorisé(e) »   |
    | Mandat | Mandat        | Statut d'acceptation du comptable  | « Non révisé(e) » |

-   Lignes de facture des mandats qui ont été rejetés par le comptable.
    | Enregistrement  | Table dérivée | Champ                        | Critères   |
    |--------|---------------|------------------------------|------------|
    | Mandat | Mandat        | Statut d'acceptation du comptable | « Rejeté(e) » |






