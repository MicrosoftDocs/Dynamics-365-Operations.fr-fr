---
title: Paramétrer Operational Insights
description: Cet article explique comment configurer et utiliser la fonctionnalité Operational Insights dans Microsoft Dynamics 365 Commerce.
author: ashishMSFT
ms.date: 12/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: ca0d31e403275d6131fa6d53f0a7b46a7ddb651d
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832125"
---
# <a name="set-up-operational-insights"></a>Paramétrer Operational Insights

[!include [banner](../includes/banner.md)]

Cet article explique comment configurer et utiliser la fonctionnalité Operational Insights dans Microsoft Dynamics 365 Commerce.

Operational Insights est une fonctionnalité Dynamics 365 Commerce conçue pour donner aux clients une meilleure visibilité sur l’état de leur service et leurs fonctionnalités commerciales en envoyant la télémétrie directement à un compte client Application Insights .

En activant Operational Insights pour vos environnements Commerce headquarters, vous pouvez collecter une liste organisée d’événements à partir de Commerce Scale Unit (CSU) et de vos appareils de point de vente (PDV). Ces événements peuvent vous aider à mieux comprendre les performances de vos systèmes et vous permettent de surveiller les principales mesures techniques et commerciales.

Même si vous ne souhaitez pas collecter cette télémétrie tout le temps, vous pouvez bénéficier d’une activation ou d’une désactivation rapide de la collecte pour des environnements spécifiques. De cette manière, la télémétrie peut vous aider à dépanner ou à déboguer pendant le développement ou en production.

## <a name="access-logs-in-application-insights"></a>Accéder aux journaux Application Insights

Pour accéder aux journaux d’événements de diagnostic pour les composants Commerce CSU et PDV via Application Insights, suivez les procédures de cette section.

### <a name="minimum-version-requirements-for-csu"></a>Configuration minimale de la version requise pour CSU

CSU a les exigences de version minimales suivantes :

- 10.0.23 (version Retail Server 9.33.22062.15 et versions ultérieures)
- 10.0.24 (version Retail Server 9.34.22062.14 et versions ultérieures)
- 10.0.25 (version Retail Server 9.35.22062.13 et versions ultérieures)
- 10.0.26 et ultérieures (toutes versions)

### <a name="enable-diagnostic-events-in-application-insights"></a>Activer les événements de diagnostic dans Application Insights

> [!IMPORTANT]
> Si vous utilisiez auparavant une version préliminaire d’Operational Insights, vous devez utiliser la procédure suivante pour activer Operational Insights. De cette façon, vous vous assurez que l’accès fiable et sécurisé aux événements peut continuer.

