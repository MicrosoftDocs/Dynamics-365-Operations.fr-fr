---
title: Concevoir un format ER pour conserver les lignes ensemble sur la même page Excel
description: Cette rubrique explique comment concevoir un format de gestion des états électroniques (ER) qui conserve les lignes ensemble sur la même page Microsoft Excel.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.openlocfilehash: 711681ab38fb24b57a83f008f86a8261176aa5a5
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388591"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>Concevoir un format ER pour conserver les lignes ensemble sur la même page Excel

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique explique comment un utilisateur ayant le rôle d’administrateur système ou de consultant fonctionnel des états électroniques peut configurer un [format de gestion des états électroniques ](general-electronic-reporting.md) [(ER)](er-overview-components.md#format-component) qui génère des documents sortants dans Microsoft Excel et gérer la pagination des documents de telle sorte que les lignes créées sont conservées sur la même page.

Dans cet exemple, vous allez modifier le format ER fourni par Microsoft qui est utilisé pour imprimer des factures financières dans Excel. Vos modifications vous permettront de gérer la pagination d’un état de facture financière généré afin que toutes les lignes d’une même ligne de facture soient conservées sur la même page lorsque cela est possible.

Les procédures de cette rubrique peuvent être effectuées dans la compagnie **USMF**. Aucun codage n’est requis.

Dans cet exemple, vous créerez les [configurations](general-electronic-reporting.md#Configuration) ER requises pour la société fictive, **Litware, Inc**. Veillez à ce que le fournisseur de configuration pour l’exemple de société **Litware, Inc.** (`http://www.litware.com`) soit répertorié pour la structure ER et qu’il soit marqué comme **actif**. Si ce fournisseur de configuration n’est pas répertorié ou s’il n’est pas marqué comme **actif**, suivez les étapes de la rubrique [Créer un fournisseur de configuration et le marquer comme actif](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="enter-a-new-free-text-invoice"></a>Saisir une nouvelle facture financière

1. Suivez les étapes de la procédure [Créer une facture financière](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1) pour ajouter une facture financière.

    1. Ajoutez une seule ligne à la facture.
    2. Ajoutez cinq notes pour la ligne de facture.

    ![Examen des notes de ligne de facture sur la page Pièces jointes.](./media/er-keep-excel-rows-together-notes.png)

2. Suivez les étapes de [Copier des lignes](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines) pour créer cinq lignes de facture supplémentaires qui sont des copies de la ligne de facture que vous avez ajoutée à l’étape précédente.

    ![Examen des lignes de facture financière sur la page Facture financière.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>Configurer la structure de gestion des états électroniques

Procédez comme suit dans [Configurer la structure des états électroniques](er-quick-start2-customize-report.md#ConfigureFramework) pour configurer l’ensemble minimum de paramètres d’état électronique. Vous devez terminer cette configuration avant de commencer à utiliser la structure des états électroniques pour concevoir une version personnalisée d’un format de gestion des états électroniques standard.

## <a name="import-the-standard-er-format-configuration"></a>Importer la configuration du format de gestion des états électroniques standard

Suivez les étapes de l’action [Importer la configuration du format de gestion des états électroniques standard](er-quick-start2-customize-report.md#ImportERSolution1) pour ajouter les configurations des états électroniques standard à votre instance actuelle de Dynamics 365 Finance. Par exemple, importez la version **252.116** de la configuration du format ER **Facture financière (Excel)** personnalisée. La version de base **252** de la configuration de base **Modèle de facture** est automatiquement importée du référentiel avec la configuration requise **Mise en correspondance du modèle de facture**.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>Configurer la gestion de l’impression pour utiliser le format ER standard

Suivez les étapes dans [Configurer la gestion de l’impression](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1) pour configurer la gestion de l’impression pour le module **Comptes débiteurs** afin que le format ER standard soit utilisé pour imprimer les factures financières.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>Configurer une destination de format pour le format ER standard

Suivez les étapes dans [Configurer une destination de format pour l’aperçu à l’écran](er-quick-start1-new-solution.md#ConfigureDestination) pour configurer la destination ER [Écran](er-destination-type-screen.md) du format ER standard afin que les rapports générés soient convertis au format PDF et prévisualisés sur un nouvel onglet du navigateur.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>Imprimer une facture financière en utilisant le format ER standard

1. Suivez les étapes dans [Imprimer une facture financière](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1) pour utiliser le format ER standard pour générer un rapport de facture financière au format Excel pour la facture ajoutée.
2. Téléchargez le classeur Excel généré et examinez-le dans l’application de bureau Excel.

    Notez que la sixième ligne de la facture commence sur la première page du rapport et se poursuit sur la deuxième page. La dernière note apparaît sur la deuxième page, et il n’est pas évident qu’elle appartienne à la sixième ligne de la facture. Par conséquent, le saut de page au milieu du contenu de la ligne de facture rend ce document plus difficile à lire.

    ![Examen de la pagination de la facture financière générée dans l’application de bureau Excel.](./media/er-keep-excel-rows-together-invoice1.gif)

Les procédures restantes de cette rubrique montrent comment ajuster le format ER standard pour améliorer l’apparence et la lisibilité du rapport de facture en conservant tout le contenu d’une seule ligne de facture sur la même page.

## <a name="create-a-custom-format"></a>Créer un format personnalisé

Suivez les étapes dans [Créer un format personnalisé](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat) pour dériver un format du format ER importé et créer une configuration ER **Facture financière (Excel) personnalisée** disponible pour l’édition et la modification.

## <a name="edit-the-custom-format"></a>Modifier le format personnalisé

1. Suivez les étapes dans [Créer un format personnalisé](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat) pour ouvrir le format ER dérivé pour le modifier dans le concepteur de format ER.
2. Sur la page **Concepteur de formats**, dans l’arborescence des formats dans le volet gauche, développez **Facture financière \> Feuille \> InvoiceLines** et sélectionnez le composant **InvoiceLines_Values**.
3. Dans l’onglet **Format**, définissez l’option **Conserver les lignes ensemble** sur **Oui**.

    ![Définition de l’option Conserver les lignes ensemble pour le format ER modifiable sur la page Concepteur de format.](./media/er-keep-excel-rows-together-format.png)

4. Cliquez sur **Enregistrer**, puis fermez la page.

## <a name="mark-the-custom-format-as-runnable"></a>Marquer le format personnalisé comme exécutable

Suivez les étapes dans [Marquer le format personnalisé comme exécutable](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable) pour rendre exécutable la version modifiée du format ER personnalisé.

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>Configurer la gestion de l’impression pour utiliser le format ER personnalisé

Suivez les étapes dans [Configurer la gestion de l’impression](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2) pour configurer la gestion de l’impression pour le module **Comptes débiteurs** afin que le format ER personnalisé soit utilisé pour imprimer les factures financières.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>Configurer une destination de format pour le format ER personnalisé

Suivez les étapes dans [Configurer une destination de format pour l’aperçu à l’écran](er-quick-start1-new-solution.md#ConfigureDestination) pour configurer la destination ER **Écran** du format ER personnalisé afin que les rapports générés soient convertis au format PDF et prévisualisés sur un nouvel onglet du navigateur.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>Imprimer une facture financière en utilisant le format ER personnalisé

1. Suivez les étapes dans [Imprimer une facture financière](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2) pour utiliser le format ER personnalisé pour générer un rapport de facture financière au format Excel pour la facture ajoutée.
2. Téléchargez le classeur Excel généré et examinez-le dans l’application de bureau Excel.

    Notez que la sixième ligne de la facture commence sur la deuxième page et que toutes les lignes Excel qui représentent cette ligne de facture apparaissent ensemble sur cette page.

    ![Examen de la pagination mise à jour de la facture financière générée dans l’application de bureau Excel.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer une configuration pour générer des documents au format Excel](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
