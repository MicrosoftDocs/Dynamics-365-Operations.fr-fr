---
title: Importer des fonctionnalités depuis le référentiel global
description: Cette rubrique explique comment importer des fonctionnalités de globalisation à partir du référentiel global.
author: dkalyuzh
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ff3019986d089a286f7aef94346398b3d328ad54
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371632"
---
# <a name="import-features-from-the-global-repository"></a>Importer des fonctionnalités depuis le référentiel global

[!include [banner](../includes/banner.md)]

Le référentiel global contient des fonctionnalités de facturation électronique qui sont partagées avec votre fournisseur de configuration. Toutes les fonctionnalités de facturation électronique fournies par Microsoft sont partagées avec toutes les entreprises. Vous avez automatiquement accès à toutes les fonctionnalités de facturation électronique que Microsoft lance et publie dans le référentiel mondial.

Pour commencer à utiliser les fonctionnalités de facturation électronique partagées avec votre fournisseur de configuration, importez-les dans votre instance de Regulatory Configuration Service (RCS) à partir du référentiel global. Passez ensuite en revue les détails de la fonctionnalité, tels que les configurations de gestion des états électroniques (ER) et les pipelines de traitement.

## <a name="import-a-feature-from-the-global-repository"></a>Importer une fonctionnalité depuis le référentiel global

1. Connectez-vous à votre compte RCS.
2. Dans l’espace de travail **Fonctionnalité de globalisation**, dans la section **Fonctionnalités**, sélectionnez la vignette **Facturation électronique**.
3. Sélectionnez **Importation** pour ouvrir la recherche **Importer une fonctionnalité depuis le référentiel global**.
4. Pour parcourir les fonctionnalités de facturation électronique disponibles dans le référentiel global pour un fournisseur de configuration spécifique, synchronisez l’instance RCS de votre organisation en sélectionnant **Synchroniser**. Une fois la synchronisation terminée, la liste des fonctionnalités de facturation électronique disponibles est mise à jour depuis le référentiel global. Cette mise à jour peut prendre quelques minutes.
5. Sélectionnez la fonctionnalité à importer, puis sélectionnez **Importation**.

Pour afficher la fonctionnalité de facturation électronique, veillez à ce que le fournisseur de configuration approprié soit sélectionné. Par défaut, les fonctionnalités créées par le fournisseur de configuration actif sont automatiquement filtrées. Vous pouvez ajuster le filtre pour afficher les fonctionnalités créées par d’autres fournisseurs, tels que le fournisseur de configuration Microsoft.

Vous pouvez maintenant utiliser la fonctionnalité importée. Vous pouvez revoir ses détails et créer une fonctionnalité en utilisant la fonctionnalité importée comme modèle.

> [!NOTE]
> Vous pouvez modifier une fonctionnalité uniquement si elle a été créée par le fournisseur de configuration actuellement actif. Vous pouvez créer une fonctionnalité en utilisant la fonction d’origine comme base. Vous pouvez ensuite apporter les modifications requises ou configurer les paramètres.

Lorsque Microsoft ou une autre société qui partage les fonctionnalités de globalisation avec votre société met à jour les fonctionnalités que vous avez importées, vous pouvez vérifier les versions mises à jour en sélectionnant **Rechercher les mises à jour des fonctionnalités** dans la section **Paramètres associés** de l’espace de travail **Fonctionnalités de globalisation**.

Si vous constatez qu’il existe des mises à jour pour une fonctionnalité que vous utilisez comme modèle, vous pouvez importer une nouvelle version après avoir synchronisé la liste des fonctionnalités publiées dans le référentiel global.
