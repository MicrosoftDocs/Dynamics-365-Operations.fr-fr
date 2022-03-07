---
title: Modèles de planification budgétaire pour Excel
description: Cette rubrique décrit la procédure de création de modèles Microsoft Excel qui peuvent être utilisés avec les plans budgétaires.
author: ryansandness
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanSetLayout
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 471c719a8e6de0ebe6fcdad0ae222453db841c87
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443298"
---
# <a name="budget-planning-templates-for-excel"></a>Modèles de planification budgétaire pour Excel

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la procédure de création de modèles Microsoft Excel qui peuvent être utilisés avec les plans budgétaires.

Cette rubrique explique comment créer des modèles Excel qui seront utilisés avec les plans budgétaires à l’aide de l’ensemble de données de démonstration standard et de la connexion utilisateur Administrateur. Pour plus d’informations sur la planification budgétaire, voir [Vue d’ensemble de la planification budgétaire](budget-planning-overview-configuration.md). Vous pouvez également suivre le didacticiel [Planification budgétaire](budget-plan.md) pour connaître les principes de configuration et d’utilisation du module de base.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Générer une feuille de calcul à l’aide de la mise en page des documents du plan budgétaire

Les documents du plan budgétaire peuvent être affichés et modifiés à l’aide d’une ou de plusieurs mises en page. Chaque mise en page peut être associée à un modèle de document de plan budgétaire pour afficher et modifier les données du plan budgétaire dans une feuille de calcul Excel. Dans cette rubrique, un modèle de document de plan budgétaire sera généré à l’aide d’une configuration de mise en page existante. 

1. Ouvrez la liste **Plans budgétaires** (**Budgétisation** &gt; **Plans budgétaires**). 
2. Cliquez sur **Nouveau** pour créer un document de plan budgétaire. 

   [![Liste des plans budgétaires](./media/bpt11-1024x552.png)](./media/bpt11.png) 

3. Utilisez l’option de ligne **Ajouter** pour ajouter des lignes. Cliquez sur **Mises en page** pour afficher la configuration de la mise en page du document de plan budgétaire. 

   [![Ajout de plans budgétaires](./media/bpt2-1024x274.png)](./media/bpt2.png) 

Vous pouvez examiner la configuration de la mise en page et l’ajuster si nécessaire. 
1. Accédez à **Modèle** &gt; **Générer** pour créer un fichier Excel pour cette mise en page. 
2. Une fois le modèle généré, accédez à **Modèle** &gt; **Afficher** pour ouvrir et examiner le modèle de document de plan budgétaire. Vous pouvez enregistrer le fichier Excel sur votre disque local. 

[![Enregistrer sous](./media/bpt3-1024x545.png)](./media/bpt3.png)

> [!NOTE] 
> La mise en page du document de plan budgétaire ne peut pas être modifiée une fois qu’un modèle Excel lui est associée. Pour modifier la mise en page, supprimez le fichier de modèle Excel associé et régénérez-le. Cette opération est nécessaire pour assurer la synchronisation des champs de la mise en page et de la feuille de calcul. 

Le modèle Excel contiendra tous les éléments de la mise en page du document de plan budgétaire, avec la colonne **Disponible dans la feuille de calcul** définie sur Vrai. Les éléments ne peuvent pas se chevaucher dans le modèle Excel. Par exemple, si la mise en page contient les colonnes Demande T1, Demande T2, Demande T3 et Demande T4, et une colonne Demande totale qui représente la somme des 4 colonnes trimestrielles, seules les colonnes trimestrielles ou la colonne de total peuvent être utilisées dans le modèle Excel. Le fichier Excel ne peut pas mettre à jour les colonnes qui se chevauchent pendant la mise à jour, car les données de la table peuvent devenir obsolètes et inexactes.

> [!NOTE] 
> Pour éviter les problèmes potentiels d’affichage et de modification des données du plan budgétaire à l’aide d’Excel, le même utilisateur doit être connecté dans Microsoft Dynamics 365 Finance et le connecteur de données du complément Office Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Ajouter un en-tête au modèle de document de plan budgétaire
Pour ajouter des informations d’en-tête, sélectionnez la ligne supérieure dans le fichier Excel et insérez des lignes vides. Cliquez sur **Créer** dans le **Connecteur de données** pour ajouter des champs d’en-tête au fichier Excel.

Dans l’onglet **Créer**, cliquez sur le champ **Ajouter**, puis sélectionnez **BudgetPlanHeader** comme source de données de l’entité.

Pointez le curseur sur l’emplacement souhaité dans le fichier Excel. Cliquez sur **Ajouter une étiquette** pour ajouter l’étiquette de champ à l’emplacement sélectionné. Sélectionnez **Ajouter une valeur** pour ajouter le champ de valeur à l’emplacement sélectionné. Cliquez sur **Terminé** pour fermer le concepteur.

## <a name="select-add-valuemediabpt7png"></a>[![Sélectionner Ajouter une valeur](./media/bpt7.png)](./media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Ajouter une colonne calculée à la table du modèle de document de plan budgétaire
--------------------------------------------------------------

Ensuite, les colonnes calculées seront ajoutées au modèle de document de plan budgétaire généré. Une colonne **Demande totale** qui récapitule les colonnes Demande T1 : Demande T4, et une colonne **Ajustement** qui recalcule la colonne **Demande totale** selon un facteur prédéfini.

