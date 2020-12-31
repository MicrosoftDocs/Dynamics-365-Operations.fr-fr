---
title: Résolution générale des problèmes
description: Cette rubrique fournit des informations sur la résolution générale des problèmes liés à l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 6356ec6850667f32f9e9e4133686c40f0b6d76d7
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688257"
---
# <a name="general-troubleshooting"></a>Résolution générale des problèmes

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Cette rubrique fournit des informations sur la résolution générale des problèmes liés à l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a>Lorsque vous essayez d’installer le package de double écriture à l’aide de l’outil Package Deployer, aucune solution disponible n’est affichée.

Certaines versions de l’outil Package Deployer sont incompatibles avec le package de solution de double écriture. Pour installer correctement le package, assurez-vous d’utiliser la [version 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) ou une version ultérieure de l’outil Package Deployer.

Après avoir installé l’outil Package Deployer, installez le package de solution en suivant ces étapes.

1. Téléchargez le dernier fichier de package de solution depuis Yammer.com. Une fois le fichier zip du package téléchargé, cliquez dessus avec le bouton droit et sélectionnez **Propriétés**. Cochez la case **Débloquer**, puis sélectionnez **Appliquer**. Si vous ne voyez pas la case à cocher **Débloquer**, le fichier zip est déjà débloqué et vous pouvez ignorer cette étape.

    ![Boîte de dialogue Propriétés](media/unblock_option.png)

2. Extrayez le fichier zip du package et copiez tous les fichiers dans le dossier **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.

    ![Contenu du dossier Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. Collez tous les fichiers copiés dans le dossier **Outils** de l’outil Package Deployer. 
4. Exécutez **PackageDeployer.exe** pour sélectionner l’environnement Dataverse et installez les solutions.

    ![Contenu du dossier Outils](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Activer et afficher le journal de suivi des plug-ins dans Dataverse pour afficher les détails de l’erreur

**Rôle requis pour activer le journal de suivi et afficher les erreurs :** Administrateur système

Pour activer le journal de suivi, procédez comme suit.

1. Connectez-vous à l’application pilotée par modèle dans Dynamics 365, ouvrez la page **Paramètres**, puis, sous **Système**, sélectionnez **Administration**.
2. Sur la page **Administration**, sélectionnez **Paramètres système**.
3. Sur l’onglet **Personnalisation**, dans le champ **Suivi de plug-ins et d’activités de workflow personnalisées**, sélectionnez **Tout** pour activer le journal de suivi du plug-in. Si vous souhaitez consigner les journaux de suivi uniquement lorsque des exceptions se produisent, sélectionnez plutôt **Exception**.


Pour afficher le journal de suivi, procédez comme suit.

1. Connectez-vous à l’application pilotée par modèle dans Dynamics 365, ouvrez la page **Paramètres**, puis, sous **Personnalisation**, sélectionnez **Journal de suivi du plug-in**.
2. Recherchez les journaux de suivi où le champ **Nom du type** est défini sur **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Double-cliquez sur un élément pour afficher le journal complet, puis, sur le raccourci **Exécution**, passez en revue le texte du **Bloc de message**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Activez le mode débogage pour résoudre les problèmes de synchronisation en direct dans les applications Finance and Operations

**Rôle requis pour afficher les erreurs :** Les erreurs de double écriture d’administrateur système provenant de Dataverse peuvent s’afficher dans l’application Finance and Operations. Dans certains cas, le texte intégral du message d’erreur n’est pas disponible, car le message est trop long ou contient des informations d’identification personnelle (IIP). Vous pouvez activer la journalisation détaillée des erreurs en procédant comme suit.

1. Toutes les configurations de projet dans les applications Finance and Operations ont une propriété **IsDebugMode** dans l’entité **DualWriteProjectConfiguration**. Ouvrez l’entité **DualWriteProjectConfiguration** à l’aide du module complémentaire Excel.

    > [!TIP]
    > Un moyen simple d’ouvrir l’entité consiste à activer le mode **Conception** dans le module complémentaire Excel, puis ajoutez **DualWriteProjectConfigurationEntity** à la feuille de calcul. Pour en savoir plus, voir [Ouvrir des données d’entité dans Excel et les mettre à jour à l’aide du module complémentaire Excel](../../office-integration/use-excel-add-in.md).

2. Définissez la propriété **IsDebugMode** sur **Oui** pour le projet.
3. Exécutez le scénario qui génère des erreurs.
4. Les journaux détaillés sont disponibles dans la table DualWriteErrorLog. Pour rechercher des données dans le navigateur de table, utilisez l’URL suivante (remplacez **XXX**, le cas échéant) :

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Vérifier les erreurs de synchronisation sur la machine virtuelle pour l’application Finance and Operations

**Rôle requis pour afficher les erreurs :** Administrateur système

1. Connectez-vous à Microsoft Dynamics Lifecycle Services (LCS).
2. Ouvrez le projet LCS que vous avez choisi pour effectuer le test de double écriture.
3. Sélectionnez la vignette **Environnements hébergés dans le cloud**.
4. Utilisez Remote Desktop pour vous connecter à la machine virtuelle pour l’application Finance and Operations. Utilisez le compte local affiché dans LCS.
5. Ouvrez l’observateur d’événements.
6. Sélectionnez **Journaux des applications et des services \> Microsoft \> Dynamics \> AX-DualWriteSync \> Opérationnel**.
7. Consultez la liste des erreurs récentes.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Dissocier et lier un autre environnement Dataverse depuis une application Finance and Operations

**Rôle requis pour dissocier l’environnement :** Administrateur système pour l’application Finance and Operations ou Dataverse.

1. Connectez-vous à l’application Finance and Operations.
2. Accédez à **Espaces de travail \> Gestion des données** et sélectionnez la vignette **Double écriture**.
3. Sélectionnez toutes les mises en correspondance en cours d’exécution et sélectionnez **Arrêter**.
4. Cliquez sur **Supprimer le lien avec l’environnement**.
5. Sélectionnez **Oui** pour confirmer l’opération.

Vous pouvez maintenant lier un nouvel environnement.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Impossible d’afficher le formulaire d’informations de ligne de la commande client 

Lorsque vous créez une commande client dans Dynamics 365 Sales, cliquer sur **+ Ajouter des produits** peut vous rediriger vers le formulaire de ligne de commande Dynamics 365 Project Operations. Il n’y a aucun moyen à partir de ce formulaire pour afficher le formulaire de ligne de commande client **Informations**. L’option pour **Informations** n’apparaît pas dans la liste déroulante sous **Nouvelle ligne de commande**. Cela se produit car Project Operations a été installé dans votre environnement.

Pour réactiver l’option de formulaire **Informations**, procédez comme suit :
1. Accédez à l’entité **Ligne de commande**.
2. Recherchez le formulaire **Informations** sous le nœud de formulaires. 
3. Sélectionnez le formulaire **Informations** et cliquez sur **Activer les rôles de sécurité**. 
4. Modifiez le paramètre de sécurité sur **Afficher pour tout le monde**.
