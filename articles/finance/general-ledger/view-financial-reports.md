---
title: Afficher les états financiers
description: Cet article décrit comment afficher et explorer des états financiers dans Microsoft Dynamics 365 Finance. Il inclut des informations sur les différentes options que vous pouvez appliquer à des états financiers pour modifier leur apparence et les données qu’ils incluent.
author: kweekley
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f932bbef2543e4894c65b9a04c1ef66f1b3ab8e
ms.sourcegitcommit: d27fef61593c6d1e9e26d5c9fad21411bc52fabc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9802389"
---
# <a name="view-financial-reports"></a>Afficher les états financiers

[!include [banner](../includes/banner.md)]

Cet article décrit comment afficher et explorer des états financiers. Il inclut des informations sur les différentes options que vous pouvez appliquer à des états financiers pour modifier leur apparence et les données qu’ils incluent.

## <a name="financial-reporting-overview"></a>Présentation des états financiers

## <a name="open-a-financial-report"></a>Ouvrir un état financier
Pour ouvrir un état, sélectionnez le nom de l’état. La première fois que l’état est ouvert, il est automatiquement généré pour le mois précédent. Par exemple, si vous ouvrez un état pour la première fois en août 2020, l’état est généré pour le 31 juillet 2020. Après l’ouverture d’un état, vous pouvez démarrer l’exploration en accédant à des ensembles de données spécifiques et en modifiant les options d’état.

## <a name="drill-down-on-a-financial-report"></a>Exploration d’un état financier
Les états financiers peuvent inclure plusieurs niveaux de détail. Le niveau financier est le premier niveau proposé lorsque vous ouvrez un état financier. Pour accéder au niveau des comptes, sélectionnez les données à explorer. Par exemple, pour afficher les détails de compte pour les ventes, sélectionnez les données de vente que vous souhaitez explorer. à partir du niveau du compte, vous pouvez faire un zoom avant pour afficher les transactions qui constituent le solde de compte. Il existe deux manières d’afficher les transactions : transactions d’état et pièces comptables.

-   **Transactions d’état** – Les transactions apparaissent dans un affichage formaté inclus dans l’état financier. Pour afficher les transactions dans l’affichage formaté, sélectionnez les données à explorer, puis cliquez sur **Accéder au niveau de la transaction d’état**.
-   **Pièces comptables** – Une recherche de pièces comptables s’ouvre, dans laquelle vous pouvez afficher les transactions. Pour afficher les transactions dans la recherche transactions de N° document, sélectionnez les données à explorer, puis cliquez sur **Ouvrir des transactions en compte**.

Si les données sont des données de budget, vous pouvez choisir d’ouvrir les écritures de compte budgétaires. Pour fermer l’un des niveaux de l’état et revenir au point de départ, vous pouvez appuyer sur la touche échap ou sur le bouton **Fermer**(**X**) en haut à droite.

## <a name="change-report-options"></a>Modifier les options d’état
Vous pouvez appliquer des filtres d’attribut et de dimension, ou modifier le scénario de budget dans l’état **Réel versus budget**. Dans le Volet Action, cliquez sur **Options d’état**, puis suivez une ou plusieurs des étapes suivantes :

-   Pour appliquer des filtres d’attributs à un état, sélectionnez **Ajoutez un filtre d’attribut**. Sélectionnez l’attribut, entrez la valeur d’attribut, puis cliquez sur **OK**. Par exemple, si vous sélectionnez l’attribut **Catégorie de compte**, entrez **VENTES** comme valeur de l’attribut. Pour supprimer un filtre d’attributs, cliquez sur **Effacer**.
-   Pour appliquer des filtres de dimension à un état, sélectionnez **Ajouter un filtre de dimension**. Sélectionnez la dimension, puis entrez l’ID de dimension ou sélectionnez la dimension dans la liste. Pour supprimer un filtre de dimension, cliquez sur **Effacer**.
-   Pour modifier le scénario dans un état **Réel versus budget**, sélectionnez un nouveau scénario, puis cliquez sur **OK**. Si le scénario sélectionné concerne un autre exercice, aucun résultat ne sera retourné. Par exemple, si un rapport est généré pour l’exercice 2015, que le scénario actuel est pour l’exercice 2020 et que le nouveau scénario sélectionné est pour l’exercice 2016, aucun résultat ne sera retourné. Si un nouveau scénario pour un exercice autre est nécessaire, générez une nouvelle version de l’état pour l’exercice lié au scénario.

