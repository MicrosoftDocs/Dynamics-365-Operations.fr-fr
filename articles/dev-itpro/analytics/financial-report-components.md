---
title: Composants des rapports financiers
description: "Cet article décrit l’utilisation des composants ou des blocs élémentaires, de définitions d'état dans la génération d’états financiers. Ces blocs élémentaires incluent les définitions de lignes, les définitions de colonnes et les définitions d'arborescence de génération d'états. Cet article explique comment organiser et verrouiller les blocs élémentaires et comment utiliser des groupes de blocs élémentaires."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5c09b1fc061f95cd78e9f18c2bdf846fdbfc7cf1
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="financial-report-components"></a>Composants des rapports financiers

[!include[banner](../includes/banner.md)]


Cet article décrit l’utilisation des composants ou des blocs élémentaires, de définitions d'état dans la génération d’états financiers. Ces blocs élémentaires incluent les définitions de lignes, les définitions de colonnes et les définitions d'arborescence de génération d'états. Cet article explique comment organiser et verrouiller les blocs élémentaires et comment utiliser des groupes de blocs élémentaires. 

La philosophie de conception derrière le générateur d'états financiers consiste à décomposer les informations en composants ou blocs élémentaires les plus petits possibles, puis de mélanger et faire correspondre les composants selon les besoins. Par conséquent, votre mise en forme d'état est distincte de vos données financières, et vous pouvez modifier la mise ne page d'un état sans modifier les données financières de votre système Microsoft Dynamics ERP. En utilisant cette approche de bloc élémentaire, vous pouvez combiner le texte, les montants et les calculs afin de générer les rapports dont vous avez besoin. De plus, cette flexibilité encourage la créativité en simplifiant l'affichage de vos opérations de différentes manières. Les différents blocs élémentaires d'une définition de rapport sont similaires à une feuille de calcul tridimensionnelle, mais plus performants. Une définition de rapport précise la définition de ligne, de colonne et d'organigramme d'entreprise facultatif à utiliser pour le rapport. Elle comprend également les informations relatives à l'emplacement de stockage du rapport généré ainsi qu'à sa mise en page. Pour une réutilisation et un partage optimums, vous pouvez créer un groupe de blocs élémentaires qui est un ensemble de définitions de rapport, de ligne, de colonne, d'organigramme d'entreprise existantes et d'ensembles de dimensions associés à une société.

## <a name="building-blocks-of-a-report"></a> Blocs élémentaires d'un rapport
| Bloc élémentaire            | Description                                                                                                                                                                                                                                                                              | Plus d'informations                                                                                                 |
|---------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Définition de ligne            | Une définition de ligne définit les lignes descriptives, par exemple, les salaires ou les ventes, dans un rapport. Elle répertorie également les valeurs de segment ou les dimensions contenant les valeurs pour chaque article de ligne et inclut la mise en page et les calculs de ligne.                                                    | [Définitions de ligne](row-definitions-financial-reporting.md)                       |
| Définition de colonne         | Une définition de colonne définit la période à utiliser lors de l'extraction des données à partir des dimensions financières. Elle inclut également la mise en forme et les calculs de colonne.                                                                                                                                 | [Définitions de colonne](column-definitions-financial-reports.md)         |
| Définition d'organigramme d'entreprise | Une définition d'organigramme d'entreprise s'apparente à un organigramme. Elle contient les unités organisationnelles individuelles qui représentent chaque case de l'organigramme. Les unités peuvent être les départements individuels des données financières ou les unités de niveau supérieur récapitulant les données d'autres unités organisationnelles. | [Définitions d'organigramme d'entreprise](financial-reporting-tree-definitions.md) |
| Définition de rapport         | Une définition de rapport utilise une définition de ligne, de colonne et d'organigramme d'entreprise facultatif pour générer un rapport. Elle fournit également des options supplémentaires et des paramètres pour personnaliser un rapport.                                                                    | [Définition de rapport](design-financial-report-definitions.md)                  |

Si vous débutez en matière de conception de rapports, il est utile d'utiliser l'Assistant de rapport pour créer rapidement une définition de rapport que vous pourrez personnaliser ultérieurement. Si vous avez une certaine expérience en termes de conception de rapports et si vous souhaitez davantage de flexibilité en la matière, vous pouvez associer des blocs existants ou de nouveaux blocs afin de créer une définition de rapport. Vous n'avez pas besoin de comprendre complètement toutes les options de définition de rapport disponibles pour produire des rapports de qualité. À mesure que vous vous familiarisez avec la conception de rapports, vous pouvez développer vos définitions de rapport pour profiter de plus de fonctionnalités. Après avoir créé un rapport de base, vous pouvez personnaliser la définition de rapport et tout bloc élémentaire de la définition de rapport.

