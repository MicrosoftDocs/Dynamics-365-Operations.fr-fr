---
title: Prise en charge des appels paramétrés des sources de données de gestion des états électroniques (ER) de type Champ calculé
description: Cette rubrique offre des informations concernant l’utilisation du type Champ calculé pour les sources de données de gestion des états électroniques.
author: NickSelin
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3f21b323ddbf653bf8ca8dd1f879a6bdbddcdefc
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681254"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a>Prise en charge des appels paramétrés des sources de données de gestion des états électroniques (ER) de type Champ calculé

[!include [banner](../includes/banner.md)]

Cette rubrique explique comment vous pouvez concevoir une source de données de gestion des états électroniques à l’aide du type **Champ Calculé**. Cette source de données peut contenir une expression de gestion des états électroniques qui, une fois exécutée, peut être contrôlée par les valeurs des arguments de paramètre qui sont configurés dans une liaison qui appelle cette source de données. En configurant les appels paramétrés d’une telle source de données, vous pouvez réutiliser une seule source de données dans de nombreuses liaisons, ce qui réduit le nombre total de sources de données qui doivent être configurées dans les mappages de modèle de gestion des états électroniques ou de formats de gestion des états électroniques. Cela simplifie également le composant de gestion des états électroniques configuré, ce qui réduit les coûts de maintenance et le coût d’utilisation par d’autres consommateurs.

## <a name="prerequisites"></a>Conditions préalables
Pour exécuter les exemples décrits dans cette rubrique, vous devez disposer de l’accès suivant :

- Accès à l’un de ces rôles :

    - Développeur d’états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

- Accès aux Regulatory Configuration Services (RCS) qui ont été mis en service pour le même locataire que Finance and Operations, pour un des rôles suivants :

    - Développeur de gestion des états électroniques
    - Consultant fonctionnel des états électroniques
    - Administrateur système

Vous devez également télécharger et localement enregistrer les fichiers suivants.

