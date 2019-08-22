---
title: Définitions d'arborescence de génération d'états dans les états financiers
description: Cet article fournit des informations sur les définitions d'arborescence de génération d'états. Une définition d’arborescence de génération d'états est un composant d’état, ou un bloc élémentaire, qui vous permet de définir la structure et la hiérarchie de votre organisation.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 57592
ms.assetid: 747faa47-9a23-4277-bc11-8d0a1267c3a4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8127c694d21064392b1932525a87044b9554973d
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849531"
---
# <a name="reporting-tree-definitions-in-financial-reports"></a>Définitions d'arborescence de génération d'états dans les états financiers

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur les définitions d'arborescence de génération d'états. Une définition d’arborescence de génération d'états est un composant d’état, ou un bloc élémentaire, qui vous permet de définir la structure et la hiérarchie de votre organisation.

Les états financiers prennent en charge la génération d'états flexible afin qu'il soit facile d'apporter des modifications à mesure que la structure de votre organisation change. Les états sont générés à partir de différents composants ou de blocs élémentaires. Un de ces blocs élémentaire est une définition de l’arborescence de génération d'états. Une définition de l’arborescence de génération d'états permet de définir la structure et la hiérarchie de votre organisation. Il s'agit d'une hiérarchie inter-dimensionnelles basée sur des relations dimensionnelles dans vos données financières. Elle fournit des informations au niveau de l’unité de génération d'états et à un niveau synthétique pour toutes les unités dans l’arborescence. Les définitions d'arborescence de génération d'états peuvent être combinées avec les définitions de colonne et les définitions d'état pour créer un groupe de blocs élémentaires pouvant être utilisé par plusieurs sociétés. Une unité de génération d'état est utilisée pour chaque case d'un organigramme. Une unité organisationnelle peut être un service issu des données financières ou une unité de synthèse de niveau supérieur qui combine des informations provenant d'autres unités organisationnelles. Pour une définition d'état incluant une arborescence de génération d'états, un état est généré pour chaque unité de génération d'état et pour le niveau de synthèse. Tous ces états utilisent les définitions de ligne et de colonne spécifiées dans la définition d'état, sauf si la définition d'état indique d'utiliser l'arborescence de génération d'états de la définition de ligne. Les définitions de ligne et de colonne sont des composantes importantes de la conception et de la fonctionnalité des états financiers. Les arborescences de génération d'états augmentent la puissance des composants et prennent en charge la génération d'états flexible à mesure que la structure de l'organisation change. Les états financiers qui ne sont pas fondés sur une arborescence de génération d'états utilisent uniquement certaines des fonctionnalités de génération d'états financiers. Vous pouvez utiliser plusieurs définitions d'arborescence de génération d'états avec les mêmes définitions de ligne et de colonne pour afficher les données de votre organisation de différentes manières.

## <a name="reporting-tree-best-practices"></a>Bonnes pratiques d'arborescence de génération d'états
Avant de créer une arborescence de génération d'états, tenez compte des bonnes pratiques suivantes :

- déterminez d'abord les dimensions de déclaration dont a besoin votre entité juridique ou votre société ;
- considérez la manière dont vous avez paramétré votre structure, puis tracez un organigramme de votre société. Grâce à l'organigramme hiérarchique, vous pouvez déterminer la façon dont vous souhaitez regrouper les unités organisationnelles dans un ou plusieurs organigrammes d'entreprise.
- Commencez par le niveau de détail disponible le plus bas, comme les départements et projets définis dans les données financières. Ajoutez autant de cases au niveau de détail que nécessaire pour refléter les divisions ou régions de niveau supérieur. Chaque case représente une unité potentielle de génération d'état dans toute arborescence de génération d'états que vous créez.
- Vous devez également prendre en compte la meilleure façon de construire les arborescences. Vous pouvez utiliser un processus d'élaboration automatisé pour générer une arborescence de génération d'états, ou vous pouvez créer manuellement une arborescence de génération d'états. Il est important de comprendre les deux méthodes avant de concevoir les arborescences.
- Vous pouvez utiliser les unités de génération d'état définies dans votre système de données financières pour ajouter ces unités de génération d'état à la définition d'arborescence de génération d'états.

