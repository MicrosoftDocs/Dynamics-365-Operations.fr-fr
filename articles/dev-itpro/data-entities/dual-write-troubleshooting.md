---
title: Guide de résolution des problèmes d'intégration de données
description: Cette rubrique fournit des informations sur le dépannage de l'intégration des données entre Microsoft Dynamics 365 for Finance and Operations et Common Data Service.
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
ms.openlocfilehash: ca62a6b3aa64ec2383ee3ded3b7bbf4650a41166
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797273"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guide de résolution des problèmes d'intégration de données

## <a name="enable-plugin-trace-in-common-data-service-and-check-the-dual-write-plugin-error-details"></a>Activez le traçage de plug-ins dans Common Data Service et vérifiez les détails de l'erreur de plug-in en double écriture

Si vous faites face à un problème ou à une erreur avec la synchronisation en double écriture, vous pouvez examiner les erreurs dans le journal de suivi :

1. Avant de pouvoir examiner les erreurs, vous devez activer le traçage de plug-ins à l'aide de les instructions du [Plug-in de Registre](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) pour activer le traçage de plug-ins. Vous pouvez désormais examiner les erreurs.
2. Connectez-vous à Dynamics 365 for Sales.
3. Cliquez sur l'icône Paramètres (engrenage), et sélectionnez **Paramètres avancés**.
4. Dans le menu **Paramètres**, choisissez **Personnalisation > journal de suivi des plug-ins**.
5. Cliquez sur le nom de type **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** pour afficher les détails de l'erreur.

## <a name="check-dual-write-synchronization-errors-in-finance-and-operations"></a>Vérifier les erreurs de synchronisation en double écriture dans Finance and Operations

Vous pouvez vérifier les erreurs au cours des tests en procédant comme suit :

+ Connectez-vous à LifeCycle Services (LCS).
+ Ouvrez le projet LCS que vous avez choisi pour effectuer le test de double écriture.
+ Accédez aux Environnements hébergés dans le cloud.
+ Machine virtuelle de Bureau à distance vers Finance and Operations à l'aide du compte local qui s'affiche dans LCS.
+ Ouvrez la visionneuse d'événements. 
+ Accédez à **Journaux des applications et des services > Microsoft > Dynamics > AX-DualWriteSync > Opérationnel**. Les erreurs et les détails sont affichés.

## <a name="how-to-unlink-and-link-another-common-data-service-environment-from-finance-and-operations"></a>Procédure pour supprimer un lien et lier un autre environnement Common Data Service avec Finance and Operations

Vous pouvez mettre à jour les liens en procédant comme suit :

+ Accédez à l'environnement Finance and Operations.
+ Ouvrez Gestion des données.
+ Cliquez sur **Lien vers CDS for Apps**.
+ Sélectionnez toutes les mises en correspondance en cours d'exécution et cliquez sur **Arrêter**. 
+ Sélectionnez toutes les mises en correspondance et cliquez sur **Supprimer**.

    > [!NOTE]
    > L'option **Supprimer** ne s'affiche pas si le modèle **CustomerV3-Account** est sélectionné. Désactivez-le si nécessaire. **CustomerV3-Account** est un modèle anciennement mis en service et fonctionne avec la solution Prospect en disponibilités. Comme il est disponible mondialement, il s'affiche sous tous les modèles.

+ Cliquez sur **Supprimer le lien avec l'environnement**.
+ Cliquez sur **Oui** pour confirmer.
+ Pour lier le nouvel environnement, suivez les étapes du [guide d'installation](https://aka.ms/dualwrite-docs).

