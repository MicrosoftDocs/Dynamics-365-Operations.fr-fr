---
title: Codes étape de vague
description: Cette rubrique fournit une vue d'ensemble des codes étape de vague et de leur utilisation.
author: josaw1
manager: tfehr
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveStepCode, WHSReplenishmentTemplates, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9332e45f7213ed815e4417969b617256778598db
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428297"
---
# <a name="wave-step-codes"></a>Codes étape de vague

[!include [banner](../includes/banner.md)]

Les codes étape de vague désignent des codes que les utilisateurs peuvent paramétrer et utiliser pour lier des instances spécifiques de méthodes de vague à un modèle correspondant. Parmi les modèles figurent des modèles pour le réapprovisionnement, la mise en conteneur, l'impression d'étiquettes, la création de chargement et le tri.

Lorsque les codes étape de vague ne sont pas utilisés, les utilisateurs doivent saisir un texte libre en référence à un modèle spécifique depuis l'instance de la méthode de vague. Le texte libre est enclin aux erreurs, car les utilisateurs doivent veiller à ce que le texte de l'étape de vague qu'ils ajoutent pour une méthode d'étape de vague spécifique dans un modèle de vague corresponde exactement au texte d'étape de vague dans le modèle cible.

Les codes étape de vague pour un type d'étape de vague spécifique sont configurés sur une page à part. Pour chaque instance de méthode d'étape de vague dans un modèle de vague qui exige un code étape de vague, il convient de sélectionner ce dernier dans une liste déroulante. La sélection dans une liste déroulante remplace la saisie de texte libre et permet de réduire le risque et l'impact d'erreurs humaines. Les codes de configuration sont utilisés pour associer une méthode d'étape de vague dans un modèle de vague à un modèle cible pour la méthode.

> [!NOTE]
> L'utilisation de la fonction de codes d'étapes de vague est facultative. Elle est activé à l'échelle de l'organisation pour toutes les entités juridiques.

## <a name="setup-demo"></a>Démonstration de paramétrage 

Pour cette démonstration, il convient d'avoir des données de démonstration installées, et vous utiliserez l'entreprise de données de démonstration **USMF**.

### <a name="enable-wave-step-codes"></a>Activer les codes étape de vague

Procédez comme suit pour activer la fonctionnalité des codes étape de vague.

1. Accédez à **Gestion des fonctions**.
2. Sélectionnez pour activer la fonction appelée **Code d'étape de vague à l'échelle de l'organisation**.

Tous les textes libres d'étape de vague existant dans toutes les entités juridiques sont mis à niveau vers la nouvelle structure. Une fois cette mise à niveau terminée pour toutes les entités juridiques, la fonctionnalité est activée. Si la fonctionnalité ne peut pas être activée pour une ou plusieurs entités juridiques, alors la fonctionnalité n'est activée pour aucune entité juridique.

Pendant l'activation, les validations sont effectuées pendant la mise à niveau des données. Si la mise à niveau échoue, vous recevez un message d'erreur. Une mise à niveau risque d'échouer en raison des conflits suivants :

- Des doublons de texte libre d'étape de vague existent.
- Des personnalisations existent.
- Un texte libre d'étape de vague associé à une instance de méthode d'étape de vague ne correspond pas au type de modèle prévu.

Après avoir corrigé les conflits identifiés au cours des validations, vous pouvez réessayer d'activer la fonctionnalité.

Une fois la fonctionnalité validée, la page **Codes étape de vague** (**Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**) est disponible. Cette page affiche les codes étape de vague mis à niveau lorsque la fonction Codes étape de vague à l'échelle de l'organisation a été activée.

### <a name="create-new-wave-step-codes"></a>Créer des codes étape de vague

Vous pouvez utiliser la page **Codes étape de vague** pour créer et supprimer des codes étape de vague.

Chaque nouveau code étape de vague et son ID associé doivent être uniques dans tous les types d'étape de vague et doivent être définis pour un type d'étape de vague spécifique.

### <a name="apply-wave-step-codes"></a>Appliquer les codes étape de vague

Après avoir défini les codes étape de vague appropriés, ils peuvent être appliqués aux méthodes de processus de vague.

Pour appliquer des codes étape de vague, accédez au modèle cible approprié. Voici les modèles cibles sur lesquels les codes étape de vague sont désignés :

- **Modèles de réapprovisionnement :** Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement
- **Modèles de création de chargement :** Gestion des entrepôts \> Configuration \> Chargement \> Modèles de création de chargement
- **Modèles de tri :** Gestion des entrepôts \> Configuration \> Emballage \> Modèles de tri sortants
- **Modèles de mise en conteneur :** Gestion des entrepôts \> Configuration \> Conteneurs \> Modèles de création de conteneur
- **Modèles d'impression d'étiquette :** Gestion des entrepôts \> Configuration \> Acheminement des documents \> Modèles d'étiquette de vague

Les modèles de cette liste sont appliqués lorsqu'ils font référence à une méthode de traitement par vague sélectionnée dans un modèle de vague. Lorsque le code étape de vague sur une méthode de traitement par vague dans un modèle de vague correspond au code étape de vague dans un des types de modèle, le modèle est appliqué.

### <a name="sample-scenario"></a>Exemple de scénario

La procédure suivante permet de garantir que le modèle de réapprovisionnement que vous avez créé sera appliqué au modèle de vague.

1. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Codes étape de vague**, puis créez un code étape de vague de type **Réapprovisionnement**.
2. Accédez à **Gestion des entrepôts \> Configuration \> Réapprovisionnement \> Modèles de réapprovisionnement**, et créez un modèle de réapprovisionnement.
3. Dans le modèle de réapprovisionnement, sélectionnez le code étape de vague créé pour le type **Réapprovisionnement**.
4. Accédez à **Gestion des entrepôts \> Configuration \> Vagues \> Modèles de vague**, puis sélectionnez le modèle de vague que vous souhaitez utiliser.
5. Dans le modèle, sous l'organisateur **Méthodes**, sélectionnez la méthode **Réapprovisionnement**.
6. Dans le champ **Code étape de vague**, sélectionnez le code étape de vague que vous avez sélectionné dans le modèle de réapprovisionnement.

Vous effectuez ces étapes pour chaque entité juridique.
