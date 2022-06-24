---
title: Ajouter de nouveaux champs à un modèle de document commercial dans Microsoft Excel
description: Cet article fournit des informations sur l’ajout de nouveaux champs à un modèle de document commercial dans Microsoft Excel à l’aide de la fonction de gestion de documents commerciaux.
author: NickSelin
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 8395a87e88ebbd1942c87da0cecebe6d25bdf625
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869400"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>Ajouter de nouveaux champs à un modèle de document commercial dans Microsoft Excel

[!include[banner](../includes/banner.md)]

Vous pouvez ajouter de nouveaux champs à un modèle utilisé pour générer des documents commerciaux dans le format Microsoft Excel. Ces champs peuvent être ajoutés comme espaces réservés qui sont utilisés pour compléter les documents générés avec les informations requises depuis l’application. Pour chaque champ que vous ajoutez, vous pouvez également préciser un lien vers les sources de données afin de préciser quelles données d’application seront saisies dans le champ lorsque le modèle est utilisé pour générer des documents commerciaux.

Pour en savoir plus sur cette fonctionnalité, exécutez l’exemple décrit dans cet article. Cet exemple présente comment mettre à jour un modèle pour compléter les champs dans les formulaires de facture financière qui sont générés.

## <a name="configure-business-document-management-to-edit-templates"></a>Configurer le module Gestion de document commercial pour modifier les modèles

Comme le module Gestion de document commercial repose sur la structure [Vue d’ensemble de la gestion des états électroniques](general-electronic-reporting.md), vous devez configurer les paramètres des états électroniques et du module Gestion de document commercial avant de pouvoir commencer à utiliser ce dernier.

1.  Connectez-vous à l’instance de Microsoft Dynamics 365 Finance en tant qu’administrateur système.
2.  Suivez les étapes suivantes de l’exemple de l’article [Vue d’ensemble du module Gestion de document commercial](er-business-document-management.md) :

    1.  Configurez les paramètres de gestion des états électroniques.
    2.  Activez le module Gestion de document commercial.

Vous pouvez maintenant commencer à utiliser le module Gestion de document commercial pour modifier les modèles de document commercial.

## <a name="import-er-solutions-that-contain-a-template"></a>Importez les solutions de gestion des états électroniques qui contiennent un modèle.

L’exemple de cette procédure utilise la solution de gestion des états électroniques publiée officiellement. Vous devez importer les configurations de gestion des états électroniques de cette solution dans votre instance actuelle de Finance.

La configuration du format de gestion des états électroniques **Facturation financière (Excel)** de cette solution contient le modèle de document commercial au format Excel qui peut être modifié à l’aide du module Gestion de document commercial. Importez la dernière version de cette configuration du format de gestion des états électroniques depuis Microsoft Dynamics Lifecycle Service (LCS). Le modèle de données de gestion des états électroniques correspondants et les configurations de mise en correspondance du modèle de gestion des états électroniques seront importés automatiquement.

Pour plus d’informations sur la manière d’importer des configurations de gestion des états électroniques, voir [Gérer le cycle de vie de la configuration des états électroniques](general-electronic-reporting-manage-configuration-lifecycle.md).

