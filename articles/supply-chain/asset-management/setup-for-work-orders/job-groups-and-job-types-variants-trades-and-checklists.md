---
title: Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance
description: Cette rubrique décrit les catégories de type de tâche de maintenance et les types de tâches de maintenance, les variantes de type de tâche de maintenance, les opérations de tâches de maintenance et les listes de contrôle de maintenance dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetJobTypeDefaultForecast, EntAssetJobTrade, EntAssetJobTypeDefaultCopy, EntAssetChecklistVariableValueLookup, EntAssetChecklistTemplateCreate, EntAssetJobVariant, EntAssetJobTypeDefaultReference, EntAssetJobTypeDefaultChecklist, EntAssetJobTypeDefault, EntAssetJobType, EntAssetJobTypeDefaultChecklistCopy, EntAssetChecklistTemplate, EntAssetJobTypeDefaultDescription, EntAssetJobTypeLookup, EntAssetJobTypeDefaultToolCopy, EntAssetJobTypePreviewPart, EntAssetJobTypeDefaultTool, EntAssetJobTypeDefaultForecastCopy, EntAssetChecklistTemplateLookup, EntAssetJobGroup, EntAssetChecklistVariable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bf7c53a6150a2beeca5c6e9b5ab4ea98584158d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427870"
---
# <a name="maintenance-job-type-categories-and-maintenance-job-types-maintenance-job-type-variants-maintenance-job-trades-and-maintenance-checklists"></a>Catégories de type de tâche de maintenance et types de tâches de maintenance, variantes de type de tâche de maintenance, opérations de tâches de maintenance et listes de contrôle de maintenance

[!include [banner](../../includes/banner.md)]

 

Un type d'actif est associé à chaque actif. Les types d'actif définissent les types de tâches de maintenance (et par conséquent, les tâches de maintenance) qui peuvent être effectués sur les actifs. Lorsque vous créez un ordre de travail, vous devez sélectionner un type de tâche de maintenance. Vous pouvez sélectionner uniquement les types de tâches de maintenance associés au paramétrage du type d'actif utilisé pour l'actif.

Pour obtenir une vue d'ensemble graphique des actifs et des types de tâches de maintenance, et leur connexion aux ordres de travail, voir [Postes techniques et actifs](../overview/functional-locations-and-objects.md).

Des variantes de type de tâche de maintenance peuvent être paramétrées pour un type de tâche de maintenance. Des variantes de type de tâche de maintenance définissent les variations d'un type de tâche, telles que les tailles (petite, moyenne ou grande), des périodes (hebdomadaire, bihebdomadaire, mensuelle ou trimestrielle), et des configurations (exigence faible, flexible, ou performances élevée).

Les opérations de tâches de maintenance fournissent des informations sur les opérations professionnelles, telles que les opérations mécaniques, électriques et hydrauliques. Des qualifications requises peuvent être paramétrées sur une opération de tâche de maintenance. Toutes les opérations de tâches de maintenance peuvent être utilisées pour tous les types de tâches de maintenance. La sélection d'une variante du type de tâche de maintenance et/ou d'une opération de tâche de maintenance est facultative.

Pour chaque type de tâche de maintenance, des variations du paramétrage du type de tâche de maintenance peuvent être créées. Par exemple, pour un type de tâche de maintenance nommé **Service**, vous pouvez créer les variations suivantes : **Camions 30 000 kilomètres**, **Voitures 30 000 kilomètres**, et **Fourgons 30 000 kilomètres**.

Les catégories de types de tâche de maintenance permettent de collecter un groupe de types de tâches de maintenance pour obtenir une vue d'ensemble. Parmi les catégories de types de tâches de maintenance on trouve **Étalonnage**, **Inspection**, **Révision**, et **Instrumentation**.

Les modèles de liste de contrôle de maintenance et les variables de la liste de contrôle de maintenance sont utilisés pour paramétrer des listes de contrôle de maintenance. Les listes de contrôle de maintenance sont paramétrées sur les types de tâches de maintenance et utilisées sur les ordres de travail.