## <a name="organize-the-building-blocks"></a>Organisation des blocs élémentaires
Permet d'utiliser les dossiers afin d'organiser vos blocs élémentaires dans le Concepteur de rapports. Tous les fichiers sont spécifiques au type de bloc élémentaire qu'ils contiennent. Par exemple, tous les dossiers contenant des définitions de ligne sont situés dans le volet **Définitions de ligne** du générateur d'états.

### <a name="create-a-folder"></a>Création d'un dossier

1.  Dans le Concepteur de rapports, sélectionnez le type de bloc élémentaire à organiser dans le volet de navigation. Par exemple, pour trier une définition de ligne, cliquez sur **Définitions de ligne**.
2.  Dans le volet de navigation, sélectionnez le dossier existant sous lequel le nouveau dossier sera créé, puis effectuez l'une des actions suivantes :
    -   Cliquez avec le bouton droit sur le dossier parent et sélectionnez **Nouveau dossier**.
    -   Sélectionnez le dossier parent, cliquez sur **Fichier**, puis cliquez sur **Nouveau dossier**.

3.  Lorsque le nouveau dossier s'affiche, entrez le nom du nouveau dossier et appuyez sur Entrer.

## <a name="lock-a-building-block"></a> Verrouillage d'un bloc élémentaire
Vous pouvez créer un mot de passe pour protéger et verrouiller un bloc élémentaire. Ainsi, vou spouvez ajouter un niveau de sécurité à un composant de rapport sans avoir à sécuriser l'intégralité du système. Un mot de passe peut aider à protéger les informations du bloc élémentaire essentielles pour votre processus de déclaration de fin de mois. Un utilisateur de n’importe quel rôle peut verrouiller un bloc élémentaire. Toutefois, les autres utilisateurs ont toujours accès en lecture seule à un composant verrouillé. Les utilisateurs peuvent ouvrir, modifier, puis enregistrer le composant verrouillé sous nouveau nom. Un utilisateur ayant un rôle d'administrateur peut toujours accéder et modifier un bloc élémentaire protégé.
1.  Dans le générateur d'états, ouvrez le composant d'état à verrouiller, tel qu'une définition de ligne, une colonne de ligne, une définition de rapport ou une définition d'organigramme d'entreprise.
2.  Dans le menu **Outils**, cliquez sur **Protéger/Ôter la protection**. Vous pouvez également cliquer sur l'icône (un verrou) **Protéger/Ôter la protection** dans la barre d'outils.
3.  Dans la boîte de dialogue **Protéger**, entrez et confirmez un mot de passe, puis cliquez sur **OK**. L'icône de verrouillage dans la barre d'outils est mise en surbrillance lorsqu'un bloc élémentaire actif est verrouillé.

Pour déverrouiller un bloc élémentaire verrouillé, ouvrez le bloc élémentaire, puis cliquez sur l'icône **Protéger/Ôter la protection** dans la barre d'outils. Sinon, dans le menu **Outils**, cliquez sur **Protéger/Ôter la protection**.

## <a name="building-block-groups"></a>Groupes de blocs élémentaires

Les blocs élémentaires sont les définitions de ligne, de colonne, d'organigramme d'entreprise et de rapport que vous créez pour un rapport. Les groupes de blocs élémentaires sont des collections de définitions et d'ensembles de dimensions associés à une société. Les groupes de blocs élémentaires peuvent être spécifiques à la société, ou plusieurs sociétés peuvent partager le même ensemble de blocs élémentaires. Si vous avez des sociétés avec différents plans de compte, vous pouvez envisager d'utiliser un autre groupe de blocs élémentaires pour chaque société. Sinon, vous pouvez envisager de nommer chacun de vos blocs élémentaires pour indiquer avec quelle société ils sont compatibles.
### <a name="create-a-building-block-group"></a>Création d'un groupe de blocs élémentaires

