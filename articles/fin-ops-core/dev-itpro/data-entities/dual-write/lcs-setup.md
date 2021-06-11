---
title: Configuration en double écriture depuis Lifecycle Services
description: Cette rubrique explique comment configurer une connexion de double écriture à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
ms.date: 05/11/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: eb4170ef6cb09c862f6a4163670c519d5d8077fb
ms.sourcegitcommit: 365092f735310990e82516110141d42aaf04e654
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "6103567"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuration en double écriture depuis Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cette rubrique explique comment activer la double écriture depuis Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Conditions préalables

Vous devez terminer l’intégration de Power Platform comme décrit dans les rubriques suivantes :

+ [Intégration de Power Platform - Activer pendant le déploiement de l’environnement](../../power-platform/overview.md#enable-during-environment-deployment)
+ [Intégration de Power Platform - Configurer après le déploiement de l’environnement](../../power-platform/overview.md#set-up-after-environment-deployment)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Configurer la double écriture pour les nouveaux environnements Dataverse

Suivez ces étapes pour configurer la double écriture depuis la page **Détails de l'environnement** de LCS :

1. Dans la page **Détails de l’environnement**, développez la section **Intégration de Power Platform**.

2. Sélectionnez le bouton **Application de double écriture**.

    ![Intégration de Power Platform](media/powerplat_integration_step2.png)

3. Passez en revue les conditions générales, puis sélectionnez **Configurer**.

4. Cliquez sur **OK** pour continuer.

5. Vous pouvez surveiller la progression en actualisant régulièrement la page des détails de l’environnement. La configuration prend généralement 30 minutes au maximum.  

6. Une fois la configuration terminée, un message vous informera si le processus a réussi ou échoué. Si la configuration a échoué, un message d’erreur associé s’affiche. Vous devez corriger les erreurs avant de passer à l’étape suivante.

7. Sélectionnez **Lier à l’environnement Power Platform** pour créer un lien entre Dataverse et les bases de données de l’environnement actuel. Cette opération prend généralement moins de 5 minutes.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Lier à l’environnement Power Platform":::

8. Une fois la liaison terminée, un lien hypertexte s’affiche. Utilisez le lien pour vous connecter à la zone d’administration de la double écriture dans l’environnement Finance and Operations. À partir de là, vous pouvez configurer les mappages d’entités.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Configurer la double écriture pour un environnement Dataverse existant

Pour configurer la double écriture pour un environnement Dataverse existant, vous devez créer un [ticket de support](../../lifecycle-services/lcs-support.md) Microsoft. Le ticket doit inclure :

+ L’ID de votre environnement Finance and Operations.
+ Le nom de votre environnement dans Lifecycle Services.
+ L’ID de l’organisation Dataverse ou l’ID de l’environnement Power Platform dans le centre d’administration de Power Platform. Dans votre ticket, demandez que l’ID soit l’instance utilisée pour l’intégration de Power Platform.

> [!NOTE]
> Vous ne pouvez pas dissocier des environnements à l’aide de LCS. Pour dissocier un environnement, ouvrez l’espace de travail **Intégration des données** dans l’environnement Finance and Operations, puis sélectionnez **Dissocier**.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
