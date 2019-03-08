---
title: Prévisions de projet et budgets
description: Microsoft Dynamics 365 for Finance and Operations offre deux méthodes de prévision et de budgétisation des projets pour gérer et contrôler vos projets.
author: KimANelson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 530a2717427c540d80509c4862e6fb8ea7c5694a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "310390"
---
# <a name="project-forecasts-and-budgets"></a>Prévisions de projet et budgets

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations propose deux façons de gérer et contrôler vos projets : prévisions de projet et budgets de projet. 

Utilisez les prévisions de projet si votre organisation a une perspective opérationnelle orientée sur les produits et les coûts qui sont dérivés de transactions spécifiques. Utilisez la budgétisation de projet si votre organisation s'oriente plus sur les montants financiers. 

Les prévisions et les budgets de projets utilisent des modèles de prévision pour contenir les montants de transaction projetés. 

Chaque méthode a ses avantages. Avant de sélectionner une méthode pour votre organisation, tenez compte des points suivants.

|                           |                                          |                                                    |
|---------------------------|------------------------------------------|----------------------------------------------------|
|                           | **Prévisions de projet**                  | **Budgétisation de projet**                              |
| **Répartition par période**     | Vous ne pouvez pas répartir explicitement des transactions sur une période fiscale. Au lieu de cela, la prévision et le contrôle de la prévision sont basés sur la durée de vie du projet. Étant donné que les prévisions sont basées sur une date spécifique, vous devez déduire la période à partir de la date. | Vous pouvez répartir les transactions sur l'ensemble du projet ou sur une période fiscale. Si vous procédez à une répartition sur une période, vous pouvez reporter les montants inutilisés sur la période fiscale suivante. |
| **Consultation des transactions**  | Vous pouvez afficher les transactions dans les écrans de prévision, dans lesquels vous pouvez consulter les prévisions de l'intégralité de la société et pour tous les projets, indépendamment de la hiérarchie. Pour vous concentrer sur un projet spécifique, vous devez filtrer les données.                                       | Vous pouvez afficher les transactions budgétisées pour une hiérarchie de projet unique. Par conséquent, vous pouvez afficher les détails de transaction pour un projet parent ou ses sous-projets.                 |
| **Variables de transaction** | Lorsque vous spécifiez les transactions de prévision, vous pouvez utiliser chaque attribut qui existe pour une transaction réelle. Cela permet de mieux détailler la prévision. Par exemple, vous pouvez détailler les quantités, les travailleurs, les articles ou les propriétés de ligne.         | Lorsque vous spécifiez les détails du budget, vous pouvez uniquement utiliser des montants, des catégories et des activités.                    |
| **Sécurité**              | Les prévisions sont basées sur les transactions que vous entrez dans les écrans des prévisions et n'impliquent pas de mécanisme de contrôle du processus. Tout collaborateur doté d'autorisations pour un écran de prévision peut réviser les informations sans approbation.                                        | La budgétisation utilise le système de workflow, ce qui active la gestion des modifications et vous permet de conserver un historique des révisions.         |
| **Types d'entrées**           | Les entrées de transaction de prévision sont basées sur le nombre d'unités et sur les prix de vente et de revient unitaires.  | Les détails de budget sont basés sur les montants, qui sont répartis entre les coûts et les produits.                                          |
| **Modèles de prévision**       | Étant donné que chaque prévision doit être associée à un modèle, vous pouvez créer plusieurs modèles de prévision et également paramétrer des sous-modèles.           | La budgétisation du projet limite les modèles de prévision utilisés pour la budgétisation. Un nombre réduit de modèles de prévision permet d'augmenter la cohérence des projections.                           |
| **Dépassement des coûts**         | Vous pouvez uniquement autoriser ou rejeter l'entrée des transactions qui provoqueront un dépassement des coûts.   | La budgétisation du projet fournit des options de contrôle supplémentaires aux utilisateurs. Vous pouvez autoriser les avertissements et les dépassements.                    |
| **Contrôler**               | Le contrôle des prévisions s'effectue en utilisant la réduction prévisionnelle. Les montants réels sont soustraits des soldes des transactions de prévision sans piste d'audit. Cela peut compliquer le suivi de réalisation des transactions réelles.                   | Dans le contrôle budgétaire du projet, les montants réels sont soustraits des montants du budget restant. Cela permet de clarifier la piste d'audit.                                   |

## <a name="project-forecasts"></a>Prévisions de projet
La prévision de projet vous permet d'entrer des transactions de prévision dans les écrans de prévision pour chaque type de transaction. Chaque attribut disponible pour une transaction réelle peut être utilisé pour une transaction de prévision (par exemple, rentabilité de ligne, attributs de ligne, collaborateurs ou descriptions). Vous pouvez également prévoir le délai de facturation d'un client après la prise en charge d'un coût. 

