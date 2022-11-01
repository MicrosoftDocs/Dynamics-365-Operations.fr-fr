---
title: Recalculer les montants nets des lignes lors de l’importation de commandes client et de devis
description: Cet article décrit si et comment le système recalcule les montants nets des lignes lorsque les commandes client et les devis sont importés. Il explique également comment vous pouvez contrôler le comportement dans différentes versions de Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 08/05/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2022-06-08
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: edda0c016130e2a273adf8f3d3e00e2d3ae9d5c6
ms.sourcegitcommit: ce58bb883cd1b54026cbb9928f86cb2fee89f43d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/25/2022
ms.locfileid: "9719332"
---
# <a name="recalculate-line-net-amounts-when-importing-sales-orders-and-quotations"></a>Recalculer les montants nets des lignes lors de l’importation de commandes client et de devis

[!include [banner](../includes/banner.md)]

Cet article décrit si et comment le système recalcule les montants nets des lignes lorsque les commandes client et les devis sont importés. Il explique également comment vous pouvez contrôler le comportement dans différentes versions de Microsoft Dynamics 365 Supply Chain Management.

## <a name="how-updates-to-net-line-amounts-are-calculated-on-import"></a>Comment les mises à jour des montants de ligne nets sont calculées lors de l’importation

Supply Chain Management version 10.0.23 a introduit [bugfix 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418). Cette correction de bogue a changé les conditions dans lesquelles le champ **Montant net** d’une ligne peut être mis à jour ou recalculé lorsque des mises à jour de commandes clients et de devis existants sont importées. Dans la version 10.0.29, vous pouvez remplacer ce correctif en activant la fonctionnalité *Calculer le montant net de la ligne à l’importation*. Cette fonctionnalité a un effet similaire, mais elle fournit un paramètre global qui vous permet de revenir à l’ancien comportement si nécessaire. Bien que le nouveau comportement permette au système de fonctionner de manière plus intuitive, il peut produire des résultats inattendus dans des scénarios spécifiques où toutes les conditions suivantes sont remplies :

- Les données qui mettent à jour les enregistrements existants sont importées via l’entité *Lignes de commande client V2*, *Lignes de devis V2*, ou *Lignes de commande de retour* à l’aide du protocole Open Data Protocol (OData), y compris les situations où vous utilisez la double écriture, l’importation/exportation via Excel et certaines intégrations tierces.
- [Stratégies d’évaluation des accords commerciaux](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper) qui sont en place établissent une stratégie de changement qui limite les mises à jour au **Montant net** sur les lignes de commande client, les lignes de devis de vente et/ou les lignes de commande de retour. Notez que pour les lignes d’ordre de retour, le champ **Montant net** est toujours calculé et ne peut pas être défini manuellement.
- Les données importées incluent les modifications apportées au champ **Montant net** sur les lignes, ou des modifications (telles que le prix unitaire, la quantité ou la remise) qui entraîneront la valeur du champ **Montant net** sur les lignes à être recalculées pour un ou plusieurs enregistrements de ligne existants.

Dans ces scénarios spécifiques, la stratégie d’évaluation des accords commerciaux a pour effet de restreindre les mises à jour du champ **Montant net** sur la ligne. Cette restriction est connue sous le nom de *stratégie de changement*. En raison de cette stratégie, lorsque vous utilisez l’interface utilisateur pour modifier ou recalculer le champ, le système vous invite à confirmer si vous souhaitez apporter la modification. Cependant, lorsque vous importez un enregistrement, le système doit faire le choix pour vous. Avant la version 10.0.23, le système laissait toujours le montant net de la ligne inchangé, sauf si le montant net de la ligne entrante était de 0 (zéro). Cependant, dans les versions plus récentes, le système met toujours à jour ou recalcule le montant net selon les besoins, sauf instruction explicite de ne pas le faire. Bien que le nouveau comportement soit plus logique, il peut vous causer des problèmes si vous exécutez déjà des processus ou des intégrations qui adoptent l’ancien comportement. Cet article décrit comment revenir à l’ancien comportement si nécessaire.

## <a name="control-calculations-of-line-net-amounts-in-versions-10029-and-later"></a>Contrôler les calculs des montants nets de ligne dans les versions 10.0.29 et ultérieures

La version 10.0.29 de Supply Chain Management a introduit une fonctionnalité nommée *Calculer le montant net de la ligne à l’importation*. Cette fonctionnalité ajoute une option nommée **Calculer le montant net de la ligne** à la page **Paramètres des comptes clients**. Cette option vous permet de choisir entre le nouveau comportement et l’ancien comportement pour le calcul des montants nets de ligne lors de l’importation.

### <a name="turn-the-calculate-line-net-amount-on-import-feature-on-or-off"></a>Activez ou désactivez la fonction Calculer le montant net de la ligne à l’importation

