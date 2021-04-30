---
title: Créer une configuration de gestion des états électroniques pour générer des états au format Word
description: Cette rubrique explique comment les utilisateurs peuvent configurer un nouveau format de gestion des états électroniques pour générer des rapports comme documents Microsoft Word.
author: NickSelin
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 7790d7e581b9b4260a4c57af84b02a182dde953d
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894074"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Créer une configuration de gestion des états électroniques pour générer des états au format Word

[!include [banner](../includes/banner.md)]

Pour générer des états comme documents Microsoft Word, vous devez concevoir un modèle pour les rapports en utilisant, par exemple, l’application de bureau Word. L’illustration suivante montre l’exemple de modèle de rapport de contrôle qui peut être généré pour afficher les détails des paiements fournisseur traités.

![Exemple de modèle pour le rapport de contrôle dans l’application de bureau Word](./media/er-design-configuration-word-image1.png)

Pour utiliser un document Word comme modèle d’états au format Word, vous pouvez configurer une nouvelle [solution](er-quick-start1-new-solution.md) de [gestion des états électroniques](general-electronic-reporting.md). Cette solution doit inclure une [configuration](general-electronic-reporting.md#Configuration) de gestion des états électroniques qui contient un composant de [format](general-electronic-reporting.md#FormatComponentOutbound) de gestion des états électroniques.

> [!NOTE]
> Lorsque vous créez une configuration de format de gestion des états électroniques pour générer des états au format Word, vous devez soit sélectionner **Word** comme le type de format dans la boîte de dialogue déroulante **Créer une configuration**, soit laisser le champ **Type de format** vide.

![Créer une configuration du format personnalisé sur la page Configurations](./media/er-design-configuration-word-image2.gif)

Le composant de format de gestion des états électroniques de la solution doit contenir l’élément de format **Excel\\File**, et cet élément de format doit être lié au document Word qui sera utilisé comme modèle pour les états générés lors de l’exécution. Pour configurer le composant de format de gestion des états électroniques, vous devez ouvrir la version [Brouillon](general-electronic-reporting.md#component-versioning) de la configuration de gestion des états électroniques créée dans le concepteur de format de gestion des états électroniques. Puis ajoutez l’élément de **Excel\\File**, joignez votre modèle Word au format de gestion des états électroniques modifiable et associez ce modèle à l’élément **Excel\\File** que vous avez ajouté.

> [!NOTE]
> Lorsque vous joignez manuellement un modèle, vous devez utiliser un [type de document](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) précédemment [configuré](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) dans les paramètres de gestion des états électroniques pour enregistrer les modèles de formats de gestion des états électroniques.

![Joindre un modèle sur la page Concepteur de format](./media/er-design-configuration-word-image3.gif)

Vous pouvez ajouter des éléments imbriqués **Excel\\Range** et **Excel\\Cell** pour l’élément **Excel\\File** pour préciser la structure des données qui seront saisies dans les états générés au moment de l’exécution. Vous devez ensuite associer ces éléments aux sources de données du format de gestion des états électroniques modifiable pour spécifier les données réelles qui seront entrées dans les états générés lors de l’exécution.

![Ajouter les éléments imbriqués sur la page Concepteur de format](./media/er-design-configuration-word-image4.gif)

Lorsque vous enregistrez vos modifications au format de gestion des états électroniques au moment de la conception, la structure de format hiérarchique est stockée dans le modèle Word joint en tant que [partie XML personnalisée](/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) qui est nommé **État**. Vous devez accéder au modèle modifié, le télécharger depuis Finance, le stocker localement et l’ouvrir dans l’application de bureau Word. L’illustration suivante montre l’exemple de modèle stocké localement pour le rapport de contrôle qui contient la partie XML personnalisée **État**.

![Afficher l’aperçu du modèle pour le rapport de contrôle dans l’application de bureau Word](./media/er-design-configuration-word-image5.gif)

Lors de la liaison des éléments de format **Excel\\Range** et **Excel\\Cell** au moment de l’exécution, les données fournies par chaque liaison sont intégrées au document Word en tant que champ individuel de la partie XML personnalisée **État**. Pour entrer les valeurs des champs de la partie XML personnalisée dans un document généré, vous devez ajouter le mot approprié [contrôles de contenu](/office/client-developer/word/content-controls-in-word) à votre modèle Word pour servir d’espace réservé pour les données qui seront renseignées lors de l’exécution. Pour spécifier la manière dont les contrôles de contenu sont remplis, mappez chaque contrôle de contenu au champ approprié de la partie XML personnalisée **État**.

![Ajout et mappage de contrôles de contenu dans l’application de bureau Word](./media/er-design-configuration-word-image6.gif)

Vous devez ensuite remplacer le modèle Word d’origine du format pour la gestion des états électroniques modifiable par le modèle modifié qui contient désormais les contrôles de contenu Word mappés aux champs de la partie XML personnalisée **État**.

![Remplacer le modèle sur la page du concepteur de format](./media/er-design-configuration-word-image7.gif)

Lorsque vous exécutez le format pour la gestion des états électroniques configuré, le modèle Word joint est utilisé pour générer un nouveau rapport. Les données réelles sont stockées dans le rapport Word en tant que partie XML personnalisée nommée **État**. Lorsque le rapport généré est ouvert, les contrôles de contenu Word sont remplis avec les données de la partie XML personnalisée **État**.

## <a name="frequently-asked-questions"></a>Forum aux questions

**Question :** J’ai configuré un format pour la gestion des états électroniques pour imprimer un document Word contenant une adresse d’entreprise. Dans le modèle Word pour ce format pour la gestion des états électroniques, j’ai inséré un contrôle de contenu en texte enrichi pour présenter une adresse d’entreprise. Dans Finance, j’ai entré l’adresse de l’entreprise sous forme de texte multiligne et j’ai sélectionné **Entrée** pour ajouter un retour chariot pour chaque ligne que j’ai entrée. Par conséquent, je m’attends à ce que l’adresse de l’entreprise apparaisse sous forme de texte multiligne dans les documents générés. Cependant, l’adresse apparaît sous la forme d’une seule ligne de texte contenant des symboles spéciaux au lieu de retours chariot. Quel est le problème avec mes paramètres ?

**Réponse :** au lieu d’utiliser un contrôle de contenu de texte enrichi, vous devez utiliser un contrôle de contenu de texte brut et cocher la case **Autoriser les retours chariot (plusieurs paragraphes)** dans les propriétés du contrôle.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Réutiliser les configurations pour la gestion des états électroniques avec des modèles Excel pour générer des rapports au format Word](./tasks/er-design-configuration-word-2016-11.md)
- [Intégrer des images et des formes dans les documents que vous générez ER à l’aide de la gestion des états électroniques (ER)](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]