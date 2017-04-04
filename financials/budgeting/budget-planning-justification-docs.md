---
title: Budget planning justification documents
description: "Les documents de justification fournissent un récit pour ceux qui ont demandé un budget pour expliquer la raison pour laquelle un budget spécifique est nécessaire."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: c86d01fec3d8d7c210c7e73a034f4e9e384a0dcf
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-justification-documents"></a>Budget planning justification documents

Les documents de justification fournissent un récit pour ceux qui ont demandé un budget pour expliquer la raison pour laquelle un budget spécifique est nécessaire. 

Un modèle de plan budgétaire est créé par le responsable du budget dans Microsoft Word et affecté au processus de planification budgétaire actuel. Les propriétaires de budget peuvent ensuite ouvrir le modèle et obtenir des données automatiquement renseignées dans Word selon leur demande de budget. Vous pouvez ensuite ajouter du texte supplémentaire ou des données avant de l'enregistrement et de joindre le document personnalisées de justification à leur plan budgétaire.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Complément Office de Microsoft Dynamics de paramétrage pour Microsoft Word

1.  Ouvrez un document Microsoft Word.
2.  Cliquez sur ** insertion ** dans le ruban, puis cliquez sur ** magasin **.
3.  Recherche de complément Office Microsoft Dynamics et cliquez sur ** ajoutez **.
4.  Dans Word, dans le volet droit, cliquez sur ** ajoutez les informations du serveur **.
5.  Tapez ou collez l'URL du serveur et cliquez sur ** effectué correctement **.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Définissez le modèle de justification dans Microsoft Word

1.  Cliquez sur ** conception ** dans le complément Office de Microsoft Dynamics après avoir connecté.
2.  Pour les informations d'en-tête, utilisez ** ajoutez les champs ** le bouton.
3.  Sélectionnez la source de données d'entité de BudgetPlanJustification, puis cliquez sur Suivant ** **. ** Remarque : ** Cette entité est requise pour tout document de justification. D'autres entités peuvent être utilisées mais le téléchargement vers Microsoft Dynamics 365 pour les opérations échouera si cette entité n'est pas incluse.
4.  Ajoutez le BudgetPlanName, le BudgetPlanPreparer, le ResponsibilityCenter, et les étiquettes et les valeurs de DocumentNumber dans le document Word. ** Remarque : ** Vous pouvez utiliser vos propres étiquettes personnalisées, plutôt que des d'affichage standard, si nécessaire.
5.  Cliquez sur ** fait ** pour honorer la section d'en-tête.
6.  Pour détail de niveau vers ligne des montants de plan budgétaire, cliquez sur ** ajoutez la table **.
7.  Là aussi, sélectionnez la source de données d'entité de BudgetPlanJustification, puis cliquez sur Suivant ** **.
8.  Permet d'ajouter des champs pour EffectiveDate, ScenarioName, AccountDisplayValue, et AccountingCurrencyExpenseAmount. ** Remarque : ** Si les commentaires sont disponibles à ajouter dans le plan budgétaire individuelles, celles peuvent être ajoutés à la table ici.
9.  Ajoutez les instructions supplémentaires de livrer à l'utilisateur, puis effectuez toute mise en forme nécessaire ou du style apparaissant dans le document.
10. Enregistrez le document à votre ordinateur local et de fermer le fichier avant de passer.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Paramétrez le processus de planification budgétaire pour utiliser le modèle de justification

1.  Dans Microsoft Dynamics 365 pour les opérations, passez ** budgétisation ** &gt; ** au paramétrage ** &gt; ** planification budgétaire ** &gt; ** des modèles de document de justification **.
2.  Cliquez sur ** nouveau ** et accéder à votre document Microsoft Word nouvellement créée.
3.  Entrez le nom et la description d'affichage de modèle. Click **OK**.
4.  Allez ** budgétisation ** &gt; ** au paramétrage ** &gt; ** budget ** ** planification ** &gt; ** processus de planification budgétaire **.
5.  Sélectionnez le processus de création du modèle de justification doit être utilisé, puis cliquez sur ** modifiez **.
6.  Dans ** modèle de document de justification ** le champ, sélectionnez le modèle approprié et l'enregistrer.

##### <a name="edit-and-save-personalized-justification-documents"></a>Modification et enregistrer les documents personnalisés de justification

1.  Dans Dynamics 365 pour les opérations, créez un plan budgétaire ou ouvrez un plan budgétaire existant.
2.  Dans ** justification ** le menu déroulant, sélectionnez ** créez la nouvelle justification **.
3.  Après l'avoir complété dans Détails, sélectionnez pour télécharger le document personnalisées ** justification ** du menu déroulant.



