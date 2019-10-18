---
title: Activer un calcul de taxe différé sur le journal
description: Cette rubrique explique comment utiliser la fonctionnalité **Activer un calcul de taxe différé sur le journal** pour améliorer les performances du calcul de taxe lorsque le volume de lignes de journal est conséquent.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177684"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a>Activer un calcul de taxe différé sur le journal
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cette rubrique explique comment utiliser la fonctionnalité **Activer un calcul de taxe différé sur le journal** pour améliorer les performances du calcul de taxe lorsque le volume de lignes de journal est conséquent.

Le comportement actuel de calcul de la taxe sur le journal est déclenché en temps réel lorsque l'utilisateur met à jour les champs liés à la taxe, par exemple, le groupe de taxes/groupe de taxes d'article. Toute mise à jour au niveau de la ligne du journal recalculera le montant de la taxe sur toutes les lignes du journal. Elle permet à l'utilisateur de voir le montant de la taxe calculée en temps réel, mais pourrait également générer un problème de performance si le volume des lignes du journal est conséquent.

Cette fonction offre une option de retard du calcul de la taxe pour résoudre le problème de performances. Si cette fonction est activée, le montant de la taxe est calculé uniquement lorsque l'utilisateur clique sur la commande « Taxe » ou valide le journal.

L'utilisateur peut activer/désactiver le paramètre sur trois niveaux :
- Par entité juridique
- Par nom de journal
- Par en-tête de journal

Le système considèrera la valeur de paramètre sur l'en-tête de journal comme valeur finale. La valeur du paramètre sur l'en-tête du journal sera par défaut le nom du journal. La valeur du paramètre sous le nom de journal passera par défaut au paramètre de comptabilité lorsque le nom du journal est créé.

Les champs « Montant de taxe réel » et « Montant de taxe calculé » du journal seront masqués si ce paramètre est activé. L'objectif n'est pas de confondre l'utilisateur, car la valeur de ces deux champs indiquera toujours 0 avant que l'utilisateur ne déclenche le calcul de la taxe.

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a>Activer le calcul de taxe différé par entité juridique

1. Accédez à **Comptabilité > Paramétrage de la comptabilité > Paramètres de comptabilité**
2. Cliquez sur l'onglet **Taxe**
3. Sous l'organisateur **Général**, cherchez le paramètre **Calcul de taxe différé** et activez/désactivez-le.

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a>Activer un calcul de taxe différé par le nom du journal

1. Accédez à **Comptabilité > Paramétrage du journal > Noms des journaux**
2. Sous l'organisateur **Général**, cherchez le paramètre **Calcul de taxe différé** et activez/désactivez-le.

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a>Activer un calcul de taxe différé par journal

1. Accédez à **Comptabilité > Entrées de journal > Journaux des opérations diverses**.
2. Cliquez sur **Nouveau**.
3. Sélectionner un nom de journal
4. Cliquez sur **Paramétrage**
5. Cherchez le paramètre **Calcul de taxe différé** et activez/désactivez-le.

![](media/delayed-tax-calculation-journal-header.png)
