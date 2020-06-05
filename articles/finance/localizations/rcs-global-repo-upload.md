---
title: Créer des configurations ER dans RCS et les télécharger dans le référentiel global
description: Cette rubrique explique comment créer une configuration d'état électronique (ER) dans Microsoft Regulatory Configuration Services (RCS) et comment la télécharger dans le référentiel global.
author: JaneA07
manager: AnnBe
ms.date: 05/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0e194a8b777f984412d81e315f92ab4bb8a3b0c9
ms.sourcegitcommit: 204cec8ca2a6c4474d21dbcd408e369131a47856
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "3371245"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Créer des configurations ER dans Regulatory Configuration Services (RCS) et les télécharger dans le référentiel global

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour concevoir des configurations d'états électroniques (ER) et les publier afin qu'elles puissent être utilisées dans votre organisation.

Les procédures suivantes expliquent comment un utilisateur ayant un rôle d'administrateur système ou de développeur d'états électroniques peut créer une version dérivée d'une configuration ER qui a été configurée dans une instance RCS, puis la télécharger dans le référentiel global. 

Avant d'exécuter cette procédure, vous devez d'abord effectuer ce qui suit :

- Accédez à une instance RCS.
- Créez un fournisseur de configuration actif. Pour plus d'informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Vous devez également vous assurer qu'un environnement RCS est configuré pour votre entreprise.

1. Dans une application Finance and Operations, allez dans **Administration d'organisation** \> **Espaces de travail** \> **États électroniques**.
2. Si vous n'avez pas d'environnement RCS configuré dans votre société, sélectionnez **Regulatory services – Configuration externe** et suivez les instructions pour en mettre un en service.

Si un environnement RCS a déjà été configuré pour votre entreprise, utilisez l'URL de la page pour y accéder en sélectionnant l'option de connexion.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Créer une version dérivée d'une configuration dans RCS

1. Dans l'espace de travail **États électroniques**, vérifiez que vous disposez d'un fournisseur de configuration actif pour votre organisation. 
2. Sélectionnez **Configurations des états**.
3. Sélectionnez la configuration dont vous souhaitez dériver une nouvelle version. Vous pouvez utiliser le champ de filtre au-dessus de l'arborescence pour affiner votre recherche.
4. Sélectionnez **Créer une configuration** \> **Provenant du nom**.
5. Saisissez un nom et une description, puis sélectionnez **Créer une configuration** pour créer une nouvelle version dérivée.
6. Sélectionnez la configuration nouvellement dérivée, ajoutez une description de la version, puis sélectionnez **OK**. Le statut de la configuration est remplacé par **Terminé**.

![Nouvelle version de la configuration dans RCS](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Lorsque l'état de la configuration est modifié, vous pouvez recevoir un message d'erreur de validation lié aux applications connectées. Pour désactiver la validation, dans le volet Actions de l'onglet **Configurations**, sélectionnez **Paramètres utilisateur**, puis définissez l'option **Ignorer la validation lors du changement d'état de la configuration et rebaser** sur **Oui** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Télécharger une configuration dans le référentiel global

Pour partager une configuration nouvelle ou dérivée avec votre organisation, vous pouvez la télécharger dans le référentiel global.

1. Sélectionnez la version terminée de la configuration, puis sélectionnez **Télécharger dans le référentiel**.
2. Sélectionnez l'option **Global (Microsoft)**, puis sélectionnez **Télécharger**.

    ![Télécharger dans les options du référentiel](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Dans la boîte de dialogue de confirmation, cliquez sur **Oui**. 
4. Mettez à jour la description de la version selon vos besoins, puis sélectionnez **OK**. 

Le statut de la configuration est mis à jour sur **Partager** et la configuration est téléchargée dans le référentiel global. Vous pouvez ensuite l'utiliser de plusieurs manières :

- Vous pouvez l'importer dans votre instance Dynamics 365. Pour plus d'informations, voir [(ER) Importer les configurations depuis RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Vous pouvez la partager avec un tiers ou une organisation externe, consultez [RCS Partager des configurations d'états électroniques (ER) avec des organisations externes](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/rcs-global-share-configuration.md)

![Version de configuration Intrastat Contoso dérivée dans le référentiel global](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Config_upload_GlobalRepo.JPG)
