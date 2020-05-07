---
title: Créer des contrats avancés pour la facturation en fonction de la progression
description: Cette rubrique explique comment créer des contrats de projet afin de pouvoir générer des factures pour les clients, en fonction d'un pourcentage de travail terminé.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282825"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a>Créer des contrats avancés pour la facturation en fonction de la progression
[!include [banner](../includes/banner.md)]

Cette rubrique explique comment créer des contrats de projet afin de pouvoir créer des factures pour les clients, en fonction d'un pourcentage de travail terminé. Les montants de facture correspondant aux catégories de travail budgétisées définies pour le projet sont calculés automatiquement. L'échéance des factures est définie lors de la négociation du contrat de projet avec le client.

Utilisez les procédures de cette rubrique pour définir un contrat, un projet associé et les règles de facturation qui calculent les montants de la facture pour les catégories de travail budgétisées définies pour le projet.

Après la création du contrat et du projet, vous pouvez paramétrer les détails du projet. Par exemple, vous pouvez définir les activités et affecter des collaborateurs au projet.

## <a name="example"></a>Exemple

Votre organisation est une société de développement logiciel. Vous avez convenu de développer un module de gestion des salaires, pour un montant total de 20 000 dollars américains (USD). Votre organisation s'est engagée à facturer le client à mesure que certains pourcentages spécifiés du projet sont accomplis. Vous définissez les catégories de projets suivantes pour le travail, afin de pouvoir les utiliser dans le processus de facturation :

- Consultance
- Mise en page
- Installation

Vous paramétrez aussi des règles de facturation qui calculent automatiquement les montants à facturer pour le pourcentage de travail du projet réalisé dans chaque catégorie.

Le responsable du budget crée un budget pour les catégories de projet. La quantité de travail réalisé est automatiquement calculée sous forme d'un pourcentage du travail réel comparé aux montants budgétés.

## <a name="prerequisites"></a>Conditions préalables

Avant de créer un projet qui utilise des règles de facturation, vous devez configurer les séquences de numéros pour les règles de facturation et un journal des frais utilisé pour valider la facturation par tranche.

1. Accédez à **Gestion de projets et comptabilité** \> **Paramétrage** \> **Paramètres de gestion de projets et de comptabilité**.
2. Sur la page **Paramètres de gestion de projet et de comptabilité**, sur l'onglet **Séquences de numéros**, définissez la séquence de numéros à utiliser lors de la création des règles de facturation.
3. Accédez à **Intégration dans Gestion de projets et comptabilité** \> **Journaux** \> **Frais**.
4. Sur la page **Journal des frais**, sélectionnez **Nouveau** et entrez le nom du journal.

## <a name="create-a-contract-for-progress-billings"></a>Création d'un contrat basé sur des facturations par tranche

Cette procédure permet de créer un contrat de projet pour un projet à prix fixe. Vous créez une facture de projet lorsque le travail terminé pour le projet atteint un pourcentage spécifié.

1. Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Contrats de projets**.
2. Dans la page **Contrats de projet**, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Nouveau contrat de projet**, sélectionnez les champs suivants :

    - **Nom**
    - **Type de financement**
    - **Source de financement**
    - **Devise de vente** – Par défaut, cette devise est utilisée pour les factures client associées au contrat de projet. Toutefois, vous pouvez modifier la devise de vente sur une facture client spécifique.

4. Cliquez sur **OK**. Les informations sont copiées dans l'en-tête de la page **Contrats de projet**.
5. Sur la page **Contrats de projet**, remplissez le reste des informations requises pour le projet.

## <a name="create-a-project-for-progress-billings"></a>Création d'un projet basé sur des facturations par tranche

Suivez cette procédure pour créer un projet et d'éventuels sous-projets associés à un contrat de projet.

1. Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Tous les projets**.
2. Sur la page **Tous les projets**, sélectionnez **Nouveau**.
3. Dans la boîte de dialogue **Nouveau projet**, dans le champ **Type de projet**, sélectionnez **Temps et matériel**.
4. Permet de sélectionner un groupe de projets. Un groupe de projets définit les informations de validation des projets affectés au groupe.
5. Sélectionnez **Créer un projet**.
6. Une fois le projet créé, définissez la phase du projet sur **En cours**.

## <a name="create-a-budget-for-a-project"></a>Création d'un budget pour le projet

Les catégories budgétisées permettent de calculer automatiquement les montants à facturer pour le pourcentage de travail réalisé dans chaque catégorie. Suivez ces étapes pour créer des catégories de budget pour les coûts estimés.

1. Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Tous les projets**.
2. Sur la page **Tous les projets**, sélectionnez et ouvrez le projet souhaité.
3. Sur la page **Projets**, dans le volet Actions, sur l'onglet **Plan**, dans le groupe **Budget**, sélectionnez **Budget du projet**.
4. Sur la page **Budget du projet**, entrez une estimation du coût pour chaque catégorie du projet.

## <a name="create-billing-rules-for-progress-billings"></a>Création de règles de facturation pour un contrat basé sur des facturations par tranche

1. Accédez à **Gestion et comptabilité des projets** \> **Projets** \> **Contrats de projets**.
2. Sur la page **Contrats de projet**, sélectionnez et ouvrez un contrat de projet.
3. Sur la page du contrat de projet, sur l'organisateur **Règles de facturation**, sélectionnez **Ajouter**.
4. Sur la page **Règle de facturation**, dans le champ **Type de ligne**, sélectionnez **Progression**.
5. Dans l'organisateur **Détails de la ligne de règle de facturation**, dans le champ **Valeur du contrat**, entrez la valeur totale du contrat.
6. Dans le champ **Catégorie**, sélectionnez la catégorie dans laquelle valider la transaction de frais.
7. Dans le champ **Projet**, sélectionnez le projet qui utilise cette règle de facturation.
8. Facultatif : Affectez la règle de facturation à d'autres projets. Sur l'organisateur **Projet**, dans la section **Projets disponibles**, sélectionnez un projet, puis cliquez sur le bouton fléché vers la droite pour ajouter le projet à la section **Projets sélectionnés**.
9. Facultatif : Calculez le montant du pourcentage retenu par le client sur le paiement d'une facture. Dans l'organisateur **Conditions de rétention de paiement**, sélectionnez la source de financement, puis, dans le champ **Pourcentage de rétention**, entrez le pourcentage de rétention.
10. Répétez ces étapes pour créer d'autres règles de facturation pour le contrat de projet.
