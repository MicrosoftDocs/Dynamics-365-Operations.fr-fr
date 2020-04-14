---
title: Transférer les budgets de projet à la fin de l'exercice
description: Cet article fournit des informations sur la façon de transférer les montants budgétaires restants aux années futures et de créer les détails du registre budgétaire.
author: RadhikaRS
manager: AnnBe
ms.date: 03/23/2020
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
ms.openlocfilehash: 41e985825a24de2d6510938cf3d61715c35f9939
ms.sourcegitcommit: 2ea5ff784500d5be9203e9a1560eabd4fea46f4e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172328"
---
# <a name="transfer-project-budgets-at-fiscal-year-end"></a>Transférer les budgets de projet à la fin de l'exercice

[!include [banner](../includes/banner.md)]

Lorsque vous travaillez sur un projet sur plusieurs années, vous pouvez avoir un budget restant à la fin de l'exercice. Vous pouvez transférer les montants budgétaires restants pour un exercice futur et créer des détails du registre budgétaire pour les montants des comptes de comptabilité associés. Avant de reporter les montants restants, examinez et analysez les montants budgétaires restants.

## <a name="review-and-analyze-remaining-budget-amounts"></a>Examen et analyse des montants budgétaires restants

Procédez comme suit pour examiner les montants budgétaires de fin d'exercice pour les projets, mais pas pour reporter les montants.

1. Accédez à **Gestion de projet et comptabilité** > **Périodique** > **Budgets** > **Reporter les budgets**. 
2. Sur la page **Processus de report du budget du projet**, sur l'onglet **Options de fin d'exercice**, vérifiez que l'option **Reporter les montants restants du budget de projet** n'est pas activée.
3. Sur l'onglet **Paramètres**, dans le champ **Année budgétaire du projet**, sélectionnez le début de l'exercice pour lequel vous souhaitez afficher le montant budgétaire restant. 
4. Dans le champ **Ouverture de l'exercice**, sélectionnez le début de l'exercice pour lequel vous souhaitez afficher le montant budgétaire restant. 
5. Dans le champ **À partir du modèle de prévision**, sélectionnez **Budget restant**. 
6. Pour inclure des projets qui répondent aux critères que vous avez sélectionnés et qui n'ont pas de budget restant, sélectionnez **Afficher zéro en tant que montant restant**.  
7. Sur l'onglet **Sélectionner les budgets**, sélectionnez **Récupérer tous les budgets** pour charger tous les budgets qui correspondent aux critères que vous avez sélectionnés, puis sélectionnez **Processus**. 
8. Pour créer une requête de base de données qui charge un ensemble spécifique de budgets de projet dans le volet, sélectionnez **Récupérer les budgets sélectionnés**.

Pour plus d'informations sur une ligne spécifique dans le volet, sélectionnez la ligne, puis sélectionnez **Afficher les détails du budget** ou **Afficher les comptes**.

## <a name="carry-forward-remaining-budget-amounts"></a>Reporter les montants restants du budget 

