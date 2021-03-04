---
title: Niveaux de service de l'actif
description: Cette rubrique explique les niveaux de service de l'actif dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35e7a55b1ba230be6bb72b20fcd805ea061b648e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427796"
---
# <a name="asset-service-levels"></a>Niveaux de service de l'actif

[!include [banner](../../includes/banner.md)]

 

Cette rubrique explique les niveaux de service de l'actif dans le module Gestion des actifs. Les niveaux de service de l'actif sont associés aux actifs, et sont transférés vers les demandes de maintenance et les ordres de travail. Ils sont utilisés pour calculer la priorité des ordres de travail lors de la planification des ordres de travail. Les niveaux de service de l'actif peuvent être modifiés, si cela est nécessaire.

Pour plus d'informations sur le paramétrage lié au calcul des scores pour la planification des ordres de travail, voir [Paramètres de gestion des actifs](../setup-for-objects/enterprise-asset-management-parameters.md). Vous devez paramétrer au moins un enregistrement par défaut pour le niveau de service de l'actif. Cet enregistrement par défaut est utilisé si aucune autre correspondance n'est trouvée lors de la planification des ordres de travail.

**Exemple 1 :** niveau de service par défaut qui est utilisé si aucune autre correspondance n'est trouvée. Dans cet enregistrement, vous sélectionnez uniquement un niveau de service.

**Exemple 2 :** niveau de service élevé qui est utilisé pour planifier des tâches pour un moteur de camion Volvo. Dans cet enregistrement, vous sélectionnez un type d'actif approprié (par exemple, **Moteur de camion**), un fabricant (**Volvo**) et un niveau de service.

## <a name="set-up-asset-service-levels"></a>Paramétrer les niveaux de service de l'actif

1. Sélectionnez **Gestion des actifs** \> **Paramétrage** \> **Niveaux de service d'actifs**.
2. Sélectionnez **Nouveau** pour créer un enregistrement.
3. En fonction du niveau de détail requis pour le niveau de service de l'actif, effectuez les sélections appropriées dans les champs **Poste technique**, **Type d'actif**, **Fabricant**, **Modèle**, **Actif**, **Type d'ordre de travail** et **Niveau de service**.

    > [!NOTE]
    > Lorsque le niveau de service de l'actif est utilisé pour les demandes de maintenance et les ordres de travail, le module Gestion des actifs recherche une correspondance possible dans tous les enregistrements de niveau de service d'actif. Il vérifie toujours la combinaison la plus spécifique en premier. En d'autres termes, le module Gestion des actifs recherche d'abord une correspondance pour le champ **Type d'ordre de travail**. Si aucune correspondance n'est trouvée, il recherche une correspondance pour le champ **Actif**, etc. Comme vous pouvez voir dans la disposition de la page **Niveaux de service d'actifs**, ce comportement signifie que, pour trouver la combinaison la plus spécifique, le module Gestion des actifs recherche une correspondance dans chaque enregistrement en allant de la droite vers la gauche. Si aucune correspondance n'est trouvée, l'enregistrement par défaut qui ne comporte aucune sélection dans ces champs est utilisé.

4. Dans le champ **Niveau de service**, sélectionnez un nombre qui indique le niveau de service (priorité).


> [!NOTE]
> Si vous modifiez un enregistrement de niveau de service d'actif dans la page **Niveaux de service d'actifs** après l'avoir déjà utilisé sur un ordre de travail, le niveau de service des demandes de maintenance et des ordres de travail n'est pas mis à jour en conséquence.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]