| **Contenu**                           | **Nom de fichier**                                        |
|---------------------------------------|------------------------------------------------------|
| Exemple de configuration de modèle de données ER    | [Model to learn parameterized calls.version.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| Exemple de configuration de métadonnées ER      | [Metadata to learn parameterized calls.version.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| Exemple de configuration de mappage de modèles ER | [Mapping to learn parameterized calls.version.1.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| Exemple de configuration de format ER        | [Format to learn parameterized calls.version.1.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a>Connexion à votre instance RCS
Dans cet exemple, vous allez créer une configuration pour l’exemple de société, Litware, Inc. Tout d’abord, dans RCS, vous devez suivre les étapes de la procédure [Créer des fournisseurs de configuration et les marquer comme actifs](tasks/er-configuration-provider-mark-it-active-2016-11.md) :

1. Dans le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.
2. Sélectionnez **Configurations des états**.
3. Importez les configurations téléchargées vers RCS dans l’ordre suivant : modèle de données, métadonnées, mise en correspondance des modèles, format. Procédez comme suit pour chaque configuration de gestion des états électroniques :

    1. Sélectionnez **Échanger**.
    2. Sélectionnez **Charger depuis le fichier XML**.
    3. Sélectionnez **Parcourir**, puis sélectionnez la configuration ER requise au format XML.
    4. Cliquez sur **OK**.

## <a name="review-the-provided-er-solution"></a>Examen de la solution ER fournie

### <a name="review-model-mapping"></a>Examen de la mise en correspondance des modèles

1. Dans l’arborescence de configuration, développez le contenu de l’élément **Modèle pour l’apprentissage des appels paramétrés**.
2. Sélectionnez **Mise en correspondance pour l’apprentissage des appels paramétrés**.
3. Sélectionnez **Concepteur**.
4. Sélectionnez **Concepteur**.  
   
    Cette mise en correspondance des modèles de gestion des états électroniques est conçue pour faire ce qui suit :

    - Récupérez la liste des codes taxe (source de données **Taxe**) se trouvant dans la table **TaxTable**.
    - Récupérez la liste des transactions de taxe (source de données **Trans**) se trouvant dans la table **TaxTrans**.
    
        - Regroupez la liste des transactions extraites (source de données **Gr** ) par code taxe.
        - Calculer les transactions regroupées selon les valeurs cumulées par code taxe :

            - Somme des valeurs de base de taxe.
            - Somme des valeurs de taxe.
            - Valeur minimale du taux de taxe appliqué.

    La mise en correspondance des modèles dans cette configuration met en œuvre le modèle des données de base pour tous les formats de gestion des états électroniques créés pour ce modèle et exécutés dans Finance and Operations. Par conséquent, le contenu **Taxe** et source de données **Gr** est exposé pour les formats de gestion des états électroniques tels que des sources de données abstraites.

    ![Page du concepteur de mise en correspondance des modèles affichant les sources des données Taxe et Gr](media/er-calculated-field-type-01.png)

5.  Fermez la page **Concepteur de mise en correspondance des modèles**.
6.  Fermez la page **Mise en correspondance des modèles**.

### <a name="review-format"></a>Examen du format

1. Dans l’arborescence de configuration, développez le contenu de l’élément **Modèle pour l’apprentissage des appels paramétrés**.
2. Sélectionnez **Format pour l’apprentissage des appels paramétrés**.
3. Sélectionnez **Concepteur**. Ce format de gestion des états électroniques est conçue pour faire ce qui suit :

    - Générez un relevé de taxe au format XML.
    - Présentez les niveaux suivants de taxation dans le relevé de taxe : normal, réduit et aucun.
    - Présentez plusieurs détails à chaque niveau de taxation, avec un nombre différents de détails à chaque niveau.

    ![Page Concepteur de formats](media/er-calculated-field-type-02.png)

4. Sélectionnez **Mappage**.
5. Développez les articles **Modèle**, **Données** et **Synthèse**. 

    Le champ calculé **Model.Data.Summary.Level** contient l’expression qui renvoie le code du niveau de taxation (**Normal**, **Réduit**, **Aucun,** ou **Autre**) comme valeur de texte pour un code taxe pouvant être récupéré de la source de données **Model.Data.Summary** au moment de l’exécution.

    ![Page du concepteur de format affichant les détails du modèle Modèle de données pour l’apprentissage des appels paramétrés](media/er-calculated-field-type-03.png)

6. Développez l’article **Modèle**. **Data2**.
7. Développez l’article **Modèle**. **Data2.Summary2**.
   
    La source de données **Model**.**Data2.Summary2** est configurée pour regrouper les détails de transaction de la source de données **Model.Data.Summary** par niveau de taxation (renvoyé par le champ calculé **Model.Data.Summary.Level**) et calcul les agrégations.

    ![Page du concepteur de format présentant les détails de la source de données Model.Data2.Summary2](media/er-calculated-field-type-04.png)

8. Examinez les champs calculés **Modèle**.**Data2.Level1**, **Modèle**.**Data2.Level2** et **Modèle**.**Data2.Level3.** Ces champs calculés sont utilisés pour filtrer la liste des enregistrements **Modèle**.**Data2.Summary2** et renvoyer uniquement les enregistrements qui représentent un niveau de taxation spécifique.
9. Fermez la page **Concepteur de format**.

## <a name="create-a-derived-format"></a>Créer un format dérivé
Vous pouvez améliorer le format de livraison en ajoutant un champ calculé pour filtrer le niveau requis de taxation au lieu d’utiliser les trois champs existants : **Modèle**.**Data2.Level1**, **Modèle**.**Data2.Level2** et **Modèle**.**Data2.Level3**. Le niveau de taxation requis peut être précisé à l’emplacement où ce nouveau champ calculé sera appelé.

1. Dans l’arborescence de configuration, développez le contenu de l’élément **Modèle pour l’apprentissage des appels paramétrés**.
2. Sélectionnez **Format pour l’apprentissage des appels paramétrés**.
3. Sélectionnez **Créer une configuration**.
4. Sélectionnez **Provenant du nom : Format pour l’apprentissage des appels paramétrés, Microsoft**.
5. Dans le champ **Nom**, entrez **Format pour l’apprentissage des appels paramétrés (personnalisés)**.
6. Sélectionnez **Créer une configuration**.

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a>Configuration d’un champ calculé paramétré qui renvoie une liste des enregistrements

### <a name="start-adding-a-new-calculated-field"></a>Commencer l’ajout d’un nouveau champ calculé

1. Sélectionnez **Concepteur**.
2. Sélectionnez **Développer/Réduire** pour développer tous les articles de format.
3. Sélectionnez **Mappage**.
4. Développez l’article **Modèle**.
5. Sélectionnez l’article **Modèle.Data2**.
6. Sélectionnez **Ajouter**.
7. Sélectionnez **Fonctions\\Champ calculé**.
8. Dans le champ **Nom**, entrez **Niveaux**.
9. Sélectionnez **Modifier la formule**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Définir un paramètre pour ajouter un champ calculé

1. Sélectionnez **Paramètres**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom**, entrez **Niveau de taxation**.
4. Dans le champ **Type**, sélectionnez **Chaîne**.

    Seuls les types de données principaux peuvent être utilisés pour préciser le type d’argument du paramètre. Par conséquent, les types **Liste d’enregistrement**, **Enregistrement** et **Énumération** ne peuvent pas être utilisés à cet effet.

    Le nombre maximum de paramètres pouvant être spécifiés pour un unique champ calculé est 8.

    ![Liste de source de données des paramètres](media/er-calculated-field-type-05.png)

5. Cliquez sur **OK**.

En ajoutant ce paramètre, vous précisez la condition qui doit être en place pour appeler ce champ calculé. Lorsque vous appelez ce champ calculé, vous devez spécifier l’argument du paramètre **Niveau de taxation** comme valeur avec le format **Chaîne**.

   Assurez-vous que vous définissez des paramètres uniquement pour ces champs calculés qui se trouvent dans un conteneur ( **Liste d’enregistrement**, **Enregistrement** ou **Conteneur**).

   Le paramètre configuré est disponible dans la liste des sources de données de ce champ calculé. Vous pouvez ajouter le paramétrage à l’expression configurée en sélectionnant **Ajouter la source de données**.

   ![Champs de source de données](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Définir une expression pour ajouter un champ calculé

1. Dans le champ **Formule**, saisissez : 

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level =**
    
2. Sélectionnez le paramètre **Niveau de taxation** dans la liste des sources de données.
3. Sélectionnez **Ajouter une source de données**.
4. Dans le champ **Formule**, finalisez l’expression comme suit :  

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level = ’Taxation Level’)**

5. Sélectionnez **Enregistrer**.

    ![Informations sur le champ de source de données](media/er-calculated-field-type-07.png)

6. Fermez la page **Concepteur de formule**.

### <a name="finish-adding-a-new-calculated-field"></a>Terminer l’ajout d’un nouveau champ calculé

- Cliquez sur **OK**.

Sur la page **Concepteur de format**, le champ calculé paramétré configuré **Niveaux** exige un argument **Chaîne**.

![Liste développée des niveaux de champ calculé](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a>Utiliser le champ calculé configuré pour lier les éléments de format

1. Sélectionnez **Model.Data2.Levels** pour sélectionner le champ calculé configuré.
2. Sélectionnez l’élément de format **Statement.Taxation.Regular**.
3. Sélectionnez **Lier**.
4. Sélectionnez **Oui** pour confirmer le remplacement de la source de données utilisée actuellement, **Level1**, par la nouvelle source de données, **Niveaux**, dans tous les éléments de format imbriqués de l’élément de format sélectionné.

    La liaison appliquée a été créée comme appel du champ calculé paramétré. Par défaut, le nom de l’élément de format lié est utilisé comme argument pour le champ calculé paramétré sous les conditions suivantes :

      - Le champ calculé est configuré pour utiliser un unique paramètre.
      - Le type de données de ce paramètre est défini sur **Chaîne**.

    Lorsque le nom de l’élément de format lié est vide, le nom de source de données de cet élément est utilisé dans la liaison appliquée.

5. Sélectionnez l’élément de format **Statement.Taxation.Reduced**.
6. Sélectionnez **Lier**.
7. Sélectionnez **Oui** pour confirmer le remplacement de la source de données utilisée actuellement, **Level2**, par la nouvelle source de données, **Niveaux**, dans tous les éléments de format imbriqués de l’élément de format sélectionné.
8. Sélectionnez l’élément de format **Statement.Taxation.None**.
9. Sélectionnez **Lier**.
10. Sélectionnez **Oui** pour confirmer le remplacement de la source de données utilisée actuellement, **Level3**, par la nouvelle source de données, **Niveaux**, dans tous les éléments de format imbriqués de l’élément de format sélectionné.

   Lorsque vous spécifiez l’argument du champ calculé paramétré pour l’élément XML représentant le niveau de taxation (par exemple, la valeur **Model.Data2.Levels("Reduced")** comme valeur de texte), il est inutile de faire de même pour les attributs XML imbriqués. Leurs liaisons hériteront automatiquement de la valeur de l’argument définie sur le niveau parent (**Model.Data2.Levels.aggregated.Base**, **Model.Data2.Levels("Reduced").aggregated.Base**).

Les appels récurrents de tout champ calculé paramétré ne sont pas pris en charge.

Vous pouvez sélectionner **Modifier la formule**, et changer l’argument appliqué par défaut du champ calculé paramétré dans la liaison sélectionnée. Si cet argument manque, cela peut générer des erreurs à l’exécution. Les utilisateurs sont informés d’une telle situation lorsque le format actuel est validé.

![Notification d’avertissement de validation](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a>Configuration d’un champ calculé paramétré qui renvoie un enregistrement
Lorsqu’un champ calculé paramétré renvoie un enregistrement, vous devez prendre en charge la liaison des champs individuels de cet enregistrement avec les éléments de format. En pareille situation, il n’y aura pas de liaison parente qui contient la valeur d’un argument pour appeler un champ calculé paramétré. Cette valeur doit être définie dans la liaison d’un seul champ d’enregistrement.

### <a name="start-adding-a-new-calculated-field"></a>Commencer l’ajout d’un nouveau champ calculé

1. Sélectionnez l’article **Modèle.Data2**.
2. Sélectionnez **Ajouter**.
3. Sélectionnez **Fonctions\\Champ calculé**.
4. Dans le champ **Nom**, entrez **LevelRecord**.
5. Sélectionnez **Modifier la formule**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Définir un paramètre pour ajouter un champ calculé

1. Sélectionnez **Paramètres**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom**, entrez **Niveau de taxation**.
4. Dans le champ **Type**, sélectionnez **Chaîne**.
5. Cliquez sur **OK**.

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Définir une expression pour ajouter un champ calculé

1. Dans le champ **Formule**, entrez l’expression suivante :  
    
    **FIRSTORNULL(\@.Levels(**

2. Sélectionnez le paramètre **Niveau de taxation**.
3. Sélectionnez **Ajouter une source de données**.
4. Dans le champ **Formule**, ajoutez **’Taxation Level’))** à ce que vous avez entré dans l’étape 1 pour finaliser l’expression :  
    
    **FIRSTORNULL(\@.Levels(’Taxation Level’))**

5. Sélectionnez **Enregistrer**.
6. Fermez la page **Concepteur de formule**.

### <a name="finish-adding-a-new-calculated-field"></a>Terminer l’ajout d’un nouveau champ calculé

-   Cliquez sur **OK**.

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a>Utiliser le champ calculé configuré pour lier les éléments de format

1. Développer **Model.Data2.LevelRecord** pour sélectionner le champ calculé configuré.
2. Développez le conteneur **Model.Data2.LevelRecord.aggregated** pour sélectionner le champ calculé configuré.
3. Sélectionnez le champ **Model.Data2.LevelRecord.aggregated.Base**.
4. Sélectionnez l’élément de format **Statement.Taxation.None**.
5. Sélectionnez **Annuler la liaison**.
6. Sélectionnez l’élément de format **Statement.Taxation.None.Base**.
7. Sélectionnez **Lier**.
8. Sélectionnez **Modifier la formule**.
9. Changez l’expression pour **Model.Data2.LevelRecord("None").aggregated.Base**.

![Expression mise à jour](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a>Supprimer les champs calculés qui ne sont pas utilisés

1. Sélectionnez **Model.Data2.Level1**.
2. Sélectionnez **Supprimer**.
3. Sélectionnez **Model.Data2.Level2**.
4. Sélectionnez **Supprimer**.
5. Sélectionnez **Model.Data2.Level3**.
6. Sélectionnez **Supprimer**.
7. Sélectionnez **Enregistrer**.

  > [!NOTE]
  > Vous avez réutilisé le même champ calculé **Model.Data2.Levels** plusieurs fois dans les liaisons de format. Il est beaucoup plus facile d’utiliser et de tenir à jour seul un champ calculé au lieu de le faire pour plusieurs champs similaires.

8. Fermez la page **Concepteur de format**.

## <a name="complete-adjusted-version-of-a-derived-format"></a>Terminer la version ajustée d’un format dérivé

1. Dans l’organisateur **Versions**, sélectionnez **Modifier le statut**.
2. Sélectionnez **Terminer**.

## <a name="export-completed-version-of-a-derived-format"></a>Exporter la version terminée d’un format dérivé

1. Sélectionnez le format **Format pour l’apprentissage des appels paramétrés (personnalisé)** dans l’arborescence de configurations.
2. Dans l’organisateur **Versions**, sélectionnez la version terminée 1.1.1.
3. Sélectionnez **Exchange**.
4. Sélectionnez **Exporter en tant que fichier XML**.
5. Enregistrez la configuration téléchargée localement, au format XML.

## <a name="test-er-formats"></a>Tester les formats de gestion des états électroniques 
Vous pouvez exécuter les formats de gestion des états électroniques d’origine et améliorés pour veiller à ce que les champs calculés paramétrés configurés fonctionnent correctement.

### <a name="import-er-configurations"></a>Importer les configurations ER
Vous pouvez importer des configurations révisées depuis RCS à l’aide du référentiel de gestion des états électroniques de type **RCS**. Si vous avez déjà effectué la procédure de la rubrique [Importer les configurations des états électroniques (ER) des services de configuration réglementaires (RCS)](rcs-download-configurations.md), utilisez le référentiel de gestion des états électroniques configurés pour importer les configurations abordées précédemment dans cette rubrique dans votre environnement. Sinon, procédez comme suit :

1. Sélectionnez la société **DEMF** et sur le tableau de bord par défaut, sélectionnez **Gestion des états électroniques**.
2. Sélectionnez **Configurations des états**.
3. Importez les configurations provenant du centre de téléchargement Microsoft dans l’ordre suivant : modèle de données, métadonnées, mise en correspondance des modèles, format. Procédez comme suit pour chaque configuration de gestion des états électroniques :

    1. Sélectionnez **Échanger**.
    2. Sélectionnez **Charger depuis le fichier XML**.
    3. Sélectionnez **Parcourir** pour sélectionner la configuration ER requise au format XML.
    4. Cliquez sur **OK**.

4. Importez la version finalisée 1.1.1 provenant de RCS du format **Format pour l’apprentissage des appels paramétrés (personnalisé)**  :

    1. Sélectionnez **Échanger**.
    2. Sélectionnez **Charger depuis le fichier XML**.
    3. Sélectionnez **Parcourir** pour sélectionner le fichier localement enregistré **Format pour l’apprentissage des appels paramétrés (personnalisé)** au format XML.
    4. Cliquez sur **OK**.

### <a name="run-er-formats"></a>Exécuter les formats de gestion des états électroniques

1. Dans l’arborescence de configuration, développez le contenu de l’élément **Modèle pour l’apprentissage des appels paramétrés**.
2. Sélectionnez **Format pour l’apprentissage des appels paramétrés**.
3. Sélectionnez **Exécuter** dans le ruban le plus haut.
4. Enregistrez la sortie localement générée.
5. Sélectionnez l’élément **Format pour l’apprentissage des appels paramétrés (personnalisé)**.
6. Sélectionnez **Exécuter** dans le ruban le plus haut.
7. Enregistrez la sortie localement générée. 
8. Comparez le contenu des sorties générées.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Concepteur de formule dans les états électroniques (ER)](general-electronic-reporting-formula-designer.md)
- [Améliorer les performances des solutions ER en ajoutant des sources de données CHAMP CALCULÉ paramétrées](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]