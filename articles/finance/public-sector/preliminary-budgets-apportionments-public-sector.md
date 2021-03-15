---
title: Budgets préliminaires et répartitions dans le secteur public
description: Cette rubrique couvre la création d’un budget préliminaire, et le paramétrage de la budgétisation et du contrôle budgétaire pour les répartitions et un budget préliminaire.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetBalancesActuals, BudgetControlConfiguration, BudgetTransactionCode
audience: Application User
ms.reviewer: roschlom
ms.custom: 19701
ms.assetid: 8885478d-67f5-4db8-b97b-c0734216f8dd
ms.search.region: Global
ms.search.industry: Public sector
ms.author: brpotter
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26d99e5d2c2736601e8f2517e226d47b6d835cb7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4984709"
---
# <a name="preliminary-budgets-and-apportionments-in-the-public-sector"></a>Budgets préliminaires et répartitions dans le secteur public

[!include [banner](../includes/banner.md)]

Cette rubrique couvre la création d’un budget préliminaire, et le paramétrage de la budgétisation et du contrôle budgétaire pour les répartitions et un budget préliminaire. 

Les sections suivantes de cette rubrique décrivent les fonctionnalités de budgétisation disponibles pour le secteur public.  Avant de lire cette rubrique, vous devez également lire [Budgétisation dans le secteur public](budgeting-public-sector.md).

-   Paramétrage de la budgétisation et du contrôle budgétaire pour les répartitions - Vous pouvez définir un ou plusieurs codes budget pour le type de budget Répartition et configurer le contrôle budgétaire pour les répartitions.
-   Paramétrage de la budgétisation et du contrôle budgétaire pour un budget préliminaire - Vous pouvez définir des codes budget pour le type de budget Préliminaire et configurer le contrôle budgétaire pour les budgets préliminaires.
-   Création, affichage et contrepassation d’un budget préliminaire - Vous pouvez créer des écritures budgétaires préliminaires, ainsi que des écritures budgétaires d’origine.


## <a name="set-up-budgeting-and-budget-control-for-apportionments"></a>Paramétrage de la budgétisation et du contrôle budgétaire pour les répartitions
Les répartitions représentent la part du budget d’origine qui a été approuvée pour les dépenses. Par exemple, une organisation peut disposer d’un budget d’origine de 1 000 000 € mais n’être autorisée à dépenser que 150 000 € au cours du premier trimestre de l’exercice. Vous pouvez enregistrer une écriture de registre budgétaire d’origine de 1 000 000 € pour l’exercice. Vous pouvez ensuite enregistrer une écriture de registre budgétaire de répartition de 150 000 € pour les trois premiers mois de l’exercice. Seuls les 150 000 € répartis peuvent être dépensés au cours du premier trimestre. 

> [!NOTE] 
> Vous ne pouvez pas répartir une somme supérieure au montant budgétaire d’origine pour les valeurs de dimensions financières. 

Après avoir paramétré la budgétisation de base et le contrôle budgétaire, utilisez les procédures suivantes pour ajouter des informations sur les répartitions au niveau de la budgétisation de base et du contrôle budgétaire.

### <a name="how-do-i-define-budget-codes-for-the-apportionment-budget-type"></a>Comment définir les codes budget pour le type de budget Répartition ?

Vous pouvez définir un ou plusieurs codes budget pour le type de budget Répartition sur la page **Codes budget**. Vous devez définir les codes budget correspondant au type de budget d’origine lors du paramétrage de la budgétisation de base. Lorsque vous créez un code budget et une description du budget, sélectionnez également le type de budget Répartition.

Utilisez des codes budget pour le type de budget de répartition lorsque vous entrez des écritures de registre budgétaires pour les montants budgétaires répartis. Utilisez des codes budget pour le type de budget d’origine lorsque vous entrez des écritures de registre budgétaires pour les montants budgétaires d’origine.

### <a name="how-do-i-configure-budget-control-for-apportionments"></a>Comment configurer le contrôle budgétaire pour les répartitions ?

La page **Configuration du contrôle budgétaire** contient des options pour utiliser les répartitions. 

Dans la section **Fonds budgétaires disponibles**, lorsque vous sélectionnez l’option **N’utiliser que le montant réparti**, les autres options sous **Montants à additionner** deviennent indisponibles. En outre, le calcul des fonds budgétaires disponibles inclut uniquement les montants répartis dans les montants à additionner. Généralement, vous incluriez les dépenses réelles, les réservations budgétaires pour les engagements, les réservations budgétaires pour les engagements non confirmées, et les réservations budgétaires pour les engagements préalables dans les montants à soustraire. 

