---
title: Analyse de concordance d’optimisation de la planification
description: Cette rubrique explique comment vérifier votre configuration et vos données par rapport aux fonctionnalités de la fonction d’optimisation de la planification.
author: ChristianRytt
ms.date: 07/07/2021
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
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 52048ea6cced6f670faf13ef07f1288183e6d9b67a016608030f9e192a98faa7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751096"
---
# <a name="planning-optimization-fit-analysis"></a>Analyse de concordance pour l’optimisation de la planification

[!include [banner](../../includes/banner.md)]

Vous devez analyser le résultat de l’analyse d’ajustement de l’optimisation de la planification dans le cadre du processus de migration. Notez que la portée de l’optimisation de la planification n’est pas identique à celle de la fonctionnalité de planification générale intégrée actuelle. Nous vous recommandons de collaborer avec votre partenaire et de lire la documentation pour préparer votre migration. 

L’analyse d’ajustement de l’optimisation de la planification vous aide à identifier les différences de résultats entre le moteur de planification générale intégré et l’optimisation de la planification. Cette analyse est effectuée en fonction de votre configuration et de vos données actuelles. 

Pour voir le résultat de l’analyse d’ajustement de l’optimisation de la planification, accédez à **Planification générale** \> **Configuration** \> **Analyse de l’ajustement de l’optimisation de la planification**, puis sélectionnez **Lancer l’analyse**. Si l’analyse permet de trouver des incohérences, elles sont répertoriées sur la même page. (L’exécution de l’analyse peut prendre quelques minutes.)

> [!NOTE]
> Si des incohérences sont détectées, vous pouvez utiliser l’optimisation de la planification. Les résultats de l’analyse de concordance indiquent simplement les endroits où le service de planification n’honorera pas votre configuration actuelle. En d’autres termes, ils affichent les endroits où certains processus pourraient être ignorés ou ne pourraient pas être pris en charge.

## <a name="analysis-results-example-1"></a>Résultats d’analyse : Exemple 1

- **Fonctionnalité :** Production
- **Problème :** Articles dont le niveau de nomenclature est supérieur à zéro : 56
- **Explication :** l’analyse de concordance a trouvé 56 articles avec une configuration de nomenclature pour la production. Puisque la version actuelle de l’optimisation de la planification en prend pas en charge la production, l’optimisation de la planification génèrera les commandes fournisseur planifiées plutôt que les ordres de production planifiés. Elle affichera également un avertissement qui répertorie les articles concernés.

## <a name="analysis-results-example-2"></a>Résultats d’analyse : Exemple 2

- **Fonctionnalité :** Actions
- **Problème :** Groupes de couverture avec calcul des actions activé : 6
- **Explication :** l’analyse de concordance a trouvé six groupes de couverture où le calcul des actions est activé. Puisque la version actuelle de l’optimisation de la planification ne prend pas en charge les actions, aucune action ne sera générée pendant la planification.

## <a name="overview-of-possible-results-from-the-fit-analysis"></a>Aperçu des résultats possibles de l’analyse de concordance