Les transactions de prévision de projet sont basées sur des unités et montants. 

Vous devez associer chaque prévision de projet à un modèle de prévision. Lorsque vous entrez une transaction de prévision, un modèle de prévision est automatiquement suggéré. Le modèle de prévision sert de conteneur pour les transactions de prévision. 

Vous pouvez indiquer des modèles de prévision comme sous-modèles pour un modèle. Cela vous permet d'effectuer des prévisions par région, période, ou département. Vous pouvez copier les transactions de prévision dans un modèle pour créer un nouveau modèle et également transférer les transactions vers la comptabilité. En raison de la relation 1 à 1 entre une prévision et un modèle, chaque modèle de prévision constitue un budget séparé pour un projet. 

Les modèles de prévision peuvent utiliser la réduction prévisionnelle comme mécanisme de contrôle pour les projets. Dans le cadre de la réduction des prévisions, les transactions réelles réduisent les soldes des transactions de prévision. Toutefois, comme la réduction prévisionnelle est appliquée au premier projet dans la hiérarchie, elle fournit un aperçu limité des modifications dans la prévision. Par exemple, si un travailleur est associé à un sous-projet, les transactions réelles pour le travailleur sont validées dans le projet parent. Cela peut rendre difficile le suivi des modification, car vous ne pouvez pas facilement identifier la transaction ayant réduit le montant prévisionnel, et le sous-projet auquel elle appartient. Par conséquent, il est judicieux de créer une copie d'un modèle de prévision à utiliser par la réduction des prévisions. Vous pouvez ensuite utiliser les états pour afficher ce qui a été initialement prévu. 

Vous pouvez réviser, copier, supprimer ou transférer les prévisions de projet vers un budget comptable. Toutefois, le processus n'est pas contrôlé. Tout collaborateur doté d'une autorisation pour un écran de prévision peut effectuer des modifications sans révision.

-   **Réviser** – Vous pouvez réviser une transaction de prévision dans les écrans de création des entrées d'origine.
-   **Copier ou Supprimer** – Lorsque vous copiez des transactions de prévision, vous copiez les lignes de transaction d'un modèle de prévision vers un autre modèle de prévision. Lorsque vous supprimez une prévision, vous supprimez les transactions de prévision d'un modèle de prévision. Pour limiter les transactions de prévision qi sont copiées ou supprimées, sélectionnez des types et dates de transaction spécifiques. Cela vous permet de copier ou de supprimer uniquement certaines parties d'une prévision.
-   **Transférer** – Lorsque vous transférez une prévision de projet vers un budget comptable, vous transférez les transactions de prévision d'un modèle de prévision vers un budget comptable. Vous pouvez remplacer les transactions précédemment transférées dans le budget comptable vers lequel vous transférez votre prévision de projet.

## <a name="project-budgets"></a>Budgets de projet
La budgétisation de projet est une méthode plus simple que la prévision, bien qu'elle s'intègre aux modèles de prévision. Elle utilise un écran de saisie unique pour les détails de budget d'origine et pour les révisions, et permet de créer des projections basées uniquement sur le montant, la catégorie ou l'activité. 

Dans la budgétisation de projet, tous les budgets d'origine et les révisions doivent être transmis à un workflow de projet pour approbation. Les workflows renforcent le contrôle sur le processus et créent un enregistrement d'historique des modifications. 

La budgétisation de projet est semblable à la budgétisation de comptabilité, mais elle est plus simple et rapide à paramétrer. La plupart des options disponibles dans la budgétisation de comptabilité (souches de numéros, devise, etc.) ne doivent pas être paramétrées séparément pour les projets.

Les budgets de projet sont automatiquement associés à deux modèles de prévision, l'un pour le budget d'origine et l'autre pour le budget restant. Par conséquent, les états basés sur des modèles de prévision peuvent utiliser des données du budget. Lorsqu'un budget de projet est engagé, le système crée les transactions de prévision en fonction des modèles associés, qui sont utilisés à des fins de déclaration et de contrôle.

## <a name="forecast-models"></a>Modèles de prévision
Les modèles de prévision sont dotés d'une hiérarchie à une seule couche. Cela signifie qu'une prévision de projet doit être associée à un modèle de prévision.

Si vous utilisez des prévisions de projet, vous pouvez identifier des modèles comme sous-modèles, ce qui permet de créer des prévisions par département, période ou région. Par exemple, vous pouvez créer un modèle de prévision pour une année, puis créer des sous-modèles pour les prévisions des régions Nord-Est, Sud-Est, Nord-Ouest et Sud-Ouest, qui sont soumises par les directions régionales. En sélectionnant différentes options dans les états disponibles, vous pouvez afficher les informations par prévision totale ou par sous-modèle.