## <a name="create-multiple-reporting-trees"></a> Créer plusieurs arborescences de génération d'état
Vous pouvez créer un nombre illimité d'arborescences de génération d'état pour afficher les données de votre organisation de différentes manières. Chaque organigramme d'entreprise peut contenir une combinaison quelconque de services et d'unités de synthèse. Une définition d'état peut contenir un lien vers une seule arborescence de génération d'états à la fois. En réarrangeant la structure des unités de génération d'état, vous pouvez créer différentes arborescences de génération d'état. Vous pouvez ensuite utiliser les mêmes définitions de ligne et de colonne pour chaque arborescence de génération d'états. De cette manière, vous pouvez créer rapidement différentes mises en page d'états financiers. Si vous créez plusieurs arborescences de génération d'état, vous pouvez imprimer une série de tableaux d'analyse chaque mois qui analysent et représentent les opérations de votre société de diverses manières. Pour plus d'informations, consultez les exemples des structures d'unité de déclaration à la fin de cet article.

## <a name="create-a-reporting-tree-definition"></a> Créer une définition d'arborescence de génération d'états
Une définition d'arborescence de génération d'états contient les colonnes décrites dans le tableau suivant.

| Colonne d'arborescence de génération d'états | Description |
|-----------------------|-------------|
| Société               | Nom de la société pour l'unité de déclaration. La valeur **@ANY**, qui n'est généralement affectée qu'au niveau de synthèse, permet d'utiliser l'organigramme d'entreprise pour toutes les sociétés. Toutes les branches enfants sont affectées à une société. |
| Nom de l'unité             | Code identifiant cette unité de déclaration dans l'arborescence graphique de génération d'état. Veillez à établir un système de codage unique qui est cohérent et qui sera facile à comprendre pour les utilisateurs. |
| Description de l'unité      | Le titre de l'unité de déclaration apparaît dans l'en-tête ou le pied de page de l'état si vous entrez **UnitDesc** comme code sous l'onglet **En-têtes et pieds de page** de la définition d'état. Le titre apparaît dans la description de ligne d'état si vous entrez **UnitDesc** dans la cellule **Description** de la définition de ligne. |
| Dimensions            | Une unité de déclaration qui tire les informations directement des données financières. Elle définit le positionnement logique et les longueurs pour le compte et les segments associés. Chaque ligne d'unité de génération de rapports doit avoir une dimension dans cette colonne. Vous pouvez également insérer une dimension dans une ligne d’unité de synthèse (par exemple, pour les dépenses qui sont directement liées à cette unité). Si vous entrez une dimension dans une ligne d'unité de synthèse, les comptes utilisés dans les unités parent ne doivent pas être utilisés dans les unités enfant. Dans le cas contraire, les montants peuvent être dupliqués. |
| Définitions de ligne       | Le nom de la définition de ligne pour l'unité de déclaration. La même définition de ligne est utilisée pour chaque unité de l'organigramme d'entreprise. Lorsque vous générez un rapport, cette définition de ligne sert à chaque unité organisationnelle. La définition de ligne peut inclure plusieurs liens de dimensions financières. Si une définition de ligne est spécifiée dans l’arborescence de génération d'états, activez la case à cocher **Utiliser la définition de ligne de l'arborescence de génération d'états** sur l'onglet **État** de la définition d'état. |
| Lien de ligne              | Lien de ligne à utiliser pour l'unité organisationnelle. Les liens de ligne sont définis pour permettre à la définition de ligne d'identifier les dimensions financières vers lesquelles établir un lien. |
| Lien externe         | Lien de ligne à utiliser pour cette unité organisationnelle. Les liens de ligne sont définis pour la définition de ligne pour identifier l'état à relier. |
| Fichier externe         | Chemin d’accès au fichier de la feuille de génération d'état financier duquel extraire des données. |
| Options de page          | Cette colonne détermine si les détails de l’unité de génération d'états sont supprimés lorsque l'état est affiché ou imprimé. |
| Cumul %              | Le pourcentage de l'unité de déclaration qui doit être affectée à son unité parent. Le pourcentage que vous entrez dans cette colonne s'applique à chaque ligne de la définition de ligne avant que la valeur de la ligne soit ajoutée à l'état parent. Par exemple, si une unité enfant doit être divisée également entre deux départements, les montants dans chaque ligne seront multipliés par 50 % avant que la valeur soit ajoutée à l'état du département. Une unité de génération d'état ne peut pas avoir deux unités parent. Pour répartir les montants d'une unité de déclaration entre deux unités parent, créez une autre unité de déclaration possédant la même dimension pour y cumuler les 50 % supplémentaires. Entrez des pourcentages entiers sans décimale. Par exemple, **25** représente la répartition de 25 pour cent pour le parent. Si vous incluez un point décimal (**.25**), 0,25 % est affectée au parent. Pour utiliser un pourcentage inférieur à 1 pour cent, utilisez l'option **Autoriser le cumul &lt;1 %** dans la définition d'état. Cette option se trouve sous l'onglet **Options supplémentaires** dans la boîte de dialogue **Paramètres d'état**. Vous accédez à cette boîte de dialogue à l'aide du bouton **Divers** sous l'onglet **Paramètres** de la définition d'état. |
| Sécurité de l'unité         | Restrictions d'accès aux informations de l'unité de déclaration des utilisateurs et des groupes. |
| Texte supplémentaire       | Texte inclus dans l'état. |

