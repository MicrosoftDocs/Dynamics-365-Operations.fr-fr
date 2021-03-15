---
title: Documents justificatifs de planification budgétaire
description: Les documents justificatifs fournissent des informations narratives pour ceux qui demandent un budget pour expliquer pourquoi un budget spécifique est nécessaire.
author: panolte
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9ca0c291b5d446325f6be6b6bed612bd26e7c640
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019201"
---
# <a name="budget-planning-justification-documents"></a>Documents justificatifs de planification budgétaire

[!include [banner](../includes/banner.md)]

Les documents justificatifs fournissent des informations narratives pour ceux qui demandent un budget pour expliquer pourquoi un budget spécifique est nécessaire. 

Un modèle de plan budgétaire est créé par le responsable du budget dans Microsoft Word et affecté au processus de planification budgétaire actuel. Les propriétaires de budget peuvent alors ouvrir le modèle et renseigner automatiquement les données dans Word selon leur demande de budget. Ils peuvent ensuite ajouter du texte ou des données supplémentaires avant d’enregistrer et de joindre leur document justificatif personnalisé à leur plan budgétaire.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Configurer le complément Office Microsoft Dynamics pour Microsoft Word

1.  Ouvrez un nouveau document Microsoft Word.
2.  Cliquez sur **Insérer** sur le ruban, puis sur **Magasin**.
3.  Recherchez le complément Office Microsoft Dynamics et cliquez sur **Ajouter**.
4.  Dans Word, dans le volet droit, cliquez sur **Ajouter des informations sur le serveur**.
5.  Tapez ou collez l’URL du serveur et cliquez sur **OK**.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Définir le modèle de justification dans Microsoft Word

1.  Cliquez sur **Créer** dans le complément Office Microsoft Dynamics une fois que vous êtes connecté.
2.  Pour les informations d’en-tête, utilisez le bouton **Ajouter des champs**.
3.  Sélectionnez la source de données d’entité BudgetPlanJustification, puis cliquez sur **Suivant**. **Remarque :** cette entité est requise pour tout document justificatif. D’autres entités peuvent être utilisées mais le téléchargement vers Microsoft Dynamics 365 Finance échouera si cette entité n’est pas incluse.
4.  Ajoutez les étiquettes et les valeurs BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter et DocumentNumber dans le document Word. **Remarque :** vous pouvez utiliser vos propres étiquettes personnalisées au lieu des étiquettes standard, si nécessaire.
5.  Cliquez sur **Terminé** pour terminer la section d’en-tête.
6.  Pour le détail au niveau de la ligne des montants du plan budgétaire, cliquez sur **Ajouter une table**.
7.  Sélectionnez à nouveau la source de données d’entité BudgetPlanJustification, puis cliquez sur **Suivant**.
8.  Ajoutez des champs pour EffectiveDate, ScenarioName, AccountDisplayValue et AccountingCurrencyExpenseAmount. **Remarque :** si vous souhaitez ajouter des commentaires dans les lignes de plan budgétaire individuelles, ceux-ci peuvent être ajoutés à la table ici.
9.  Ajoutez des instructions supplémentaires à fournir à l’utilisateur final, puis appliquez la mise en forme ou le style nécessaire au document.
10. Enregistrez le document sur votre ordinateur local et fermez le fichier avant de continuer.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Paramétrer le processus de planification budgétaire pour utiliser le modèle de justification

1.  Accédez à **Budgétisation** &gt; **Paramétrage** &gt; **Planification budgétaire** &gt; **Modèles de document justificatif**.
2.  Cliquez sur **Nouveau** et accédez à votre document Microsoft Word nouvellement créé.
3.  Entrez un nom complet et une description pour le modèle. Cliquez sur **OK**.
4.  Accédez à **Budgétisation** &gt; **Paramétrage** &gt; **Planification** **budgétaire** &gt; **Processus de planification budgétaire**.
5.  Sélectionnez le processus dans lequel le modèle de justification doit être utilisé, puis cliquez sur **Modifier**.
6.  Dans le champ **Modèle de document de justificatif**, sélectionnez le modèle approprié et enregistrez-le.

##### <a name="edit-and-save-personalized-justification-documents"></a>Modifier et enregistrer les documents justificatifs personnalisés

1.  Créez un nouveau plan budgétaire ou ouvrez un plan budgétaire existant.
2.  Dans le menu déroulant **Justification**, sélectionnez **Créer une justification**.
3.  Après avoir renseigné les détails, sélectionnez pour télécharger le document personnalisé à partir du menu déroulant **Justification**.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]