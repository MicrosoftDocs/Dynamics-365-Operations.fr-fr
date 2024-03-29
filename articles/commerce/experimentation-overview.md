---
title: Expérimentation dans Dynamics 365 Commerce
description: L’expérimentation permet la création, la modification et la gestion des traitements des dispositions des pages et du contenu dans le générateur de site. La prise en charge de l’expérimentation de bout en bout est activée pour les pages et les entités e-commerce au sein d’une page.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: overview
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1ef877072ba7ffe1b0326cf8d526b512b5ab30b8
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946202"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Expérimentation dans Dynamics 365 Commerce
Utiliser l’expérimentation dans Dynamics 365 Commerce pour valider des hypothèses sur l’efficacité de vos pages e-commerce et prendre des décisions en vous basant sur les données. Commerce prend en charge les tests A/B sur les pages, les modules et les fragments, et vous permet de mesurer l’impact des modifications proposées sur votre site web.

Vous pouvez créer, modifier et gérer les traitements de page et de contenu appelés **variantes** dans le générateur de site Commerce. Commerce s’intègre à des services tiers que vous pouvez utiliser pour créer des expériences et des affectations de traitement. Les flux d’événements en temps réel capturés dans Commerce activent les analyses qui définissent les résultats de l’expérience dans le service tiers. Vous pouvez ensuite tirer parti de ces analyses pour aider à soutenir ou à réfuter votre hypothèse.

## <a name="set-up-prerequisites"></a>Paramétrage des conditions préalables

1. **Obtenir la version appropriée de Commerce** - Mettez à niveau votre bibliothèque de modules, le kit de développement logiciel (SDK) d’extensibilité de canal en ligne et Commerce Scale Unit vers la version Commerce 10.0.13 ou une version ultérieure.
1. **Configurer un connecteur d’expérimentation** - Un connecteur d’expérimentation permet à Commerce de se connecter à des services tiers pour récupérer la liste des expériences et déterminer quand montrer une expérience à un utilisateur. Vous pouvez acheter un connecteur tiers auprès de [AppSource](https://appsource.microsoft.com). Suivez les instructions de configuration fournies par l’éditeur. Vous pouvez également utiliser l’exemple de connecteur de test de Commerce pour tester le flux de travail d’expérimentation sans avoir besoin de configurer un service externe. Pour plus d’informations, consultez [Configurer et activer les connecteurs](e-commerce-extensibility/connectors.md). 
1. **Activer l'indicateur de fonctionnalité d’expérimentation dans Commerce** - Vous pouvez activer l’expérimentation au niveau du client en accédant à **Paramètres du client \> Fonctionnalités** ou au niveau du site en accédant à **Paramètres du site \> Fonctionnalités**. Activez l'indicateur **Expérimentation** pour commencer à créer des variantes de module. Si vous désactivez cet indicateur, cela empêche l’affichage de toutes les expériences aux utilisateurs et supprime toutes les fonctions d’édition dans le générateur de site.
    
## <a name="experimentation-lifecycle"></a>Cycle de vie de l’expérimentation

Configurer une expérience, créer des variantes et exécuter une expérience est un processus itératif. Le diagramme ci-dessous illustre le cycle de vie de l’expérimentation dans Commerce et le service tiers. 

[ ![Cycle de vie de l’expérimentation.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Pour en savoir plus sur chaque étape du processus d’expérimentation, reportez-vous aux articles suivants.
- [Identifier une hypothèse et déterminer les métriques pour une expérience](experimentation-identify.md)
- [Paramétrer une expérience](experimentation-setup.md)
- [Connecter et modifier une expérience](experimentation-connect-edit.md)
- [Prévisualiser et publier une expérience](experimentation-preview-publish.md)
- [Exécuter et surveiller une expérience](experimentation-run-monitor.md)
- [Promouvoir une variante et terminer une expérience](experimentation-review-complete.md)

> [!NOTE]
> Pour savoir où se situe une expérience dans le cycle de vie, sélectionnnez **Expériences** dans le volet de navigation de gauche du générateur de site. Une liste d’expériences s’affiche avec l’état de chaque expérience dans Commerce et dans le service tiers. Pour plus d’informations, consultez [Examiner l’état d’une expérience](experimentation-status.md).

## <a name="next-step"></a>Étape suivante
[Identifier une hypothèse et déterminer les métriques de réussite pour une expérience](experimentation-identify.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