> [!NOTE] 
> Lorsque vous sélectionnez l’option **N’utiliser que le montant réparti**, le budget d’origine, les transferts et les révisions sont toujours suivis sans toutefois être utilisés dans le calcul. 

Dans la section **Documents et journaux**, lorsque vous sélectionnez **Demandes d’achat**, notez que les options pour les commandes fournisseur et les factures fournisseur sont automatiquement sélectionnées. 

Après avoir défini des codes budget pour la budgétisation de base et configuré le contrôle budgétaire pour les répartitions, vous pouvez créer des écritures de registre budgétaires pour les types de budget d’origine et de répartition. Pour plus d’informations, voir « Comment créer et afficher un budget préliminaire ? » plus loin dans cette rubrique.

### <a name="tips"></a>Conseils

Sur la page **Écritures de registre budgétaires**, vous pouvez effectuer le suivi et l’audit des activités budgétaires pour les répartitions en affichant :

-   Soldes budgétaires
-   Statistiques de contrôle budgétaire
-   Comparatif totaux réels/totaux de budget
-   Écritures de registre budgétaires qui incluent le budget d’origine et les répartitions

Vous pouvez également effectuer le suivi et l’audit des activités budgétaires pour les répartitions à partir des pages suivantes :

-   La page **Budgets périodiques** affiche les soldes budgétaires et les soldes de répartition par période, les montants cumulés et les pourcentages cumulés de la somme du budget et des répartitions pour toutes les périodes.
-   La page **Statistiques de contrôle budgétaire** affiche les soldes budgétaires pour un cycle budgétaire et un modèle de budget. Pour afficher des détails supplémentaires, sélectionnez une ligne dans la grille, puis cliquez sur **Répartitions**. Une fois les demandes d’achat et les commandes fournisseur validées, la page **Statistiques de contrôle budgétaire** vous permet d’afficher les réservations budgétaires pour les engagements et les engagements préalables. **Remarque :** Les champs **Répartitions** et **Budget préliminaire** apparaissent uniquement si vous avez sélectionné **Budget préliminaire** et **N’utiliser que le montant réparti** dans la section **Fonds budgétaires disponibles** de la page **Configuration du contrôle budgétaire**.
-   La page **Comparatif Réel/Budget par période** affiche le comparatif des dépenses réelles et de la somme des écritures de registre budgétaires pour la période :
    -   Le champ **Répartitions** contient la somme de toutes les écritures de registre budgétaires de répartition pour le modèle de budget et les valeurs de dimension.
    -   La colonne **Montant de l’écart** affiche le résultat du calcul suivant : Répartition pour la période - réel pour la période = montant de l’écart pour la période.
    -   Le champ **Budget préliminaire** contient la somme de toutes les écritures de registre budgétaires préliminaires pour le modèle de budget et les valeurs de dimension.

## <a name="set-up-budgeting-and-budget-control-for-a-preliminary-budget"></a>Paramétrage de la budgétisation et du contrôle budgétaire pour un budget préliminaire
Après avoir paramétré la budgétisation de base et le contrôle budgétaire, utilisez les procédures suivantes pour ajouter des informations sur les budgets préliminaires au niveau de la budgétisation de base et du contrôle budgétaire. 

Vous pouvez créer un budget temporaire préliminaire pendant l’examen et l’approbation du budget réel. Si vous utilisez le contrôle budgétaire, vous pouvez sélectionner les documents source et les journaux comptables à évaluer pour le contrôle budgétaire pendant que vous utilisez le budget préliminaire. Vous pouvez assurer le suivi des montants budgétaires préliminaires en utilisant des codes budget distincts pour le type de budget Préliminaire. Ensuite, une fois que le budget approuvé est adopté, les montants budgétaires préliminaires peuvent être réduits à mesure que les montants budgétaires approuvés sont augmentés.

### <a name="how-do-i-define-budget-codes-for-the-preliminary-budget-type"></a>Comment définir des codes budget pour le type de budget Préliminaire ?

