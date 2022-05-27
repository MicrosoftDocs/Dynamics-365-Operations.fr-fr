---
title: Créer et envoyer un flux de travail de budget de projet
description: Cette procédure décrit comment créer et envoyer le budget d’un projet.
author: GalynaFedorova
ms.date: 11/22/2021
ms.topic: article
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e554fb578371f52f665ef348d6fa81fd27196a9e
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671026"
---
# <a name="create-and-submit-a-project-budget-workflow"></a>Créer et envoyer un flux de travail de budget de projet

[!include [banner](../../includes/banner.md)]

Lors de la création d’un budget de projet, vous pouvez entrer les revenus et les coûts estimés pour le projet, puis utiliser les valeurs pour contrôler les transactions de projet réelles. La budgétisation de projet nécessite que tous les budgets d’origine et les révisions soient transmis à un flux de travail de projet pour approbation. Le flux de travail renforce le contrôle sur la budgétisation et crée un enregistrement d’historique des modifications. Après avoir [créé un projet](/dynamicsax-2012/appuser-itpro/create-a-project), utilisez cette procédure pour créer et soumettre le budget.

1. Accédez à **Modules** > **Gestion et comptabilité des projets** > **Projets** > **Tous les projets**.
1. Sélectionnez le projet dans la liste des projets.
1. Sélectionnez l’onglet **Plan** dans la page des détails du projet.
1. Sous le groupe **Budget**, sélectionnez **Budget de projet**.
1. Dans le raccourci **Général**, entrez les informations suivantes :
   - Tapez une valeur dans la zone **Description**.
   - Sélectionnez l’option pour **Budget d’origine**.
   - Sélectionnez l’option pour **Budget restant**.
1. Développez le raccourci **Coûts** et sélectionnez **Nouveau**. Ensuite, définissez les paramètres suivants :
   - Sélectionnez une option pour **Type de transaction**.
   - Sélectionnez une **Catégorie** appropriée.
   - Entrez une valeur dans **Budget d’origine**.
1. Développez le raccourci **Produits** et sélectionnez **Nouveau**. Ensuite, définissez les paramètres suivants :
   - Sélectionnez une option pour **Type de transaction**.
   - Sélectionnez une **Catégorie**.
   - Entrez une valeur pour **Budget d’origine**.
1. Cliquez sur **Enregistrer**.
1. Sélectionnez **Flux de travail \>Soumettre**.
1. Sur la page **Flux de travail Passer en revue le budget d’origine - Soumettre**, entrez un **Commentaire**, puis sélectionnez **Soumettre**.
