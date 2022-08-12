---
title: Créer des configurations ER dans RCS et les télécharger dans le référentiel global
description: Cet article explique comment créer une configuration d’état électronique (ER) dans Microsoft Regulatory Configuration Services (RCS) et comment la télécharger dans le référentiel global.
author: JaneA07
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f73f7189ad82d85169a4e0df573dd26dab8bb009
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070598"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Créer des configurations ER dans Regulatory Configuration Services (RCS) et les télécharger dans le référentiel global

[!include [banner](../includes/banner.md)]

Vous pouvez utiliser Microsoft Regulatory Configuration Services (RCS) pour concevoir des configurations d’états électroniques (ER) et les publier afin qu’elles puissent être utilisées dans votre organisation.

Les procédures suivantes expliquent comment un utilisateur ayant un rôle d’administrateur système ou de développeur d’états électroniques peut créer une version dérivée d’une configuration ER qui a été configurée dans une instance RCS, puis la télécharger dans le référentiel global. 

Avant d’exécuter cette procédure, vous devez d’abord effectuer ce qui suit :

- Ayez accès à un environnement RCS pour votre organisation.
- Créez un fournisseur de configuration actif et marquez-le comme actif. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Vous devez également vous assurer qu’un environnement RCS est configuré pour votre organisation. Si vous n’avez pas d’instance RCS provisionnée pour votre organisation, vous pouvez le faire en procédant comme suit :

1. Dans une application de finances et d’opérations, accédez à **Administration d’organisation** \> **Espaces de travail** \> **Gestion des états électroniques**.
2. Dans **Liens connexes / Liens externes**, sélectionnez **Regulatory services – Configuration**, puis suivez les instructions pour **Vous inscrire** pour en configurer une.

Si un environnement RCS a déjà été configuré pour votre organisation, utilisez l’URL de la page pour y accéder et sélectionnez l’option de **connexion**.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Créer une version dérivée d’une configuration dans RCS

> [!NOTE]
> Si c’est la première fois que vous utilisez RCS, vous n’aurez aucune configuration disponible de laquelle en dériver une nouvelle. Vous devrez importer une configuration depuis le référentiel global. Pour plus d’informations, voir [Télécharger les configurations des états électroniques (ER) à partir du référentiel global de Configuration Service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. **Connectez-vous** à RCS et sélectionnez l’espace de travail **Gestion des états électroniques**.
2. Vérifiez que vous disposez d’un fournisseur de configuration actif pour votre organisation qui soit défini comme actif (voir les conditions préalables). 
3. Sélectionnez **Configurations des états**.
4. Sélectionnez la configuration dont vous souhaitez dériver une nouvelle version. Vous pouvez utiliser le champ de filtre au-dessus de l’arborescence pour affiner votre recherche.
5. Sélectionnez **Créer une configuration** \> **Provenant du nom**.
6. Saisissez un nom et une description, puis sélectionnez **Créer une configuration** pour créer une nouvelle version dérivée ayant le statut « Brouillon ».
7. Sélectionnez la configuration nouvellement dérivée et apportez des modifications supplémentaires au format de la configuration, si nécessaire. 
8. Une fois vos modifications terminées, vous devez **Modifier le statut** de la configuration en **Terminé** pour pouvoir la publier dans le référentiel. Cliquez sur **OK**.

![Nouvelle version de la configuration dans RCS.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Lorsque l’état de la configuration est modifié, vous pouvez recevoir un message d’erreur de validation lié aux applications connectées. Pour désactiver la validation, dans le volet Actions de l’onglet **Configurations**, sélectionnez **Paramètres utilisateur**, puis définissez l’option **Ignorer la validation lors du changement d’état de la configuration et rebaser** sur **Oui** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Télécharger une configuration dans le référentiel global

Pour partager une configuration nouvelle ou dérivée avec votre organisation, vous pouvez la charger dans le référentiel global en procédant comme suit :

1. Sélectionnez la version terminée de la configuration, puis sélectionnez **Télécharger dans le référentiel**.
2. Sélectionnez l’option **Global (Microsoft)**, puis sélectionnez **Télécharger**.

    ![Télécharger dans les options du référentiel.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. Dans la boîte de dialogue de confirmation, cliquez sur **Oui**. 
4. Mettez à jour la description de la version selon vos besoins, puis sélectionnez **OK**. Vous pouvez également éventuellement charger la version vers une application connectée ou vers un référentiel GIT.  

Le statut de la configuration est mis à jour sur **Partagé** et la configuration est chargée dans le référentiel global. Une version brouillon de la configuration que vous avez chargée est également créée et peut être utilisée si des modifications ultérieures sont nécessaires.

Une fois la configuration chargée dans le référentiel global, vous pouvez l’utiliser de la manière suivante :

- Vous pouvez l’importer dans votre instance Dynamics 365. Pour plus d’informations, voir [(ER) Importer les configurations depuis RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Vous pouvez la partager avec un tiers ou une organisation externe, consultez [RCS Partager des configurations d’états électroniques (ER) avec des organisations externes](rcs-global-repo-share-configuration.md)

    ![Version de configuration Intrastat Contoso dérivée dans le référentiel global.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Supprimer une configuration du référentiel Global
Effectuez les étapes suivantes pour supprimer une configuration que votre organisation a créée.

1. Dans l’espace de travail **États électroniques**, vérifiez que votre fournisseur de configuration est **Actif**. Pour plus d’informations, voir la procédure [Créer des fournisseurs de configuration et les marquer comme actif](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Sur votre fournisseur de configuration actif, sélectionnez **Référentiel**.
3. Sélectionnez le type de référentiel **Global** et sélectionnez **Ouvrir**.
4. Sur le FastTab **Filtre**, recherchez la configuration que vous souhaitez supprimer en utilisant la fonctionnalité **Filtre**.
5. Sur le FastTab **Version**, sélectionnez la version de la configuration que vous souhaitez supprimer, puis sélectionnez **Supprimer** :

    ![Supprimer une configuration du référentiel global.](media/RCS_Delete_from_GlobalRepo.JPG)

6. Dans la boîte de dialogue de confirmation, cliquez sur **Oui**.

    ![Supprimer le message de confirmation de la version de la configuration.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
La version de la configuration est supprimée et un message de confirmation s’affiche. 

> [!NOTE]
> Les configurations ne peuvent être supprimées que par le fournisseur de configuration qui les a créées. Si la configuration a été partagée avec une autre organisation, le partage de la configuration devra être annulé avant que vous ne la supprimiez.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

