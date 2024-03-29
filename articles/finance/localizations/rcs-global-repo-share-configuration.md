---
title: Partager les configurations ER dans RCS/le référentiel global avec des organisations externes
description: Cet article explique comment partager des configurations d’états électroniques (ER) dans Microsoft Regulatory Configuration Services (RCS)/le référentiel global directement avec des organisations externes.
author: kfend
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
ms.openlocfilehash: d9400ffcede9924a01391a433b570651d3f0c5e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284813"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>Partager des configurations d’états électroniques (ER) dans Regulatory Configuration Services (RCS)/le référentiel global avec des organisations externes.

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour partager des configurations d’états électroniques (ER) et les publier dans des organisations externes.

Les procédures suivantes expliquent comment un utilisateur RCS peut partager une version d’une configuration ER qui a été configurée dans une instance RCS avec une organisation externe. Avant d’exécuter cette procédure, vous devez d’abord effectuer ce qui suit :

- Accédez à une instance RCS.
- Créez un fournisseur de configuration actif. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
- Créez et téléchargez une nouvelle version de configuration ER. Pour plus d’informations, voir [Créer et télécharger une nouvelle version d’une configuration d’état électronique (ER)](rcs-global-repo-upload.md).

Vous devez également vous assurer qu’un environnement RCS est configuré pour votre entreprise.

1. Dans une application de finances et d’opérations, accédez à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques**.
2. Si vous n’avez pas d’environnement RCS configuré dans votre société, sélectionnez **Regulatory services – Configuration externe** et suivez les instructions pour en mettre un en service.

Si un environnement RCS a déjà été configuré pour votre entreprise, utilisez l’URL de la page pour y accéder en sélectionnant l’option de connexion.

## <a name="verify-the-configuration-that-you-want-to-share"></a>Vérifier la configuration à partager

Suivez ces étapes pour vérifier que la configuration que vous souhaitez partager a déjà été téléchargée dans le référentiel global.

1. Dans l’espace de travail **États électroniques**, sélectionnez **Référentiels** comme fournisseur de configuration.

    ![Fournisseurs de configuration.](media/1_RCS_Repo_for_config_provider.JPG)

2. Select **Référentiel global** \> **Ouvrir**.
3. Recherchez la configuration à partager. Vous pouvez utiliser le champ de filtre pour affiner votre recherche. Si vous ne trouvez pas la configuration dans le référentiel global, suivez les étapes indiquées dans [Créer et télécharger une nouvelle version d’une configuration d’état électronique (ER)](rcs-global-repo-upload.md).

## <a name="share-er-configurations-with-external-organizations"></a>Partager des configurations ER avec des organisations externes

Une fois qu’une configuration a été créée sous votre fournisseur de configuration, vous pouvez la partager directement avec des organisations externes en utilisant le raccourci **Partagé avec** de la page **Référentiel de configuration globale**.

1. Dans l’espace de travail **États électroniques**, sélectionnez **Référentiels** comme fournisseur de configuration.
2. Select **Référentiel global** \> **Ouvrir**. 
3. Sélectionnez la configuration à partager.
4. Dans le raccourci **Partagé avec**, sélectionnez **Organisation**.

    ![Raccourci Partagé avec.](media/1_RCS_Repo_for_Share_with_org.JPG)

5. Dans la boîte de dialogue, entrez le nom de domaine de l’organisation externe, puis sélectionnez **OK**.

    ![Boîte de dialogue Partager la version de la configuration avec l’organisation externe.](media/1_RCS_Repo_for_Share_with_form.JPG)

La configuration est partagée avec l’organisation externe et est disponible pour cette organisation dans le référentiel global. De là, elle peut être importée dans l’instance de RCS de l’organisation ou dans ses instances des applications de finances et d’opérations.

6. Pour annuler le partage d’une configuration qui a été précédemment partagée avec une organisation externe, sélectionnez la configuration et cliquez sur **Annuler le partage**, puis cliquez sur **OK**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