Vous devez commencer par paramétrer les catégories de type de tâche de maintenance, les variantes de type de tâche de maintenance et les opérations de tâches de maintenance. Vous pouvez ensuite créer des types de tâches de maintenance. Enfin, dans la page **Type de tâche de maintenance par défaut**, vous devez créer toutes les variations de types de tâche de maintenance qui sont nécessaires pour votre équipement. Sur cette page, vous pouvez également paramétrer des prévisions, des listes de contrôle de maintenance et des outils pour une combinaison de types de tâches de maintenance.

> [!NOTE]
> Un type de tâche de maintenance ne peut être lié qu'à une seule catégorie de type de tâche de maintenance.

## <a name="create-a-maintenance-job-type-category"></a>Créer une catégorie de type de tâche de maintenance

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Tâches** \> **Catégories de type de tâche de maintenance**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Catégorie de type de tâche de maintenance**, entrez un ID pour la catégorie de type de tâche de maintenance.
4. Dans le champ **Nom**, entrez un nom.

    Après avoir lié les catégories de types de tâches de maintenance aux types de tâches de maintenance, le champ **Types de tâche** affiche le nombre de types de tâches de maintenance liées à cette catégorie de type de tâche de maintenance.

![Page Catégories de type de tâche de maintenance](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>Créer une variante du type de tâche de maintenance

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Tâches** \> **Variantes de type de tâche de maintenance**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Variante du type de tâche de maintenance**, entrez un ID pour la variante de type de tâche de maintenance.
4. Entrez une description dans le champ **Description**.
5. Dans le raccourci **Types de tâches de maintenance**, sélectionnez **Ajouter** pour ajouter un type de tâche de maintenance.
6. Sélectionnez le type de tâche de maintenance dans le champ **Type de tâche de maintenance**.
7. Répétez les étapes 5 à 6 pour ajouter plus de types de tâches de maintenance à la variante de type de tâche de maintenance.

    Dans le raccourci **Détails**, le champ **Types de tâches** indique le nombre de types de tâches de maintenance ajoutés à cette variante de type de tâche de maintenance.

![Page Variantes de type de tâche de maintenance](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>Créer une opération de tâche de maintenance

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Tâches** \> **Opération de tâche de maintenance**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Transaction**, entrez un ID pour l'opération de tâche de maintenance.
4. Entrez une description dans le champ **Description**.
5. Dans le raccourci **Compétences**, sélectionnez **Ajouter** pour ajouter une nouvelle compétence qui doit être liée à l'opération de tâche de maintenance.
6. Sélectionnez la compétence dans le champ **Compétence**.
7. Sélectionnez le niveau de compétence dans le champ **Niveau**.
8. Répétez les étapes 5 à 7 pour ajouter d'autres compétences à l'opération de tâche de maintenance.

    Dans le raccourci **Détails**, le champ **Compétences** indique le nombre de compétences ajoutées à cette opération de tâche de maintenance.

9. Dans le raccourci **Certificats**, sélectionnez **Ajouter** pour ajouter un certificat à l'opération de tâche de maintenance.
10. Sélectionnez le certificat dans le champ **Type de certificat**.
11. Répétez les étapes 9 à 10 pour ajouter d'autres certificats à l'opération de tâche de maintenance.

    Dans le raccourci **Détails**, le champ **Certificats** indique le nombre de certificats ajoutés à cette opération de tâche de maintenance.

![Page Opération de tâche de maintenance](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>Créer une variable de liste de contrôle de maintenance

Lorsque vous créez des lignes de liste de contrôle de maintenance dans le type de tâche de maintenance par défaut, vous devez sélectionner un type de liste de contrôle de maintenance. **Variable** est un type de liste de contrôle de maintenance. Il permet de définir un résultat possible dans une plage sur une ligne de liste de contrôle de maintenance liée à une ligne d'ordre de travail. Une variable permet de créer un ensemble de résultats prédéfinis sans devoir effectuer une mesure précise.

**Exemple 1 :** Vous pouvez calculer le niveau d'huile en définissant trois valeurs : **Niveau trop haut**, **Niveau trop bas** et **Niveau correct**. Pour chaque valeur, vous devez définir si le résultat de la valeur est **Réussite**, **Échec** ou **Aucun**.

**Exemple 2 :** Vous procédez à une inspection visuelle d'une pièce de l'équipement pour en évaluer l'usure.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Listes de contrôle de maintenance** \> **Variables de la liste de contrôle de maintenance**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Variable**, entrez un ID pour la variable de liste de contrôle de maintenance.
4. Dans le champ **Nom**, entrez un nom.
5. Dans le raccourci **Général**, sélectionnez **Ajouter** pour ajouter une ligne à la variable.

    Un numéro de ligne séquentiel est automatiquement entrée dans le champ **Numéro de ligne** . Après avoir ajouté toutes les lignes, vous pouvez modifier les numéros de ligne comme vous le souhaitez. Lorsque vous sélectionnez une ligne et que vous appuyez sur la touche **Flèche bas**, le numéro suivant dans la séquence est automatiquement entré sur la ligne suivante.

6. Dans le champ **Valeur**, entrez une description de la valeur.
7. Dans le champ **Résultat**, sélectionnez un résultat pour la ligne.

![Créer Variables de liste de contrôle de maintenance](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>Créer un modèle de liste de contrôle de maintenance

Les modèles de liste de contrôle de maintenance peuvent être utilisés comme ensemble courant de tâches qu'un agent doit effectuer pour exécuter un ordre de travail correctement. Les modèles sont référencés à partir des lignes de liste de contrôle de maintenance sur le type de tâche de maintenance par défaut. Les modèles peuvent être référencés entre plusieurs lignes de valeur par défaut du type de tâche de maintenance. Par conséquent, vous pouvez facilement réutiliser un ensemble de tâches courantes de liste de contrôle de maintenance. Parmi les exemples de modèles de liste de contrôle de maintenance on trouve des instructions de sécurité générales, et une liste d'articles et de conditions qui doivent être remplies sur une pompe spécifique ou des modèles similaires d'un convoyeur.

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Listes de contrôle de maintenance** \> **Modèles de liste de contrôle de maintenance**.
2. Sélectionnez **Nouveau**.

    Un ID de modèle est automatiquement entré dans le champ **Modèle de liste de contrôle de maintenance**.

3. Dans le champ **Nom**, entrez un nom pour le modèle de liste de contrôle de maintenance.
4. Dans le raccourci **Lignes de liste de contrôle de maintenance**, sélectionnez **Ajouter** pour ajouter une ligne de modèle.

    Un numéro de ligne séquentiel est automatiquement entrée dans le champ **Numéro de ligne** . Après avoir ajouté toutes les lignes, vous pouvez modifier les numéros de ligne comme vous le souhaitez. Lorsque vous sélectionnez une ligne et que vous appuyez sur la touche **Flèche bas**, le numéro suivant dans la séquence est automatiquement entré sur la ligne suivante.

5. Dans le champ **Type**, sélectionnez un type pour la ligne de la liste de contrôle de maintenance. Pour chaque type de liste de contrôle de maintenance, les champs associés sont affichés sous le raccourci **Détails de ligne**. Les valeurs disponibles sont les suivantes :

    - **Texte** : La ligne contient le texte décrivant ce qu'il faut faire Utilisez ce type de liste de contrôle de maintenance si vous souhaitez qu'un employé contrôle ou vérifie quelque chose, sans attendre un résultat spécifique (mesurable). Après avoir sélectionné ce type, entrez un nom ou un en-tête dans le champ **Nom**. Dans le champ **Instructions**, entrez une description de ce qui doit être effectué. Si l'étape est obligatoire pour la liste de contrôle de maintenance, définissez l'option **Obligatoire** sur **Oui**.
    - **En-tête** : La ligne est utilisée comme en-tête pour regrouper les lignes de la liste de contrôle de maintenance affichées en-dessous. Ce type est utile si vous avez plusieurs lignes de liste de contrôle de maintenance qui peuvent être divisées en zones spécifiques. Les en-têtes fournissent une vue d'ensemble à l'agent qui parcourt la liste de contrôle de maintenance qui contient plusieurs lignes. Après avoir sélectionné ce type, entrez un nom descriptif dans le champ **Nom**.
    - **Modèle** : Cette ligne permet de faire référence à un modèle existant. Après avoir sélectionné ce type, entrez un nom pour le modèle dans le champ **Nom**. Sélectionnez le modèle dans le champ **Modèle**.
    - **Variable** : Cette ligne est utilisée pour définir un résultat possible dans une plage. Pour plus d'informations sur le paramétrage des variables de liste de contrôle de maintenance, reportez-vous à la section [Créer une variable de liste de contrôle de maintenance](#create-a-maintenance-checklist-variable). Après avoir sélectionné ce type, entrez un nom descriptif pour la variable dans le champ **Nom**. Sélectionnez la variable dans le champ **Variable**. Dans le champ **Instructions**, entrez une description de ce qui doit être effectué. Si l'étape est obligatoire pour la liste de contrôle de maintenance, définissez l'option **Obligatoire** sur **Oui**.
    - **Mesure** : Cette ligne permet d'enregistrer une mesure spécifique. Vous pouvez paramétrer la mesure qui doit être associée à un compteur prédéfini. Après avoir sélectionné ce type, entrez un nom pour le modèle dans le champ **Nom**. Si cette étape est obligatoire pour la liste de contrôle de maintenance, définissez l'option **Obligatoire** sur **Oui**. Si vous souhaitez utiliser la ligne de mesure comme enregistrement de compteur, sélectionnez le compteur dans le champ **Compteur**. Le champ **Unité** associé est alors mis à jour automatiquement. Si vous avez sélectionné un compteur, sélectionnez la méthode de mise à jour dans le champ **Valeur**. Entrez la plage de valeurs autorisées dans les champs **Valeur minimale** et **Valeur maximale**. Dans le champ **Instructions**, entrez une description de ce qui doit être effectué.

        > [!NOTE]
        > Toutes les lignes de type **Mesure** qui n'ont pas de compteur paramétré sont traitées comme un enregistrement de mesure indépendant car il n'existe aucun suivi automatique dans le module Gestion des actifs. De même, si le type de compteur sélectionné n'est pas présent sur l'actif lié à l'ordre de travail, la tâche de la liste de contrôle de maintenance est considérée comme une mesure indépendante. La valeur du compteur peut être modifiée plusieurs fois. Elle n'est pas validée tant que l'[état du cycle de vie de l'ordre de travail](work-order-lifecycle-states.md) n'est pas remplacé par un état dans lequel l'option **Traiter la liste de contrôle de maintenance** est définie sur **Activé**.

    Dans le raccourci **Détails**, le champ **Chèques** affiche le nombre total de lignes de la liste de contrôle dans le modèle. Ce dernier inclut les lignes imbriquées dans n'importe quel modèle existant que vous avez indiqué dans le modèle.

![Créer Modèles de liste de contrôle de maintenance](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>Créer un type de tâche de maintenance

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Tâches** \> **Types de tâche de maintenance**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Type de tâche de maintenance**, entrez un ID pour le type de tâche de maintenance.
4. Dans le champ **Nom**, entrez un nom.

    Le raccourci **Détails** affiche une vue d'ensemble du nombre de variantes de type des tâches de maintenance, des qualifications, des certificats, des tâches réussies, et des types d'actifs qui ont été créés sur ce type de tâche de maintenance. Le champ **Lignes de paramétrage** affiche le nombre de lignes de valeur par défaut du type de tâche de maintenance définies sous ce type de tâche de maintenance. Le champ **Actifs** affiche le nombre d'actifs actifs qui utilisent actuellement ce type de tâche de maintenance.

5. Sous l'onglet **Général**, dans le champ **Catégorie de type de tâche de maintenance**, entrez une catégorie de type de tâche de maintenance.
6. Définissez l'option **Activités des temps d'arrêt pour maintenance** sur **Oui** si le type de tâche de maintenance nécessite un arrêt de la maintenance de l'équipement avant que la tâche soit exécutée.
7. Dans le raccourci **Description**, entrez une description du type de tâche de maintenance.
8. Dans le raccourci **Variantes de type de tâche de maintenance**, vous pouvez ajouter des variantes au type de tâche de maintenance.
9. Dans les raccourcis **Compétences requises** et **Certificats requis**, vous pouvez ajouter des exigences en matière de compétences et de certificat au type de tâche de maintenance.
10. Si un type de tâche de maintenance spécifique doit être effectué après, ajoutez-le dans le raccourci **Tâches suivantes**. Vous pouvez également paramétrer une variante de type de tâche de maintenance et une opération de tâche de maintenance associées au type de tâche de maintenance. Si la tâche suivante doit commencer un nombre spécifique de jours avant ou après que la tâche utilisant ce type de tâche de maintenance a commencé, entrez le nombre de jours dans le champ **Retard en jours**. Les nombres positifs représentent les jours après le début de la tâche associée, et les nombres négatifs représentent les jours avant la date de début prévue de la tâche associée. Par exemple, si vous entrez **5**, la tâche suivante commencera cinq jours après le début de la tâche associée au type de tâche de maintenance. Si vous entrez **-3**, la tâche suivante commencera trois jours avant le début prévu de la tâche associée au type de tâche de maintenance.

    > [!NOTE]
    > Si vous ajoutez plusieurs lignes de type de tâche de maintenance, l'ordre des lignes indique l'ordre dans lequel elles doivent être effectuées. La séquence commence en haut de la liste.

11. Dans le raccourci **Types d'actif**, vous pouvez ajouter des types d'actif au type de tâche de maintenance.

![Page Types de tâches de maintenance](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>Créer des lignes de valeur par défaut du type de tâche maintenance et des prévisions, des listes de contrôle de maintenance, des outils, une description, et des pièces jointes associés

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Tâches** \> **Type de tâche de maintenance par défaut**.

    - ou -

    Sélectionnez **Gestion d'immobilisation** \> **Paramétrage** \> **Tâches** \> **Types de tâches de maintenance**, sélectionnez le type de tâche de maintenance, puis sélectionnez **Type de tâche de maintenance par défaut**.

2. Sélectionnez **Nouveau**.
3. Dans les champs **Poste technique**, **Type d'actif**, **Fabricant**, **Modèle**, et **Actif**, sélectionnez les valeurs appropriées, selon la spécificité du type de tâche de maintenance par défaut.
4. Dans le champ **Type de tâche de maintenance**, sélectionnez un type de tâche de maintenance s'il n'a pas été sélectionné automatiquement.
5. Dans les champs **Variante du type de tâche de maintenance** et **Transaction**, sélectionnez une variante du type de tâche de maintenance et une opération de tâche de maintenance comme vous le souhaitez.
6. Sélectionnez **Prévision**.
7. Dans la page **Prévision des valeurs par défaut du type de tâche de maintenance**, vous pouvez effectuer des prévisions sur les heures, les articles, et les dépenses. Sous les onglets concernés, sélectionnez **Ajouter**, puis effectuez des sélections pour créer les prévisions requises pour le type de tâche de maintenance.
8. Dans l'onglet **Prévision d'article**, vous pouvez sélectionner les dimensions de stock à afficher sur la ligne de l'article. Sélectionnez **Stock** \> **Dimensions**, sélectionnez les dimensions à afficher, définissez l'option **Enregistrer le paramétrage** sur **Oui**, puis sélectionnez **OK**.
9. Sur l'onglet **Prévision d'article**, sélectionnez **Cas d'emploi d'article** pour obtenir une vue d'ensemble de l'emplacement d'utilisation de l'article sur la ligne sélectionnée dans le module Gestion des actifs, en ce qui concerne les actifs, le type de tâche de maintenance par défaut, les pièces détachées et les ordres de travail. 

    Le raccourci **Totaux de prévisions de maintenance** donne une vue d'ensemble des totaux de prévision. Cette vue d'ensemble inclut le nombre total d'heures et les lignes de prévision qui ont été créées.

    > [!NOTE]
    > Pour copier le paramétrage de la prévision à partir d'un autre type de tâche de maintenance, sélectionnez **Copier la prévision**, puis sélectionnez le type de tâche de maintenance à partir duquel copier le paramétrage.

11. Sélectionnez **Enregistrer** pour enregistrer les modifications.
12. Fermez la page **Prévision des valeurs par défaut du type de tâche de maintenance** pour revenir à la page **Type de tâche de maintenance par défaut**.
13. Sélectionnez **Liste de contrôle de maintenance**.
14. Dans la page **Liste de contrôle du type de tâche de maintenance par défaut**, vous pouvez ajouter les lignes de liste de contrôle de maintenance par défaut sélectionnées au type de tâche de maintenance par défaut. Dans le raccourci **Lignes de contrôle de maintenance**, sélectionnez **Nouveau** pour ajouter une ligne à la liste de contrôle de maintenance.

    Les numéros de ligne sont automatiquement insérés dans le champ **Numéro de ligne** pour indiquer la séquence des lignes de la liste de contrôle de maintenance. Vous pouvez modifier les numéros de ligne comme vous le souhaitez. Après avoir créé la première ligne de la liste de contrôle de maintenance, sélectionnez la ligne, puis appuyez sur la touche **Flèche bas** pour ajouter une ligne en-dessous. Sinon, vous pouvez sélectionner une ligne de liste de contrôle de maintenance, puis sélectionnez **Nouveau**. Dans ce cas, une nouvelle ligne est ajoutée au-dessus de la ligne de la liste de contrôle de maintenance sélectionnée.

15. Dans le champ **Type**, sélectionnez le type de ligne, puis ajoutez les informations concernant le type de liste de contrôle de maintenance. Pour obtenir la description des types disponibles et des champs associés, voir la section [Créer un modèle de liste de contrôle de maintenance](#create-a-maintenance-checklist-template).

    > [!NOTE]
    > Pour copier le paramétrage de la liste de contrôle de maintenance à partir d'un autre type de tâche de maintenance, sélectionnez **Copier la liste de contrôle de maintenance**, puis sélectionnez le type de tâche de maintenance à partir duquel copier le paramétrage.
    >
    > Vous pouvez facilement créer un modèle à partir d'une liste de contrôle de maintenance existante. Vous pouvez ensuite réutiliser le modèle entre plusieurs listes de contrôle de maintenance. Le nouveau modèle est une copie exacte de la liste de contrôle de maintenance active. Sélectionnez **Créer un modèle**, puis entrez un nom pour le modèle. Pour remplacer la liste de contrôle de maintenance existante par une ligne unique qui référence le nouveau modèle, définissez l'option **Remplacer** sur **Oui**. Vous pouvez afficher le contenu du modèle dans la page de détails **Modèles de liste de contrôle de maintenance**.

16. Sélectionnez **Enregistrer** pour enregistrer les modifications.
17. Revenez à la page **Type de tâche de maintenance par défaut**.
18. Sélectionnez **Outils**.
19. Dans la page **Outils du type de tâche de maintenance par défaut**, vous pouvez ajouter des outils (ressources) à utiliser pour le type de tâche de maintenance. Sélectionnez **Nouveau**, puis sélectionnez l'outil dans le champ **Ressource**.

    > [!NOTE]
    > Pour copier le paramétrage de l'outil à partir d'un autre type de tâche de maintenance, sélectionnez **Copier les outils**, puis sélectionnez le type de tâche de maintenance à partir duquel copier le paramétrage.

20. Sélectionnez **Enregistrer** pour enregistrer les modifications.
21. Revenez à la page **Type de tâche de maintenance par défaut**.
22. Sélectionnez **Description du travail**.
23. Dans la page **Description du travail**, sélectionnez **Modifier**, puis ajoutez une description de la valeur par défaut du type de tâche de maintenance sélectionné, comme vous le souhaitez.
24. Sélectionnez **Enregistrer** pour enregistrer la description.

    Si vous ajoutez une description du travail ici, elle remplace la description qui est paramétrée pour le type de tâches de maintenance sur la page **Types de tâche de maintenance**. Si vous n'ajoutez pas une description du travail ici, toute description paramétrée pour le type de tâche de maintenance est utilisée. Les descriptions sont automatiquement transférées vers les ordres de travail qui utilisent le type de tâche de maintenance ou la valeur par défaut du type de tâche de maintenance.

25. Revenez à la page **Type de tâche de maintenance par défaut**.
26. Pour paramétrer les pièces jointes sur la ligne par défaut d'un type de tâche de maintenance sélectionné, sélectionnez **Joindre des documents**. Les pièces jointes définies sur la ligne par défaut d'un type de tâche de maintenance sont automatiquement incluses dans les lignes de l'ordre de travail qui utilisent cette ligne par défaut.
27. Sélectionnez **Nouveau**, puis sélectionnez un type de document.
28. Téléchargez le document ou le fichier.
29. Définissez les champs de la page **Pièces jointes**. Le paramétrage de la pièce jointe utilise la fonctionnalité de paramétrage de document standard.
30. Sélectionnez **Enregistrer** pour enregistrer la pièce jointe.

    > [!NOTE]
    > Les pièces jointes dans une ligne de valeur par défaut du type de tâche de maintenance sont imprimées avec un état d'ordre de travail uniquement si les types de document des pièces jointes sont sélectionnés dans l'onglet **Types de documents** de la page **Paramètres de gestion des actifs** (**Gestion d'actifs** \> **Paramétrage** \> **Paramètres de gestion des actifs**). Parmi les exemples de pièces jointes on trouve des instructions qui expliquent comment traiter une tâche spécifique ou une liste prédéfinie de contrôle de maintenance (si vous n'utilisez pas la fonctionnalité de liste de contrôle de maintenance pour les lignes par défaut du type de tâche de maintenance).

    Dans la page **Type de tâche de maintenance par défaut**, chaque ligne indique le nombre d'heures prévues, ainsi que le nombre de lignes créées pour des articles, des dépenses, des listes de contrôle de maintenance, et des outils. Le champ **Actifs** affiche le nombre d'actifs actifs qui sont associés à la ligne par défaut d'un type de tâche de maintenance.

31. Pour copier une valeur par défaut du type de tâches de maintenance sur une autre valeur par défaut, sélectionnez la ligne de la valeur par défaut du type de tâche de maintenance pour copier un autre paramétrage, sélectionnez **Copier le paramétrage**, puis sélectionnez la valeur par défaut du type de tâche de maintenance à copier.
32. Pour afficher la liste des actifs, des plans de maintenance, ou des visites de maintenance qui utilisent actuellement une ligne de valeur par défaut du type de tâches de maintenance, sélectionnez la ligne, puis sélectionnez **Utilisé par**.

![Page Valeurs par défaut du type de tâche de maintenance](media/07-setup-for-work-orders.png)

Lorsque le système sélectionne la valeur par défaut du type de tâche de maintenance disponible qui doit être utilisée dans une ligne d'ordre de travail, la sélection est basée sur l'actif et le paramétrage du type d'actif. Le module Gestion des actifs parcourt tous les enregistrements de valeur par défaut du type de tâche de maintenance associés au type de tâches de maintenance associé au type d'actif à la recherche d'une correspondance possible. Il vérifie toujours la combinaison la plus spécifique en premier. En d'autres termes, le module Gestion des actifs vérifie tout d'abord une correspondance possible pour le champ **Transaction** afin de trouver la combinaison la plus spécifique. Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Variante du type de tâche de maintenance**. Si aucune correspondance n'est détectée, il cherche une correspondance pour le champ **Type de tâche de maintenance**, etc. (sur **Transaction**, puis sur **Variante de type de tâche de maintenance**, puis sur **Type de tâche de maintenance**, puis sur **Actif**, puis sur **Modèle**, puis sur **Fabricant**, puis sur **Type d'actif**). Si aucune correspondance n'est détectée, l'enregistrement par défaut où seul le type de tâche de maintenance est sélectionné est utilisé.

Un ID d'activité de projet est automatiquement associé à chaque ligne par défaut d'un type de tâche de maintenance que vous créez. L'activité de projet est créée dans le projet de prévision sélectionné dans le champ **Projet de prévisions en matière de maintenance** sur l'onglet **Actifs** de la page **Paramètres de gestion des actifs**. L'objectif de l'activité de projet est de gérer les prévisions d'heures, d'articles, et de dépenses en relation avec les ordres de travail. Les prévisions de type de tâche de maintenance sont automatiquement transférées vers la ligne de l'ordre de travail, et sont copiées du projet de prévision au projet d'ordre de travail qui est créée pour la ligne d'ordre de travail. L'objectif de l'activité de projet est de gérer les prévisions en relation avec les ordres de travail.

Vous pouvez paramétrer un traitement par lots pour mettre à jour les références de valeur par défaut du type de tâche de maintenance à intervalles réguliers, ou vous pouvez l'exécuter manuellement. Pour créer un traitement par lots ou effectuer une mise à jour manuelle, sélectionnez **Gestion d'actifs** \> **Périodique** \> **Maintenance préventive** \> **Mettre à jour les références de valeur par défaut du type de tâche de maintenance**.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>Vue d'ensemble des types de tâches de maintenance associés aux actifs

Après avoir créé les combinaisons par défaut de type de tâche de maintenance requises, vous pouvez utiliser la page **Tous les actifs** pour obtenir une vue d'ensemble de la valeur par défaut du type de tâche de maintenance associé à un actif spécifique. Cette vue d'ensemble indique toutes les combinaisons de valeurs par défaut du type de tâche de maintenance qui peuvent être utilisées sur le type d'actif sélectionné pour l'actif. Ces combinaisons incluent des combinaisons ayant différentes variantes de type de tâche de maintenance et d'opérations de tâches de maintenance.

1. Sélectionnez **Gestion des actifs** \> **Commun** \> **Actifs** \> **Tous les Actifs** ou **Actifs actifs**.
2. Dans la liste, sélectionnez l'actif pour afficher une vue d'ensemble des combinaisons de types de tâches de maintenance.
3. Dans le volet Actions, sous l'onglet **Général**, dans le groupe **Informations associées**, cliquez sur **Types de tâches de maintenance**.

    Le volet gauche de la page **Types de tâches de maintenance de l'actif** contient la liste de toutes les combinaisons de types de tâches de maintenance associées à l'actif sélectionné.

4. Sélectionnez une combinaison de types de tâches de maintenance pour voir le paramétrage associé pour les listes de contrôle de maintenance, les prévisions et les outils. La section **Détails** du raccourci **Type de tâche de maintenance par défaut** indique le numéro des listes de contrôle de maintenance associées, les heures prévues, les articles, etc., qui sont associés à la combinaison de type de tâche de maintenance sélectionnée.
5. Pour afficher les détails du type de tâche de maintenance sélectionné, sélectionnez **Types de tâches de maintenance**.

![Page Types de tâches de maintenance de l'actif](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>Mise à jour automatique des prévisions de type de tâche de maintenance

Dans le module Gestion des actifs, vous pouvez automatiquement mettre à jour les modifications apportées aux prévisions de type de tâche de maintenance concernant les coûts horaires, les coûts d'article et les dépenses, qui ont été mises à jour dans d'autres modules. Vous pouvez ainsi aider à garantir que les prévisions de type de tâche de maintenance utilisent toujours les derniers prix de revient.

1. Sélectionnez **Gestion des actifs** \> **Périodique** \> **Prévision** \> **Mettre à jour les prévisions de type de tâche de maintenance**.
2. Dans la boîte de dialogue **Mettre à jour les prévisions de type de tâche de maintenance**, sous le raccourci **Enregistrements à inclure**, vous pouvez ajouter des sélections pour les types de tâches de maintenance spécifiques comme vous le souhaitez. Sélectionnez **Filtre**, puis sélectionnez **Sélection** pour effectuer les sélections.
3. Sous le raccourci **Exécuter à l'arrière-plan**, vous pouvez configurer la mise à jour automatique comme traitement par lots comme vous le souhaitez.
4. Cliquez sur **OK** pour démarrer la mise à jour des prévisions.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]