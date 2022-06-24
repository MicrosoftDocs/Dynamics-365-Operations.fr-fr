---
title: Essayer les unités d’échelle dans une topologie hybride distribuée
description: Cet article fournit des informations sur l’évaluation des unités d’échelle de Cloud et de Edge pour les charges de travail de fabrication et de gestion d’entrepôt.
author: perlynne
ms.date: 05/02/2022
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-03-03
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 5645955109e7a942e617b3b90a27065c2a8fe4a3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893582"
---
# <a name="try-out-scale-units-in-a-distributed-hybrid-topology"></a>Essayer les unités d’échelle dans une topologie hybride distribuée

[!include [banner](../includes/banner.md)]

Le processus d’évaluation de la topologie hybride distribuée est simple. Au cours de la première phase, vous devez valider les personnalisations pour vous assurer qu’elles fonctionnent dans la topologie distribuée. Deux possibilités s’offrent à vous.

## <a name="option-1-evaluate-customizations-in-development-environments"></a>Option 1 : évaluer les personnalisations dans des environnements de développement

Avant de commencer à intégrer vos environnements bac à sable ou de production, nous vous recommandons d’explorer les unités d’échelle dans une configuration de développement, comme un environnement monobloc (également appelé environnement de niveau 1), afin de pouvoir valider les processus, les personnalisations et les solutions. Au cours de cette phase, les données et les personnalisations seront appliquées aux environnements monoblocs. Vous pouvez exécuter sur un environnement unique, qui peut jouer le rôle à la fois de hub d’entreprise et d’unité d’échelle. Sinon, vous pouvez avoir deux environnements de développement, dont l’un joue le rôle de hub et l’autre joue le rôle d’unité d’échelle. Cette configuration constitue le meilleur moyen d’identifier et de résoudre les problèmes. La dernière [version préliminaire](../../fin-ops-core/fin-ops/get-started/one-version.md#how-can-i-get-early-access-to-non-released-platform-updates) peut également être utilisée pour accomplir cette phase.

Vous devez utiliser les [outils de déploiement d’unité d’échelle pour les environnements de développement monoblocs](https://github.com/microsoft/SCMScaleUnitDevTools) pour installer et préserver les environnements. Ces outils vous permettent de configurer le hub et les unités d’échelle dans un ou deux environnements monoblocs. Les outils sont fournis sous forme de version binaire et en code source sur GitHub. Consultez le wiki du projet, qui comprend un [Guide d’utilisation pas à pas](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) qui décrit l’utilisation des outils. Si vous [déployez des unités d’échelle de périphérie sur du matériel personnalisé à l’aide de données d’entreprise locales (LBD)](cloud-edge-edge-scale-units-lbd.md), vous devez suivre un processus différent.

## <a name="option-2-acquire-add-ins-and-deploy-in-your-sandbox-environments"></a>Option 2 : acquérir des compléments et les déployer dans vos environnements bac à sable

Pour tester la topologie hybride distribuée, vous devez disposer de deux environnements sandbox (niveau 2), dont l’un contient vos données (hub d’entreprise) et l’autre est destiné à l’unité d’échelle et contient des « données vides ».

Vous devez acquérir des compléments pour au moins une unité d’échelle cloud ou périphérique. Des créneaux de projet et d’environnement correspondants seront alors attribués dans [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), afin que les environnements d’unités d’échelle puissent être déployés à l’aide du [portail du gestionnaire d’unités d’échelle](https://aka.ms/SCMSUM).

Contactez le support Microsoft pour demander l’activation des environnements sandbox.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