Lorsque vous effectuez la mise à jour vers la version 10.0.29, la fonctionnalité *Calculer le montant net de la ligne à l’importation* est activée par défaut, et la nouvelle option **Calculer le montant net de la ligne** est initialement définie sur *Oui*. Le paramètre *Oui* correspond au nouveau comportement standard. Il correspond au comportement du système lorsque la fonction est désactivée, sauf dans le cas de la fonctionnalité du [Paramètre CalculateLineAmount](#CalculateLineAmount), comme décrit plus loin dans cet article. Le paramètre *Non* correspond au comportement du système avant la version 10.0.23 et est fourni principalement pour prendre en charge les scénarios d’intégration hérités.

Les administrateurs peuvent activer ou désactiver la fonctionnalité *Calculer le montant net de la ligne à l’importation* à l’aide de l’[Espace de travail de gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="set-the-calculate-line-net-amount-option"></a>Définir l’option Calculer le montant net de la ligne

Lorsque la fonctionnalité *Calculer le montant net de la ligne à l’importation* est activée, vous pouvez régler l’option **Calculer le montant net de la ligne** en suivant ces étapes.

1. Accédez à **Comptabilité client \> Configuration \> Paramètres de la comptabilité client**.
1. Dans l’onglet **Prix**, sur le raccourci **Calcul du montant net de la ligne par intégration**, définissez l’option **Calculer le montant net de la ligne** sur l’une des valeurs suivantes :

    - *Oui* – Le système recalculera et mettra à jour les montants des lignes si besoin. (Par conséquent, il ignorera la stratégie d’évaluation des accords commerciaux.)
    - *Non* – Si le montant net existant ou entrant pour une ligne est 0 (zéro), la valeur de cette ligne est recalculée en fonction d’autres valeurs (telles que le prix unitaire, la quantité et la remise). Si le montant net existant ou entrant diffère de 0 (zéro) et qu’une stratégie de changement est définie sur le champ **Montant net** sur la ligne, le champ n’est pas recalculé ni mis à jour, même lorsque des modifications entrantes du prix de la ligne, de la quantité et/ou de la remise impliquent que le total de la ligne doit être recalculé. Ce comportement correspond à celui de la version 10.0.22.

### <a name="how-the-calculate-line-net-amount-on-import-feature-affects-the-calculatelineamount-parameter"></a><a name="CalculateLineAmount"></a>Comment la fonctionnalité Calculer le montant net de la ligne à l’importation affecte le paramètre CalculateLineAmount

Quand la fonctionnalité *Calculer le montant net de la ligne à l’importation* est activée, la valeur du paramètre `CalculateLineAmount` pour les tables `SalesLine` et `SalesQuotationLine` n’a aucun effet. Au lieu de cela, le comportement est contrôlé globalement par l’option **Calculer le montant net de la ligne** décrite dans la section précédente. Par conséquent, lorsque la fonctionnalité est activée, vous ne devez pas prendre de dépendance sur la valeur `CalculateLineAmount`.

Quand la fonctionnalité *Calculer le montant net de la ligne à l’importation* est désactivée, le paramètre `CalculateLineAmount` pour les tables `SalesLine` et `SalesQuotationLine` fonctionnent comme dans les versions 10.0.23 à 10.0.28 de Supply Chain Management, comme décrit dans la section suivante.

## <a name="control-line-net-amount-calculations-in-versions-10028-and-earlier"></a>Calculs des montants nets de ligne dans les versions 10.0.28 et antérieures

Lorsque [correction de bug 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418) a été introduit dans la version 10.0.23, il est devenu possible de sélectionner le comportement de chaque entité de données pertinente lorsqu’un montant net de ligne a été modifié ou a dû être recalculé en raison d’autres modifications (comme un prix d’article mis à jour). Vous pouviez contrôler ce comportement en définissant le nouveau paramètre `CalculateLineAmount` pour chaque ligne sur l’une des valeurs suivantes dans le fichier importé :

- **`CalculateLineAmount` = *1*** - Le champ **Montant net** sur la ligne est toujours recalculé et mis à jour, qu’une stratégie de changement soit définie pour le champ ou non, et quelle que soit la valeur du montant net de la ligne entrante ou existante.
- **`CalculateLineAmount` = *0*** – Si le montant net existant ou entrant pour une ligne est 0 (zéro), la valeur de cette ligne est recalculée en fonction d’autres valeurs (telles que le prix unitaire, la quantité et la remise). Si le montant net existant ou entrant diffère de 0 (zéro) et qu’une stratégie de changement est définie sur le champ **Montant net** sur la ligne, le champ n’est pas recalculé ni mis à jour.  

Le comportement du système dépend de votre version de Supply Chain Management :

- Dans la version 10.0.22 et les versions antérieures, le système se comporte toujours comme si `CalculateLineAmount` était défini sur *0*, et il n’y a aucun moyen de le faire se comporter comme si `CalculateLineAmount` était défini sur *1*.
- Dans les versions 10.0.23 à 10.0.28, le système se comporte comme si `CalculateLineAmount` était réglé sur *1* pour toutes les lignes où il n’est pas explicitement défini sur *0* dans le fichier d’importation.
