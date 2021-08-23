---
title: Configuration en double écriture depuis Lifecycle Services
description: Cette rubrique explique comment configurer une connexion de double écriture à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 060734154607263b5fed80b21fc9355b513ea26e3b1be88498310905531dceaa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6729041"
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

Suivez ces étapes pour configurer la double écriture depuis la page **Détails de l’environnement** de LCS :

1. Dans la page **Détails de l’environnement**, développez la section **Intégration de Power Platform**.

2. Sélectionnez le bouton **Application de double écriture**.

    ![Intégration à Power Platform.](media/powerplat_integration_step2.png)

3. Passez en revue les conditions générales, puis sélectionnez **Configurer**.

4. Cliquez sur **OK** pour continuer.

5. Vous pouvez surveiller la progression en actualisant régulièrement la page des détails de l’environnement. La configuration prend généralement 30 minutes au maximum.  

6. Une fois la configuration terminée, un message vous informera si le processus a réussi ou échoué. Si la configuration a échoué, un message d’erreur associé s’affiche. Vous devez corriger les erreurs avant de passer à l’étape suivante.

7. Sélectionnez **Lier à l’environnement Power Platform** pour créer un lien entre Dataverse et les bases de données de l’environnement actuel. Cette opération prend généralement moins de 5 minutes.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Lier à l’environnement Power Platform.":::

8. Une fois la liaison terminée, un lien hypertexte s’affiche. Utilisez le lien pour vous connecter à la zone d’administration de la double écriture dans l’environnement Finance and Operations. À partir de là, vous pouvez configurer les mappages d’entités.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Configurer la double écriture pour un environnement Dataverse existant

Pour configurer la double écriture pour un environnement Dataverse existant, vous devez créer un [ticket de support](../../lifecycle-services/lcs-support.md) Microsoft. Le ticket doit inclure :

+ L’ID de votre environnement Finance and Operations.
+ Le nom de votre environnement dans Lifecycle Services.
+ L’ID de l’organisation Dataverse ou l’ID de l’environnement Power Platform dans le centre d’administration de Power Platform. Dans votre ticket, demandez que l’ID soit l’instance utilisée pour l’intégration de Power Platform.

> [!NOTE]
> Vous ne pouvez pas dissocier des environnements à l’aide de LCS. Pour dissocier un environnement, ouvrez l’espace de travail **Intégration des données** dans l’environnement Finance and Operations, puis sélectionnez **Dissocier**.

## <a name="linking-mismatch"></a>Incompatibilité de liaison

Il est possible que votre environnement LCS soit lié à une instance Dataverse, tandis que votre environnement à double écriture est lié à une autre instance Dataverse. Cette incompatibilité de liaison peut provoquer un comportement inattendu et entraîner l’envoi de données au mauvais environnement. L’environnement qu’il est recommandé d’utiliser pour la double écriture est celui qui est créé dans le cadre de l’intégration Power Platform et, à long terme, ce sera le seul moyen d’établir un lien entre les environnements.

Si votre environnement présente une incompatibilité de liaison, LCS affiche un avertissement sur la page des détails de votre environnement semblable à « Microsoft a détecté que votre environnement est lié par la double écriture à une destination différente de celle spécifiée dans l’intégration Power Platform, ce qui n’est pas recommandé » :

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform lien d’intégration incompatible.":::

Si vous rencontrez cette erreur, deux options s’offrent à vous, en fonction de vos besoins :

+ [Dissocier et relier les environnements à double écriture (réinitialiser ou modifier la liaison)](relink-environments.md#scenario-reset-or-change-linking) comme spécifié sur la page des détails de votre environnement LCS. Il s’agit de l’option idéale, car vous pouvez l’exécuter sans le Support Microsoft.  
+ Si vous souhaitez conserver votre lien en double écriture, vous pouvez demander l’aide du Support Microsoft pour modifier l’intégration Power Platform afin d’utiliser votre environnement Dataverse tel que documenté dans la section précédente.  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
