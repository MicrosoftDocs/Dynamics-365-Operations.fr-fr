---
title: Titres de recette dans le secteur public en France
description: Le titre de recette permet au directeur d'informer le comptable que l'organisation est autorisée à recouvrer un montant spécifique auprès d'une autre entité et d'autoriser le comptable à déposer ledit montant. Le directeur ou le comptable peut déléguer la tâche à un commercial, mais il a toujours la responsabilité de chaque tâche. Le titre permet de garantir une séparation nette obligatoire entre le rôle opérationnel du directeur et le rôle comptable du comptable.
author: rschloma
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 19931
ms.search.region: France
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0ba76e50abd5ce124b91515eacf860dbe2e81ae2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "370702"
---
# <a name="titres-de-recette-in-the-public-sector-in-france"></a>Titres de recette dans le secteur public en France

[!include [banner](../includes/banner.md)]

Le titre de recette permet au directeur d'informer le comptable que l'organisation est autorisée à recouvrer un montant spécifique auprès d'une autre entité et d'autoriser le comptable à déposer ledit montant. Le directeur ou le comptable peut déléguer la tâche à un commercial, mais il a toujours la responsabilité de chaque tâche. Le titre permet de garantir une séparation nette obligatoire entre le rôle opérationnel du directeur et le rôle comptable du comptable.

Dans Microsoft Dynamics 365 for Finance and Operations, une seule ligne de facture financière est affectée à chaque titre. Cela permet de garantir que chaque titre ne concerne qu'un seul débiteur et n'inclut qu'un seul compte budgétaire. Un groupe de titres liés avec leurs documents associés sont affectés à un bordereau de titre pour être soumis au comptable.

## <a name="directors-tasks"></a>Tâches du directeur
Sur la page **Tenir à jour les titres de recette**, le directeur peut effectuer les tâches suivantes :

-   **Affecter des lignes de facture à un titre de recette.** Pour rechercher les lignes de facture qui n'ont pas encore été affectées à un titre, vous pouvez filtrer les lignes récupérées par la colonne **Titre**.
-   **Autoriser le recouvrement des lignes de facture affectées à des titres.** Cette opération peut également être effectuée à partir de l'onglet **Titre de recette** de la page de facture financière.
-   **Affectation de titres à un bordereau de titre.** Pour rechercher les lignes de facture qui n'ont pas encore été affectées à un bordereau de titre, vous pouvez filtrer les lignes récupérées par la colonne **Bordereau de titre**.

Pour soumettre les titres au comptable pour dépôt, le directeur recueille les titres imprimés et leurs documents associés sous un bordereau de titre.

-   Imprimez les titres affectés à un bordereau à partir de l'organisateur **Enregistrements à inclure** de la page **État de titre de recette**.
-   Imprimez le bordereau à partir de l'organisateur **Enregistrements à inclure** de la page **État de bordereau de titre**.

## <a name="accountants-tasks"></a>Tâches du comptable
À partir de la page **Tenir à jour les titres de recette** ou de l'onglet **Titre de recette** de la page de facture financière, le comptable peut accepter, rejeter ou mettre en attente les titres. Lorsqu'un titre est rejeté, le statut du directeur est remplacé par Non vérifié et les numéros du titre et du bordereau de titre sont effacés.

## <a name="using-the-database-inquiry-page"></a>Utilisation de la page de recherche dans la base de données
Pour ouvrir la page de recherche dans la base de données à partir de la page **Tenir à jour les titres de recette**, spécifiez la plage de dates dans laquelle vous souhaitez sélectionner des factures. Cliquez ensuite sur **Récupérer les lignes**. Cela ouvre la page de recherche dans la base de données, sur laquelle vous pouvez spécifier les critères pour les lignes de facture que vous souhaitez récupérer. Lorsque vous fermez l'écran, toutes les lignes de facture qui correspondent aux critères sélectionnés s'affichent dans la grille. Les lignes des factures qui sont en cours de modification ne sont pas récupérées. **Conseil** : utilisez les critères suivants dans la page de recherche dans la base de données pour récupérer des lignes.

- Lignes de facture qui n'ont pas été révisées par le directeur.

  | Enregistrement | Table dérivée |             Champ             |    Critères    |
  |-------|---------------|-------------------------------|----------------|
  | Titre |     Titre     | Statut d'autorisation du directeur | « Non révisé(e) » |


- Lignes de facture des titres qui ont été autorisés au recouvrement par le directeur, mais pas encore approuvées par le comptable.

  | Enregistrement | Table dérivée |             Champ             |    Critères    |
  |-------|---------------|-------------------------------|----------------|
  | Titre |     Titre     | Statut d'autorisation du directeur |  « Autorisé(e) »  |
  | Titre |     Titre     | Statut d'acceptation du comptable  | « Non révisé(e) » |


- Lignes de facture des titres qui ont été rejetés par le comptable.

  | Enregistrement | Table dérivée | Champ                        | Critères   |
  |-------|---------------|------------------------------|------------|
  | Titre | Titre         | Statut d'acceptation du comptable | « Rejeté(e) » |





