---
title: "Modèles de planification budgétaire pour Excel"
description: "Cette rubrique décrit la procédure de création des modèles de Microsoft Excel qui peuvent être utilisés avec les plans budgétaires."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261794
ms.assetid: 1d8e99c1-b70d-41ba-991e-ab50b16797e0
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 0e2eb6e7c130f03edbf60a185d397d94b5d61d7d
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-templates-for-excel"></a>Modèles de planification budgétaire pour Excel

Cette rubrique décrit la procédure de création des modèles de Microsoft Excel qui peuvent être utilisés avec les plans budgétaires.

Affiche la de cette rubrique comment créer les modèles Excel qui seront utilisés avec les plans budgétaires à l'aide de l'ensemble de données standard de démonstration et la connexion d'utilisateur Administrateur. Pour plus d'informations sur la planification budgétaire, voir [vue d'ensemble de la planification budgétaire.] (budget-planning-overview-configuration.md) Vous pouvez également suivre planification budgétaire [101] le didacticiel (budget-plan.md) pour en savoir des principes de configuration et d'utilisation du module de base.

## <a name="generate-a-worksheet-using-budget-plan-document-layout"></a>Générez une feuille de calcul à l'aide de le modèle de document de plan budgétaire
Les documents de plan du budget peuvent être affichés et modifier des entrepôts dans un ou plusieurs mises en page. Chaque mise en page peut être associé à un modèle de document associé de plan budgétaire pour afficher et modifier les données de plan budgétaire dans une feuille de calcul Excel. Dans cette rubrique, un modèle de document de plan budgétaire sera généré à l'aide d'une configuration existante de mise en page. Ouvrez ** les plans budgétaires répertorient ** (** budgétisation **&gt; ** des plans budgétaires **). Cliquez sur ** nouveau ** pour créer un document de plan budgétaire. ![bpt1 [] (. /media/bpt11-1024x552.png)](. /media/bpt11.png) 

Utilisent ** Ajouter ** la ligne option pour ajouter des lignes. Cliquez sur ** dispositions ** pour afficher la configuration du modèle de document de plan budgétaire. 
![bpt2 [] (. /media/bpt2-1024x274.png)](. /media/bpt2.png) 

Vous pouvez revoir la configuration de disposition et l'ajuster selon vos besoins. Atteindre ** modèle ** &gt; ** se produisent ** pour créer un fichier Excel pour cette mise en page. Une fois le modèle soit généré, passez ** modèle ** &gt; ** à la vue ** pour ouvrir et examiner le modèle de document de plan budgétaire. Vous pouvez enregistrer le fichier Excel dans le lecteur local. ![bpt3 [] (. /media/bpt3-1024x545.png)](. /media/bpt3.png) 

> [!NOTE] 
> La mise en page du document de plan budgétaire ne peut pas être modifiée une fois qu'un modèle Excel soit associé. Pour modifier la mise en page, supprimez le fichier associé Modèle Excel et régénérez- le. Requis pour conserver les champs de la mise en page et la feuille de calcul synchronisées. 

Modèle Excel qui contiendra tous les éléments de la mise en page du document de plan budgétaire, où ** disponible dans la feuille de calcul ** la colonne est définie sur Vrai. Se chevauchant n'est pas autorisé des éléments dans le modèle Excel. Par exemple, si la mise en page contient des colonnes de la demande Q1, de la demande Q2, de la demande Q3, et la demande Q4, et une colonne de demande totale qui représente la somme de chacune des 4 colonnes trimestrielles, seuls les colonnes ou la colonne trimestrielles total est disponible pour être utilisée dans le modèle Excel. Le fichier Excel ne peut pas chevaucher mettre à jour des colonnes de mise à jour car les données de la table peut devenir démodées et inexactes.

![bpt4 [] (. /media/bpt4-1024x615.png)](. /media/bpt4.png)

> [!NOTE] 
> Pour éviter les problèmes de potentiel avec les données de plan budgétaire d'affichage et de modification dans Excel, le même utilisateur doit être enregistré dans Dynamics 365 pour les opérations et le Business Connector de données de complément Office de Microsoft Dynamics.

## <a name="add-a-header-to-budget-plan-document-template"></a>Ajoutez un en-tête au modèle de document de plan budgétaire
Pour ajouter des informations d'en-tête, sélectionnez la ligne supérieure du fichier Excel et insérer les lignes vides. Cliquez sur ** conception ** dans ** Business de données ** pour ajouter des champs d'en-tête au fichier Excel.

![bpt5 [] (. /media/bpt5-1024x615.png)](. /media/bpt5.png) 

Dans ** conception ** l'onglet, ** ** cliquez sur ** ajoutez ** les champs, puis sélectionnez ** BudgetPlanHeader ** comme source de données d'entité.

![bpt6 [] (. /media/bpt6-1024x615.png)](. /media/bpt6.png)

Indiquent le curseur l'emplacement souhaité dans le fichier Excel. Cliquez sur ** ajoutez l'étiquette ** pour ajouter l'étiquette de champ à l'emplacement sélectionné. Sélectionnez ** ajoutez la valeur ** pour ajouter le champ de valeur à l'emplacement sélectionné. Cliquez sur ** fait ** pour fermer le Concepteur.

## <a name="bpt7mediabpt7pngmediabpt7png"></a>![bpt7 [] (. /media/bpt7.png)](. /media/bpt7.png)

<a name="add-a-calculated-column-to-budget-plan-document-template-table"></a>Ajoutent une colonne calculée à la table de modèle de document de plan budgétaire
--------------------------------------------------------------

Ensuite, des colonnes calculées sont ajoutées au modèle de document généré de plan budgétaire. A ** demande totale ** colonne, qui résume la demande Q1 : Demander des colonnes Q4, et ** ajustement ** une colonne, qui doit recalculer ** demande totale ** la colonne par un facteur prédéfini.

Cliquez sur ** conception ** dans ** Business de données ** permet d'ajouter des colonnes à la table. Cliquez sur ** modifiez ** en regard ** BudgetPlanWorksheet ** de la source de données pour démarrer ajouter des colonnes.

![bpt8 [] (. /media/bpt8-1024x301.png)](. /media/bpt8.png) 

Le groupe de champs sélectionné affiche les colonnes disponibles dans le modèle. Cliquez sur ** formule ** pour ajouter une nouvelle colonne. Saisie d'un nom pour la nouvelle colonne puis coller la formule dans ** formule ** le champ. Cliquez sur ** mise à jour ** pour insérer la colonne.

![bpt12 [] (. /media/bpt12-1024x565.png)](. /media/bpt12.png)

> [!NOTE] 
> Pour définir la formule, Créer une formule dans la feuille, puis la copient vers ** conception ** la fenêtre. Dynamics 365 pour la table associée par opérations est généralement appelé « AXTable1 ». Par exemple, pour résumer la demande Q1 : Demander des colonnes Q4 dans la feuille, la formule = la demande Q4\]de la demande Q3\]+AxTable1\[de la demande Q2\]+AxTable1\[de la demande Q1\]+AxTable1\[d'AxTable1\[.

Répétez ces étapes pour insérer ** ajustement ** la colonne. Utilisez la formule = la demande\]\*$I$1 total d'AxTable1\[pour cette colonne. Il prend la valeur dans la cellule I1 et multipliera les valeurs dans ** demande totale ** la colonne pour calculer les montants d'ajustement.