Pour créer une définition d'arborescence de génération d'états, procédez comme suit.

1. Permet d'ouvrir le Concepteur de rapports.
2. Cliquez sur **Fichier** &gt; **Nouveau** &gt; **Définition d'arborescence de génération d'états**.
3. Cliquez sur **Modifier** &gt; **Insérer des unités de génération d'états à partir des dimensions**.
4. Dans la boîte de dialogue **Insérer des unités de génération d'états à partir des dimensions**, cochez la case de chaque dimension à inclure dans l'arborescence de génération d'états. La boîte de dialogue **Insérer des unités de génération d'états à partir des dimensions** contient les sections suivantes.

    | Section                          | Description |
    |----------------------------------|-------------|
    | Segmentation des dimensions de la génération d'état | Les boutons **Fractionner les segments** et **Combiner les segments** permettent de modifier le nombre et la longueur des segments.<blockquote>[!NOTE] Seuls les segments que vous avez fractionnés peuvent être combinés. Pour combiner plusieurs dimensions, utilisez des caractères génériques dans les valeurs de dimension.</blockquote> |
    | Inclure/Position de caractère       | Cette section répertorie les dimensions définies dans les données financières et indique le nombre de caractères dans la valeur définie la plus longue pour chaque dimension. Activez la case à cocher d'une dimension pour inclure celle-ci dans la hiérarchie de l'arborescence de génération d'états. |
    | Hiérarchie et plages de segments     | Cette section indique la hiérarchie de dimensions. Vous pouvez déplacer les dimensions dans la liste pour modifier leur ordre de génération d'état. Dans les zones **Dimension source** et **Dimension cible**, vous pouvez spécifier une plage de valeurs dans chaque dimension. Si vous ne spécifiez pas de plage, toutes les valeurs de dimension sont insérées dans l’arborescence de génération d'états.<blockquote>[!NOTE] Si vous utilisez plusieurs dimensions, seules les combinaisons de dimensions qui ont été validées sont renvoyées dans les résultats.</blockquote> |

    Pour une capture d’écran qui illustre un exemple de la boite de dialogue **Insérer les unités organisationnelles à partir des dimensions**, reportez-vous à la section « Exemple d'insertion d'unités de déclaration à partir de la boîte de dialogue Dimensions » plus loin dans cet article.