![Page de bibliothèque d’actifs partagés LCS.](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>Modifiez le modèle de solution de gestion des états électroniques

1.  Connectez-vous en tant qu’utilisateur avec accès à l’espace de travail **Gestion de document commercial**.
2.  Ouvrez l’espace de travail du module **Gestion de document commercial**.

    ![Espace de travail du module Gestion de document commercial.](./media/BDM-AddFldExcel-Workspace.png)

3.  Dans la grille, sélectionnez le modèle **Facture financière (Excel)**.
4.  Dans le volet droit, sélectionnez **Nouveau modèle** pour créer un modèle basé sur le modèle sélectionné.
5.  Dans le champ **Titre**, entrez **Facture financière (Excel) Contoso** comme titre du nouveau modèle.
6.  Cliquez sur **OK** pour confirmer le début du processus de modification.

La page Éditeur de modèle BDM s’affiche. Vous pouvez utiliser Microsoft 365 pour modifier le modèle sélectionné en ligne dans le contrôle intégré.

![Page Éditeur de modèle BDM.](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>Ajoutez le libellé pour un nouveau champ au modèle

1.  Sur la page Éditeur de modèle BDM, sur le ruban Excel, sur l’onglet **Afficher**, sélectionnez les cases **En-têtes et grilles de ligne** pour le modèle Excel modifiable.

    ![Cases à cocher En-têtes et Lignes de grille sélectionnées.](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  Sélectionnez les cellules **E8:F8**.
3.  Dans le ruban d’Excel, sur l’onglet **Accueil**, sélectionnez **Fusionner et centrer** pour fusionner les cellules sélectionnées en une cellule fusionnée **E8:F8**.
4.  Dans la cellule fusionnée **E8:F8**, saisissez **URL**.
5.  Sélectionnez la cellule fusionnée **E7:F7**, sélectionnez **Reproduire la mise en forme**, puis sélectionnez la cellule fusionnée **E8:F8** pour la formater de la même manière que la cellule fusionnée **E7:F7**.

    ![Nouveau libellé de champ ajouté au modèle.](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>Formater le modèle pour réserver l’espace pour un nouveau champ

1.  Sur la page Éditeur de modèle BDM, sélectionnez la cellule fusionnée **G8:H8**.
2.  Dans le ruban d’Excel, sur l’onglet **Accueil**, sélectionnez **Fusionner et centrer** pour fusionner les cellules sélectionnées en une cellule fusionnée **G8:H8**.
3.  Sélectionnez la cellule fusionnée **G7:H7**, sélectionnez **Reproduire la mise en forme**, puis sélectionnez la cellule fusionnée **G8:H8** pour la formater de la même manière que la cellule fusionnée **G7:H7**.

    ![Espace réservé pour le nouveau champ.](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  Dans le champ **Nom**, sélectionnez **CompanyInfo**.

    La plage **CompanyInfo** du modèle Excel actuel contient tous les champs qui sont utilisés pour remplir l’en-tête d’un état généré avec les détails de la société actuelle en tant que vendeur.

    ![Plage CompanyInfo sélectionnée.](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>Ajouter un nouveau champ au modèle

1.  Dans la page **Éditeur de modèle BDM**, dans le volet Actions, sélectionnez **Afficher le format**.
2.  Dans le volet **Structure de modèle**, sélectionnez **Ajouter**.

    > [!NOTE]
    > Vous devez ajuster la section du modèle à utiliser comme nouveau champ. Vous avez déjà apporté cet ajustement en formatant la cellule fusionnée **G8:H8**.

    ![Ajout d’un nouveau champ au modèle.](./media/BDM-AddFldExcel-AddCell.png)

3.  Sélectionnez **Excel\Cellule** pour ajouter un nouveau champ comme cellule dans le modèle.

    Vous pouvez sélectionner **Excel\Plage** si vous souhaitez ajouter une plage au modèle. La plage saisie peut contenir plusieurs cellules. Vous pouvez ajouter ces cellules ultérieurement.
    
    Observez que le composant modèle **CompanyInfo** est automatiquement sélectionné dans le volet **Structure du modèle**, car il s’agit du composant parent le plus approprié dans la structure de modèle actuelle pour le champ que vous ajoutez.
    
4.  Dans le champ **Plage Excel**, entrez **CompanyURL_Value**.
5.  Cliquez sur **OK**.

    ![Champ CompanyURL_Value ajouté à la structure de modèle.](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  Dans le volet **Structure du modèle**, sélectionnez le bouton représentant les points de suspension (…), et sélectionnez **Afficher les liaisons**.

    ![Afficher les liaisons sélectionnées.](./media/BDM-AddFldExcel-ShowBindings.png)

    Le volet **Structure du modèle** affiche maintenant les sources de données disponibles au format de gestion des états électroniques sous-jacents.

7.  Sélectionnez **CompanyInfo_Value** comme le champ que vous prévoyez de lier à une source de données du format de gestion des états électroniques sous-jacents.
8.  Dans la section **Sources de données** du volet **Structure du modèle**, développez **Modèle \> InvoiceBase \> CompanyInfo**.
9.  Sous **CompanyInfo**, sélectionnez l’élément **WebsiteURI**.

    ![Élément WebsiteURI sélectionné.](./media/BDM-AddFldExcel-BindURL.png)

10. Sélectionnez **Lier**.
11. Dans le volet **Structure de modèle**, sélectionnez **Enregistrer**, puis fermez la page Éditeur de modèle BDM.

Dans l’espace de travail **Gestion de document commercial**, l’onglet **Modèle** dans le volet de droit présente le modèle mis à jour. Dans la grille, notez que le champ **Statut** pour le modèle modifié a été modifié sur **Brouillon**, et le champ **Révision** n’est plus vide. Ces modifications indiquent que le processus de modification de ce modèle a commencé.

![Modèle modifié dans l’espace de travail Gestion de document commercial.](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>Revoir les paramètres de société

1.  Accédez à **Administration d’organisation \> Organisations \> Entités juridiques**.
2.  Dans l’organisateur **Informations de contact**, vérifiez que l’URL de la société est entrée.

![URL de société entrée sur la page Entités juridiques.](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>Générer des documents commerciaux pour tester le modèle mis à jour

1.  Dans l’application, modifiez la société **USMF**, puis accédez à **Comptabilité client \> Factures \> Toutes les factures financières**.
2.  Sélectionnez la facture **FTI-00000002**, puis sélectionnez **Gestion de l’impression**.
3.  Dans le volet gauche, développez **Module – Comptabilité client \> Documents \> Facture financière**.
4.  Sous **Facture financière**, sélectionnez le niveau **Document d’origine** pour préciser le champ des factures à traiter.
5.  Dans le volet droit, dans le champ **Format de l’état**, sélectionnez le modèle **Facture financière (Excel) Contoso** pour le niveau spécifié de document.

    ![Modèle Facture financière (Excel) Contoso sélectionné.](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  Appuyez sur **Échap** pour fermer la page actuelle.
7.  Sélectionnez **Imprimer \> Sélectionné**.
8.  Téléchargez le document généré, puis rouvrez-le dans Excel.

    ![Facture financière dans Excel.](./media/BDM-AddFldExcel-PreviewReport.png)

Le modèle révisé est utilisé pour générer l’état de facture financière pour l’article sélectionné. Pour analyser la manière dont cet état est affecté par les modifications apportées au modèle, vous pouvez exécuter cet état dans une session de l’application immédiatement après avoir modifié le modèle dans une autre session de l’application.

## <a name="related-links"></a>Liens connexes

[Vue d’ensemble des états électroniques (ER)](general-electronic-reporting.md)

[Vue d’ensemble de la gestion de document commercial](er-business-document-management.md)

[Concevoir une configuration pour générer des états au format OPENXML](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]