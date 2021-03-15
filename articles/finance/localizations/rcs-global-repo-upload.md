---
title: Créer des configurations ER dans RCS et les télécharger dans le référentiel global
description: Cette rubrique explique comment créer une configuration d’état électronique (ER) dans Microsoft Regulatory Configuration Services (RCS) et comment la télécharger dans le référentiel global.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ef12c911c8953b181db1c0eff0874a3d8cfcb3da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005746"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Créer des configurations ER dans Regulatory Configuration Services (RCS) et les télécharger dans le référentiel global

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour concevoir des configurations d’états électroniques (ER) et les publier afin qu’elles puissent être utilisées dans votre organisation.

Les procédures suivantes expliquent comment un utilisateur ayant un rôle d’administrateur système ou de développeur d’états électroniques peut créer une version dérivée d’une configuration ER qui a été configurée dans une instance RCS, puis la télécharger dans le référentiel global. 

Avant d’exécuter cette procédure, vous devez d’abord effectuer ce qui suit :

- Accédez à une instance RCS.
- Créez un fournisseur de configuration actif. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Vous devez également vous assurer qu’un environnement RCS est configuré pour votre entreprise.

1. Dans une application Finance and Operations, allez dans **Administration d’organisation** \> **Espaces de travail** \> **États électroniques**.
2. Si vous n’avez pas d’environnement RCS configuré dans votre société, sélectionnez **Regulatory services – Configuration externe** et suivez les instructions pour en mettre un en service.

Si un environnement RCS a déjà été configuré pour votre entreprise, utilisez l’URL de la page pour y accéder en sélectionnant l’option de connexion.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Créer une version dérivée d’une configuration dans RCS

1. Dans l’espace de travail **États électroniques**, vérifiez que vous disposez d’un fournisseur de configuration actif pour votre organisation. 
2. Sélectionnez **Configurations des états**.
3. Sélectionnez la configuration dont vous souhaitez dériver une nouvelle version. Vous pouvez utiliser le champ de filtre au-dessus de l’arborescence pour affiner votre recherche.
4. Sélectionnez **Créer une configuration** \> **Provenant du nom**.
5. Saisissez un nom et une description, puis sélectionnez **Créer une configuration** pour créer une nouvelle version dérivée.
6. Sélectionnez la configuration nouvellement dérivée, ajoutez une description de la version, puis sélectionnez **OK**. Le statut de la configuration est remplacé par **Terminé**.

![Nouvelle version de la configuration dans RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Lorsque l’état de la configuration est modifié, vous pouvez recevoir un message d’erreur de validation lié aux applications connectées. Pour désactiver la validation, dans le volet Actions de l’onglet **Configurations**, sélectionnez **Paramètres utilisateur**, puis définissez l’option **Ignorer la validation lors du changement d’état de la configuration et rebaser** sur **Oui** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Télécharger une configuration dans le référentiel global

Pour partager une configuration nouvelle ou dérivée avec votre organisation, vous pouvez la télécharger dans le référentiel global.

1. Sélectionnez la version terminée de la configuration, puis sélectionnez **Télécharger dans le référentiel**.
2. Sélectionnez l’option **Global (Microsoft)**, puis sélectionnez **Télécharger**.

    ![Télécharger dans les options du référentiel](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Dans la boîte de dialogue de confirmation, cliquez sur **Oui**. 
4. Mettez à jour la description de la version selon vos besoins, puis sélectionnez **OK**. 

Le statut de la configuration est mis à jour sur **Partager** et la configuration est téléchargée dans le référentiel global. Vous pouvez ensuite l’utiliser de plusieurs manières :

- Vous pouvez l’importer dans votre instance Dynamics 365. Pour plus d’informations, voir [(ER) Importer les configurations depuis RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Vous pouvez la partager avec un tiers ou une organisation externe, consultez [RCS Partager des configurations d’états électroniques (ER) avec des organisations externes](rcs-global-repo-share-configuration.md)

    ![Version de configuration Intrastat Contoso dérivée dans le référentiel global](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Supprimer une configuration du référentiel Global
Effectuez les étapes suivantes pour supprimer une configuration que votre organisation a créée.

1. Dans l’espace de travail **États électroniques**, vérifiez que votre fournisseur de configuration est **Actif**. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Sur votre fournisseur de configuration actif, sélectionnez **Référentiel**.
3. Sélectionnez le type de référentiel **Global** et sélectionnez **Ouvrir**.
4. Sur le FastTab **Filtre**, recherchez la configuration que vous souhaitez supprimer en utilisant la fonctionnalité **Filtre**.
5. Sur le FastTab **Version**, sélectionnez la version de la configuration que vous souhaitez supprimer, puis sélectionnez **Supprimer** :

    ![Supprimer une configuration du référentiel global](media/RCS_Delete_from_GlobalRepo.JPG)

6. Dans la boîte de dialogue de confirmation, cliquez sur **Oui**.

    ![Supprimer le message de confirmation de la version de la configuration](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
La version de la configuration est supprimée et un message de confirmation s’affiche. 

> [!NOTE]
> Les configurations ne peuvent être supprimées que par le fournisseur de configuration qui les a créées. Si la configuration a été partagée avec une autre organisation, le partage de la configuration devra être annulé avant que vous ne la supprimiez.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]