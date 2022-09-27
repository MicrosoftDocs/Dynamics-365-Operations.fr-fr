---
title: Analyse de concordance d’optimisation de la planification
description: Cet article explique comment vérifier votre configuration et vos données par rapport aux fonctionnalités de la fonction d’optimisation de la planification.
author: t-benebo
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsFitAnalysis, MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: f9c85c4fbcc3c66d6cc4c65431b76c31cbb7aebf
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542350"
---
# <a name="planning-optimization-fit-analysis"></a>Analyse de concordance pour l’optimisation de la planification

[!include [banner](../../includes/banner.md)]

Vous devez analyser le résultat de l’analyse d’ajustement de l’optimisation de la planification dans le cadre du processus de migration. Notez que la portée de l’optimisation de la planification n’est pas identique à celle de la fonctionnalité de planification générale intégrée actuelle. Nous vous recommandons de collaborer avec votre partenaire et de lire la documentation pour préparer votre migration. 

L’analyse d’ajustement de l’optimisation de la planification vous aide à identifier les différences de résultats entre le moteur de planification générale intégré et l’optimisation de la planification. Cette analyse est effectuée en fonction de votre configuration et de vos données actuelles. 

Pour voir le résultat de l’analyse d’ajustement de l’optimisation de la planification, accédez à **Planification générale** \> **Configuration** \> **Analyse de l’ajustement de l’optimisation de la planification**, puis sélectionnez **Lancer l’analyse**. Si l’analyse permet de trouver des incohérences, elles sont répertoriées sur la même page. (L’exécution de l’analyse peut prendre quelques minutes.)

> [!NOTE]
>
> - Certaines incohérences ne peuvent pas être identifiées par l’analyse de concordance pour l’optimisation de la planification. Pour plus d’informations, consultez [Différences entre la planification générale classique et l’optimisation de la planification](planning-optimization-differences-with-built-in.md).
>
> - Si des incohérences sont détectées, vous pouvez utiliser l’optimisation de la planification. Les résultats de l’analyse de concordance indiquent simplement les endroits où le service de planification n’honorera pas votre configuration actuelle. En d’autres termes, ils affichent les endroits où certains processus pourraient être ignorés ou ne pourraient pas être pris en charge.

## <a name="analysis-results-example-1"></a>Résultats d’analyse : Exemple 1

- **Fonctionnalité :** Production
- **Problème :** Articles dont le niveau de nomenclature est supérieur à zéro : 56
- **Explication :** l’analyse de concordance a trouvé 56 articles avec une configuration de nomenclature pour la production. Puisque la version actuelle de l’optimisation de la planification en prend pas en charge la production, l’optimisation de la planification génèrera les commandes fournisseur planifiées plutôt que les ordres de production planifiés. Elle affichera également un avertissement qui répertorie les articles concernés.

## <a name="analysis-results-example-2"></a>Résultats d’analyse : Exemple 2

- **Fonctionnalité :** Actions
- **Problème :** Groupes de couverture avec calcul des actions activé : 6
- **Explication :** l’analyse de concordance a trouvé six groupes de couverture où le calcul des actions est activé. Puisque la version actuelle de l’optimisation de la planification ne prend pas en charge les actions, aucune action ne sera générée pendant la planification.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Aperçu des résultats possibles de l’analyse de concordance

