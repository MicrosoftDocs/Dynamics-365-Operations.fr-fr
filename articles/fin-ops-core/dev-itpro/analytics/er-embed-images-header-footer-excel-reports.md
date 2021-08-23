---
title: Concevoir un format ER pour générer un rapport au format Excel avec des images incorporées aux en-têtes ou pieds de page
description: Cette rubrique explique comment utiliser les états électroniques (ER) pour générer des documents commerciaux contenant des images et des formes incorporées aux en-têtes ou pieds de page.
author: NickSelin
ms.date: 06/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-06-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1115be8c33eeaf16c1a533e63b31d87b0fc5f68d6469ff075428f72ac146b2f4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746633"
---
# <a name="design-an-er-format-to-generate-a-report-in-excel-format-with-embedded-images-in-page-headers-or-footers"></a>Concevoir un format ER pour générer un rapport au format Excel avec des images incorporées aux en-têtes ou pieds de page

[!include[banner](../includes/banner.md)]

Cette rubrique explique comment un utilisateur doté du rôle Administrateur système ou Consultant fonctionnel de gestion des états électroniques peut effectuer les tâches suivantes :

- Configurer les paramètres de la structure de [gestion des états électroniques (ER)](general-electronic-reporting.md).
- Importer des [configurations ER](general-electronic-reporting.md#Configuration) qui sont [fournies](general-electronic-reporting.md#Provider) par Microsoft et utilisées pour générer des [factures financières](../../../finance/accounts-receivable/create-free-text-invoice-new.md), sur la base d'un [modèle](er-fillable-excel.md#excel-file-component) au format Microsoft Excel.
- Créer une version [personnalisée (dérivée)](general-electronic-reporting.md#building-a-format-selecting-another-format-as-a-base-customization) d’une configuration du format de gestion des états électroniques standard fournie par Microsoft.
- Modifiez la configuration du format ER personnalisé afin qu'elle génère un rapport de facture financière comportant une image du logo de la compagnie dans le pied de page.

Les procédures de cette rubrique peuvent être effectuées dans la compagnie **USMF**. Aucun codage n’est requis. Avant de commencer, téléchargez et enregistrez le fichier suivant.

| Description         | Nom de fichier |
|--------------------|-----------|
| Image du logo de l'entreprise | [Logo de société au format .png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png) |

## <a name="content"></a>Contenu

- [Configurer l'entité juridique](#ConfigureLegalEntity)
- [Configurer la structure de gestion des états électroniques](#ConfigureFramework)

    - [Configurer les paramètres de gestion des états électroniques](#ConfigureParameters)
    - [Activer un fournisseur de configuration de gestion des états électroniques](#ActivateProvider)

        - [Consulter la liste des fournisseurs de configuration de gestion des états électroniques](#ReviewProvidersList)
        - [Ajouter un nouveau fournisseur de configuration de gestion des états électroniques](#AddProvider)
        - [Activer le nouveau fournisseur de configuration de gestion des états électroniques](#ActivateAddedProvider)

- [Importer les configurations du format de gestion des états électroniques standard](#ImportERSolution1)

    - [Importer les configurations de gestion des états électroniques standard](#ImportERFormat)
    - [Passer en revue les configurations de gestion des états électroniques importées](#ReviewImportedERSolution)

- [Imprimer une facture financière en utilisant le format ER standard](#PrintInvoice1)

    - [Paramétrer la gestion de l'impression](#ConfigurePrintManagement1)
    - [Imprimer une facture financière](#ProcessInvoice1)

- [Personnaliser le format de gestion des états électroniques standard](#CustomizeProvidedFormat)

    - [Créer un format personnalisé](#DeriveProvidedFormat)
    - [Modifier le format personnalisé](#ConfigureDerivedFormat)
    - [Marquer le format personnalisé comme exécutable](#MarkFormatRunnable)

- [Imprimer une facture financière en utilisant le format ER personnalisé](#PrintInvoice2)

    - [Paramétrer la gestion de l'impression](#ConfigurePrintManagement2)
    - [Imprimer une facture financière](#ProcessInvoice2)

- [Ressources supplémentaires](#References)

## <a name="configure-the-legal-entity"></a><a id="ConfigureLegalEntity"></a>Configurer l'entité juridique

1. Allez dans **Administration d’organisation** \> **Organisations** \> **Entités juridiques**.
2. Sur la page **Entités juridiques**, sur le raccourci **Signaler l'image du logo de la compagnie**, sélectionnez **Changer**.
3. Dans la boîte de dialogue **Sélectionnez le fichier image à charger**, sélectionnez **Parcourir**, puis le fichier **Logo de la compagnie.png** que vous avez téléchargé précédemment.
4. Sélectionnez **Enregistrer**, puis fermez la page **Entités juridiques**.

![Image du logo de la compagnie sélectionnée sur la page Entités juridiques.](./media/er-embed-images-header-footer-excel-reports-company-logo-image.png)

## <a name="configure-the-er-framework"></a><a id="ConfigureFramework"></a>Configurer la structure de gestion des états électroniques

En tant qu’utilisateur doté du rôle Consultant fonctionnel de gestion des états électroniques, vous devez configurer l’ensemble minimal des paramètres de gestion des états électroniques avant de pouvoir commencer à utiliser la structure de gestion des états électroniques pour créer une version personnalisée d’un format de gestion des états électroniques standard.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurer les paramètres de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Paramètres de gestion des états électroniques**.
3. Sur la page **Paramètres de gestion des états électroniques**, sous l’onglet **Général**, définissez l’option **Activer le mode de configuration** sur **Oui**.
4. Dans l’onglet **Pièces jointes**, définissez les paramètres suivants :

    - Dans le champ **Configurations**, sélectionnez le type **Fichier** pour la société **USMF**.
    - Dans les champs **Archive de tâche**, **Temporaire**, **Référence** et **Autres**, sélectionnez le type **Fichier**.

Pour plus d’informations sur les paramètres de gestion des états électroniques, voir [Configurer la structure de gestion des états électroniques](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Activer un fournisseur de configuration de gestion des états électroniques

Chaque configuration de gestion des états électroniques ajoutée est marquée comme appartenant à un fournisseur de configuration de gestion des états électroniques. Le fournisseur de configuration de gestion des états électroniques activé dans l’espace de travail **Gestion des états électroniques** est utilisé à cet effet. Par conséquent, vous devez activer un fournisseur de configuration de gestion des états électroniques dans l’espace de travail **Gestion des états électroniques** avant de commencer à ajouter ou modifier des configurations de gestion des états électroniques.

> [!NOTE]
> Une configuration ER ne peut être modifiée que par le propriétaire de la configuration. Avant qu’une configuration de gestion des états électroniques puisse être modifiée, le fournisseur de configuration de gestion des états électroniques approprié doit être activé dans l’espace de travail **Gestion des états électroniques**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Consulter la liste des fournisseurs de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Table des fournisseurs de configuration**, chaque enregistrement de fournisseur a un nom et une URL uniques. Passez en revue le contenu de cette page. S’il existe déjà un enregistrement pour **Litware, Inc.** (`https://www.litware.com`), ignorez la procédure suivante, [Ajouter un nouveau fournisseur de configuration de gestion des états électroniques](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Ajouter un nouveau fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Liens connexes**, sélectionnez **Fournisseurs de configuration**.
3. Sur la page **Fournisseurs de configuration**, sélectionnez **Nouveau**.
4. Dans le champ **Nom**, entrez **Litware, Inc.**
5. Dans le champ **Adresse Internet**, entrez `https://www.litware.com`.
6. Sélectionnez **Enregistrer**.

#### <a name="activate-the-new-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Activer le nouveau fournisseur de configuration de gestion des états électroniques

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Litware, Inc.**, puis sélectionnez **Activer**.

Pour plus d’informations sur les fournisseurs de configuration de gestion des états électroniques, voir [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-standard-er-format-configurations"></a><a id="ImportERSolution1"></a>Importer les configurations du format de gestion des états électroniques standard

### <a name="import-the-standard-er-configurations"></a><a id="ImportERFormat"></a>Importer les configurations de gestion des états électroniques standard

Pour ajouter les configurations de gestion des états électroniques standard à votre instance actuelle de Dynamics 365 Finance, vous devez les importer depuis le [référentiel](general-electronic-reporting.md#Repository) de gestion des états électroniques qui a été configuré pour cette instance.

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Sur la page **Configurations de localisation**, dans la section **Fournisseurs de configuration**, sélectionnez la vignette **Microsoft**, puis sélectionnez **Référentiels** pour afficher la liste des référentiels du fournisseur **Microsoft**.
3. Sur la page **Référentiels de configuration**, sélectionnez le référentiel de type **Global**, puis sélectionnez **Ouvrir**. Si vous êtes invité à autoriser la connexion à [Regulatory Configuration Service](../../../finance/localizations/rcs-overview.md), suivez les instructions d’autorisation.
4. Sur la page **Référentiel de configuration**, dans l’arborescence de configuration du volet gauche, sélectionnez la configuration de format **Facture financière (Excel)**.
5. Dans l’organisateur **Versions**, sélectionnez la dernière version (par exemple, **240.112**) de la configuration du format de gestion des états électroniques sélectionnée.
6. Sélectionnez **Importer** pour télécharger la version sélectionnée depuis le référentiel global vers l’instance actuelle de Finance.

![Importation de configurations ER standard sur la page Référentiel de configuration.](./media/er-embed-images-header-footer-excel-reports-import-solution.png)

> [!TIP]
> Si vous ne parvenez pas à accéder au [Référentiel global](er-download-configurations-global-repo.md), vous pouvez [télécharger les configurations](download-electronic-reporting-configuration-lcs.md) depuis Microsoft Dynamics Lifecycle Services (LCS).

### <a name="review-the-imported-er-configurations"></a><a id="ReviewImportedERSolution"></a>Passer en revue les configurations de gestion des états électroniques importées

1. Accédez à **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Dans la page **Configurations de localisation**, dans la section **Configurations**, sélectionnez la vignette **Configurations des états**.
3. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture**.
4. En plus du format ER **Facture financière (Excel)** sélectionné, d’autres configurations ER requises ont été importées. Assurez-vous que les configurations de gestion des états électroniques suivantes sont disponibles dans l’arborescence de configuration :

    - **Modèle de facture** – Cette configuration contient le composant de gestion des états électroniques [Modèle de données](general-electronic-reporting.md#data-model-and-model-mapping-components) qui représente la structure de données du domaine d’activité de la facturation.
    - **Mappage de modèle de facture** – Cette configuration contient le composant de gestion des états électroniques [Mappage de modèle](general-electronic-reporting.md#data-model-and-model-mapping-components) qui décrit comment le modèle de données est rempli avec les données d’application au moment de l’exécution.
    - **Facture financière (Excel)** – Cette configuration contient le [format](general-electronic-reporting.md#FormatComponentOutbound) et les composants ER de mappage de format. Le composant de format spécifie la disposition du rapport, basée sur un modèle au format Excel. Le composant Mise en correspondance des formats contient la source de données du modèle et spécifie comment cette source de données est utilisée pour remplir la présentation de l’état au moment de l’exécution.

![Configurations ER importées sur la page Configurations.](./media/er-embed-images-header-footer-excel-reports-imported-solution.png)

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a><a id="PrintInvoice1"></a>Imprimer une facture financière en utilisant le format ER standard

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement1"></a>Paramétrer la gestion de l'impression

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sur la page **Facture financière**, sélectionnez la facture **FTI-00000002**, puis, dans le volet Action, sous l’onglet **Facture**, dans le groupe **Gestion de l'impression**, sélectionnez **Gestion de l'impression**.
3. Sur la page **Configuration de la gestion de l'impression**, dans l'arborescence de gauche, développez **Module - Comptabilité client\> Documents \> Facture financière**, puis sélectionnez l'élément **\<Default\> d'origine**.
4. Dans le champ **Format d’état**, sélectionnez **Facture financière (Excel)**.
5. Sélectionnez la touche **Échap** pour quitter la page **Paramétrage de la gestion de l’impression** et revenir à la page **Facture financière**.

![Paramètres de gestion de l'impression pour une facture financière au format ER standard sur la page Paramétrage de la gestion de l’impression.](./media/er-embed-images-header-footer-excel-reports-print-management.png)

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice1"></a>Imprimer une facture financière

1. Sur la page **Facture financière**, vérifiez que la facture **FTI-00000002** est toujours sélectionnée, puis, dans le volet Action, sous l’onglet **Facture**, dans le groupe **Document**, sélectionnez **Imprimer** \> **Sélection**.
2. Téléchargez la facture générée au format Excel et ouvrez-la pour un aperçu.
3. Notez que, conformément à la structure du modèle Excel pour le format ER fourni, le pied de page de la facture générée contient des informations sur le numéro de page actuel et le nombre total de pages dans l’état.

![Facture financière générée.](./media/er-embed-images-header-footer-excel-reports-print-invoice1.gif)

## <a name="customize-the-standard-er-format"></a><a id="CustomizeProvidedFormat"></a>Personnaliser le format de gestion des états électroniques standard

Pour l'exemple de cette section, vous pouvez utiliser les configurations ER fournies par Microsoft pour générer une facture financière au format Excel. Cependant, vous devez ajouter une personnalisation pour mettre une image de logo de compagnie dans le pied de page des factures générées.

Dans ce cas, en tant que représentant de Litware, Inc., vous devez créer (dériver) une nouvelle configuration du format de gestion des états électroniques basée sur la configuration fournie par Microsoft **Facture financière (Excel)**.

### <a name="create-a-custom-format"></a><a id="DeriveProvidedFormat"></a>Créer un format personnalisé

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de facture**, puis sélectionnez **Facture financière (Excel)**. Litware, Inc. utilisera la version importée (par exemple, **240.112**) de cette configuration du format de gestion des états électroniques comme base pour la version personnalisée.
3. Sélectionnez **Créer une configuration** pour ouvrir la boîte de dialogue déroulante. Utilisez cette boîte de dialogue pour créer une configuration pour un format de paiement personnalisé.
4. Dans le groupe de champs **Nouveau**, sélectionnez l’option **Provenant du nom : Facture financière (Excel), Microsoft**.
5. Dans le champ **Nom**, entrez **Facture financière (Excel) personnalisée**.
6. Sélectionnez **Créer une configuration**.

![Création d'une configuration pour un format de paiement personnalisé dans la boîte de dialogue déroulante Créer une configuration.](./media/er-embed-images-header-footer-excel-reports-add-derived-format.png)

La version 240.112.1 de la configuration du format ER **Facture financière (Excel) personnalisée** est créée. Cette version présente le [statut](general-electronic-reporting.md#component-versioning) **Brouillon** et peut être modifiée. Le contenu actuel de votre format de gestion des états électroniques personnalisé correspond au contenu du format fourni par Microsoft.

![Nouvelle version de la configuration du format ER créée sur la page Configurations.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration1.png)

### <a name="edit-the-custom-format"></a><a id="ConfigureDerivedFormat"></a>Modifier le format personnalisé

Configurez votre format personnalisé afin qu'une image du logo de la compagnie soit placée dans le pied de page de chaque page de l’état.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Sur la page **Configurations**, dans l’arborescence de configuration du volet gauche, développez **Modèle de paiement**, puis sélectionnez **Facture financière (Excel) personnalisée**.
3. Dans l’organisateur **Versions**, sélectionnez la version **240.112.1** de la configuration sélectionnée.
4. Sélectionnez **Concepteur**.
5. Sur la page **Concepteur de formats**, sélectionnez **Afficher les détails** pour afficher d’autres informations sur les éléments de format.
6. Développez et passez en revue les éléments suivants :

    - L’élément **Facture financière** du type **Excel**. Cet élément permet de générer une facture au format de classeur Excel.
    - L’élément **Facture financière \\ Facture** du type **Feuille**. Cet élément est utilisé pour générer une feuille de calcul du classeur Excel généré.
    - L’élément **Facture financière \\ Facture \\ Pied de page** du type **Pied de page**. Cet élément permet de compléter un pied de page de facture.

7. Sélectionnez l’élément **Facture financière \\ Facture \\ Pied de page**.

    ![Élément de pied de page dans le concepteur d’opérations de gestion des états électroniques.](./media/er-embed-images-header-footer-excel-reports-derived-format0.png)

    > [!NOTE]
    > Chaque pied de page d'une facture générée contient des informations sur le numéro de page actuel et le nombre total de pages dans l’état. Comme vous pouvez le voir, l'élément **Facture financière \\ Facture \\ Pied de page** ne contient aucun élément enfant. Par conséquent, le modèle Excel utilisé est configuré pour afficher les détails de la pagination au centre du pied de page de chaque état.

8. Sélectionnez **Ajouter**, puis sélectionnez le type **Excel \\ Image** de l’élément de format que vous ajoutez :

    1. Dans le champ **Alignement**, sélectionnez **Droite**.
    2. Dans le champ **Mettre à l'échelle la hauteur**, sélectionnez **Relatif**.
    3. Dans le champ **Échelle en pourcentage**, entrez **70**.
    4. Cliquez sur **OK**.

        > [!NOTE]
        > L'élément **Excel \\ Image** est utilisé pour ajouter une image de logo de compagnie et l'aligner sur le côté droit du pied de page.

    ![Propriétés de l'élément Image dans la boîte de dialogue Propriétés du composant.](./media/er-embed-images-header-footer-excel-reports-derived-format1.png)

9. Dans l'arborescence de la structure des formats à gauche, sélectionnez l’élément **Image** que vous venez d'ajouter, puis, sous l’onglet **Mappage**, développez source de données **modèle**.
10. Développez **model.Payment** \> **model.InvoiceBase \> model.InvoiceBase.CompanyInfo**, puis sélectionnez le champ de source de données **model.InvoiceBase.CompanyInfo.Logo**. Le champ de source de données du type [Conteneur](er-formula-supported-data-types-composite.md#container) expose l'image du logo de la compagnie en tant que contenu multimédia.
11. Sélectionnez **Lier**. L'élément de format **Image** est maintenant lié au champ de source de données **model.InvoiceBase.CompanyInfo.Logo**. Par conséquent, lors de l'exécution, une image du logo de la compagnie sera placée dans le pied de page des factures générées.

    ![L'élément de format Image lié au champ de source de données model.InvoiceBase.CompanyInfo.Logo dans le concepteur d’opérations de gestion des états électroniques.](./media/er-embed-images-header-footer-excel-reports-derived-format2.png)

12. Sélectionnez **Enregistrer**, puis fermez la page **Concepteur**.

### <a name="mark-the-custom-format-as-runnable"></a><a id="MarkFormatRunnable"></a>Marquer le format personnalisé comme exécutable

La première version du format personnalisé ayant été créée et présentant le statut **Brouillon**, vous pouvez exécuter le format à des fins de test. Pour exécuter l’état, traitez un paiement fournisseur en utilisant le mode de paiement qui fait référence à votre format de gestion des états électroniques personnalisé. Par défaut, lorsque vous appelez un format de gestion des états électroniques depuis l’application, seules les versions qui ont le statut **Terminé** et **Partagé** sont [prises en compte](general-electronic-reporting.md#component-versioning). Ce comportement permet de ne pas utiliser les formats de gestion des états électroniques dont les conceptions sont inachevées. Cependant, pour vos exécutions de test, vous pouvez forcer l’application à utiliser la version de votre format de gestion des états électroniques dont le statut est **Brouillon**. De cette façon, vous pouvez ajuster la version actuelle du format si des modifications sont nécessaires. Pour plus d’informations, voir [Applicabilité](electronic-reporting-destinations.md#applicability).

Pour utiliser la version provisoire d’un format de gestion des états électroniques, vous devez explicitement marquer le format de gestion des états électroniques.

1. Accédez à **Administration d’organisation** \> **États électroniques** \> **Configurations**.
2. Dans la page **Configurations**, dans le volet Actions, sous l’onglet **Configurations**, dans le groupe **Paramètres avancés**, sélectionnez **Paramètres utilisateur**.
3. Dans la boîte de dialogue **Paramètres utilisateur**, définissez l’option **Paramètres d’exécution** sur **Oui**, puis cliquez sur **OK**.
4. Sélectionnez **Modifier** pour rendre la page active modifiable, puis, dans l’arborescence de configuration du volet gauche, sélectionnez **Facture financière (Excel) personnalisée**.
5. Définissez l’option **Exécuter le brouillon** sur **Oui**.

![Marquer le format personnalisé comme exécutable sur la page Configurations.](./media/er-embed-images-header-footer-excel-reports-derived-format-configuration2.png)

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a><a id="PrintInvoice2"></a>Imprimer une facture financière en utilisant le format ER personnalisé

### <a name="set-up-print-management"></a><a id="ConfigurePrintManagement2"></a>Paramétrer la gestion de l'impression

1. Allez dans **Comptabilité client** \> **Factures** \> **Toutes factures financières**.
2. Sur la page **Facture financière**, sélectionnez la facture **FTI-00000002**, puis, dans le volet Action, sous l’onglet **Facture**, dans le groupe **Gestion de l'impression**, sélectionnez **Gestion de l'impression**.
3. Sur la page **Configuration de la gestion de l'impression**, dans l'arborescence de gauche, développez **Module - Comptabilité client** \> **Documents** \> **Facture financière**, puis sélectionnez l'élément **\<Default\>** **d'origine**.
4. Dans le champ **Format d’état**, sélectionnez **Facture financière (Excel) personnalisée**.
5. Sélectionnez **Échap** pour quitter la page **Paramétrage de la gestion de l’impression** et revenir à la page **Facture financière**.

### <a name="print-a-free-text-invoice"></a><a id="ProcessInvoice2"></a>Imprimer une facture financière

1. Sur la page **Facture financière**, vérifiez que la facture **FTI-00000002** est toujours sélectionnée, puis, dans le volet Action, sous l’onglet **Facture**, dans le groupe **Document**, sélectionnez **Imprimer** \> **Sélection**.
2. Téléchargez la facture générée au format Excel et ouvrez-la pour un aperçu.
3. Notez que, conformément à la structure du format ER personnalisé, le pied de page de la facture générée contient une image du logo de la compagnie en plus des informations sur la pagination de l’état.

![Facture financière générée avec une image du logo de la compagnie dans le pied de page.](./media/er-embed-images-header-footer-excel-reports-print-invoice2.gif)

## <a name="additional-resources"></a><a id="References"></a>Ressources supplémentaires

- [Créer une configuration pour générer des documents au format Excel](er-fillable-excel.md)
- [Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md)