5. Pour créer des segments supplémentaires (par exemple en divisant un segment en deux segments plus petits), cliquez sur l'emplacement approprié dans le champ **Position de caractère**, puis cliquez sur **Diviser les segments**.
6. Pour fusionner deux segments en un seul, cliquez sur dans l'une des zones des segments à fusionner, puis cliquez sur **Combiner les segments**.
7. La hiérarchie définit la manière dont les dimensions interagissent entre elles ainsi que la plage de chaque dimension. Pour modifier la hiérarchie des dimensions dans la zone **Hiérarchie et plages de segments**, sélectionnez la dimension à déplacer, puis cliquez sur **Déplacer vers le haut** ou **Déplacer vers le bas**.
8. Pour spécifier une plage de valeurs de dimension à ajouter à la nouvelle arborescence de génération d'états, dans la zone **Hiérarchie et plages de segments**, procédez comme suit :

    1. Dans le champ **Dimension source** pour cette dimension, entrez la première valeur de la plage.
    2. Dans le **Dimension cible** , entrez la dernière valeur dans la plage.

9. Répétez les étapes 7 à 8 pour chaque dimension dans la zone **Hiérarchie et plages de segments**.
10. Après avoir terminé de définir la manière dont les unités de déclaration seront introduites dans la nouvelle arborescence de génération d'états, cliquez sur **OK**.
11. Cliquez sur **Fichier** &gt; **Enregistrer** pour enregistrer l'arborescence de génération d'états. Entrez un nom unique et une description pour l'arborescence de génération d'états, puis cliquez sur **OK**.

### <a name="open-an-existing-reporting-tree-definition"></a>Ouvrir une définition d'arborescence de génération d'états existante

1. Dans le générateur d'état, cliquez sur **Définitions d'arborescence de génération d'états** dans le volet de navigation.
2. Double-cliquez sur un nom dans la liste d'arborescence de génération d'états pour l'ouvrir.
3. Pour afficher tous blocs élémentaires associés à l'arborescence de génération d'états, cliquez avec le bouton droit sur la définition d'arborescence de génération d'états, puis sélectionnez **Associations**.

### <a name="roll-up-data-in-a-reporting-tree"></a>Cumuler des données dans une arborescence de génération d'états

Lorsque vous utilisez une arborescence de génération d'états, vous pouvez agréger les montants issus des unités de déclaration enfant au niveau d'unité de déclaration parent. Cette agrégation est appelée cumul des données. Les règles suivantes permettent de cumuler les montants dans les unités parent dans une arborescence de génération d'états :

- Dans une arborescence de génération d'états, les unités enfant doivent contenir des dimensions, à moins qu'il ne s'agisse d'une arborescence de génération d'états à un seul niveau. Les unités parent ne contiennent généralement pas de dimensions dans une arborescence de génération d'états.

    > [!NOTE]
    > Si vous spécifiez des dimensions pour des unités enfant et des unités parent, vous pouvez causer la duplication des données dans l'état.