1.  Dans le Concepteur de rapports, sur le menu **Société**, cliquez sur **Groupes de blocs élémentaires**.
2.  Dans la boîte de dialogue **Groupes de blocs élémentaires**, cliquez sur **Nouveau**.
3.  Entrez un nom unique et la description pour le groupe de blocs élémentaires. Chaque champ peut contenir un maximum de 256 caractères. (Ce nombre inclut des espaces.)
4.  Cliquez sur **OK** pour créer le groupe de blocs élémentaires.

### <a name="assign-a-building-block-group"></a>Affectation d'un groupe de blocs élémentaires

Une fois un groupe de blocs créé, vous devez l’affecter à au moins une société. Vous pouvez ensuite créer des définitions de rapport, de ligne, de colonne et d'organigramme d'entreprise et les enregistrer dans le groupe de blocs élémentaires. Vous devez fermer tous les blocs élémentaires avant de commencer la procédure suivante.
1.  Dans le générateur d'état, dans le menu **Société**, cliquez sur **Sociétés**.
2.  Dans la boîte de dialogue **Sociétés**, sélectionnez la société à laquelle vous affectez un groupe de blocs élémentaires.
3.  Cliquez sur **Modifier**.
4.  Dans la boîte de dialogue **Modifier la société**, dans le champ **Groupe de blocs élémentaires**, sélectionnez le groupe de blocs élémentaires à affecter à la société ou cliquez sur **Nouveau** pour créer un groupe de blocs élémentaires.
5.  Cliquez sur **OK** pour affecter le groupe de blocs élémentaires.
6.  Cliquez sur **Fermer** pour fermer la boîte de dialogue **Sociétés**. Le groupe de blocs élémentaires sélectionné est à présent affecté à la société. Maintenant, toutes les nouvelles définitions de ligne, de colonne, etc. qui sont créées feront partie du groupe de blocs élémentaires affecté à cette société. Vous pouvez également importer un fichier .tdbx ou un rapport à partir d'un autre système.

### <a name="view-a-building-block-group"></a> Affichage d'un groupe de blocs élémentaires

Une fois un groupe de blocs élémentaires créé et utilisé, vous pouvez afficher tous les blocs élémentaires qui lui sont affectés. Vous pouvez également exporter ou importer un groupe de blocs élémentaires et effectuer la maintenance supplémentaire sur les groupes de blocs élémentaires.
1.  Dans le Concepteur de rapports, sur le menu **Société**, cliquez sur **Groupes de blocs élémentaires**.
2.  Dans la boîte de dialogue **Groupes de blocs élémentaires**, sélectionnez le bloc élémentaire à afficher.
3.  Cliquez sur **Afficher** pour ouvrir la boîte de dialogue **Afficher le groupe de blocs élémentaires** où vous pouvez afficher le contenu du groupe de blocs élémentaires.
4.  Cliquez sur **Fermer** pour fermer les boîtes de dialogue.

### <a name="save-a-building-block-group-under-a-new-name"></a>Enregistrer un groupe de blocs élémentaires sous un nouveau nom

Vous pouvez enregistrer un groupe de blocs élémentaires existant sous un nouveau nom. Vous pouvez ensuite modifier le nouveau groupe de blocs élémentaires sans modifier le groupe de blocs élémentaires d'origine.
1.  Dans le Concepteur de rapports, sur le menu **Société**, cliquez sur **Groupes de blocs élémentaires**.
2.  Dans la boîte de dialogue **Groupes de blocs élémentaires**, sélectionnez le groupe de blocs élémentaires à enregistrer sous un nouveau nom.
3.  Cliquez sur **Enregistrer sous**.
4.  Entrez un nouveau nom et la description pour le groupe de blocs élémentaires.
5.  Cliquez sur **OK**. Le nouveau groupe de blocs élémentaires s'affiche dans la boîte de dialogue **Groupes de blocs élémentaires**.

### <a name="export-a-building-block-group"></a> Exportation d'un groupe de blocs élémentaires

