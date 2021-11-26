---
title: Résolution générale des problèmes
description: Cette rubrique fournit des informations sur la résolution générale des problèmes liés à l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: bcedb9f6e8fb15210512ed6a376d4329759593e4
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781172"
---
# <a name="general-troubleshooting"></a>Résolution générale des problèmes

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique fournit des informations sur la résolution générale des problèmes liés à l’intégration de la double écriture entre les applications Finance and Operations et Dataverse.

> [!IMPORTANT]
> Certains des problèmes abordés dans cette rubrique peuvent exiger le rôle d’administrateur système ou les identifiants d’admin client Microsoft Azure Active Directory (Azure AD). La section pour chaque problème explique si un rôle spécifique ou des informations d’identification sont requis.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Activer et afficher le journal de suivi des plug-ins dans Dataverse pour afficher les détails de l’erreur

**Rôle requis pour activer le journal de suivi et afficher les erreurs :** Administrateur système

Pour activer le journal de suivi, procédez comme suit.

1. Connectez-vous à l’application d’engagement client , ouvrez la page **Paramètres** puis, sous **Système**, sélectionnez **Administration**.
2. Sur la page **Administration**, sélectionnez **Paramètres système**.
3. Sur l’onglet **Personnalisation**, dans la colonne **Suivi de plug-ins et d’activités de workflow personnalisées**, sélectionnez **Tout** pour activer le journal de suivi du plug-in. Si vous souhaitez consigner les journaux de suivi uniquement lorsque des exceptions se produisent, sélectionnez plutôt **Exception**.


Pour afficher le journal de suivi, procédez comme suit.

1. Connectez-vous à l’application d’engagement client , ouvrez la page **Paramètres** puis, sous **Personnalisation**, sélectionnez **Journal de suivi du plug-in**.
2. Recherchez les journaux de suivi où la colonne **Nom du type** est définie sur **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Double-cliquez sur un élément pour afficher le journal complet, puis, sur le raccourci **Exécution**, passez en revue le texte du **Bloc de message**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Activez le mode débogage pour résoudre les problèmes de synchronisation en direct dans les applications Finance and Operations

**Rôle requis pour afficher les erreurs :** Administrateur système

Des erreurs de double écriture qui proviennent de Dataverse peuvent apparaître dans l’application Finance and Operations. Pour activer la journalisation détaillée des erreurs, procédez comme suit :

1. Pour toutes les configurations de projet dans l’application Finance and Operations, il y a un indicateur **IsDebugMode** sur la table **DualWriteProjectConfiguration**.
2. Ouvrez la table **DualWriteProjectConfiguration** à l’aide du module complémentaire Excel. Pour utiliser le complément, activez le mode conception dans le module complémentaire Excel Finance and Operations et ajoutez **DualWriteProjectConfiguration** à la fiche. Pour plus d’informations, voir [Afficher et mettre à jour les données d’entité avec Excel](../../office-integration/use-excel-add-in.md).
3. Définissez **IsDebugMode** sur **Oui** sur le projet.
4. Exécutez le scénario qui génère des erreurs.
5. Les journaux détaillés sont disponibles dans la table **DualWriteErrorLog**.
6. Pour rechercher des données sur le navigateur de table, utilisez le lien suivant : `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, remplaçant `999` comme requis.
7. Mettez à jour à nouveau après [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), qui est disponible pour les mises à jour de plate-forme 37 et versions ultérieures. Si vous avez installé ce correctif, le mode de débogage capturera plus de journaux.  

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

1. Accédez à la table **Ligne de commande**.
2. Recherchez le formulaire **Informations** sous le nœud de formulaires.
3. Sélectionnez le formulaire **Informations** et cliquez sur **Activer les rôles de sécurité**.
4. Modifiez le paramètre de sécurité sur **Afficher pour tout le monde**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Comment activer et enregistrer le suivi du réseau afin que le suivi puisse être joint aux tickets de support

L’équipe du support technique peut avoir besoin d’examiner le suivi du réseau pour résoudre certains problèmes. Pour créer un suivi du réseau, procédez comme suit :

### <a name="chrome"></a>Chrome

1. Dans l’onglet ouvert, appuyez sur **F12** ou choisissez **Outils de développement** pour ouvrir les outils de développement.
2. Ouvrez l’onglet **Réseau** et saisissez **entier** dans la zone de texte du filtre.
3. Exécutez votre scénario et observez les demandes enregistrées.
4. Faites un clic droit sur les entrées et sélectionnez **Enregistrer tout en tant que HAR avec contenu**.

### <a name="microsoft-edge"></a>Microsoft Edge

1. Dans l’onglet ouvert, appuyez sur **F12** ou choisissez **Outils de développement** pour ouvrir les outils de développement.
2. Ouvrez l’onglet **Réseau**.
3. Exécutez votre scénario.
4. Sélectionnez **enregistrer** pour exporter les résultats au format HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