Vous pouvez définir des codes budget pour le type de budget Préliminaire sur la page **Codes budget**. Pour assurer le suivi de différentes catégories d’écritures de registre budgétaires préliminaires, vous pouvez définir plusieurs codes budget pour le type de budget préliminaire. 

Vous devez définir les codes budget correspondant au type de budget d’origine lors du paramétrage de la budgétisation de base. Lorsque vous créez un code budget et une description du budget, sélectionnez également le type de budget Préliminaire. 

Utilisez des codes budget pour le type de budget préliminaire lorsque vous entrez des écritures de registre budgétaires pour les montants budgétaires préliminaires. Utilisez des codes budget pour le type de budget d’origine lorsque vous entrez des écritures de registre budgétaires pour les montants budgétaires d’origine.

### <a name="how-do-i-configure-budget-control-for-preliminary-budgets"></a>Comment configurer le contrôle budgétaire pour les budgets préliminaires ?

La page **Configuration du contrôle budgétaire** contient les options pour utiliser les budgets préliminaires. Dans la section **Fonds budgétaires disponibles**, sélectionnez l’option **Budget préliminaire**. Notez que vous devrez peut-être cliquer sur **Créer un brouillon** pour poursuivre. 

> [!NOTE]
> Si les budgets préliminaires sont inclus dans le calcul des fonds budgétaires disponibles, il est important de contrepasser les écritures de registre budgétaires préliminaires lorsque les écritures de registre budgétaires d’origine sont enregistrées dans les soldes budgétaires. Si les écritures de registre budgétaires associées à des codes budget préliminaire ne sont pas contrepassées, les types de budget préliminaire et d’origine sont ajoutés, ce qui surévalue le solde disponible. Pour plus d’informations, voir « Comment contrepasser un budget préliminaire ? » plus loin dans cet article. Dans la section **Documents et journaux**, lorsque vous sélectionnez l’option **Demandes d’achat**, notez que les options pour les commandes fournisseur et les factures fournisseur sont automatiquement sélectionnées.


## <a name="create-view-and-reverse-a-preliminary-budget"></a>Création, affichage et contrepassation d’un budget préliminaire
Après avoir paramétré la budgétisation de base et le contrôle budgétaire pour le budget préliminaire, vous pouvez créer des écritures de registre budgétaires pour le type de budget préliminaire.

### <a name="how-do-i-create-and-view-a-preliminary-budget"></a>Comment créer et afficher un budget préliminaire ?

Vous pouvez créer des écritures de registre budgétaires préliminaires pour un modèle de budget et des valeurs de dimension spécifiques. Une fois le budget réel approuvé, vous pouvez créer des écritures de registre budgétaires d’origine.

#### <a name="tips"></a>Conseils

Pour afficher des informations supplémentaires sur les budgets préliminaires, sélectionnez les recherches suivantes :

-   La page **Statistiques de contrôle budgétaire** vous permet d’afficher les soldes budgétaires pour un cycle budgétaire et un modèle de budget. Une fois les demandes d’achat et les commandes fournisseur validées, vous pouvez afficher les réservations budgétaires pour les engagements et les engagements préalables.
-   La page **Comparatif Réel/Budget** vous permet d’afficher le comparatif des dépenses réelles et de la somme des écritures de registre budgétaires pour la période. Le champ **Budget préliminaire** contient la somme de toutes les écritures de registre budgétaires préliminaires pour le modèle de budget et pour les valeurs de dimension.

### <a name="how-do-i-reverse-a-preliminary-budget"></a>Comment contrepasser un budget préliminaire ?

Lorsque vous créez une écriture budgétaire d’origine et que vous utilisez le modèle de budget et des valeurs de dimension qui contiennent des montants budgétaires préliminaires, ceux-ci peuvent être contrepassés. Par exemple, vous pouvez entrer un montant budgétaire préliminaire de 2 500 dollars dans le compte général 50 000. Par la suite, si vous entrez un montant budgétaire d’origine de 10 000 dollars dans le compte général 50 000, le montant budgétaire préliminaire de 2 500 dollars sera contrepassé. Le compte général 50000 afficherait un montant budgétaire de 10 000 €. 

Vous pouvez afficher les écritures de registre budgétaires pour le budget d’origine en sélectionnant l’écriture de compte budgétaire dans l’organisateur **Écritures de compte budgétaires** de la page **Écriture de registre budgétaire**. Dans la barre de menus, cliquez sur **Informations associées**, puis sur **Écritures de registre budgétaires**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]