Vous pouvez exporter un groupe de blocs élémentaires ou des blocs élémentaires d'état spécifiques dans un groupe de blocs élémentaires. Vous pouvez utiliser le groupe de blocs élémentaires exporté en tant que sauvegarde. Vous pouvez également copier les données exportées entre des groupes de blocs élémentaires ou des installations Finance and Operations. Le concepteur d'états inclut les styles de police et ensembles de dimensions référencés avec le groupe de blocs élémentaires.
1.  Dans le Concepteur d'états, sur le menu **Société**, cliquez sur **Groupes de blocs élémentaires**.
2.  Dans la boîte de dialogue **Groupes de blocs élémentaires**, sélectionnez le groupe de blocs élémentaires à exporter, puis cliquez sur **Exporter**.
3.  Dans la boîte de dialogue **Exporter**, sélectionnez les définitions de rapport à exporter :
    -   Pour exporter toutes vos définitions de rapport et les blocs élémentaires associés, cliquez sur **Sélectionner tout**.
    -   Pour exporter des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, cliquez sur l'onglet approprié et sélectionnez les éléments à exporter. Maintenez la touche CTRL enfoncée pour sélectionner plusieurs éléments dans un onglet. **Remarque :** Lorsque vous sélectionnez des rapports à exporter, les lignes, colonnes, organigrammes et ensembles de dimensions associés doivent être sélectionnés.

4.  Lorsque vous avez terminé de sélectionner les éléments à exporter, cliquez sur **Exporter**.
5.  Dans la boîte de dialogue **Enregistrer sous**, sélectionnez un emplacement où exporter le groupe de blocs élémentaires.
6.  Dans le champ **Nom du fichier**, entrez un nom pour le fichier. Le générateur d'états ajoute automatiquement une extension .tdbx au nom de fichier.
7.  Cliquez sur **Enregistrer**. Le groupe de blocs élémentaires est enregistré à l'emplacement que vous avez spécifié.

### <a name="import-a-building-block-group"></a> Importation d'un groupe de blocs élémentaires

Vous pouvez importer un groupe de blocs élémentaires dans un groupe de blocs élémentaires existant, ou vous pouvez créer un nouveau groupe de blocs élémentaires pour les données. Tous les groupes de bloc élémentaires importés conservent leurs styles de police et les références de la société d’origine et incluent les ensembles de dimensions appropriés.
1.  Dans le Concepteur de rapports, sur le menu **Société**, cliquez sur **Groupes de blocs élémentaires**.
2.  Dans la boîte de dialogue **Groupes de blocs élémentaires**, sélectionnez le groupe de blocs élémentaires dans lequel importer un groupe de blocs élémentaires, puis cliquez sur **Importer**.
3.  Dans la boîte de dialogue **Ouvrir**, sélectionnez le groupe de blocs élémentaires à importer, puis cliquez sur **Ouvrir**.
4.  Dans la boîte de dialogue **Importer**, sélectionnez les définitions de rapport à importer :
    -   Pour importer toutes les définitions de rapport et les blocs élémentaires pris en charge, cliquez sur **Sélectionner tout**.
    -   Pour importer des rapports, lignes, colonnes, organigrammes ou ensembles de dimensions spécifiques, sélectionnez les rapports, lignes, colonnes, organigrammes ou ensembles de dimensions à importer.

5.  Lorsque vous avez terminé de sélectionner les éléments à importer, cliquez sur **Importer**.

### <a name="undo-a-checkout-of-a-building-block"></a>Annulation de l'extraction d'un bloc élémentaire

Lorsque vous ouvrez un bloc élémentaire, d'autres utilisateurs peuvent accéder uniquement à ce bloc élémentaire en mode lecture seule. Parfois les utilisateurs oublient de fermer un bloc élémentaire ou arrêtent son système sans fermer le bloc élémentaire. Par conséquent, le bloc élémentaire reste extrait et aucun autre utilisateur ne peut l'ouvrir. Dans ces situations, un administrateur de génération d'états financiers peut utiliser la boîte de dialogue **Éléments extraits** pour vérifier les blocs élémentaires que les utilisateurs l'ont laissé avec un statut extrait. **Remarque :** Vous devez avoir le rôle d'administrateur pour vérifier les blocs élémentaires depuis la boîte de dialogue **Éléments extraits**.
1.  Dans le Concepteur de rapports, sur le menu **Outils**, cliquez sur **Éléments extraits**.
2.  Dans la boîte de dialogue **Éléments extraits**, sélectionnez **Afficher les éléments de tous les utilisateurs**. La liste est mise à jour pour afficher tous les blocs élémentaires qui sont extraits et les utilisateurs qui les ont extraits.
3.  Sélectionnez un bloc élémentaire, puis cliquez sur **Annuler l'extraction**.
4.  Cliquez sur **Oui** pour vérifier le bloc élémentaire.

# <a name="see-also"></a>Voir également :

[États financiers](financial-reporting-intro.md)