- Les unités de déclaration contenant des dimensions dans l'arborescence de génération d'états correspondent aux dimensions utilisées dans les définitions de ligne et de colonne. La combinaison des dimensions détermine les montants retournés pour cette unité. Par exemple, les lignes 6 et 7 de l'exemple 2 renverront uniquement les valeurs pour les départements 00 et 01, respectivement.
- Les montants des unités de déclaration parent qui ne contiennent pas de dimension dans l'arborescence de génération d'états sont déterminés à partir de l'état de l'unité enfant et se cumulent au montant de l'unité parent spécifiée. Par exemple, si l'unité parent (voir Contoso USA dans l'exemple 2 des exemples de cumul des données) a deux unités enfant (022 et 023) et ne contient pas de dimension, un état est généré pour chaque enfant et le parent. Le total parent est la somme des deux montants enfant.

### <a name="manage-reporting-units"></a>Gestion des unités de déclaration

Chaque définition d’arborescence de génération d'états est affichée dans des vues uniques. Il existe une vue graphique pour afficher la hiérarchie des parents et enfants et une vue de feuille de calcul qui affiche les informations spécifiques à chaque unité de déclaration. La vue graphique et la vue de feuille de calcul sont connectés. Lorsque vous sélectionnez une unité de déclaration dans une vue, elle est également sélectionnée dans l'autre vue. Vous pouvez créer des hiérarchies inter-dimensionnelles sur la base des relations dimensionnelles dans les données financières. Lorsque vous créez une définition d'arborescence de génération d'états, vous pouvez utiliser les mêmes définitions de ligne à plusieurs reprises, que vous génériez vous générez un état des revenus départemental ou un état des revenus récapitulatif consolidé. Les dimensions définies dans la définition de ligne peuvent être combinées avec les dimensions dans la définition d'arborescence de génération d'états pour fournir un grand choix de vues des performances de votre organisation.

### <a name="reporting-unit-structure"></a> Structure d'unité de déclaration

Les types d'unités de déclaration suivants sont utilisés dans la génération d'états financiers :

- Une unité détaillée tire les informations directement des données financières, à partir d'une feuille de calcul Excel, ou d'une autre feuille de calcul de génération d'états financiers.
- Une unité de synthèse résume les données issues des unités de niveau inférieur.

Une unité de déclaration parent est une unité de synthèse qui agrège les informations résumées d'une unité détaillée. Une unité de synthèse peut être à la fois une unité de détail et une unité de synthèse. Par conséquent, une unité de synthèse peut tirer des informations d’une unité de niveau inférieur, des données financières ou d'une feuille de calcul Excel. Une unité parent peut être l'unité enfant d'une unité parent plus élevée. Une unité de déclaration enfant peut être une unité détaillée qui extrait les informations directement des données financières ou d'une feuille de calcul Excel. Une unité de génération d'états enfant peut également être une unité de synthèse intermédiaire. En d’autres termes, elle peut être l’unité parent d’une unité de niveau inférieur et également l’unité enfant d’une unité de synthèse de niveau supérieur. Dans le scénario le plus courant pour les unités de déclaration est d'avoir les unités parent avec une cellule vide dans la colonne **Dimension** et d'avoir des unités enfant avec des liens vers des combinaisons de dimensions spécifiques ou génériques.

### <a name="organize-reporting-units"></a> Organisation des unités de déclaration

Vous pouvez réorganiser la structure organisationnelle d'une définition d'arborescence de génération d'états en déplaçant les unités de déclaration dans la vue graphique. Vous pouvez également faire passe des unités de déclaration à un niveau supérieur dans l'arborescence de génération d'états, ou les restreindre à un niveau inférieur.

1. Dans le générateur d'état, ouvrez la définition d'arborescence de génération d'états à modifier.
2. Dans la vue graphique de la définition d'arborescence de génération d'états, sélectionnez une unité de déclaration.
3. Faites glisser l’unité vers un nouvel emplacement. Sinon, cliquez avec le bouton droit sur l'unité et sélectionnez **Promouvoir l'unité de déclaration** ou **Rétrograder l'unité de déclaration**.
4. Cliquez sur **Fichier** &gt; **Enregistrer** pour enregistrer les modifications.

### <a name="add-text-about-a-reporting-unit"></a> Ajouter un texte à une unité de déclaration

Une entrée de texte supplémentaire est une chaîne de texte statique, jusqu'à 255 caractères, qui ajoute des informations à la définition d'arborescence de génération d'états. Par exemple, le texte supplémentaire peut être une description courte de la société. Vous pouvez créer jusqu'à dix entrées de texte supplémentaires pour chaque unité de déclaration dans une définition d'arborescence de génération d'états. Le texte supplémentaire apparaît dans l'état de l'unité de déclaration à laquelle le texte est affecté. Vous pouvez ajouter des entrées de texte à partir de la colonne **Description** de la définition de ligne et de l'onglet **En-têtes et pieds de page** dans la définition d'état.

1. Dans le générateur d'état, ouvrez la définition d'arborescence de génération d'états à modifier.
2. Double-cliquez sur la cellule **Texte supplémentaire** pour la ligne d'unité de déclaration.
3. Dans la première ligne vide de la boîte de dialogue **Texte supplémentaire**, tapez le texte. La première ligne qui contient du texte est référencée comme UnitText1, indépendamment de sa position dans la boîte de dialogue **Texte supplémentaire**.
4. Pour ajouter des entrées de texte pour cette unité de déclaration, tapez le texte dans une ligne vide.
5. Cliquez sur **OK**.

### <a name="remove-additional-text-from-a-reporting-unit"></a>Supprimer du texte supplémentaire à partir d'une unité de déclaration

1. Dans le Concepteur de rapports, ouvrez la définition d'organigramme d'entreprise à modifier.
2. Double-cliquez sur la cellule **Texte supplémentaire** de la ligne d'unité organisationnelle.
3. Dans la boîte de dialogue **Texte supplémentaire**, sélectionnez l'entrée à supprimer, puis cliquez sur Effacer, ou cliquez avec le bouton droit et sélectionnez **Effacer**. Sinon, cliquez avec le bouton droit sur l’entrée et sélectionnez **Couper**.
4. Cliquez sur **OK**.

### <a name="restrict-access-to-a-reporting-unit"></a>Limiter l'accès à une unité de déclaration

Vous pouvez empêcher certains utilisateurs et groupes d'accéder à une unité de déclaration. Vous pouvez également définir des restrictions afin qu’elles s’appliquent aux unités de génération d'états enfants de l’unité de génération d'état.

1. Dans le générateur d'état, ouvrez la définition d'arborescence de génération d'états à modifier.
2. Double-cliquez sur la cellule **Sécurité d'unité** de la ligne de l'unité organisationnelle dont vous souhaitez limiter l'accès.
3. Dans la boîte de dialogue **Sécurité de l'unité**, cliquez sur **Utilisateurs et groupes**.
4. Sélectionnez les utilisateurs ou les groupes qui auront accès à l'unité de déclaration limitée, puis cliquez sur **OK**.
5. Pour limiter l'accès aux unités de déclaration enfant, activez la case **Ajoutez une sécurité aux unités de déclaration enfant**.
6. Cliquez sur **OK**.

### <a name="remove-access-to-a-reporting-unit"></a>Supprimer l'accès à une unité de déclaration

1. Dans le générateur d'état, ouvrez la définition d'arborescence de génération d'états à modifier.
2. Double-cliquez sur la cellule **Sécurité de l'unité** pour la ligne d'unité de déclaration à laquelle supprimer l'accès.
3. Dans la boîte de dialogue **Sécurité de l'unité**, sélectionnez un nom, puis cliquez sur **Supprimer**.
4. Cliquez sur **OK**.

### <a name="link-toreports"></a>Lien vers les états

Après avoir créé une colonne **État** dans la définition de ligne et avoir spécifié l'état à inclure dans l'état, vous devez mettre à jour l'arborescence de génération d'états avec la colonne liée et les informations d'état. Un état peut être importé dans n'importe quelle unité de l'arborescence de génération d'états.

### <a name="identify-the-report-in-a-reporting-tree"></a>Identifier l'état dans une arborescence de génération d'états

1. Dans le générateur d'état, ouvrez la définition d'arborescence de génération d'états à modifier.
2. Dans la colonne **Définitions de ligne**, les informations dans les cellules sont fondées sur les informations de la ligne sélectionnée, car la même définition de ligne doit être utilisée dans toutes les unités de l'arborescence de génération d'états. Double-cliquez sur la cellule **Définitions de ligne**, puis sélectionnez la définition de ligne qui contient les informations sur l'état.
3. Dans la cellule **Lien de feuille de calcul** d'une unité de déclaration, sélectionnez le nom du lien correspondant à l'état.
4. Dans la cellule **Chemin du classeur ou de l'état** d'une unité de déclaration, entrez le nom de l'état ou recherchez l'état.
5. Pour spécifier une feuille de calcul dans un état, entrez le nom de la feuille de calcul dans la cellule **Nom de la feuille de calcul**.
6. Répétez les étapes 3 à 5 pour chaque unité de déclaration qui doit recevoir des données d'un état. Pour empêcher que des données erronées apparaissent dans votre état, vérifiez que les noms d'état corrects apparaissent dans l'unité correspondante de l'arborescence de génération d'états.

## <a name="examples"></a>Exemples
### <a name="reporting-unit-structure--example-1"></a>Structure d'unité de déclaration, exemple 1

Voici la structure des unités de génération d'états dans l'arborescence de génération d'états suivante :

- L’unité de génération d'états Contoso Japan est une unité parent des unités enfants Contoso Japan Sales et de Contoso Japan Consulting.
- L'unité de division Contoso Japan Sales est une unité enfant de l'unité Contoso Japan et une unité parent des unités Home Sales et Auto Sales.
- Les unités de déclaration du niveau le plus bas (Home Sales, Auto Sales, Client Services, et Operations) représentent les départements dans les données financières. Ces unités de déclarations se trouvent dans la zone grisée du schéma.
- Les unités de synthèse du plus haut niveau résument les informations des unités de détail.

[![ContosoEntertainmentSummaryReportStructure](./media/contosoentertainmentsummaryreportstructure.png)](./media/contosoentertainmentsummaryreportstructure.png)

### <a name="reporting-unit-structure--example-2"></a>Structure d'unité de déclaration, exemple 2

Le schéma suivant présente une arborescence de génération d'états qui affiche une structure d'organisation est divisée par fonctions dans l'entreprise.

[![summaryofallunitscontoso](./media/summaryofallunitscontoso.png)](./media/summaryofallunitscontoso.png)

### <a name="example-of-the-insert-reporting-units-from-dimensions-dialog-box"></a>Exemple de la boîte de dialogue Insérer des unités de déclaration à partir des dimensions

L'illustration suivante présente un exemple de la boîte de dialogue **Insérer des unités de déclaration à partir des dimensions**. Pour cet exemple, les résultats renvoient la combinaison des unités commerciales, des centres de coût et des départements.

[![InsertReportingUnits](./media/insertreportingunits.png)](./media/insertreportingunits.png)

La définition d’arborescence de génération d'états qui en résulte est triée par unité commerciale, puis par centre de coût et par département. La dimension de la cinquième unité de génération d'états est **Unité commerciale = \[001\], Centre de coût = \[\], Département = \[022\]** et identifie une unité de génération d'états pour les comptes qui sont spécifiques à l'unité commerciale 001 et au département 022.

[![ReportingTree](./media/reportingtree-1024x646.png)](./media/reportingtree.png)

### <a name="examples-of-data-roll-up"></a>Exemples de cumul de données

Les exemples suivants montrent les informations possiblement utilisées dans une définition d'arborescence de génération d'états pour des données cumulées.

#### <a name="example-1"></a>Exemple 1

[![MutliCompanyRollUp](./media/mutlicompanyrollup.png)](./media/mutlicompanyrollup.png)

#### <a name="example-2"></a>Exemple 2 :

[![CrossCompanyDepartmentRollUp](./media/crosscompanydepartmentrollup.png)](./media/crosscompanydepartmentrollup.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[États financiers](financial-reporting-intro.md)
