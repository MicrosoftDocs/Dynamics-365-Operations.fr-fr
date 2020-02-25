---
title: Guide de résolution des problèmes d'intégration de données
description: Cette rubrique fournit des informations sur le dépannage de l'intégration des données entre les applications Finance and Operations et Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 87bdb72024c1c3844ff61e832a92f7edcc77c5d6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019781"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guide de résolution des problèmes d'intégration de données

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Activer les journaux de suivi des plug-ins dans Common Data Service et vérifier les détails d'erreur de plug-in en double écriture

Si vous rencontrez un problème ou une erreur durant la synchronisation en double écriture, procédez comme suit pour examiner les erreurs dans le journal de suivi.

1. Avant de pouvoir examiner les erreurs, vous devez activer les journaux de suivi des plug-ins. Pour obtenir des instructions, voir la section « Afficher les journaux de suivi » du [Didacticiel : Écrire et enregistrer un plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).

    Vous pouvez désormais examiner les erreurs.

2. Connectez-vous à Microsoft Microsoft Dynamics 365 Sales.
3. Sélectionnez le bouton **Paramètres** (le symbole d'engrenage), puis sélectionnez **Paramètres avancés**.
4. Dans le menu  **Paramètres**, choisissez **Personnalisation \> Journal de suivi des plug-ins**.
5. Sélectionnez le nom de type **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** pour afficher les détails de l'erreur.

## <a name="inspect-dual-write-synchronization-errors"></a>Contrôler les erreurs de synchronisation en double écriture

Procédez comme suit pour examiner les erreurs au cours des tests.

1. Connectez-vous à Microsoft Dynamics Lifecycle Services (LCS).
2. Ouvrez le projet LCS pour effectuer le test de double écriture.
3. Sélectionnez **Environnements hébergés dans le cloud**.
4. Établissez une connexion RDP (Remote Desktop Protocol) à l'ordinateur virtuel (VM) de l'application en utilisant le compte local qui s'affiche dans LCS.
5. Ouvrez l'Observateur d'événements. 
6. Accédez à **Journaux des applications et des services \> Microsoft \> Dynamics \> AX-DualWriteSync \> Opérationnel**. Les erreurs et les détails sont affichés.

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a>Supprimer un environnement Common Data Service depuis l'application et lier un autre environnement

Procédez comme suit pour mettre à jour des liens.

1. Accédez à l'environnement d'application.
2. Ouvrez Gestion des données.
3. Sélectionnez **Lien vers CDS for Apps**.
4. Sélectionnez toutes les mises en correspondance qui s'exécutent, puis sélectionnez **Arrêter**.
5. Sélectionnez toutes les mises en correspondance et sélectionnez **Supprimer**.

    > [!NOTE]
    > L'option **Supprimer** n'est pas disponible si le modèle **CustomerV3-Account** est sélectionné. Effacez la sélection de ce modèle, si nécessaire. **CustomerV3-Account** est un modèle anciennement mis en service et fonctionne avec la solution Prospect en disponibilités. Comme il est disponible mondialement, il s'affiche sous tous les modèles.

6. Cliquez sur **Supprimer le lien avec l'environnement**.
7. Sélectionnez **Oui** pour confirmer l'opération.
8. Pour lier le nouvel environnement, suivez les étapes du [guide d'installation](https://aka.ms/dualwrite-docs).