Le tableau suivant présente les différents résultats qui peuvent être affichés après une analyse de concordance. Les symboles de numéro (*\#*) seront remplacés par un nombre qui indique le nombre d’enregistrements présentant le problème répertorié.

> [!IMPORTANT]
> Pour les fonctionnalités qui ne sont pas encore prises en charge, le tableau suivant fournit des informations sur la disponibilité prévue estimée en fonction de notre feuille de route actuelle. Ces estimations sont sujettes à changement sans préavis.

| Fonction | Problème répertorié | Explication | Disponibilité attendue |
| --- | --- | --- | --- |
| Actions | Groupes de couverture avec le calcul des actions activé : *\#* | Cette fonctionnalité est désormais prise en charge. | Prise en charge |
| Calendriers de base | Calendriers utilisant le calendrier de base : *\#* | Cette fonctionnalité est désormais prise en charge. | Prise en charge | 
| Codes disposition de lot | Données principales de disposition de lot qui ne sont pas disponibles à la vente : *\#* | Cette fonctionnalité est en attente. Actuellement, la fonctionnalité Codes disposition de lot est ignorée quand l’Optimisation de la planification est activée. | 2022 vague de lancement 2 <!-- KFM: Now available? [Use batch disposition codes to mark batches as available or unavailable](../../inventory/batch-disposition-codes.md) --> |
| Capable to promise (CTP) | Paramètres de commande par défaut avec le contrôle de date de livraison défini sur CTP : *\#* | Dans Supply Chain Management 10.0.28 et versions ultérieures, un processus appelé *CTP pour l’optimisation de la planification* met à disposition les dates d’expédition et de réception confirmées après l’exécution du plan dynamique. Pour les anciennes versions de Supply Chain Management, le paramètre CTP hérité est ignoré lorsque l’optimisation de la planification est activée. | Prise en charge |
| Copie du plan statique vers le plan dynamique | La fonctionnalité Copie du plan statique vers le plan dynamique est activée dans les paramètres de planification. | L’Optimisation de la planification ne copie pas le plan statique dans le plan dynamique, quel que soit ce paramètre. En général, ce concept est moins pertinent en raison de la vitesse et de la régénération complète fournies par l’Optimisation de la planification. Si deux plans ou plus sont utilisés, la planification principale doit être déclenchée pour chaque plan. | S/O |
| Confirmation | Groupes de couverture avec la plage de gestion de la confirmation automatique définie : *\#* | Dans la version 10.0.7 et les versions ultérieures, la confirmation est prise en charge en tant que traitement par lots de confirmation distinct une fois la planification principale terminée (à condition que la fonctionnalité *Confirmation automatique pour l’Optimisation de la planification* ait été activée dans la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Notez que la confirmation automatique pour l’Optimisation de la planification est basée sur la date de commande (date de début) et non sur la date du besoin (date de fin). Ce comportement garantit que la confirmation des commandes planifiées se produit en temps voulu, sans avoir à inclure le délai de livraison dans la période de confirmation. | Prise en charge |
| Confirmation | Enregistrements de couverture d’article avec la confirmation automatique définie : *\#* | Dans la version 10.0.7 et les versions ultérieures, la confirmation automatique est prise en charge en tant que traitement par lots de confirmation distinct une fois la planification principale terminée (à condition que la fonctionnalité *Confirmation automatique pour l’Optimisation de la planification* ait été activée dans la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Notez que la confirmation automatique pour l’Optimisation de la planification est basée sur la date de commande (date de début) et non sur la date du besoin (date de fin). Ce comportement garantit que la confirmation des commandes planifiées se produit en temps voulu, sans avoir à inclure le délai de livraison dans la période de confirmation. | Prise en charge |
| Confirmation | Plans généraux avec la confirmation automatique définie : *\#* | Dans la version 10.0.7 et les versions ultérieures, la confirmation automatique est prise en charge en tant que traitement par lots de confirmation distinct une fois la planification principale terminée (à condition que la fonctionnalité *Confirmation automatique pour l’Optimisation de la planification* ait été activée dans la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Notez que la confirmation automatique pour l’Optimisation de la planification est basée sur la date de commande (date de début) et non sur la date du besoin (date de fin). Ce comportement garantit que la confirmation des commandes planifiées se produit en temps voulu, sans avoir à inclure le délai de livraison dans la période de confirmation. | Prise en charge |
| FitAnalysisPlanningItems | Éléments de planification : *\#* | Cette fonctionnalité est en attente. Actuellement, les éléments de planification sont traités comme des éléments normaux quand l’Optimisation de la planification est activée. | 2022 vague de lancement 2 ou ultérieure |
| Prévision | Groupes de couverture avec l’option « Inclure les commandes intersociétés » activée : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Planification intersociétés](Intercompany-planning.md) | Prise en charge |
| Prévision | Groupes de couverture dont le paramètre « Soustraire des prévisions » est défini sur une valeur différente de « Commandes » : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, voir [Planification avec prévisions de la demande](demand-forecast.md) | Prise en charge |
| Prévision | Modèles de prévision avec des sous-modèles : *\#* |  Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, voir [Planification avec prévisions de la demande](demand-forecast.md) | Prise en charge |
| Prévision | Plans principaux avec l’option « Inclure les prévisions d’approvisionnement » activée : *\#* | Cette fonctionnalité est en attente. Actuellement, les prévisions d’approvisionnement ne sont pas prises en charge quand l’Optimisation de la planification est activée. Elles seront ignorées, quel que soit ce paramètre. | 2022 vague de lancement 2 ou ultérieure |
| Plage de gestion du gel | Groupes de couverture avec la plage de gestion du gel définie : *\#* | Cette fonctionnalité est en attente. Actuellement, la plage de gestion du gel est ignorée quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Plage de gestion du gel | Enregistrements de couverture d’article avec la plage de gestion du gel définie : *\#* | Cette fonctionnalité est en attente. Actuellement, la plage de gestion du gel est ignorée quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Plage de gestion du gel | Plans généraux avec la plage de gestion du gel définie : *\#* | Cette fonctionnalité est en attente. Actuellement, la plage de gestion du gel est ignorée quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Intersociétés | Plans généraux incluant la demande prévisionnelle en aval : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Planification intersociétés](Intercompany-planning.md) | Prise en charge |
| Kanban | Enregistrements de couverture d’article avec le kanban du type d’ordre prévisionnel : *\#* | Cette fonctionnalité est en attente. Actuellement, la couverture d’article définie sur kanban sera ignorée quand l’Optimisation de la planification est activée. Le type de commande planifiée kanban créera un avertissement au moment de la planification principale et des commandes fournisseur prévisionnelles seront créées pour couvrir la demande associée. | Vague future |
| Kanban | Articles avec le kanban du type de commande par défaut : *\#* | Actuellement, un type de commande par défaut défini sur kanban sera ignoré quand l’Optimisation de la planification est activée. Le type de commande par défaut kanban créera un avertissement au moment de la planification principale et des commandes fournisseur prévisionnelles seront créées pour couvrir la demande associée. | Vague future |
| État du cycle de vie des produits | Les états du cycle de vie des produits ne sont pas actifs pour la planification : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Exclure les produits avec des états du cycle de vie des produits spécifiques](product-lifecycle-state.md) | Prise en charge |
| Production | Lignes de nomenclature avec paramétrage d’arrondi ou multiple : *\#* | Cette fonctionnalité est en attente. Actuellement, l’arrondi et les configurations multiples sont ignorés sur les lignes de nomenclature quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | Vague future|
| Production | Lignes de nomenclature/formule avec mesure de formule : *\#* | Cette fonctionnalité est en attente. Actuellement, la mesure de formule est ignorée sur les lignes de nomenclature et de formule quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Production | Lignes de nomenclature/formule avec substitution d’article (groupes de plans) : *\#* | Cette fonctionnalité est en attente. Actuellement, la substitution d’article (groupes de plans) est ignorée sur les lignes de nomenclature et de formule quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Production | Lignes de nomenclature/formule avec quantité négative : *\#* | Cette fonctionnalité est en attente. Les lignes de nomenclature et de formule dont la quantité est négative seront incluses avec une quantité de 0 (zéro) et un avertissement sera émis quand l’Optimisation de la planification est activée. Mettez à jour les données principales pour éviter les avertissements. | 2022 vague de lancement 2 |
| Production | Lignes de nomenclature/formule à consommation de ressources : *\#* | Cette fonctionnalité est en attente. Actuellement, les lignes de nomenclature et de formule qui ont une consommation de ressources sont ignorées quand l’Optimisation de la planification est activée. Quand cette fonction est prise en charge, les besoins en matières sont définis sur la date de début de production. Tant que cette fonctionnalité n’est pas prise en charge, les besoins ne seront pas générés pour les matières marqués d’un indicateur de consommation de ressources. | 2022 vague de lancement 2 |
| Production | Lignes de nomenclature/formule à consommation par étape : *\#* | Cette fonctionnalité est en attente. Actuellement, la consommation d’étapes est ignorée sur les lignes de nomenclature et de formule quand l’Optimisation de la planification est activée. | 2022 vague de lancement 2 |
| Production | Nomenclatures présentant un rebut constant ou un rebut variable défini : *\#* | Cette fonctionnalité est en attente. Actuellement, un rebut constant et un rebut variable définis sur les nomenclatures sont ignorés quand l’Optimisation de la planification est activée. | 2022 vague de lancement 2 |
| Production | Nomenclatures avec sous-traitance : *\#* | Cette fonctionnalité est désormais prise en charge. | Prise en charge |
| Production | Nomenclatures sans site : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Planification de production](production-planning.md) | Prise en charge |
| Production | Demande avec des exigences de nomenclature ou de gamme spécifiques définies : *\#* | Cette fonctionnalité est en attente. Actuellement, les exigences de nomenclature ou de gamme spécifiques définies sur la demande (telles qu’une sous-nomenclature ou une sous-gamme sur une commande client) sont ignorées quand l’Optimisation de la planification est activée. La nomenclature ou la gamme standard sera utilisée, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Production | Versions de formule avec des co-produits ou des sous-produits : *\#* | Cette fonctionnalité est en attente. Actuellement, les co-produits et sous-produits associés à la version de formule sont ignorés quand l’Optimisation de la planification est activée. | 2022 vague de lancement 2 |
| Production | Versions de formule avec rendement : *\#* | Cette fonctionnalité est en attente. Actuellement, le rendement associé à la version de formule est ignoré quand l’Optimisation de la planification est activée. | 2022 vague de lancement 2 |
| Production | Plans incluant le classement : *\#* | Cette fonctionnalité est en attente. Actuellement, le classement est ignoré quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Production | Ordres de fabrication lancés qui n’ont pas commencé, quand la date de début planifiée est antérieure à aujourd’hui : *\#* | Cette fonctionnalité est en attente. Actuellement, si un ordre de fabrication est retardé, la planification générale supposera qu’il sera terminé aujourd’hui. Ceci est pertinent pour les ordres de fabrication lancés dont la date de livraison est dans le passé, mais qui ne sont pas encore terminés. | Vague future |
| Production | Ressources planifiées avec une capacité finie : *\#* | Cette fonctionnalité est en attente. Actuellement, les ressources planifiées avec une capacité limitée sont ignorées quand l’Optimisation de la planification est activée. La planification est effectuée en fonction du délai de livraison par défaut du produit. | 2022 vague de lancement 2 |
| Production | Gammes utilisées au moment de la planification : *\#* | Cette fonctionnalité est prise en charge. | Prise en charge |
| Production | Réservation de ligne de vente avec éclatement : *\#* | La réservation de ligne de vente qui utilise un éclatement n’est pas prise en charge quand l’Optimisation de la planification est activée. | Vague future |
| Production | Planification avec éclatement des ordres de fabrication : *\#* | La planification qui utilise un éclatement des ordres de fabrication n’est pas prise en charge quand l’Optimisation de la planification est activée. Les ordres de fabrication peuvent être planifiés individuellement. | Vague future |
| Appel d’offre | Plans généraux avec les appels d’offre activés : *\#* | Cette fonctionnalité est en attente. Actuellement, les appels d’offre ne sont pas considérés comme une demande quand l’Optimisation de la planification est activée. Elles seront ignorées, quel que soit ce paramètre. | 2022 vague de lancement 2 |
| Demandes d’achat | Plans généraux avec les demandes d’achat activées : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, voir [Demandes d’achat](purchase-requisitions.md) | Prise en charge |
| Marges de sécurité | Groupes de couverture avec la marge de sécurité : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Marges de sécurité](safety-margins.md) | Prise en charge |
| Marges de sécurité | Plans généraux avec la marge de sécurité : *\#* | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Marges de sécurité](safety-margins.md) |  Prise en charge |
| Traitement du stock de sécurité | Enregistrements de la couverture des articles avec « Exécuter le minimum » différent de « Date du jour + heure d’achat » : *\#* | L’Optimisation de la planification utilise toujours *Date du jour + heure d’achat*. Cette modification est effectuée pour préparer une configuration de planification simplifiée à l’avenir et pour fournir un résultat exploitable. Si le délai d’approvisionnement n’est pas inclus pour le stock de sécurité, les commandes planifiées qui sont créées pour le stock disponible actuellement bas seront toujours retardées en raison du délai de livraison. Ce comportement peut provoquer des perturbations importantes et des ordres prévisionnels indésirables. La meilleure pratique consiste à modifier le paramètre afin que *Date du jour + heure d’achat* soit utilisé. Mettez à jour les données principales pour éviter les avertissements. | S.o. |
| Devis de vente | Plans généraux avec les devis de vente activés : *\#* | Cette fonctionnalité est en attente. Actuellement, les devis ne sont pas considérées quand l’Optimisation de la planification est activée. Elles seront ignorées, quel que soit ce paramètre. | 2022 vague de lancement 2 ou ultérieure |
| Date d'expiration  | Plans généraux avec la date d'expiration activée : *\#* | Cette fonctionnalité est en attente. Actuellement, la durée de conservation est ignorée quand l’Optimisation de la planification est activée, quel que soit ce paramètre. | Prise en charge |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de l’optimisation de la planification](planning-optimization-overview.md)

[Mise en route de l’optimisation de la planification](get-started.md)

[Différences entre la planification générale classique et l’optimisation de la planification](planning-optimization-differences-with-built-in.md)

[Paramètres non utilisés par l’optimisation de la planification](not-used-parameters.md)

[Afficher l’historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)

[Annuler une tâche de planification](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
