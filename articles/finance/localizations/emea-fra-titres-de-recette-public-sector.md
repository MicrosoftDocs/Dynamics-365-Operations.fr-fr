---
title: Titres de recette dans le secteur public en France
description: Le titre de recette est utilisé par le directeur utilise le titre de recette pour aviser et autoriser le comptable à collecter et à déposer un montant déterminé d’une autre entité.
author: rschloma
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: kfend
ms.custom: 19931
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c51f4e7b6c54ca7690ee8cb9cd25dfa7612ede28
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5002929"
---
# <a name="titres-de-recette-in-the-public-sector-in-france"></a>Titres de recette dans le secteur public en France

[!include [banner](../includes/banner.md)]

Le directeur utilise le titre de recette est utilisé par le directeur utilise le titre de recette pour aviser et autoriser le comptable à collecter et à déposer un montant déterminé d’une autre entité. Le directeur ou le comptable peut déléguer un représentant pour exécuter la tâche. Cependant, la responsabilité de chaque tâche incombe au directeur ou au comptable. Le titre permet de garantir une séparation nette obligatoire entre le rôle opérationnel du directeur et le rôle comptable du comptable.

Dans Dynamics 365 Finance, une seule ligne de facture financière est affectée à chaque titre. Cette affectation permet de garantir que chaque titre ne concerne qu’un seul débiteur et n’inclut qu’un seul compte budgétaire. Un groupe de titres liés avec leurs documents associés sont affectés à un bordereau de titre pour être soumis au comptable.

## <a name="directors-tasks"></a>Tâches du directeur
Sur la page **Tenir à jour les titres de recette**, le directeur peut effectuer les tâches suivantes :

-   **Affecter des lignes de facture à un titre de recette.** Pour rechercher les lignes de facture qui n’ont pas encore été affectées à un titre, vous pouvez filtrer les lignes récupérées par la colonne **Titre**.
-   **Autoriser le recouvrement des lignes de facture affectées à des titres.** L’autorisation peut également être effectuée à partir de l’onglet **Titre de recette** de la page **Facture financière**.
-   **Affectation de titres à un bordereau de titre.** Pour rechercher les lignes de facture qui n’ont pas encore été affectées à un bordereau de titre, utilisez la colonne **Bordereau de titre** pour filtrer les lignes récupérées.

Pour soumettre les titres au comptable pour dépôt, le directeur recueille les titres imprimés et leurs documents associés sous un bordereau de titre.

-   Imprimez les titres affectés à un bordereau à partir de l’organisateur **Enregistrements à inclure** de la page **État de titre de recette**.
-   Imprimez le bordereau à partir de l’organisateur **Enregistrements à inclure** de la page **État de bordereau de titre**.

## <a name="accountants-tasks"></a>Tâches du comptable
À partir de la page **Tenir à jour les titres de recette** ou de l’onglet **Titre de recette** de la page de facture financière, le comptable peut accepter, rejeter ou mettre en attente les titres. Lorsqu’un titre est rejeté, le statut d’administrateur passe à Non révisé(e). Les numéros de titre et bordereau de titre sont effacés.

## <a name="using-the-database-inquiry-page"></a>Utilisation de la page Recherche dans la base de données
Pour ouvrir la page **Recherche dans la base de données** à partir de la page **Tenir à jour les titres de recette**, spécifiez la plage de dates dans laquelle vous souhaitez sélectionner des factures. Cliquez ensuite sur **Récupérer les lignes**. La page **Recherche dans la base de données** s’ouvre et vous pouvez spécifier les critères pour les lignes de facture que vous souhaitez récupérer. Lorsque vous fermez la page, toutes les lignes de facture qui correspondent aux critères sélectionnés s’affichent dans la grille. Les lignes des factures qui sont en cours de modification ne sont pas récupérées. 

Utilisez les critères suivants dans la page de recherche dans la base de données pour récupérer des lignes.

- Lignes de facture qui n’ont pas été révisées par le directeur.

  | Enregistrement | Table dérivée |             Champ             |    Critères    |
  |-------|---------------|-------------------------------|----------------|
  | Titre |     Titre     | Statut d’autorisation du directeur | « Non révisé(e) » |


- Lignes de facture des titres qui ont été autorisés au recouvrement par le directeur, mais pas encore approuvées par le comptable.

  | Enregistrement | Table dérivée |             Champ             |    Critères    |
  |-------|---------------|-------------------------------|----------------|
  | Titre |     Titre     | Statut d’autorisation du directeur |  « Autorisé(e) »  |
  | Titre |     Titre     | Statut d’acceptation du comptable  | « Non révisé(e) » |


- Lignes de facture des titres qui ont été rejetés par le comptable.

  | Enregistrement | Table dérivée | Champ                        | Critères   |
  |-------|---------------|------------------------------|------------|
  | Titre | Titre         | Statut d’acceptation du comptable | « Rejeté(e) » |