Lorsque vous traitez vos montants budgétaires restants, vous pouvez décider si vous souhaitez créer des transactions dans la comptabilité pour les montants que vous reportez. Pour créer des transactions de comptabilité, suivez les étapes de la section, [Report des montants budgétaires et création d'écritures comptables](#carry-forward). 

> [!NOTE]
> Les montants budgétaires reportés sont transférés vers le modèle de prévision sélectionné sur la page **Modèles de prévision** comme modèle de prévision de report dans l'écran.  

## <a name="carry-forward-budget-amounts-and-create-general-ledger-transactions"></a><a name="carry-forward"></a>Report des montants budgétaires et création d'écritures comptables

1.  Sélectionnez **Gestion de projet et comptabilité** > **Périodique** > **Budgets** > **Reporter les budgets**. 
2. Sur la page **Processus de report du budget du projet**, sélectionnez **Fin de l'exercice**, puis activez **Reporter les montants restants du budget de projet** et **Créer des entrées de registre budgétaire en comptabilité**. 
3. Sur l'onglet **Paramètres**, dans le groupe de champ **Paramètres du projet**, sélectionnez les éléments suivants :

   - **Année budgétaire du projet** : sélectionnez le début de l'exercice pour lequel vous souhaitez afficher les montants budgétaires restants. 
   - **Résultat** : Créer des transactions de résultat en comptabilité. 
   -  **Travaux en cours** : Créer des transactions de travaux en cours en comptabilité.
   -  **Paie** : Créer des transactions de répartition des salaires en comptabilité. 

5. Dans le groupe de champs **Comptabilité**, entrez les informations suivantes : 

   - Dans le champ **Ouverture de l'exercice**, sélectionnez le début de l'exercice pour lequel vous souhaitez transférer les montants budgétaires restants pour les projets. La valeur par défaut est une année après la valeur du champ **Année budgétaire du projet**.
   -  Dans le champ **Période de report**, sélectionnez la période dans laquelle vous souhaitez créer des détails du registre budgétaire dans la comptabilité. Il s'agit généralement de la première période de l'ouverture de l'exercice.

6. Dans le groupe de champs **Copier à partir de/vers**, entrez les informations suivantes :

   - Dans le champ **À partir du modèle de prévision**, sélectionnez le modèle de prévision du budget de projet associé aux montants budgétaires restants que vous souhaitez transférer pour les projets. 
   - Dans le champ **Vers le modèle budgétaire comptable**, sélectionnez le modèle de budget comptable associé aux montants budgétaires que vous souhaitez transférer vers la comptabilité. 
   -  Sélectionnez **Transférer la devise de vente** pour utiliser la devise de vente du projet pour les écritures comptables créées lors du transfert des montants budgétaires pour les projets. Lorsque l'option n'est pas sélectionnée, les transactions utilisent la devise comptable. 
   -  Sélectionnez **Afficher zéro en tant que montant restant** pour inclure les projets qui n'ont pas de montants budgétaires restants, mais qui répondent aux autres critères que vous sélectionnez dans les projets affichés dans le volet inférieur.

7. Sur l'onglet **Sélectionner les budgets**, sélectionnez **Récupérer tous les budgets** pour charger tous les budgets qui correspondent aux critères que vous avez sélectionnés. Si vous préférer créer une requête de base de données qui charge un ensemble spécifique de budgets de projet dans le volet, sélectionnez **Récupérer les budgets sélectionnés**.
8. Pour chaque projet que vous souhaitez traiter, activez l'option au début de la ligne pour le projet.

    > [!TIP]
    > Pour sélectionner tous ou la plupart des projets, sélectionnez la coche dans l'angle supérieur gauche. Pour exclure le traitement d'un projet, décochez la case correspondant à ce projet.

9. Pour transférer les montants budgétaires restants pour les projets sélectionnés vers l'exercice sélectionné et créer des détails du registre budgétaire dans la comptabilité, sélectionnez **Processus**.

## <a name="carry-forward-budget-amounts-without-creating-general-ledger-transactions"></a>Reporter les montants budgétaires sans création d'écritures comptables

1. Accédez à **Gestion de projet et comptabilité** > **Périodique** > **Budgets** > **Reporter les budgets**.
2. Sur la page **Processus de report du budget du projet**, dans le champ **Options de fin d'exercice**, sélectionnez **Reporter les montants restants du budget de projet**.
3. Dans le groupe **Paramètres**, dans le champ **Année budgétaire du projet**, sélectionnez le début de l'exercice pour lequel vous souhaitez afficher les montants budgétaires restants.
4. Dans le groupe **Copier à partir de/vers**, entrez les informations suivantes :

   - Dans le champ **À partir du modèle de prévision**, sélectionnez le modèle de prévision du budget de projet associé aux montants budgétaires restants que vous souhaitez transférer pour les projets. 
   - Sélectionnez **Afficher zéro en tant que montant restant** pour inclure des projets qui répondent aux critères que vous avez sélectionnés et qui n'ont pas de budget restant.
   - Dans le groupe **Sélectionner les budgets**, sélectionnez **Récupérer tous les budgets** pour charger tous les budgets qui correspondent aux critères que vous avez sélectionnés. Pour créer une requête de base de données qui charge un ensemble spécifique de budgets de projet dans le volet, sélectionnez **Récupérer les budgets sélectionnés**.

5. Pour chaque projet que vous souhaitez traiter, activez l'option au début de la ligne pour le projet. 
6. Sélectionnez **Processus** pour transférer les montants budgétaires restants pour les projets sélectionnés vers l'exercice sélectionné.

