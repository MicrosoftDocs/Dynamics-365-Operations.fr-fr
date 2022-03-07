---
title: Interrompre les configurations dans le référentiel RCS Global
description: Cette rubrique décrit comment interrompre les configurations dans le référentiel RCS Global.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 1d25d583580af3d73a3ac1eaebc9f7d8413c6563
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360203"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Interrompre les configurations dans le référentiel RCS Global

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment interrompre une configuration dans le référentiel RCS Global. Auparavant, il était possible de supprimer uniquement les configurations qui n’étaient plus nécessaires. Cependant, vous pouvez maintenant marquer une configuration lancée comme **Interrompue** dans le référentiel RCS Global. Avec cette fonctionnalité, vous pouvez également effectuer les opérations suivantes : 
 
 - Fournir des notifications à l’avance lorsque l’interruption d’une configuration est interrompue.
 - Incluez les détails applicables sur la configuration de remplacement.
 - Définissez une valeur pour **Date de fin de prise en charge** pour la configuration spécifique afin d’informer l’utilisateur de la date d’interruption.

Lorsque vous interrompez la version d’une configuration, vous pouvez spécifier les informations facultatives suivantes :

  - **Configuration de remplacement**
  - **Version de configuration de remplacement**
  - **Note libre** : Utilisez ce champ pour fournir des liens vers des documentations ou des références
  - **Date de fin de prise en charge** : Ce champ fournit la date proposée jusqu’à laquelle la configuration / version actuelle sera prise en charge. Cette date doit être mise à jour manuellement.
  
Pour interrompre la configuration, procédez comme suit. 

1. Sélectionnez si vous souhaitez interrompre une seule version ou toutes les versions avec les mêmes paramètres en une seule opération en définissant **Toutes les versions** sur **Oui**. 
2. Définissez le paramètre **Interrompre** sur **Oui**.
3. Sélectionnez **OK** pour interrompre les configurations. Le champ **Date d’interruption** sera rempli lorsque vous enregistrez les modifications.

![Interrompre les informations de configuration.](media/Discontinue-details-2.png)
  
Vous pouvez rétablir la configuration sur **Partagé** ou ajuster les informations d’interruption à tout moment. Si vous partagez une configuration, spécifiez la valeur pour **Date de fin de prise en charge** et toutes les autres informations relatives à l’interruption pour indiquer les interruptions futures que vous prévoyez.

Si vous souhaitez partager des informations sur une interruption planifiée, avant d’interrompre réellement la configuration, l’utilisateur peut préremplir tous les champs liés au remplacement, mais laisser le paramètre **Interrompre** défini sur **Non**.

> [!NOTE]
> L’interruption ne limite pas les opérations avec les configurations. Vous pouvez continuer à importer, exécuter ou dériver les configurations. Ces champs sont indicatifs.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>Finance prend en charge l’affichage de ces informations à partir de la version 10.0.14

À partir de la version 10.0.14, Dynamics 365 Finance prend en charge l’affichage des informations relatives aux interruptions. Sur la page **Référentiel global**, vous pouvez afficher les informations à jour relatives aux interruptions. Par défaut, les configurations interrompues sont ignorées.
  
La page **Configurations importées** (ERSolutionTable) affiche les configurations qui étaient déjà interrompues lors de leur importation. Pour les configurations qui ont été interrompues après l’importation, les informations d’interruption peuvent être synchronisées en exécutant la tâche **Importer les mises à jour des configurations**.


