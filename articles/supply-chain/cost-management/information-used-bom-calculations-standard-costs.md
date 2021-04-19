---
title: Informations utilisées dans les calculs de nomenclature avec les coûts standard
description: Les calculs de nomenclature utilisent les données de plusieurs sources pour calculer les coûts standard d’un article fabriqué. Les sources incluent des informations sur les articles, les gammes de nomenclatures, les formules de calcul des coûts indirects et la version d’évaluation des coûts.
author: AndersGirke
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b5096ae7901a91f602f520e4e869ff67771c244
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842175"
---
# <a name="information-used-in-bom-calculations-with-standard-costs"></a>Informations utilisées dans les calculs de nomenclature avec les coûts standard

[!include [banner](../includes/banner.md)]

Les calculs de nomenclature utilisent les données de plusieurs sources pour calculer les coûts standard d’un article fabriqué. Les sources incluent des informations sur les articles, les gammes de nomenclatures, les formules de calcul des coûts indirects et la version d’évaluation des coûts.

Les informations sur l’article acheté utilisées dans le cadre du calcul de nomenclature pour un coût standard sont les suivantes :
-   Coût − Les coûts d’un article acheté correspondent à des enregistrements des coûts spécifiques au site dans une version d’évaluation des coûts standard. Chaque enregistrement des coûts comporte une date effective et la date de calcul de nomenclature détermine l’enregistrement des coûts à utiliser. Par exemple, un calcul de nomenclature avec une date de calcul ultérieure peut utiliser un enregistrement des coûts avec un statut en attente et une date effective ultérieure.
-   Groupe de coûts − Le groupe de coûts affecté à un article acheté fournit la base de la segmentation des coûts dans les coûts calculés d’un article fabriqué.
-   Les conditions d’avertissement qui sont incorporées dans le groupe de calcul de nomenclature de l’article permettent au calcul de nomenclature d’identifier les problèmes potentiels. Cela peut se produire lorsque l’article acheté a un coût nul, une quantité nulle dans une nomenclature, ou un enregistrement de coût obsolète. Les conditions d’avertissement applicables peuvent être remplacées lors de l’élaboration d’un calcul de nomenclature.

Les informations sur l’article fabriqué utilisées dans le cadre du calcul de nomenclature pour un coût standard sont les suivantes :
-   Quantité commandée standard pour le stock − La quantité commandée standard de l’article pour le stock fait office de taille du lot comptable par défaut pour l’amortissement des coûts constants dans un calcul de nomenclature. La taille du lot comptable reflète également la quantité multiple de commande au besoin.
-   Les conditions d’avertissement qui sont incorporées dans le groupe de calcul de nomenclature de l’article permettent au calcul de nomenclature d’identifier les problèmes potentiels. Un exemple peut être que l’article fabriqué ne possède pas de nomenclature ou de gamme. Les conditions d’avertissement applicables peuvent être remplacées lors de l’élaboration d’un calcul de nomenclature.

Les informations de nomenclature utilisées dans le cadre du calcul de nomenclature pour un coût standard sont les suivantes :
-   Version de nomenclature − La version de nomenclature affectée à l’article fabriqué dispose de dates de début et de fin effectives et d’un statut approuvé et actif. Elle peut être spécifique au site ou à l’échelle de la société et peut éventuellement refléter les points d’arrêt de la quantité.
-   Quantité de lignes de nomenclature - Généralement, un composant dispose d’une quantité variable obligatoire qui peut toutefois être constante. La quantité du composant est généralement indiquée pour la production d’un article parent, mais elle peut être exprimée par 100 ou par 1 000 pour gérer les problèmes de précision décimale. La quantité du composant peut également être calculée en fonction des mesures.
-   Mise au rebut de la ligne de nomenclature - La quantité d’un composant peut être variable ou constante pour la mise au rebut planifiée.
-   Dates valides de la ligne de nomenclature - Un composant peut comporter des dates de début et de fin valides.
-   Type de production de la ligne de nomenclature − La taille du lot d’évaluation des coûts pour l’amortissement des coûts constants reflète la quantité de calcul de nomenclature et un mode d’éclatement de création dans la commande car le calcul de nomenclature suppose que le composant fabriqué sera produit dans la quantité exacte plutôt que dans sa quantité commandée standard.
-   Sous-nomenclature d’un composant fabriqué - Un composant fabriqué peut éventuellement disposer d’une version de nomenclature spécifiée, qui devrait être utilisée à la place de la version de nomenclature active actuelle de l’article dans un calcul de nomenclature.
-   Sous-gamme d’un composant fabriqué - Un composant fabriqué peut éventuellement disposer d’une version de gamme spécifiée, qui devrait être utilisée à la place de la version de gamme active actuelle de l’article dans un calcul de nomenclature.
-   Numéro d’opération et impact des pourcentages de rebut des opérations − Le numéro d’opération lie un composant à une opération spécifique et les opérations peuvent disposer d’un pourcentage de rebut. La liaison permet aux calculs de nomenclature de prendre en compte les pourcentages de rebut et les pourcentages de rebut cumulés dans plusieurs opérations sur la quantité requise du composant.
-   Ignorer la ligne de nomenclature dans les calculs des coûts - Un composant peut être ignoré à des fins de calcul de nomenclature.