Enregistrez et fermez le fichier Excel. Revenez à Dynamics 365 pour les opérations, et dans ** des mises en page **, cliquez sur ** chargement &gt; de modèle ** pour télécharger le modèle Excel enregistré à utiliser pour le plan budgétaire. 

![bpt10 [] (. /media/bpt10-1024x352.png)](. /media/bpt10.png) 

Ferment ** des mises en page ** le curseur. Dans ** plan budgétaire ** le document, cliquez sur ** feuille de calcul ** permet d'afficher et de modifier le document dans Excel. Notez que le modèle Excel ajusté a été utilisé pour créer cette feuille de calcul de plan budgétaire et des colonnes calculées sont mises à jour à l'aide de les formules qui ont été définies dans les étapes précédentes. 

![bpt11 [] (. /media/bpt111-1024x431.png)](. /media/bpt111.png)

## <a name="tips--tricks-for-creating-budget-plan-templates"></a>Inclinent et dupent pour créer des modèles de plan budgétaire
### <a name="can-i-add-and-use-additional-data-sources-to-a-budget-plan-template"></a>Des que je peux ajouter et utiliser des sources de données supplémentaires à un modèle de plan budgétaire ?

Oui, vous pouvez utiliser ** conception ** le menu pour ajouter les entités supplémentaires à la même compte ou d'autres journaux dans le modèle Excel. Par exemple, vous pouvez ajouter ** BudgetPlanProposedProject ** la source de données pour créer et tenir à jour une liste des projets proposés en même temps lorsque vous travaillez avec des données de plan budgétaire dans Excel. Notez que notamment des sources de données à fort débit peut affecter les performances du classeur Excel. 

