---
title: Réinitialiser la synchronisation de Dataverse
description: Cette rubrique explique comment résoudre les enregistrements qui ne se synchronisent pas correctement entre Microsoft Dynamics 365 Human Resources et la solution Human capital management (HCM) Common dans Microsoft Dataverse.
author: jaredha
ms.date: 09/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-27
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 8bfcd51b023c02590919155abbb836326408d298
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8696233"
---
# <a name="reset-dataverse-synchronization"></a>Réinitialiser la synchronisation de Dataverse


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Problème

Les enregistrements ne sont pas synchronisés entre Microsoft Dynamics 365 Human Resources et les entités de la solution Human capital management (HCM) Common dans Microsoft Dataverse. Pour plus d’informations sur la synchronisation, accédez à [Configurer l’intégration Dataverse](hr-admin-integration-common-data-service.md). Une mauvaise synchronisation peut se produire lorsque les travaux par lots **Nouvelle tentative d’intégration Dataverse** ou **Synchronisation des demandes d’intégration manquées Dataverse** sont bloqués dans un état **Exécution**.

## <a name="resolution"></a>Résolution

Lorsque les travaux par lots **Nouvelle tentative d’intégration Dataverse** ou **Intégration Dataverse en échec, demande de synchronisation** sont bloqués à l’état **Exécution** ou **Annulation**, vous pouvez réinitialiser l’état. Cela peut être fait en annulant le travail par lots en suivant les instructions de [réinitialisation des traitements par lots bloqués](hr-admin-troubleshooting-batch-execution.md). Une fois que vous avez annulé le traitement par lots, vous pouvez réinitialiser le traitement par lots en le définissant sur un statut **En attente**. Le travail par lots s’exécutera ensuite lors de la prochaine exécution planifiée.

1. Si vous ne l’avez pas déjà fait, activez la fonctionnalité **Abandon de lot amélioré** dans **Gestion des fonctionnalités**.
   1. Accédez aux pages **Gestion des fonctionnalités** (**Administration du système** > **Sommaire** > **Gestion des fonctionnalités**).
   2. Sélectionnez l’onglet **Tout**.
   3. Sélectionnez la colonne **Nom de la fonctionnalité** et filtrez en fonction de **Abandon de lot amélioré**.
   4. Sélectionnez l’action **Activer** si elle n’est pas déjà activée.

2. Désactivez l’intégration de Dataverse.
   1. Accédez aux pages **Intégration Microsoft Dataverse** (**Administration système**, accédez à **Liens** > **Intégrations** > **Configuration Dataverse**).
   2. Définissez **Activer l’intégration de Dataverse** sur **Non**.

3. Annulez le travail par lots **Nouvelle tentative d’intégration Dataverse**.
   1. Accédez à la page **Traitements par lots** dans (**Administration du système**, accédez à **Liens** > **Traitements par lots** > **Traitement par lots**).
   2. Filtrez la colonne **Description du poste** par **Intégration**.
   3. Sélectionnez le travail par lots **Nouvelle tentative d’intégration Dataverse**.
   4. Sur le ruban d’action, sélectionnez **Travail par lots**, **Forcer l’annulation**, puis sélectionnez **Oui** pour confirmer.

   > [!NOTE]
   > Selon le moment où l’intégration a été activée pour la première fois, le travail par lots peut avoir la description **Nouvelle tentative d’intégration Common Data Service**. Sélectionnez ce travail par lots s’il est répertorié, au lieu du traitement par lots **Nouvelle tentative d’intégration Dataverse**.

4. Supprimez tous les traitements par lots d’intégration Dataverse.
   1. Sur la page **Traitements par lots**, sélectionnez les traitements par lots **Intégration Dataverse en échec, demande de synchronisation**, **Nouvelle tentative d’intégration Dataverse** et **Synchronisation initiale de l’intégration Dataverse**.
   2. Sur le ruban d’action, sélectionnez l’action **Modifier le statut**. 
   3. Sélectionnez **Retenir**, puis sélectionnez **OK**.
   4. Sur le ruban d’action, sélectionnez l’action **Effacer**, puis sélectionnez **Oui** pour confirmer l’action.

5. Activez les traitements par lots d’intégration Dataverse.
   1. Accédez à la page **Intégration Microsoft Dataverse** (**Administration système** > **Liens** > **Intégration** > **Configuration Dataverse**).
   2. Définissez **Activer l’intégration de Dataverse** sur **Oui**.

6. Accédez à la page **Traitements par lots** et confirmez que les traitements par lots **Nouvelle tentative d’intégration Dataverse** et **Intégration Dataverse en échec, demande de synchronisation** ont été créés.

Une fois les traitements par lots recréés, vous pouvez désormais surveiller le traitement par lots **Nouvelle tentative d’intégration Dataverse** pour voir combien de temps le traitement prend pour s’exécuter. Vous pouvez ensuite vérifier que les enregistrements se synchronisent correctement avec la solution HCM Common dans Microsoft Dataverse.

## <a name="see-also"></a>Voir également :

[Configuration de l’intégration Dataverse](hr-admin-integration-common-data-service.md)<br>
[Réinitialiser les traitements par lots bloqués](hr-admin-troubleshooting-batch-execution.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