Les informations de ressource opérationnelle utilisées dans le cadre du calcul de nomenclature pour un coût standard sont les suivantes :
-   Coûts horaires − Les coûts horaires associés à une ressource opérationnelle sont exprimés en termes de catégories de coûts affectées aux temps de réglage et d’exécution. Ces catégories de coûts doivent être identifiées pour les groupes de ressources et les ressources opérationnelles. Les coûts horaires associés à une catégorie de coûts peuvent être spécifiques au site ou à l’échelle de la société.
-   Coûts unitaires − Certains environnements de fabrication affectent des coûts unitaires de ressource opérationnelle de production, qui doivent être exprimés sous la forme d’une catégorie de coûts différente pour la quantité. Par exemple, les coûts liés à la quantité peuvent refléter les taux à la pièce pour la main d’œuvre, ou un fabricant de peinture peut affecter des coûts de ressource opérationnelle par litre produit.
-   Remplacement des informations de ressource opérationnelle au cours d’opérations de gammes − Les informations de ressource sur les catégories de coûts sont héritées par des opérations au cours desquelles elles peuvent être remplacées. Les calculs de nomenclature utilisent les informations de catégorie de coûts spécifiées au cours d’opérations de gammes.
-   Groupe de coûts pour une catégorie de coûts − Le groupe de coûts affecté à une catégorie de coûts propose la segmentation des coûts dans les coûts calculés d’un article fabriqué. Par exemple, des groupes de coûts différents peuvent être utilisés pour segmenter les coûts calculés associés aux machines et à la main d’œuvre ou aux temps de réglage et d’exécution.

Les informations de gamme utilisées dans le cadre du calcul de nomenclature pour un coût standard sont les suivantes :
-   Version de gamme - La version de gamme affectée à l’article fabriqué dispose de dates de début et de fin effectives et d’un statut approuvé et actif. Elle peut être spécifique au site et peut éventuellement refléter les points d’arrêt de la quantité.
-   Durée d’opération relative à la gamme − La durée peut être indiquée pour le réglage et l’exécution. La durée horaire est généralement indiquée pour la production d’un article parent, mais elle peut être exprimée par 100 ou par 1 000 pour gérer les problèmes de précision décimale.
-   Durée d’opération relative à la gamme pour les ressources secondaires − Le numéro d’opération d’une ressource secondaire est identique à celui de la ressource principale. Il en est de même pour la durée d’opération relative à la gamme. Par exemple, une opération peut nécessiter une machine comme ressource principale et la main d’œuvre et les outils comme ressources secondaires.
-   Pourcentage de rebut des opérations de gammes − Les calculs de nomenclature prennent en compte les pourcentages de rebut et les pourcentages de rebut cumulés dans plusieurs opérations. Cela s’applique à la durée requise pour les opérations de gammes et la quantité requise des composants liés aux numéros d’opération.
-   Catégories de coûts pour une opération de gamme − Les informations de ressource opérationnelle sur les catégories de coûts sont héritées par des opérations au cours desquelles elles peuvent être remplacées. Les calculs de nomenclature utilisent les informations de catégorie de coûts spécifiées au cours d’opérations de gammes.

Les informations de frais généraux de fabrication utilisées dans le cadre du calcul de nomenclature pour un coût standard sont les suivantes :
-   Surcharge − La formule de calcul d’une surcharge reflète un pourcentage de valeur, comme 100 %, lié à un groupe de coûts spécifiques, comme la main d’œuvre.
-   Taux − La formule de calcul d’un taux reflète un montant par unité, comme 10,00 EUR par heure, lié à un groupe de coûts spécifiques, comme la main d’œuvre.
-   Frais généraux basés sur la durée par rapport aux frais généraux basés sur la matière − Les frais généraux de fabrication peuvent être liés aux opérations de gammes ou aux composants de matière.

Les informations de version d’évaluation des coûts utilisées dans le cadre du calcul de nomenclature pour un coût standard sont les suivantes :
-   Type d’évaluation des coûts − La version d’évaluation des coûts doit contenir des coûts standard. Plusieurs restrictions s’appliquent aux calculs de nomenclature qui utilisent les coûts standard. Par exemple, ces restrictions spécifient que des frais divers doivent être inclus dans les coûts unitaires et que le mode d’éclatement de calcul de nomenclature ne doit comporter qu’un seul niveau.
-   Principe de secours autorisé − La version d’évaluation des coûts peut autoriser l’utilisation d’un principe de secours, comme l’utilisation d’une version d’évaluation des coûts spécifiée ou les enregistrements des coûts actifs. Le principe de secours autorisé s’applique généralement à une version d’évaluation des coûts qui représente les mises à jour incrémentielles dans une approche à deux versions pour les mises à jour des coûts.
-   Indicateur de blocage pour les coûts en attente − Un indicateur de blocage peut empêcher les calculs de nomenclature du coût en attente des articles fabriqués.
-   Date de début spécifiée − La date de début spécifiée fait office de date de calcul par défaut pour tous les calculs de nomenclature qui impliquent la version d’évaluation des coûts.
-   Site spécifié − Un site spécifié limite les calculs de nomenclature à un seul site.
-   Le contenu de la version d’évaluation des coûts doit inclure des coûts − Le contenu doit inclure des coûts. Il peut éventuellement inclure des prix de vente afin de calculer les prix de vente suggérés pour les articles fabriqués.

Plusieurs sources d’informations peuvent être spécifiées lors de l’élaboration d’un calcul de nomenclature. Il s’agit du site, de la date de calcul et de la version d’évaluation des coûts.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]