Pour activer les événements de diagnostic du composant Commerce, vous devez disposer d’un compte Application Insights. Vous pouvez utiliser un compte existant ou [créer un compte](/azure/azure-monitor/app/create-workspace-resource#create-workspace-based-resource). Pour des raisons de confidentialité des données, nous vous recommandons d’utiliser des comptes distincts Application Insights pour les environnements de production, de bac à sable et de développement. Après avoir créé un compte, vous devez activer la fonctionnalité **Operational Insights** au siège.

Pour activer les événements de diagnostic dans Application Insights, suivez ces étapes.

1. Au siège, ouvrez l’espace de travail **Gestion des fonctionnalités** et activez la fonctionnalité **Operational Insights**.
1. Accédez à **Administration système \> Paramétrage \> Operational Insights**.
1. Dans l’onglet **Configurer**, définissez l’option **Événements du canal Commerce** sur **Oui**.
1. Dans l’onglet **Environnements**, saisissez des valeurs **ID d’environnement LCS** et **Mode d’environnement** pour chaque environnement dans lequel vous prévoyez d’utiliser Application Insights. Vous pouvez trouver l’ID d’environnement de chaque environnement sur la page **Détails de l’environnement** pour cet environnement dans Microsoft Dynamics Lifecycle Services. Cette étape est requise pour éviter que des événements de diagnostic ne soient envoyés par inadvertance à un environnement incorrect lors de l’exécution d’opérations de copie de base de données.
1. Dans l’onglet **Registre Application Insights**, spécifiez la valeur **clé d’instrumentation** Application Insights et le **Mode d’environnement** correspondant des environnements dans lesquels vous prévoyez d’utiliser chaque compte Application Insights.
1. Une fois que vous avez terminé la configuration précédente, vous devez exécuter la tâche **CDX Job 1110**. Vous pouvez attendre que cette tâche s’exécute selon sa propre planification ou vous pouvez l’exécuter manuellement.
1. Dans Lifecycle Services, accédez à **Détails de l’environnement \> Commerce \> Gérer**, sélectionnez une instance CSU, puis sélectionnez **Redémarrer**. Répétez cette étape pour chaque CSU.
1. Répétez les étapes précédentes pour chaque environnement que vous prévoyez d’utiliser Application Insights.

> [!NOTE]
> - Les événements de télémétrie dans Operational Insights sont susceptibles d’être modifiés. Nous vous recommandons d’utiliser les événements Operational Insights pour effectuer vous-même une analyse préliminaire et un dépannage, et non pour définir des tableaux de bord ou des alertes. Si vous utilisez des événements à des fins autres que la résolution des problèmes en libre-service, nous vous recommandons de valider et de mettre à jour vos requêtes après chaque version CSU/POS.
> - Depuis la version 10.0.29 de Commerce, les procédures de cette section permettent également la diffusion en continu des événements Operational Insights du PDV sur votre compte Application Insights. Pour plus d’informations, consultez [Operational Insights pour le PDV – Événements et requêtes](https://download.microsoft.com/download/9/2/b/92be35b0-0e24-4a4d-940d-6f4db29791c0/Operational-Insights-Commerce-POS-events-queries.pdf).

#### <a name="use-the-dllhostexeconfig-file-to-control-pos-operational-insights-events"></a>Utilisez le fichier DLLHost.exe.config pour contrôler les événements Operational Insights du PDV

Pour utiliser le fichier DLLHost.exe.config pour contrôler les événements Operational Insights du PDV, procédez comme suit.

1. Dans un éditeur de texte, ouvrez le **DLLHost.exe.config** fichier sur **C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\Retail Modern POS\\Courtierclient**.
1. Dans la section **diagnosticsSection**, supprimez l’élément XML récepteur qui porte le nom de classe **Microsoft.Dynamics.Retail.Diagnostics.OperationalInsights.OperationalInsightsLogger**.
1. Enregistrer le fichier.

### <a name="disable-diagnostic-events-in-application-insights"></a>Désactiver les événements de diagnostic dans Application Insights

> [!IMPORTANT]
> Si vous souhaitez désactiver les événements de diagnostic et ne plus les envoyer à Application Insights, vous devez effectuer la procédure suivante. Vous pouvez désactiver cette fonctionnalité en version préliminaire dans Gestion des fonctionnalités.

Pour désactiver les événements de diagnostic dans Application Insights, suivez ces étapes.

1. Dans le siège, accédez à **Administration système \> Operational Insights**.
1. Dans l’onglet **Configurer**, définissez l’option **Événements du canal Commerce** sur **Non**.
1. Une fois que vous avez terminé la configuration précédente, vous devez exécuter la tâche **CDX Job 1110**. Vous pouvez attendre que cette tâche s’exécute selon sa propre planification ou vous pouvez exécuter la tâche manuellement.
1. Dans Lifecycle Services, accédez à **Détails de l’environnement \> Commerce \> Gérer**, sélectionnez une instance CSU, puis sélectionnez **Redémarrer**. Répétez cette étape pour chaque CSU.
1. Répétez les étapes précédentes pour chaque environnement que vous prévoyez de mettre désactiver Application Insights.

Pour désactiver les événements de diagnostic pour un seul environnement, supprimez la clé d’instrumentation dans l’onglet **registre Application Insights** de la page **Operational Insights**. Effectuez ensuite les étapes 3 et 4 de la procédure précédente.

> [!NOTE]
> Dans la version 10.0.29 de Commerce et ultérieure, les étapes de cette section permettent également de désactiver la diffusion en continu des événements Operational Insights du PDV sur votre compte Application Insights. 
