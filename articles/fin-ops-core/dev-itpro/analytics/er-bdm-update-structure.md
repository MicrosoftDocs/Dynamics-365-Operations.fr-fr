---
title: Mettre à jour la structure d’un modèle de document commercial
description: Cette rubrique explique comment mettre à jour la structure d’un modèle de document commercial à l’aide de la fonctionnalité de gestion des documents commerciaux.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: fd279b28c43e22bec6bf814845fe97828bc96d81
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681326"
---
# <a name="update-the-structure-of-a-business-document-template"></a>Mettre à jour la structure d’un modèle de document commercial 

[!include[banner](../includes/banner.md)]

Dans le volet **Structure du modèle** de l’éditeur de modèles [Gestion des documents commerciaux](er-business-document-management.md), vous pouvez modifier un modèle de document commercial en [ajoutant de nouveaux champs](er-bdm-add-field-to-excel-template.md) à un modèle dans Microsoft Excel. La structure du modèle est ensuite automatiquement mise à jour dans Dynamics 365 Finance, afin qu’il reflète les modifications que vous avez apportées au volet **Structure du modèle**.

Vous pouvez également modifier un modèle en utilisant la fonctionnalité en ligne Office 365. Par exemple, vous pouvez ajouter un nouvel élément nommé, tel qu’une image ou une forme, à la feuille de calcul modifiable. Dans ce cas, la structure du modèle n’est pas automatiquement mise à jour dans Finance et l’élément que vous avez ajouté n’apparaît pas dans la **Structure du modèle**. Mettez à jour manuellement la structure du modèle dans Finance en sélectionnant **Mettre à jour la structure** sur la page de l’éditeur de modèles.

Pour plus d’informations sur cette fonction, réalisez l’exemple suivant.

## <a name="example-update-the-structure-of-a-business-document-template"></a>Exemple : Mettre à jour la structure d’un modèle de document commercial

Cet exemple montre comment un administrateur système peut mettre à jour la structure d’un modèle de document commercial dans Finance une fois le modèle modifié dans Office Online. Les sections suivantes expliquent les étapes impliquées.

### <a name="prepare-a-business-document-template-for-editing"></a>Préparer un modèle de document commercial à modifier

Suivez les procédures suivantes dans [Vue d’ensemble de la gestion des documents commerciaux](er-business-document-management.md).

1. [Configurer les paramètres de gestion des états électroniques](er-business-document-management.md#configure-er-parameters)
2. [Importer des solutions d’ER](er-business-document-management.md#import-er-solutions)
3. [Activer le module Gestion de document commercial](er-business-document-management.md#enable-business-document-management)
4. [Configurer les paramètres](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>Modifier un modèle de document commercial

1. Dans l’espace de travail **Gestion des documents commerciaux**, sélectionnez **Nouveau document**.
2. Sur la page **Créer un modèle**, sélectionnez le modèle **Facture en texte libre (exemple ER) (Excel)**.
3. Sélectionner **Créer un document**.
4. Dans le champ **Titre**, entrez **Exemple FTI Litware**.
5. Sélectionnez **OK** pour créer le modèle.

    > [!NOTE]
    > Si vous n’êtes pas encore connecté à Office Online vous êtes [dirigé vers la page de connexion Office 365](er-business-document-management.md#i-selected-edit-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-microsoft-365-web-page). Pour revenir à votre environnement Finance, sélectionnez le bouton **Précédent** dans votre navigateur.

    Le nouveau modèle est ouvert pour modification dans le contrôle intégré Excel Online sur la page de l’éditeur de modèle.

[![Utilisation de l’espace de travail Gestion des documents commerciaux pour commencer à modifier un modèle de document commercial](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>Examiner la structure actuelle du modèle modifiable

1. Dans Excel Online, sur le ruban, sur l’onglet **Vue**, dans le groupe **Afficher**, sélectionnez **Quadrillage**.
2. Dans le modèle modifiable, sélectionnez le rectangle au-dessus du titre du modèle. Ce rectangle est une image nommée **rptHeaderCompLogo**.
3. Si le volet **Structure du modèle** est masqué, sélectionnez **Afficher la structure**.
4. Dans le volet **Structure du modèle**, développer **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.
5. Notez que, dans la structure du modèle dans Finance, l’élément **rptHeaderCompLogo** est présenté comme un élément enfant de **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.

[![Utilisation de l’espace de travail Gestion des documents commerciaux pour examiner la structure actuelle d’un modèle modifiable](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>Mettre à jour la structure d’un modèle de document commercial en supprimant une image

1. Dans Excel Online, dans le modèle modifiable, sélectionnez l’image **rptHeaderCompLogo**.
2. Suivez l’une de ces étapes pour supprimer l’image sélectionnée du modèle modifiable :

    - Sélectionnez la touche **Supprimer** de votre clavier.
    - Sélectionnez et maintenez (ou cliquez avec le bouton droit) sur l’image, puis sélectionnez **Couper**.

    > [!NOTE]
    > L’élément **rptHeaderCompLogo** est actuellement toujours présent dans la structure du modèle dans Finance, même si l’image n’est plus incluse dans le modèle Excel.

3. Sélectionnez **Mettre à jour la structure** pour synchroniser la structure du modèle modifiable dans Excel et Finance.
4. Dans le volet **Structure du modèle**, développer **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.
5. Notez que l’élément **rptHeaderCompLogo** n’est plus inclus dans la structure du modèle dans Finance.

[![Utilisation de l’espace de travail Gestion des documents commerciaux pour supprimer une image d’un modèle de document commercial](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>Mettre à jour la structure d’un modèle de document commercial en ajoutant une image

1. Dans Excel Online, sur le ruban, sur l’onglet **Insérer**, dans le groupe **Illustrations**, sélectionnez **Image**.
2. Sélectionner **Choisir un fichier**, recherchez l’image que vous souhaitez ajouter, sélectionnez-la, puis sélectionnez **OK**.
3. Sélectionnez **Insérer**.
4. Déplacez la nouvelle image jusqu’à ce qu’elle soit au bon endroit. Par défaut, Excel nomme l’image. Par exemple, il peut nommer l’image **Image 2**.
5. Sélectionnez **Mettre à jour la structure** pour synchroniser la structure du modèle modifiable dans Excel et Finance.
6. Dans le volet **Structure du modèle**, développer **Rapport \> Facture d’achat \> rptHeader \> rptHeaderPart1**.
7. Notez que la nouvelle image est à présent incluse en tant qu’élément dans la structure du modèle dans Finance.

[![Utilisation de l’espace de travail Gestion des documents commerciaux pour ajouter une image à un modèle de document commercial](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>Liens connexes

[Vue d’ensemble des états électroniques](general-electronic-reporting.md)

[Vue d’ensemble de la gestion de document commercial](er-business-document-management.md)
