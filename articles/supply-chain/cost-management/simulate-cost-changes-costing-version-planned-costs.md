---
title: Simuler des modifications de coûts à l'aide d'une version d'évaluation des coûts pour les coûts planifiés
description: Cet article explique comment simuler les effets des modifications de coûts sur les coûts calculés d'un article fabriqué à l'aide d'une version d'évaluation des coûts séparée pour les coûts planifiés.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 78183
ms.assetid: 1e41953f-cdb9-4598-b776-46e49383a773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f6e1d52f48a6b7675fb16ccc5ecd9ba7cd25ac8b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214456"
---
# <a name="simulate-cost-changes-by-using-a-costing-version-for-planned-costs"></a>Simuler des modifications de coûts à l'aide d'une version d'évaluation des coûts pour les coûts planifiés

[!include [banner](../includes/banner.md)]

Cet article explique comment simuler les effets des modifications de coûts sur les coûts calculés d'un article fabriqué à l'aide d'une version d'évaluation des coûts séparée pour les coûts planifiés.

Vous pouvez simuler les effets des modifications de coûts sur les coûts calculés d'un article fabriqué à l'aide d'une version d'évaluation des coûts séparée pour les coûts planifiés. Une version d'évaluation des coûts séparée permet d'entrer les enregistrements des coûts en attente qui reflètent les modifications de coûts et de calculer l'impact des coûts sur les articles fabriqués. Dut fait qu'un principe de secours des coûts actifs sera utilisé dans les calculs de nomenclature, seules les modifications de coûts incrémentiels doivent être entrées.

## <a name="guidelines-for-defining-the-simulation-costing-version"></a>Instructions pour la définition de la version d'évaluation des coûts de simulation
Utilisez les instructions suivantes lorsque vous définissez la version d'évaluation des simulations :

-   Affectez un type d'analyse des coûts aux **coûts planifiés**.
-   Affectez un identificateur significatif à la version d'évaluation des coûts, tel que **simulation**.
-   Vérifiez que le contenu comprend des enregistrements de coûts.
-   Autorisez la saisie d'enregistrements des coûts. Ne bloquez pas la saisie de coûts en attente.
-   Autorisez la saisie d'enregistrements des coûts pour tous les sites. En spécifiant un site, vous limiterez l'entrée d'enregistrements de coûts à ce site.
-   Empêchez l'activation de coûts en attente. Seuls les coûts en attente doivent être entrés pour les enregistrements de coûts dans la version d'évaluation des coûts de simulation.
-   N'entrez pas de date de début. Une date de calcul est entrée pour chaque calcul de nomenclature qui utilise la version d'évaluation des coûts de simulation.
-   Spécifiez un principe de secours des **coûts actifs actuels**. Le principe de secours permet d'apporter des modifications aux coûts incrémentiels pour des simulations, tout en utilisant les coûts actifs actuels comme source pour tous les autres enregistrements de coûts. Nous considérons que tous les coûts actifs actuels existent pour tous les autres enregistrements de coûts.
-   Spécifiez un modèle de prix de revient du **prix de revient de la version** mais ne limitez pas les calculs. Par exemple, les simulations peuvent également utiliser un modèle de prix de revient d'un **groupe de calcul de nomenclature** pour indiquer la source des données de contribution des coûts pour les articles achetés.
-   Spécifiez un mode d'éclatement **à plusieurs niveaux** mais ne limitez pas les calculs. Les simulations peuvent utiliser d'autres modes d'éclatement.

## <a name="costing-versions"></a>Versions d'évaluation des coûts
Les scénarios suivants illustrent l'utilisation de la version d'évaluation des coûts de simulation pour simuler l'impact des modifications de coûts. Avant d'entrer une modification de coûts simulée, supprimez les enregistrements de coûts en attente dans la version d'évaluation des coûts de simulation pour que vous ayez un point de départ net. La page **Prix de l'article** permet d'afficher et de supprimer les enregistrements de coûts en attente associés aux prix des articles et aux prix des catégories de coûts.

-   Simulez la modification de coûts pour un article acheté. Par exemple, la modification de coûts peut refléter une augmentation ou une diminution prévue du coût des matériaux essentiels achetés. Pour définir le coût différent pour un article acheté, la page **Prix de l'article** permet d'entrer un enregistrement de coûts en attente dans la version d'évaluation des coûts de simulation.
-   Simulez la modification de coûts pour une catégorie de coûts. Par exemple, la modification de coûts peut refléter une augmentation ou une diminution prévue des coûts des taux de main-d'œuvre ou des taux horaires pour les ressources opérationnelles. Pour définir le coût différent pour une catégorie de coûts, la page **Prix des catégories de coûts** permet d'entrer un enregistrement de coûts en attente dans la version d'évaluation des coûts de simulation.
-   Simulez la modification de coûts dans une formule de calcul des coûts indirects. Par exemple, la modification des coûts peut refléter une augmentation ou une diminution prévue des frais généraux de fabrication. Pour définir la modification dans une formule de calcul des coûts indirects, la page **Paramétrage de la feuille de coûts** permet d'entrer un enregistrement de coûts en attente dans la version d'évaluation des coûts de simulation et de valider et d'enregistrer la modification.

Après avoir entré les modifications des coûts simulés, calculez les coûts des articles fabriqués qui sont touchés par les modifications de coûts. Utilisez la page **Calcul** pour la version de simulation des coûts et identifiez les articles fabriqués sélectionnés qui seront touchés par les modifications de coûts. Les calculs de nomenclature s'appliquent à tous les articles fabriqués à moins que vous sélectionnez des articles spécifiques. Vous pouvez également utiliser l'option de calcul de nomenclature pour des mises à jour d'analyses des utilisations. Affichez les enregistrements des coûts des articles dans la version d'évaluation des coûts de simulation pour analyser la manière dont les modifications des coûts simulées ont touché les coûts des articles fabriqués sélectionnés. La page **Prix de l'article** et la page **Calculer le coût de l'article** permettent d'afficher et d'analyser les coûts.