Vous pouvez utiliser ** filtre ** l'option dans ** Business de données ** d'ajouter des filtres souhaités aux sources de données supplémentaires.

### <a name="can-i-hide-the-design-option-in-the-data-connector-for-other-users"></a>Des que je peux masquer l'option de conception dans le Business de données pour d'autres utilisateurs ?

Oui, ouvrez ** Business de données ** les options de masquer ** conception ** l'option d'autres utilisateurs.

![bpt13 [] (. /media/bpt13-1024x565.png)](. /media/bpt13.png)

Développent ** options de Business Connector de données ** et désactivez ** activent la conception ** la case à cocher. Cela masquera ** conception ** l'option du ** Business de données **.

![bpt14 [] (. /media/bpt14-1024x592.png)](. /media/bpt14.png)

### <a name="can-i-prevent-users-from-accidently-closing-the-data-connector-while-working-with-data"></a>Des que je peux empêcher les utilisateurs de fermer par erreur le Business Connector de données lors de l'utilisation des données ?

Nous vous recommandons de verrouiller le modèle pour empêcher les utilisateurs de le clôturer. Pour démarrer le verrouillage, cliquez sur ** Business de données **, dans le coin supérieur droit de qu'une flèche apparaît. 

![bpt15 [] (. /media/bpt15-1024x285.png)](. /media/bpt15.png) 

Cliquent sur la flèche pour un menu supplémentaire. Sélectionnez ** verrouillage **.

### <a name="bpt16mediabpt16-1024x614pngmediabpt16png"></a>![bpt16 [] (. /media/bpt16-1024x614.png)](. /media/bpt16.png)

### <a name="can-i-use-other-excel-features-like-cell-formatting-colors-conditional-formatting-and-charts-with-my-budget-plan-templates"></a>Des que je peux utiliser d'autres fonctionnalités d'Excel, telles que la mise en forme de la cellule, les couleurs, la mise en forme conditionnelle, et les graphiques à mes modèles de plan budgétaire ?

Oui, la plupart des fonctionnalités standard de calcul Excel par lots dans des modèles de plan budgétaire. Nous vous recommandons d'utiliser des couleurs-codes pour les utilisateurs distinguent les colonnes en lecture seule et modifiables. La mise en forme conditionnelle peut être utilisée pour mettre des zones en surbrillance problématiques du budget. Les totaux de colonne peuvent facilement être présentées à l'aide de formules standard de calcul Excel au-dessus de la table.

Vous pouvez également créer et utiliser des tables et des graphiques pour le regroupement supplémentaires et une visualisation croisé dynamique des données du budget. Sous ** des données ** onglet, ** des connexions ** au groupe, cliquez sur ** actualisez tous **, puis cliquez sur ** des propriétés de connexion **. Cliquez sur ** utilisation ** l'onglet. Sous ** l'actualisez **, sélectionnez ** actualiser les données en ouvrant le fichier ** la case à cocher. 

![bpt17 [] (. /media/bpt17-1024x614.png)](. /media/bpt17.png)


