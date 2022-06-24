---
title: Configuration en double écriture depuis Lifecycle Services
description: Cet article explique comment configurer une connexion de double écriture à partir de Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 05/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 5cccba580d23c3a0e9aed62f76a305926a58585f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879802"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configuration en double écriture depuis Lifecycle Services

[!include [banner](../../includes/banner.md)]



Cet article explique comment activer la double écriture depuis Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Conditions préalables

Les clients doivent terminer l’intégration de Power Platform comme décrit dans les rubriques suivantes :

- Si vous n’utilisez pas encore Microsoft Power Platform et souhaitez étendre vos environnements Finance et Opérations en ajoutant des fonctionnalités de plateforme, consultez [Intégration Power Platform - Activer pendant le déploiement de l’environnement](../../power-platform/enable-power-platform-integration.md#enable-during-deploy).
- Si vous avez déjà Dataverse et Power Platform et que vous souhaitez les connecter aux environnements Finance et Opérations, consultez [Intégration Power Platform - Activer après le déploiement de l’environnement](../../power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="set-up-dual-write-for-new-or-existing-dataverse-environments"></a>Configurer la double écriture pour des environnements Dataverse nouveaux ou existants

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

8. Une fois la liaison terminée, un lien hypertexte s’affiche. Utilisez le lien pour vous connecter à la zone d’administration de la double écriture dans l’environnement Finances et Opérations. À partir de là, vous pouvez configurer les mappages d’entités.

## <a name="linking-mismatch"></a>Incompatibilité de liaison

Il est possible que votre environnement à double écriture soit lié à une instance Dataverse alors que LCS n’est pas configuré pour l’intégration Power Platform. Cette incompatibilité de liaison peut entraîner un comportement inattendu. Il est recommandé que les détails de l’environnement LCS correspondent à ce à quoi vous êtes connecté en double écriture afin que la même connexion puisse être utilisée par les événements métier, les tables virtuelles et les compléments.

Si votre environnement présente une incompatibilité de liaison, LCS affichera un avertissement qui ressemble à l’exemple suivant sur la page des détails de votre environnement : « Microsoft a détecté que votre environnement est lié par la double écriture à une destination différente de celle spécifiée dans l’intégration Power Platform, ce qui n’est pas recommandé » :

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Power Platform lien d’intégration incompatible.":::

Si vous recevez cet avertissement, essayez l’une des solutions suivantes :

- Si votre environnement LCS n’a jamais été configuré pour l’intégration Power Platform, vous pouvez vous connecter à l’instance Dataverse qui est configurée en double écriture en suivant les instructions de cet article.
- Si votre environnement LCS est déjà configuré pour l’intégration Power Platform, vous devez dissocier la double écriture et la reconnecter à celle spécifiée par LCS à l’aide du [Scénario : Réinitialiser ou modifier l’association](relink-environments.md#scenario-reset-or-change-linking).

Dans le passé, une option de ticket d’assistance manuelle était disponible, mais c’était avant l’existence de l’option 1 ci-dessus.  Microsoft ne prend plus en charge les demandes de réassociation manuelle via les tickets de support.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