Le tableau suivant présente les différents résultats qui peuvent être affichés après une analyse de concordance. Les symboles de numéro (_\#_) seront remplacés par un nombre qui indique le nombre d’enregistrements présentant le problème répertorié. Les fonctionnalités prises en charge ou en version préliminaire sont disponibles avec la version 10.0.9 ou les versions ultérieures (sauf si un numéro de version supérieur est indiqué dans la colonne « Disponibilité attendue »).

| Fonctionnalité | Problème répertorié | Explication | Disponibilité attendue |
| --- | --- | --- | --- |
| Actions | Groupes de couverture avec le calcul des actions activé : _\#_ | Cette fonctionnalité est en attente. Actuellement, les actions ne sont pas générées lors de la planification principale lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. L’objectif principal des actions est de suggérer des modifications aux commandes existants. Évaluez si les actions sont activement appliquées dans le cadre de vos processus métier ou si les informations de délai liées aux commandes sont suffisantes. | 2022 avril |
| Calendriers de base | Calendriers utilisant le calendrier de base : _\#_ | Cette fonctionnalité est en attente. Actuellement, le calendrier de base est ignoré lorsque l’Optimisation de la planification est activée. Évaluez si le calendrier de base est nécessaire pour vos processus métier ou si la configuration directe dans les calendriers est suffisante. | 2022 avril | 
| Codes disposition de lot | Données principales de disposition de lot qui ne sont pas disponibles à la vente : _\#_ | Cette fonctionnalité est en attente. Actuellement, les codes de disposition des lots sont ignorés lorsque l’Optimisation de la planification est activée. | Octobre 2022 ou ultérieure |
| Capable to promise (CTP) | Paramètres de commande par défaut avec le contrôle de date de livraison défini sur CTP : _\#_ | Cette fonctionnalité est en attente. Actuellement, CTP est ignoré lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 octobre |
| Copie du plan statique vers le plan dynamique | La fonctionnalité Copie du plan statique vers le plan dynamique est activée dans les paramètres de planification. | L’Optimisation de la planification ne copie pas le plan statique dans le plan dynamique, quel que soit ce paramètre. En général, ce concept est moins pertinent en raison de la vitesse et de la régénération complète fournies par l’Optimisation de la planification. Si deux plans ou plus sont utilisés, la planification principale doit être déclenchée pour chaque plan. | 2022 octobre |
| Confirmation | Groupes de couverture avec la plage de gestion de la confirmation automatique définie : _\#_ | Dans la version 10.0.7 et les versions ultérieures, la confirmation est prise en charge en tant que traitement par lots de confirmation distinct une fois la planification principale terminée (à condition que la fonctionnalité _Confirmation automatique pour l’Optimisation de la planification_ ait été activée dans la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Notez que la confirmation automatique pour l’Optimisation de la planification est basée sur la date de commande (date de début) et non sur la date du besoin (date de fin). Ce comportement garantit que la confirmation des commandes planifiées se produit en temps voulu, sans avoir à inclure le délai de livraison dans la période de confirmation. | Prise en charge |
| Confirmation | Enregistrements de couverture d’article avec la confirmation automatique définie : _\#_ | Dans la version 10.0.7 et les versions ultérieures, la confirmation automatique est prise en charge en tant que traitement par lots de confirmation distinct une fois la planification principale terminée (à condition que la fonctionnalité _Confirmation automatique pour l’Optimisation de la planification_ ait été activée dans la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Notez que la confirmation automatique pour l’Optimisation de la planification est basée sur la date de commande (date de début) et non sur la date du besoin (date de fin). Ce comportement garantit que la confirmation des commandes planifiées se produit en temps voulu, sans avoir à inclure le délai de livraison dans la période de confirmation. | Prise en charge |
| Confirmation | Plans généraux avec la confirmation automatique définie : _\#_ | Dans la version 10.0.7 et les versions ultérieures, la confirmation automatique est prise en charge en tant que traitement par lots de confirmation distinct une fois la planification principale terminée (à condition que la fonctionnalité _Confirmation automatique pour l’Optimisation de la planification_ ait été activée dans la [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)). Notez que la confirmation automatique pour l’Optimisation de la planification est basée sur la date de commande (date de début) et non sur la date du besoin (date de fin). Ce comportement garantit que la confirmation des commandes planifiées se produit en temps voulu, sans avoir à inclure le délai de livraison dans la période de confirmation. | Prise en charge |
| FitAnalysisPlanningItems | Éléments de planification : _\#_ | Cette fonctionnalité est en attente. Actuellement, les éléments de planification sont traités comme des éléments normaux lorsque l’Optimisation de la planification est activée. | Octobre 2022 ou ultérieure |
| Prévision | Groupes de couverture avec l’option « Inclure les commandes intersociétés » activée : _\#_ | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Planification intersociétés](Intercompany-planning.md) | Prise en charge |
| Prévision | Groupes de couverture dont le paramètre « Soustraire des prévisions » est défini sur une valeur différente de « Commandes » : _\#_ | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, voir [Planification avec prévisions de la demande](demand-forecast.md) | Prise en charge |
| Prévision | Modèles de prévision avec des sous-modèles : _\#_ |  Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, voir [Planification avec prévisions de la demande](demand-forecast.md) | Prise en charge |
| Prévision | Plans principaux avec l’option « Inclure les prévisions d’approvisionnement » activée : _\#_ | Cette fonctionnalité est en attente. Actuellement, les prévisions d’approvisionnement ne sont pas prises en charge lorsque l’Optimisation de la planification est activée. Elles seront ignorées, quel que soit ce paramètre. | Octobre 2022 ou ultérieure |
| Plage de gestion du gel | Groupes de couverture avec la plage de gestion du gel définie : _\#_ | La plage de gestion du gel n’est pas souvent utilisée, et il n’est actuellement pas prévu de l’inclure pour l’Optimisation de la planification. Actuellement, la plage de gestion du gel est ignorée lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | S.o. |
| Plage de gestion du gel | Enregistrements de couverture d’article avec la plage de gestion du gel définie : _\#_ | La plage de gestion du gel n’est pas souvent utilisée, et il n’est actuellement pas prévu de l’inclure pour l’Optimisation de la planification. Actuellement, la plage de gestion du gel est ignorée lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | S.o. |
| Plage de gestion du gel | Plans généraux avec la plage de gestion du gel définie : _\#_ | La plage de gestion du gel n’est pas souvent utilisée, et il n’est actuellement pas prévu de l’inclure pour l’Optimisation de la planification. Actuellement, la plage de gestion du gel est ignorée lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | S.o. |
| Intersociétés | Plans généraux incluant la demande prévisionnelle en aval : _\#_ | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Planification intersociétés](Intercompany-planning.md) | Prise en charge |
| Kanban | Enregistrements de couverture d’article avec le kanban du type d’ordre prévisionnel : _\#_ | Cette fonctionnalité est en attente. Actuellement, la couverture d’article définie sur kanban sera ignorée lorsque l’Optimisation de la planification est activée. Le type de commande planifiée kanban créera un avertissement lors de la planification principale et des commandes fournisseur prévisionnelles seront créées pour couvrir la demande associée. | Octobre 2022 ou ultérieure |
| Kanban | Articles avec le kanban du type de commande par défaut : _\#_ | Actuellement, un type de commande par défaut défini sur kanban sera ignoré lorsque l’Optimisation de la planification est activée. Le type de commande par défaut kanban créera un avertissement lors de la planification principale et des commandes fournisseur prévisionnelles seront créées pour couvrir la demande associée. | Octobre 2022 ou ultérieure |
| État du cycle de vie des produits | Les états du cycle de vie des produits ne sont pas actifs pour la planification : _\#_ | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Exclure les produits avec des états du cycle de vie des produits spécifiques](product-lifecycle-state.md) | Prise en charge |
| Production | Lignes de nomenclature avec paramétrage d’arrondi ou multiple : _\#_ | Cette fonctionnalité est en attente. Actuellement, l’arrondi et les configurations multiples sont ignorés sur les lignes de nomenclature lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2021 octobre |
| Production | Lignes de nomenclature/formule avec mesure de formule : _\#_ | Cette fonctionnalité est en attente. Actuellement, la mesure de formule est ignorée sur les lignes de nomenclature et de formule lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 octobre |
| Production | Lignes de nomenclature/formule avec substitution d’article (groupes de plans) : _\#_ | Cette fonctionnalité est en attente. Actuellement, la substitution d’article (groupes de plans) est ignorée sur les lignes de nomenclature et de formule lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 octobre |
| Production | Lignes de nomenclature/formule avec quantité négative : _\#_ | Cette fonctionnalité est en attente. Les lignes de nomenclature et de formule dont la quantité est négative seront incluses avec une quantité de 0 (zéro) et un avertissement sera émis lorsque l’Optimisation de la planification est activée. Mettez à jour les données principales pour éviter les avertissements. | 2022 octobre |
| Production | Lignes de nomenclature/formule à consommation de ressources : _\#_ | Cette fonctionnalité est en attente. Actuellement, les lignes de nomenclature et de formule qui ont une consommation de ressources sont ignorées lorsque l’Optimisation de la planification est activée. Lorsque cette fonction est prise en charge, les besoins en matières sont définis sur la date de début de production. Tant que cette fonctionnalité n’est pas prise en charge, les besoins ne seront pas générés pour les matières marqués d’un indicateur de consommation de ressources. | 2022 octobre |
| Production | Lignes de nomenclature/formule à consommation par étape : _\#_ | Cette fonctionnalité est en attente. Actuellement, la consommation d’étapes est ignorée sur les lignes de nomenclature et de formule lorsque l’Optimisation de la planification est activée. | 2022 octobre |
| Production | Nomenclatures présentant un rebut constant ou un rebut variable défini : _\#_ | Cette fonctionnalité est en attente. Actuellement, un rebut constant et un rebut variable définis sur les nomenclatures sont ignorés lorsque l’Optimisation de la planification est activée. | 2022 octobre |
| Production | Nomenclatures avec sous-traitance : _\#_ | Cette fonctionnalité est en attente. Actuellement, la configuration de la sous-traitance sur les nomenclatures est ignorée lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 avril |
| Production | Nomenclatures sans site : _\#_ | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, consultez [Planification de production](production-planning.md) | Prise en charge |
| Production | Demande avec des exigences de nomenclature ou de gamme spécifiques définies : _\#_ | Cette fonctionnalité est en attente. Actuellement, les exigences de nomenclature ou de gamme spécifiques définies sur la demande (telles qu’une sous-nomenclature ou une sous-gamme sur une commande client) sont ignorées lorsque l’Optimisation de la planification est activée. La nomenclature ou la gamme standard sera utilisée, quel que soit ce paramètre. | 2022 octobre |
| Production | Versions de formule avec des co-produits ou des sous-produits : _\#_ | Cette fonctionnalité est en attente. Actuellement, les co-produits et sous-produits associés à la version de formule sont ignorés lorsque l’Optimisation de la planification est activée. | 2022 octobre |
| Production | Versions de formule avec rendement : _\#_ | Cette fonctionnalité est en attente. Actuellement, le rendement associé à la version de formule est ignoré lorsque l’Optimisation de la planification est activée. | 2022 octobre |
| Production | Plans incluant le classement : _\#_ | Cette fonctionnalité est en attente. Actuellement, le classement est ignoré lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 octobre |
| Production | Ordres de fabrication lancés qui n’ont pas commencé, lorsque la date de début planifiée est antérieure à aujourd’hui : _\#_ | Cette fonctionnalité est en attente. Actuellement, si un ordre de fabrication est retardé, la planification générale supposera qu’il sera terminé aujourd’hui. Ceci est pertinent pour les ordres de fabrication lancés dont la date de livraison est dans le passé, mais qui ne sont pas encore terminés. | 2022 octobre |
| Production | Ressources planifiées avec une capacité finie : _\#_ | Cette fonctionnalité est en attente. Actuellement, les ressources planifiées avec une capacité limitée sont ignorées lorsque l’Optimisation de la planification est activée. La planification est effectuée en fonction du délai de livraison par défaut du produit. | 2022 octobre |
| Production | Gammes utilisées lors de la planification : _\#_ | Cette fonctionnalité est en attente. Actuellement, les gammes sont ignorées lorsque l’Optimisation de la planification est activée. Le délai de livraison par défaut du produit est utilisé. | Aperçu : Prise en charge (10.0.20), GA : octobre 2021 |
| Production | Réservation de ligne de vente avec éclatement : _\#_ | La réservation de ligne de vente qui utilise un éclatement n’est pas prise en charge lorsque l’Optimisation de la planification est activée. | 2022 octobre |
| Production | Planification avec éclatement des ordres de fabrication : _\#_ | La planification qui utilise un éclatement des ordres de fabrication n’est pas prise en charge lorsque l’Optimisation de la planification est activée. Les ordres de fabrication peuvent être planifiés individuellement. | 2022 octobre |
| Appel d’offre | Plans généraux avec les appels d’offre activés : _\#_ | Cette fonctionnalité est en attente. Actuellement, les appels d’offre ne sont pas considérés comme une demande lorsque l’Optimisation de la planification est activée. Elles seront ignorées, quel que soit ce paramètre. | 2022 octobre |
| Demandes d’achat | Plans généraux avec les demandes d’achat activées : _\#_ | Cette fonctionnalité est désormais prise en charge. Pour plus d’informations, voir [Demandes d’achat](purchase-requisitions.md) | Prise en charge |
| Marges de sécurité | Groupes de couverture avec la marge de sécurité : _\#_ | Cette fonctionnalité est désormais partiellement prise en charge. Pour plus d’informations, consultez [Marges de sécurité](safety-margins.md) | Marge de réception : prise en charge. Marge de renouvellement et marge de sortie : janvier 2022 |
| Marges de sécurité | Plans généraux avec la marge de sécurité : _\#_ | Cette fonctionnalité est désormais partiellement prise en charge. Pour plus d’informations, consultez [Marges de sécurité](safety-margins.md) | Marge de réception : prise en charge. Marge de renouvellement et marge de sortie : janvier 2022 |
| Traitement du stock de sécurité | Enregistrements de la couverture des articles avec « Exécuter le minimum » différent de « Date du jour + heure d’achat » : _\#_ | L’Optimisation de la planification utilise toujours *Date du jour + heure d’achat*. Cette modification est effectuée pour préparer une configuration de planification simplifiée à l’avenir et pour fournir un résultat exploitable. Si le délai d’approvisionnement n’est pas inclus pour le stock de sécurité, les commandes planifiées qui sont créées pour le stock disponible actuellement bas seront toujours retardées en raison du délai de livraison. Ce comportement peut provoquer des perturbations importantes et des ordres prévisionnels indésirables. La meilleure pratique consiste à modifier le paramètre afin que *Date du jour + heure d’achat* soit utilisé. Mettez à jour les données principales pour éviter les avertissements. | S.o. |
| Devis de vente | Plans généraux avec les devis de vente activés : _\#_ | Cette fonctionnalité est en attente. Actuellement, les devis ne sont pas considérées lorsque l’Optimisation de la planification est activée. Elles seront ignorées, quel que soit ce paramètre. | Octobre 2022 ou ultérieure |
| Durée de conservation | Plans généraux avec la durée de conservation activée : _\#_ | Cette fonctionnalité est en attente. Actuellement, la durée de conservation est ignorée lorsque l’Optimisation de la planification est activée, quel que soit ce paramètre. | 2022 avril |

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de l’optimisation de la planification](planning-optimization-overview.md)

[Mise en route de l’optimisation de la planification](get-started.md)

[Afficher l’historique du plan et les journaux de planification](plan-history-logs.md)

[Appliquer les filtres à un plan](plan-filters.md)

[Annuler une tâche de planification](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
