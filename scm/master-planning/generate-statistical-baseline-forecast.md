---
title: "Générez des prévisions de base statistiques"
description: "Cet article fournit des informations sur les paramètres et les filtres utilisés dans le calcul de prévision de la demande."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c0c918b94fe96d123bb6c25c42fe168a026cd8a9
ms.lasthandoff: 03/31/2017


---

# <a name="generate-a-statistical-baseline-forecast"></a>Générez des prévisions de base statistiques

Cet article fournit des informations sur les paramètres et les filtres utilisés dans le calcul de prévision de la demande. 

Lorsque vous créez une prévision de base, vous devez d'abord spécifier les paramètres et les filtres utilisés dans le calcul. Par exemple, vous pouvez créer une prévision de base qui estime la demande selon les données de transaction de l'année précédente pour une société spécifique, pour le mois à provenir, et pour un groupe d'articles sélectionné. 

Pour générer une prévision de la demande, allez dans ** la &gt; prévision de la demande de prévisions &gt; de planification &gt; générer des prévisions de base statistiques **. 

L'intervalle de prévision peut être sélectionné au moment de la génération de prévision. Les valeurs disponibles sont : jour, semaine et mois. 

Le nombre d'intervalles pour lesquels générer une prévision se définit dans le champ **Horizon de prévision**. 

Lorsque la stratégie de prévision est définie sur **Copier sur la demande historique**, la fin de l'horizon historique est ignorée. Le système copie le numéro de plages spécifiées dans la ** de prévision ** le champ à la demande prévue, en commençant par la date définie dans ** de la date ** le champ sous ** la historique **. En copiant une demande historique à partir d'une certaine date, les responsables de production peuvent effectuer le plan pour le trimestre suivant de deux manières :

-   En copiant la demande du même trimestre de l'année dernière.
-   En copiant la demande du trimestre précédent.

Pour empêcher toute confusion dans les calendriers de production, un certain nombre d'intervalles de prévision peuvent être figés. Ce nombre est défini dans le champ **Plage de temps bloquée**. Dans la page **Ajustement de la prévision de demande**, les cellules pour les intervalles figés sont désactivées, pour donner une indication visuelle que ces valeurs ne doivent pas être modifiées. 

La date de début de la prévision de la demande de base ne doit pas être la date du jour ou une date dans le futur. Pour définir une date de début différente, utilisez le champ **Date de début de prévision de base - Date de début**. Par exemple, en juin, les utilisateurs peuvent générer une prévision pour l'année suivante. Étant donné que les intervalles de prévision entre la fin d'une demande historique et le début de la base sont manquants, il se peut que les prévisions ne soient pas précises. Si vous utilisez Microsoft Dynamics 365 pour le service de prévision de la demande d'opérations, quatre façons dans lesquelles vous pouvez combler les écarts manquantes. Vous pouvez choisir la méthode que vous souhaitez en définissant le paramètre MANQUANT de SUBSTITUTION d'\_de VALEUR d'\_sur ** des paramètres de prévision de la demande ** la page. 

** Date de début de prévision de base ** - ** de la date ** champ doit être défini au début de la plage de prévision, par exemple, aux États-Unis, un dimanche si la plage de prévision est la semaine. Le système ajuste automatiquement ** date de début de prévision de base ** - ** de la date ** champ pour correspondre au début d'une plage de prévision. 

** Date de début de prévision de base ** - ** de la date ** champ peut être réglé pour une date dans dans le passé. Autrement dit, il est possible de générer une prévision de la demande dans le passé. Cela est utile pour permettre aux utilisateurs de corriger les paramètres du service de prévision afin que la prévision statistique générée dans le passé corresponde à la demande réelle historique. Les utilisateurs peuvent alors continuer à utiliser ces paramètres pour générer des prévisions de base statistiques pour L'avenir. 

Les ajustements manuels effectués dans les itérations précédentes de prévision de la demande peuvent être automatiquement appliqués à la nouvelle prévision de base si la case à cocher **Transfert des ajustements manuels dans la prévision de la demande** est activée. Si la case à cocher est désactivée, les ajustements manuels ne sont pas ajoutés à la prévision de base, mais ils ne sont pas supprimés. Les ajustements manuels apportés à une prévision peuvent être supprimés uniquement au moment de l'importation de la prévision, en désactivant la case à cocher **Enregistrer les ajustements manuels apportés à la prévision de la demande de base**. Les ajustements manuels sont enregistrés au moment de l'autorisation. Par conséquent, si un utilisateur apporte les ajustements manuels à la prévision, mais n'autorise pas la prévision vers Dynamics 365 pour les opérations, les modifications sont perdus. Pour plus d'informations sur les ajustements manuels et la manière dont elles fonctionnent, voir [autorisant la prévision ajustée] (authorize-adjusted-forecast.md). 

Une génération de prévision de la demande peut avoir un nom et des commentaires pour aider les utilisateurs à identifier la prévision générée. Ces valeurs sont visibles dans l'historique de génération de prévisions dans la page **Enregistrer les ajustements manuels apportés à la prévision de la demande de base**. 

Le groupe d'organisation intersociétés, les clés de répartition par article, ainsi que d'autres filtres peuvent être appliqués au moment de la génération de prévision. Ceux-ci peuvent être utilisés pour améliorer les performances ou pour fractionner les données en segments maniables. Toutefois, notez qu'une prévision de la demande n'est pas générée pour les membres d'une clé de répartition par article qui n'est pas associée à un groupe d'organisation intersociétés, même si cette clé de répartition par article est sélectionnée dans la requête. 

**Conseil** : il arrive parfois que les utilisateurs reçoivent des erreurs lors de la génération d'une prévision de la demande, ou que la génération de prévision soit exécutée sans journal de session. Cela peut se produire en raison de données restantes dans la requête qui ont été précédemment utilisées pour la génération de prévision. Pour résoudre ce problème, cliquez sur **Sélectionner** pour ouvrir la page **Requête**, cliquez sur **Réinitialiser**, puis régénérez la prévision de base. 

Si la prévision n'est générée pour un grand ensemble d'articles, mais, par exemple, pour un article ou une clé de répartition par article à la fois, alors afin d'obtenir d'améliorer les performances, vous pouvez sélectionner ** mode de réponse de demande d'utilisation ** la case à cocher sous ** planification - Le paramétrage - prévision de la demande ** - ** paramètres de prévision de la demande - la Machine Learning azurée ** onglet.

<a name="see-also"></a>Voir également :
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)


