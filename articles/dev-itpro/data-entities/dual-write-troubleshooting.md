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
ms.openlocfilehash: 5e71729dafd2ad85a01b055363d1c7056b5558b2
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873103"
---
# <a name="troubleshooting-guide-for-data-integration"></a>Guide de résolution des problèmes d'intégration de données

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Activer les journaux de suivi des plug-ins dans Common Data Service et vérifier les détails d'erreur de plug-in en double écriture

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Si vous rencontrez un problème ou une erreur durant la synchronisation en double écriture, procédez comme suit pour examiner les erreurs dans le journal de suivi.

1. Avant de pouvoir examiner les erreurs, vous devez activer les journaux de suivi des plug-ins. Pour obtenir des instructions, voir la section « Afficher les journaux de suivi » du [Didacticiel : Écrire et enregistrer un plug-in](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs).

    Vous pouvez désormais examiner les erreurs.

2. Connectez-vous à Microsoft Dynamics 365 for Sales.
3. Sélectionnez le bouton **Paramètres** (le symbole d'engrenage), puis sélectionnez **Paramètres avancés**.
4. Dans le menu  **Paramètres**, choisissez **Personnalisation \> Journal de suivi des plug-ins**.
5. Sélectionnez le nom de type **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** pour afficher les détails de l'erreur.

## <a name="inspect-dual-write-synchronization-errors-in-finance-and-operations"></a>Vérifier les erreurs de synchronisation en double écriture dans Finance and Operations

Procédez comme suit pour examiner les erreurs au cours des tests.

1. Connectez-vous à Microsoft Dynamics Lifecycle Services (LCS).
2. Ouvrez le projet LCS pour effectuer le test de double écriture.
3. Sélectionnez **Environnements hébergés dans le cloud**.
4. Établissez une connexion RDP (Remote Desktop Protocol) à l'ordinateur virtuel (VM) Dynamics 365 for Finance and Operations en utilisant le compte local qui s'affiche dans LCS.
5. Ouvrez l'Observateur d'événements. 
6. Accédez à **Journaux des applications et des services \> Microsoft \> Dynamics \> AX-DualWriteSync \> Opérationnel**. Les erreurs et les détails sont affichés.

## <a name="unlink-one-common-data-service-environment-from-finance-and-operations-and-link-another-environment"></a>Supprimer un environnement Common Data Service de Finance and Operations et lier un autre environnement

Procédez comme suit pour mettre à jour des liens.

1. Accédez à l'environnement Finance and Operations.
2. Ouvrez Gestion des données.
3. Sélectionnez **Lien vers CDS for Apps**.
4. Sélectionnez toutes les mises en correspondance qui s'exécutent, puis sélectionnez **Arrêter**.
5. Sélectionnez toutes les mises en correspondance et sélectionnez **Supprimer**.

    > [!NOTE]
    > L'option **Supprimer** n'est pas disponible si le modèle **CustomerV3-Account** est sélectionné. Effacez la sélection de ce modèle, si nécessaire. **CustomerV3-Account** est un modèle anciennement mis en service et fonctionne avec la solution Prospect en disponibilités. Comme il est disponible mondialement, il s'affiche sous tous les modèles.

6. Cliquez sur **Supprimer le lien avec l'environnement**.
7. Sélectionnez **Oui** pour confirmer l'opération.
8. Pour lier le nouvel environnement, suivez les étapes du [guide d'installation](https://aka.ms/dualwrite-docs).