Lorsque vous cliquez sur **OK**, toutes les options sélectionnées sont appliquées à l’état. Si vous décidez que vous ne souhaitez pas appliquer les options sélectionnées, cliquez sur **Annuler**.

## <a name="update-a-financial-report"></a>Mettre à jour un état financier
Vous pouvez actualiser (mettre à jour) un état financier afin qu’il affiche les données les plus récentes pour la période et l’exercice pour lequel l’état a été généré. Par exemple, si vous mettez à jour un état un état financier qui a été généré pour octobre 2020, l’état reflète toutes les nouvelles transactions validées pour octobre 2020. Pour mettre à jour un état financier, dans le Volet Actions, cliquez sur **Actualiser**. Un état mis à jour est disponible uniquement pour la personne qui l’a mis à jour. Pour que d’autres personnes puissent voir les mêmes données, l’état doit être publié.

## <a name="publish-a-financial-report"></a>Publier un état financier
Après avoir mis un état financier à jour, vous pouvez le publier. D’autres personnes de l’organisation peuvent ensuite l’afficher. Pour publier un état, dans le Volet Action, cliquez sur **Publier**.

## <a name="display-a-financial-report-in-a-different-currency"></a>Afficher un état financier dans une devise différente
Un état financier peut être affiché dans n’importe quelle devise, à tout moment. Pour afficher un état dans une devise différente, dans le Volet Action, cliquez sur **Devise**, puis sélectionnez une devise. L’état est converti en cette devise, et les résultats sont affichés. Tous les codes devise ou les symboles inclus dans le cadre de la création de l’état sont mis à jour pour refléter la nouvelle devise. Les devises qui apparaissent dans la liste sont les devises de génération d’état qui sont configurées dans Finance.

## <a name="display-a-summarized-view-of-the-financial-report"></a>Afficher une vue de synthèse de l’état financier
Un état financier peut contenir des lignes spécifiques et les lignes récapitulatives. Les lignes spécifiques sont des lignes contenant les comptes principaux ou des dimensions. Les lignes récapitulatives sont des lignes de description, de total et de calcul. Pour afficher seulement les lignes récapitulatives d’un état, cliquez sur **Afficher**, puis sur **Lignes de synthèse uniquement**. L’état est réduit et affiche uniquement les lignes récapitulatives. Pour afficher les lignes spécifique avec les lignes récapitulatives, cliquez sur **Afficher**, puis de nouveau sur **Lignes de synthèse uniquement**.

## <a name="print-a-financial-report"></a>Imprimer un état financier
L’impression d’un état financier génère un fichier PDF qui peut être ensuite imprimé manuellement. Pour créer un état financier imprimable, dans le Volet Actions, cliquez sur **Imprimer**, puis suivez une ou plusieurs des étapes suivantes pour définir les options d’impression :

-   Pour inclure les différents niveaux de détail dans l’état imprimé, mettez le curseur sur **Oui** ou **Non**. Si un état utilise une arborescence de déclaration, vous pouvez choisir d’inclure toutes les unités d’état ou seulement l’unité d’état actuelle.
-   Pour définir la taille de la page, sélectionnez une taille de page dans la liste.
-   Pour définir la mise en page, sélectionnez une mise en page dans la liste. Si vous souhaitez que le contenu de l’état s’adapte à la largeur sélectionnée, mettez le curseur sur **Oui**.
-   Pour définir les marges de page, entrez la taille des marges supérieur, inférieure, de gauche et de droite en pouces.

Après avoir défini les options d’impression, cliquez sur **Imprimer** pour continuer et indiquer si vous souhaitez télécharger le fichier ou l’enregistrer vers OneDrive ou SharePoint. Si vous ne souhaitez pas continuer, cliquez sur **Annuler**. Si vous continuez, l’état commence le rendu sur le serveur et vous êtes invité à télécharger l’état au format PDF. Désormais, vous pouvez afficher l’état dans votre visionneuse PDF et de là, vous pouvez sélectionner l’imprimante vers laquelle envoyer l’état, et faire les ajustements supplémentaires pour les options d’impression.

## <a name="export-a-financial-report"></a>Exporter un état financier
Pour exporter un état financier, dans le Volet Action, cliquez sur **Exporter**. L’état est exporté vers Microsoft Excel, et votre navigateur vous invite à ouvrir ou enregistrer le fichier exporté. Les paramètres d’exportation définis dans la création de l’état sont appliqués à l’état exporté.    

## <a name="additional-resources"></a>Ressources supplémentaires

[États financiers](../../fin-ops-core/dev-itpro/analytics/financial-reporting-intro.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
