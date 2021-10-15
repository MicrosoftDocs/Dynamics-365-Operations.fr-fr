---
title: Opérations pour les non-conformités
description: Cette rubrique décrit comment créer et utiliser des opérations pour les non-conformités.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35619454af8b1cb1b7d383d393362f58d9dd0ea6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573871"
---
# <a name="operations-for-nonconformances"></a>Opérations pour les non-conformités

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment créer et utiliser des opérations pour les non-conformités.

Vous pouvez utiliser la page **Opérations** pour définir les classifications des tâches pouvant être exécutées pour une non-conformité approuvée. Lorsque vous affectez une opération associée à une non-conformité, vous pouvez fournir des informations détaillées, notamment sur la matière, les heures travaillées et les charges associées requises pour l’exécution de l’opération. Le système utilise ces informations pour calculer le coût estimé de l’opération. Les informations détaillées et les coûts estimés sont fournis à titre de référence. Les opérations associées pour la qualité diffèrent des opérations pouvant être définies pour une gamme de production.

> [!NOTE]
> Bien que vous puissiez suivre les coûts, le temps et les éléments utilisés dans une opération liée à une non-conformité, les données que vous saisissez sont uniquement informatives. Elles ne sont pas automatiquement intégrées à la comptabilité, à la comptabilité auxiliaire du stock ou au module **Pointage**.

## <a name="examples-of-operations"></a>Exemples d'opérations

Vous travaillez pour une entreprise de fabrication. Une non-conformité a été créée et approuvée pour les éléments qui ont échoué à un test de qualité. Une correction a été créée pour indiquer que le problème était lié à un mauvais roulement sur une machine. Plusieurs étapes sont nécessaires pour remplacer le roulement et la responsabilité de chaque opération fait l'objet d'un suivi. Par exemple, les étapes suivantes peuvent être requises :

1. La ligne de production est arrêtée et la routine de nettoyage est exécutée.
1. Le personnel de maintenance remplace le roulement.
1. Le personnel d'assurance qualité inspecte la machine avant de la rallumer.

Pour cet exemple, les opérations suivantes peuvent être créées pour représenter le travail à effectuer :

- Arrêter la ligne de production.
- Nettoyer la ligne de production.
- Exécuter la maintenance de la machine.
- Inspecter la machine.

## <a name="create-an-operation"></a>Créer une opération

1. Accédez à **Gestion des stocks \> Paramétrage \> Gestion de la qualité \> Opérations**.
1. Dans le volet Actions, sélectionnez **Nouveau** pour ajouter une ligne à la grille. Définissez ensuite les champs suivants pour la nouvelle ligne :

    - **Opération** - Entrez un ID ou un nom unique pour l'opération.
    - **Description** – Entrez une description détaillée de l'opération.
    - **Taper** - Si l'opération ne peut être utilisée qu'avec des non-conformités liées à un type de commande spécifique, sélectionnez le type de commande (*Bon de commande* ou *Commande client*).

1. Fermez la page.

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d’ensemble de la gestion de la qualité](quality-management-processes.md)
- [Activer la gestion de la qualité et de la non-conformité](enable-quality-management.md)
- [Créer et traiter les non-conformités](tasks/create-process-non-conformance.md)
- [Collaborateurs chargés d'approuver les non-conformités](quality-responsible-workers.md)
- [Zones de contrôle pour les non-conformités](quality-quarantine-zones.md)
- [Types de diagnostic pour les non-conformités](quality-diagnostic-types.md)
- [Frais de qualité pour les non-conformités](quality-charges.md)
- [Types de problème pour les non-conformités](quality-operations.md)
- [Gestion de la qualité pour les processus d'entrepôt](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
