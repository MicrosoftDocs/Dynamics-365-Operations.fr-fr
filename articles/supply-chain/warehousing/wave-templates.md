---
title: Modèles de vague
description: Cette rubrique décrit la procédure de paramétrage des critères qui déterminent si les vagues sont traitées manuellement ou automatiquement, et le travail généré pour un entrepôt lorsqu’une vague est traitée.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 95e315c1bf1e363db413abae985d510848059e62
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020057"
---
# <a name="wave-templates"></a>Modèles de vague

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la procédure de paramétrage des critères qui déterminent si les vagues sont traitées manuellement ou automatiquement, et le travail généré pour un entrepôt lorsqu’une vague est traitée. Vous spécifiez les critères en paramétrant des modèles de vague et des requêtes qui correspondent à une vague avec des lignes libérées dans des commandes client, des ordres de fabrication et des kanbans.

## <a name="settings-for-wave-templates"></a>Paramètres des modèles de vague

Lorsque vous paramétrez un modèle de vague, vous spécifiez les éléments suivants :

- Le **Site** et l’**entrepôt** pour lequel le modèle créera le travail.
- L’ordre d’évaluation des modèles. L’ordre dans lequel les modèles sont mis en correspondance avec les lignes libérées des commandes client, ordres de fabrication et kanbans. Lorsqu’une ligne est libérée, le système applique le premier modèle de vague pour lequel la ligne répond aux critères. Plus les critères sont larges, plus il est probable qu’une ligne réponde aux critères. Vous devez donc placer les modèles avec les critères les plus spécifiques en haut de la liste. Utilisez les boutons **Déplacer vers le haut** et **Déplacer vers le bas** du volet Actions pour organiser les modèles dans la liste.
- Les actions entreprises par chaque modèle. Les **méthodes** de vague qui entreprennent les actions créées par le modèle, tel que la création ou la répartition du travail pour chaque type de modèle de vague.
- Les attributs de vague (filtres) qui doivent s’appliquer pour le modèle de vague à utiliser.

> [!NOTE]
> Si nécessaire, un développeur peut créer des méthodes supplémentaires. Vous pouvez consulter la liste complète des méthodes sur la page **Méthodes de traitement de vague**.

Certains paramètres représentent des décisions stratégiques pour le traitement des vagues, comme suit :

- Si le modèle est utilisé pour expédier des articles pour des commandes client et des ordres de transfert, ou pour déplacer des articles vers la production pour des ordres de fabrication ou des kanbans.
- Si une vague est traitée manuellement ou automatiquement, comme suit :

  - **Traitement manuel** : la ligne est ajoutée à une vague et le stock est réservé, cependant, vous devez sélectionner **Traiter** dans la page de liste **Toutes les vagues** pour créer le travail de prélèvement pour la commande.
  - **Traitement automatique** : vous pouvez automatiser entièrement ou partiellement le traitement des vagues. Si vous automatisez entièrement le traitement des vagues, une vague comprenant la ligne de la commande client, l’ordre de production ou le kanban est créée lors de la création de la commande client, de l’ordre de fabrication ou du kanban. Les articles sont déduits du stock disponible et le travail de prélèvement est créé. Si vous automatisez partiellement le traitement des vagues, vous pouvez spécifier les valeurs qui déclencheront le traitement des vagues. Par exemple, vous pouvez spécifier un poids maximal pour les expéditions, qui déclenchera le traitement de la vague lorsque le poids total des lignes de la vague atteint la valeur indiquée.

- Si vous affectez des expéditions à une vague en cours. Par exemple, si vous promettez aux clients qu’une commande passée avant 12 h 00 sera expédiée dans les 24 heures, vous pouvez paramétrer le modèle de vague pour qu’il affecte automatiquement des lignes de commande à une vague en cours jusqu’à 12 h 00. À cette heure-là, la vague est traitée automatiquement.

Lorsqu’une vague est traitée, le travail de prélèvement créé est basé sur le modèle de travail et les instructions d’emplacement spécifiés pour l’entrepôt. Le modèle de travail spécifie comment le travail de prélèvement est créé, et les instructions d’emplacement spécifie les emplacements de prélèvement et de placement.

## <a name="create-a-wave-template"></a>Créer un modèle de vague

Pour paramétrer un modèle de vague, procédez comme suit :

1. Allez à **Gestion des entrepôts** \> **Paramétrage** \> **Vagues** \> **Modèles de vague**.
1. Sélectionnez **Nouveau** pour créer un modèle de vague.
1. Dans le champ **Type de modèle de vague**, sélectionnez l’une des options suivantes :

    - *Expédition* : utilisez le modèle de vague pour expédier les articles des commandes client et des ordres de transfert.
    - *Ordres de fabrication* : utilisez le modèle de vague pour déplacer des articles pour des ordres de fabrication.
    - *Kanban* : utilisez le modèle de vague pour déplacer des articles pour des commandes kanban.

1. Dans les champs **Nom du modèle de vague** et **Description du modèle de vague**, entrez un nom et une description pour le modèle de vague.

    > [!NOTE]
    > Si plusieurs modèles sont créés pour un entrepôt, le numéro dans le champ **Séquence de modèles de vague** indique la position du modèle dans l’ordre dans lequel les modèles sont appliqués lorsque les critères du modèle sont remplis. Vous pouvez sélectionner **Déplacer vers le haut** ou **Déplacer vers le bas** pour réorganiser l’ordre des modèles.