Cliquez sur **Créer** dans le **Connecteur de données** pour ajouter des colonnes à la table. Cliquez sur **Modifier** en regard de la source de données **BudgetPlanWorksheet** pour commencer à ajouter des colonnes.

[![Démarrer l’ajout de colonnes](./media/bpt8-1024x301.png)](./media/bpt8.png) 

Le groupe de champs sélectionné affiche les colonnes disponibles dans le modèle. Cliquez sur **Formule** pour ajouter une nouvelle colonne. Attribuez un nom à la nouvelle colonne, puis collez la formule dans le champ **Formule**. Cliquez sur **Mettre à jour** pour insérer la colonne.

[![Ajouter et insérer une colonne](./media/bpt12-1024x565.png)](./media/bpt12.png)

> [!NOTE] 
> Pour définir la formule, créez la formule dans la feuille de calcul, puis copiez-la dans la fenêtre **Créer**. Une table liée Finance and Operations sera généralement nommée « AXTable1 ». Par exemple, pour récapituler les colonnes Demande T1 : Demande T4 dans la feuille de calcul, utilisez la formule = AxTable1\[Request Q1\]+AxTable1\[Request Q2\]+AxTable1\[Request Q3\]+AxTable1\[Request Q4\].

Répétez ces étapes pour insérer la colonne **Ajustement**. Utilisez la formule = AxTable1\[Total request\]\*$I$1 pour cette colonne. Elle utilise la valeur de la cellule I1 et multiplie les valeurs de la colonne **Demande totale** pour calculer les montants de l’ajustement.

Enregistrez et fermez le fichier Excel. Dans **Mises en page**, cliquez sur **Modèle &gt; Télécharger** pour télécharger le modèle Excel enregistré qui sera utilisé pour le plan budgétaire. 

[![Télécharger un modèle Excel](./media/bpt10-1024x352.png)](./media/bpt10.png) 

Fermez le curseur **Mises en page**. Dans le document **Plan budgétaire**, cliquez sur **Feuille de calcul** pour afficher et modifier le document dans Excel. Notez que le modèle Excel modifié a été utilisé pour créer cette feuille de calcul de plan budgétaire et les colonnes calculées sont mises à jour à l’aide des formules définies dans les étapes précédentes. 

[![Afficher et modifier le document dans Excel](./media/bpt111-1024x431.png)](./media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Conseils et astuces pour la création de modèles de plan budgétaire
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Puis-je ajouter des sources de données supplémentaires à un modèle de plan budgétaire et les utiliser ?

Oui, vous pouvez utiliser le menu **Créer** pour ajouter des entités supplémentaires à la même feuille ou d’autres feuilles du modèle Excel. Par exemple, vous pouvez ajouter la source de données **BudgetPlanProposedProject** pour créer et tenir à jour une liste de projets proposés tout en utilisant les données du plan budgétaire dans Excel. Notez que l’inclusion de sources de données à fort débit peut affecter les performances du classeur Excel. 

Vous pouvez utiliser l’option **Filtrer** du **Connecteur de données** pour ajouter les filtres souhaités aux sources de données supplémentaires.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Puis-je masquer l’option Créer du connecteur de données aux autres utilisateurs ?

Oui, ouvrez les options du **Connecteur de données** pour masquer l’option **Créer** aux autres utilisateurs.

[![Ouvrir les options du connecteur de données](./media/bpt13-1024x565.png)](./media/bpt13.png)

Développez les **Options du connecteur de données** et désactivez la case à cocher **Activer la configuration**. L’option **Créer** sera masquée au **Connecteur de données**.

[![Masquer l’option Créer du connecteur de données](./media/bpt14-1024x592.png)](./media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Puis-je empêcher les utilisateurs de fermer accidentellement le connecteur de données lorsqu’ils utilisent les données ?

Il est recommandé de verrouiller le modèle pour empêcher les utilisateurs de le fermer. Pour activer le verrouillage, cliquez sur **Connecteur de données** dans le coin supérieur droit où une flèche apparaît. 

[![Activer le verrouillage](./media/bpt15-1024x285.png)](./media/bpt15.png) 

Cliquez sur la flèche pour accéder à un menu supplémentaire. Sélectionnez **Verrouiller**.

### <a name="select-lockmediabpt16png"></a>[![Sélectionner Verrouiller](./media/bpt16-1024x614.png)](./media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Puis-je utiliser d’autres fonctionnalités Excel, telles que la mise en forme des cellules, les couleurs, la mise en forme conditionnelle et les graphiques avec mes modèles de plan budgétaire ?

Oui, la plupart des fonctionnalités Excel standard sont compatibles avec les modèles de plan budgétaire. Il est recommandé d’utiliser un code de couleurs pour faire la distinction entre les colonnes en lecture seule et les colonnes modifiables. La mise en forme conditionnelle peut être utilisée pour mettre en surbrillance des zones problématiques du budget. Les totaux des colonnes peuvent facilement être présentés à l’aide de formules Excel standard au-dessus du tableau.

Vous pouvez également créer et utiliser des tableaux croisés dynamiques et des graphiques pour effectuer d’autres regroupements et visualisations des données budgétaires. Sous l’onglet **Données** du groupe **Connexions**, cliquez sur **Actualiser tout**, puis sur **Propriétés de connexion**. Cliquez sur l’onglet **Utilisation**. Sous **Actualiser**, activez la case à cocher **Actualiser les données lors de l’ouverture du fichier**. 



