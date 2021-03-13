---
title: Types de postes techniques
description: Cette rubrique décrit comment créer des types de postes techniques dans Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c64a0c07bf692385370e4bd2a99f51b211cd397
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018701"
---
# <a name="functional-location-types"></a>Types de postes techniques

[!include [banner](../../includes/banner.md)]

 

Cette rubrique décrit comment créer des types de postes techniques dans Gestion des actifs. Les types de postes techniques permettent de gérer les besoins des postes techniques, notamment la manière dont les actifs sont installées à un poste technique. Vous pouvez paramétrer les types d'actifs, les plans de maintenance, les attributs de poste technique et la configuration requise de l'attribut d'actif à utiliser à un poste technique utilisant le type de poste technique spécifique. Lorsque vous créez un poste technique, le type de poste technique est obligatoire.

>[!NOTE] 
>Pour utiliser des postes techniques, vous devez créer un poste technique par défaut à utiliser uniquement à des fins de création d'actifs. Pour ce poste technique par défaut, vous devez créer un type de poste technique par défaut qui est réellement simple et autorise l'installation de plusieurs actifs au poste technique par défaut. Voir [Créer des postes techniques](../functional-locations/create-functional-locations.md) pour plus d'informations sur la configuration de postes techniques.

## <a name="create-a-default-functional-location-type"></a>Créer un type de poste technique par défaut

Cette procédure explique comment créer un type de poste technique par défaut à utiliser pour un poste technique par défaut.

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Postes techniques** > **Types de postes techniques**.
2. Sélectionnez **Nouveau** pour créer un type de poste technique.
3. Insérez un ID de type de poste technique dans le champ **Type de poste technique**, par exemple « Par défaut », et un nom dans le champ **Nom**.
4. Sélectionnez un modèle de cycle de vie dans le champ **Modèle de cycle de vie de poste technique**.
5. Sélectionnez « Oui » sur le bouton de basculement **Plusieurs actifs** pour permettre l'installation de plusieurs actifs à un poste technique (le poste technique par défaut) à l'aide de ce type.

À présent, le type de poste technique par défaut à utiliser uniquement pour un poste technique par défaut est créé. Vous ne devez plus ajouter de configurations requises ou de restrictions à ce type de poste technique par défaut.


## <a name="create-functional-location-types"></a>Créer des types de postes techniques

1. Sélectionnez **Gestion des actifs** > **Paramétrage** > **Postes techniques** > **Types de postes techniques**.
2. Sélectionnez **Nouveau** pour créer un type de poste technique.
3. Insérez un ID de type de poste technique dans le champ **Type de poste technique** et un nom dans le champ **Nom**.
4. Sélectionnez un modèle de cycle de vie dans le champ **Modèle de cycle de vie de poste technique**. Pour plus d'informations sur les états du cycle de vie de poste technique et les modèles de cycle de vie, reportez-vous à [États du cycle de vie du poste technique](../setup-for-functional-locations/functional-location-stages.md) .
5. Sélectionnez « Oui » sur le bouton de basculement **Plusieurs actifs** s'il doit être possible d'installer plusieurs actifs à un poste technique à l'aide de ce type de poste technique. Si vous sélectionnez « Non », vous pouvez uniquement installer *un* actif au poste technique à l'aide de ce type de poste technique.
6. Sélectionnez « Oui » sur le bouton de basculement **Mettre à jour la dimension de l'actif** si vous souhaitez que les actifs installés à un poste technique de ce type utilisent automatiquement les dimensions financières liées au poste technique. Cela signifie que si vous modifiez les dimensions financières de l'écran [Créer des postes techniques](../functional-locations/create-functional-locations.md), et que le poste technique utilise un type de poste technique avec ce bouton de basculement défini sur « Oui », les dimensions financières sont automatiquement mises à jour sur tous les actifs installés à ce poste technique.
7. Le champ **Type d'actif** est utilisé si vous souhaitez créer automatiquement *un* actif pour le poste technique avec le même ID et le même nom que le poste technique vous créez. Par exemple, cela peut être utile si vous créez un poste technique statique, tel qu'un bâtiment ou une canalisation. Dans ce cas, sélectionnez le type d'actif à utiliser pour l'actif créé automatiquement. N'oubliez pas que si vous effectuez une sélection dans ce champ, le bouton de basculement **Plusieurs actifs** doit être défini sur « Non ».
8. Dans le raccourci **Types d'actifs**, sélectionnez les types d'actifs à associer au type de poste technique. Sélectionnez **Ajouter la ligne**, puis sélectionnez les types d'actifs. Si vous ajoutez des types d'actifs ici, seuls les actifs utilisant ces types d'actifs peuvent être installés à un poste technique utilisant ce type de poste technique. Si aucun type d'actif n'est sélectionné dans l'organisateur **Types d'actifs**, tous les types d'actifs peuvent être installés.
9. Dans l'organisateur **Plans de maintenance**, sélectionnez les plans de maintenance à configurer automatiquement sur de nouveaux postes techniques utilisant ce type de poste technique. Sélectionnez **Ajouter la ligne**, puis sélectionnez les plans de maintenance. Si vous ajoutez des plans de maintenance ici, seuls ces plans peuvent être utilisés à un poste technique utilisant ce type de poste technique.
10. Dans l'organisateur **Exigences d'attribut d'actif**, configurez les attributs d'actif à configurer automatiquement sur de nouveaux postes techniques utilisant ce type de poste technique. Sélectionnez **Ajouter la ligne**, puis sélectionnez l'attribut. Ces exigences d'attributs fonctionnent comme instructions. Elles ne sont pas validées selon le paramétrage d'attributs d'un actif (**Gestion des actifs** > **Commun** > **Actifs** > **Tous les actifs** > sélectionnez l'actif dans la page de liste > onglet **Général** > bouton **Attributs** ). Les exigence d'attribut s'affichent lorsque vous installez des actifs à des postes techniques.
11. Dans l'organisateur **Types autorisés**, sélectionnez les types de poste technique qui doivent être valides pour des types de sous-postes techniques liés à un type de poste technique parent qui utilise le type de poste technique sélectionné.
12. Dans l'organisateur **Attributs**, sélectionnez les attributs de poste technique à configurer automatiquement sur des postes techniques utilisant ce type de poste technique. Sélectionnez **Ajouter la ligne**, puis sélectionnez l'attribut.


>[!NOTE] 
>Dans l'organisateur **Général**, vous pouvez obtenir une vue d'ensemble du nombre de types d'actifs, des plans de maintenance, des exigences d'attribut des actifs, des types autorisés, des attributs et du paramétrage de poste technique du type de poste technique. Le champ **Postes techniques** affiche le nombre de postes techniques qui utilisent le type de poste technique. Vous pouvez utiliser le bouton **Copier** pour copier les paramètres d'un type de poste technique sur le type de poste technique sélectionné.
