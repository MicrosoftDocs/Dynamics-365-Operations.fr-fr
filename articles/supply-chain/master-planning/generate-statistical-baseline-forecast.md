---
title: Générer des prévisions de base statistiques
description: Cette rubrique fournit des informations sur les paramètres et les filtres utilisés dans le calcul de prévision de la demande.
author: roxanadiaconu
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4bc5a38519efb6f4d242daca9aab5226c16e4ea0
ms.sourcegitcommit: 3be8d2be6474264f0a530a052d19ea2635e269cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/08/2019
ms.locfileid: "1729873"
---
# <a name="generate-a-statistical-baseline-forecast"></a>Générer des prévisions de base statistiques

[!include [banner](../includes/banner.md)]

Cette rubrique fournit des informations sur les paramètres et les filtres utilisés dans le calcul de prévision de la demande. 

Lorsque vous créez une prévision de base, vous devez d'abord spécifier les paramètres et les filtres utilisés dans le calcul. Par exemple, vous pouvez créer une prévision de base qui estime la demande selon les données de transaction de l'année précédente pour une société spécifique, pour le mois à provenir, et pour un groupe d'articles sélectionné. 

Pour générer une prévision de la demande, allez dans **Planification &gt; Prévisions &gt; Prévision de la demande &gt; Générer des prévisions de base statistiques**. 

L'intervalle de prévision peut être sélectionné au moment de la génération de prévision. Les valeurs disponibles sont : jour, semaine et mois. 

Le nombre d'intervalles pour lesquels générer une prévision se définit dans le champ **Horizon de prévision**. 

Lorsque la stratégie de prévision est définie sur **Copier sur la demande historique**, la fin de l'horizon historique est ignorée. Le système copie le nombre d'intervalles spécifiés dans le champ **Horizon de prévision** de la demande de prévision, en commençant par la date définie dans le champ **Date de début** sous **Horizon historique**. En copiant une demande historique à partir d'une certaine date, les responsables de production peuvent effectuer le plan pour le trimestre suivant de deux manières :

-   En copiant la demande du même trimestre de l'année dernière.
-   En copiant la demande du trimestre précédent.

Pour empêcher toute confusion dans les calendriers de production, un certain nombre d'intervalles de prévision peuvent être figés. Ce nombre est défini dans le champ **Plage de temps bloquée**. Dans la page **Ajustement de la prévision de demande**, les cellules pour les intervalles figés sont désactivées, pour donner une indication visuelle que ces valeurs ne doivent pas être modifiées. 

La date de début de la prévision de la demande de base ne doit pas être la date du jour ou une date dans le futur. Pour définir une date de début différente, utilisez le champ **Date de début de prévision de base - Date de début**. Par exemple, en juin, les utilisateurs peuvent générer une prévision pour l'année suivante. Étant donné que les intervalles de prévision entre la fin d'une demande historique et le début de la base sont manquants, il se peut que les prévisions ne soient pas précises. Si vous utilisez le service de prévision de la demande de Microsoft Dynamics 365 for Finance and Operations, il existe quatre méthodes qui permettent de combler les écarts manquants. Vous pouvez sélectionner la méthode que vous souhaitez en définissant le paramètre MISSING\_VALUE\_SUBSTITUTION dans la page **Paramètres de prévision de la demande**. 

> [!NOTE]
> Le remplacement des valeurs manquantes ne fonctionne que pour les lacunes de données entre les dates de début et de fin des données historiques. Cela ne remplit pas les données avant ou après le dernier point d'information physique. Cela ne procède que par extrapolation entre points d'informations existants réels. 

Le champ **Date de début de prévision de base** - **Date de début** doit être défini au début d'un intervalle de prévision, par exemple, aux États-unis, un dimanche si l'intervalle de prévision est la semaine. Le système règle automatiquement le champ **Date de début de prévision de base** - **Date de début** pour correspondre au début d'un intervalle de prévision. 

Le champ **Date de début de prévision de base** - **Date de début** peut être réglé sur une date passée. Autrement dit, il est possible de générer une prévision de la demande dans le passé. Cela est utile pour permettre aux utilisateurs d'ajuster les paramètres du service de prévision afin que la prévision statistique générée dans le passé corresponde à la demande réelle historique. Les utilisateurs peuvent alors continuer à utiliser ces paramètres pour générer des prévisions de base statistiques pour L'avenir. 

Les ajustements manuels effectués dans les itérations précédentes de prévision de la demande peuvent être automatiquement appliqués à la nouvelle prévision de base si la case à cocher **Transfert des ajustements manuels dans la prévision de la demande** est activée. Si la case à cocher est désactivée, les ajustements manuels ne sont pas ajoutés à la prévision de base, mais ils ne sont pas supprimés. Les ajustements manuels apportés à une prévision peuvent être supprimés uniquement au moment de l'importation de la prévision, en désactivant la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base**. Les ajustements manuels sont enregistrés au moment de l'autorisation. Par conséquent, si un utilisateur effectue des ajustements manuels sur la prévision, mais n'autorise pas la prévision sur Finance and Operations, les modifications sont perdues. Pour plus d'informations sur les ajustements manuels et leur fonctionnement, voir [Autorisation de la prévision ajustée](authorize-adjusted-forecast.md). 

Une génération de prévision de la demande peut avoir un nom et des commentaires pour aider les utilisateurs à identifier la prévision générée. Ces valeurs sont visibles dans l'historique de génération de prévisions dans la page **Enregistrer les ajustements manuels apportés à la prévision de la demande de base**. 

Le groupe d'organisation intersociétés, les clés de répartition par article, ainsi que d'autres filtres peuvent être appliqués au moment de la génération de prévision. Ceux-ci peuvent être utilisés pour améliorer les performances ou pour fractionner les données en segments maniables. Toutefois, notez qu'une prévision de la demande n'est pas générée pour les membres d'une clé de répartition par article qui n'est pas associée à un groupe d'organisation intersociétés, même si cette clé de répartition par article est sélectionnée dans la requête. 

> [!TIP]
> Il arrive parfois que les utilisateurs reçoivent des erreurs lors de la génération d'une prévision de la demande, ou que la génération de prévision soit exécutée sans journal de session. Cela peut se produire en raison de données restantes dans la requête qui ont été précédemment utilisées pour la génération de prévision. Pour résoudre ce problème, cliquez sur **Sélectionner** pour ouvrir la page **Requête**, sélectionnez **Réinitialiser**, puis régénérez la prévision de base. 

Si la prévision n'est pas générée pour un grand ensemble d'articles, mais, par exemple, pour un article ou une clé de répartition par article à la fois, alors afin d'obtenir de meilleures performances, vous pouvez activer la case à cocher **Utilisation du mode de réponse aux requêtes** sous l'onglet **Planification - Paramétrage - Prévision de la demande** - **Paramètres de prévision de la demande - Azure Machine Learning**.

> [!NOTE]
> Éventuellement, une prévision apparemment plate peut découler de données historiques qui ne couvrent pas une durée suffisante (au minimum, 3 périodes pour déceler des modèles, comme 3 ans pour des prévisions mensuelles). Pour obtenir un meilleur résultat, vous pouvez essayer de modifier la granularité de la plage temporelle, ou d'augmenter cette plage.

<a name="additional-resources"></a>Ressources supplémentaires
--------

- [Paramétrage de la prévision de la demande](demand-forecasting-setup.md)

- [Effectuer des ajustements manuels sur la prévision de base](manual-adjustments-baseline-forecast.md)

- [Autorisation de la prévision ajustée](authorize-adjusted-forecast.md)