1. Dans les champs **Site** et **Entrepôt**, sélectionnez le site et l’entrepôt pour lesquels le modèle de vague créera des vagues et un travail de prélèvement.
1. Si vous souhaitez automatiser le traitement des vagues, définissez les paramètres suivants selon vos besoins :

    - **Automatiser la création de vague** : définissez cette option sur *Oui* pour créer automatiquement une vague lorsqu’une commande client, un ordre de fabrication, ou un kanban est libéré dans l’entrepôt.
    - **Attribuer aux vagues ouvertes** : définissez cette option sur *Oui* pour attribuer automatiquement les lignes à une vague ouverte lorsque les lignes sont libérées. Les lignes sont affectées aux vagues en fonction du filtre de requête du modèle de vague.
    - **Traiter la vague à la sortie dans l’entrepôt** : définissez cette option sur *Oui* pour traiter automatiquement la vague et créer un travail lorsqu’une ligne est libérée dans l’entrepôt.
    - **Traiter la vague automatiquement au seuil** : définissez cette option sur *Oui* pour traiter automatiquement la vague lorsque ses valeurs atteignent les seuils pour le poids, l’expédition, et les lignes spécifiées dans le groupe de champs **Seuils de vague**. Ce paramètre n’est actif que si *Expédition* est sélectionné dans le champ **Type de modèle de vague**.
    - **Sortie automatique de vagues** : définissez cette option sur *Oui* pour libérer automatiquement la vague. Le travail de prélèvement est créé et rendu disponible sur les appareils mobiles.
    - **Automatiser la libération du travail de réapprovisionnement** : définissez cette option sur *Oui* pour créer un travail de réapprovisionnement basé sur la demande et le libérer automatiquement. Vous devez ajouter la méthode de vague de réapprovisionnement au modèle de vague, puis créer un modèle de réapprovisionnement utilisant le type *Demande de vague*. Paramétrez un modèle de réapprovisionnement sur la page **Modèles de réapprovisionnement**. Cela nécessite que vous ajoutiez la méthode réapprovisionnement au modèle de vague.
    - **Poursuivre le traitement de vague lorsque la création du travail échoue** : lorsque cette option est définie sur *Oui*, le système utilisera un emplacement vide s’il ne peut pas réserver le stock à l’emplacement proposé par la directive d’emplacement (par exemple, parce que le stock n’est plus disponible). Lorsqu’elle est définie sur *Non*, la vague échoue si le système ne peut pas réserver le stock.

1. Définissez le groupe de champs **Seuils de vague** selon les besoins :
    - **Seuil de poids de vague** : entrez le poids maximum qu’une vague peut contenir.
    - **Seuil d’expédition** : entrez le nombre maximum d’expéditions pouvant être incluses dans une vague.
    - **Seuil de ligne** : entrez le nombre maximum de lignes pouvant être incluses dans une vague.

1. Dans le groupe de champs **Valeurs par défaut**, sélectionnez les attributs de vague à utiliser comme critères supplémentaires pour le modèle de vague. Les attributs de vague sont utiles pour affecter des critères supplémentaires, tels qu’un nom de client spécifique, à un modèle de vague. Vous créez ces attributs sur la page **Attributs de vague**. 

1. Définissez la **Stratégie de notification de vague** sur la stratégie que vous souhaitez utiliser pour générer des notifications liées aux vagues qui utilisent ce modèle. Pour un exemple de stratégie de notification de vague, voir [Notifications d’exécution de vague](wave-execution-notifications.md).

1. Dans le raccourci **Méthodes**, le volet **Méthodes sélectionnées** répertorie les méthodes pour le modèle de vague sélectionné. Les méthodes de vague qui entreprennent les actions créées par le modèle, tel que la création ou la répartition du travail. Ces actions sont également appelées étapes de vague. Les méthodes de vague sont prédéfinies pour chaque type de modèle de vague. Vous ne pouvez pas supprimer les méthodes de vague prédéfinies ; toutefois, vous pouvez réorganiser l’ordre des méthodes et ajouter des méthodes supplémentaires. Par exemple, si vous créez un modèle de vague pour l’expédition, vous pouvez ajouter des méthodes pour le réapprovisionnement et la mise en conteneurs. La mise en conteneur de vague peut être ajoutée à une séquence de méthodes de vague pour définir la mise en conteneur des lignes traitées dans un modèle de vague. Pour ajouter une méthode supplémentaire, procédez comme suit :

    - Sélectionnez une méthode dans le volet **Méthodes restantes**, puis sélectionnez la flèche **Gauche** pour l’ajouter au volet **Méthodes sélectionnées**.
    - Pour modifier l’ordre, sélectionnez une méthode, puis sélectionnez les flèches **Haut** ou **Bas**.

    > [!NOTE]
    > Lorsque vous ajoutez une méthode, elle est automatiquement répertoriée dans l’emplacement adapté dans la suite d’étapes.

1. Pour configurer la requête qui fera correspondre les lignes libérées avec une vague appropriée, sélectionnez **Modifier la requête** dans le volet Actions.
1. Pour vérifier que les paramètres du modèle de vague sont valides, sélectionnez **Valider le modèle**.
