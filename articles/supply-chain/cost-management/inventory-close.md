---
title: "Clôture du stock"
description: "Dans le cadre du processus pour régler les transactions de sortie avec des transactions de réception, vous pouvez également choisir de mettre à jour la comptabilité pour refléter les ajustements effectués."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventClosing
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 61973
ms.assetid: c210c882-6849-4704-b78c-a777dd6cfdb6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc192b332bd736fd2ba1aac16e9e4614f3afc1dd
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="inventory-close"></a>Clôture du stock

[!include[banner](../includes/banner.md)]


Dans le cadre du processus pour régler les transactions de sortie avec des transactions de réception, vous pouvez également choisir de mettre à jour la comptabilité pour refléter les ajustements effectués.

La clôture du stock règle les transactions de sortie avec des transactions de réception sur la base du modèle d'évaluation du stock sélectionné dans le groupe de modèles d'article associé à l'article. Dans le cadre de le processus de règlement, vous pouvez spécifier que la comptabilité doit être mise à jour, afin qu'elle indique les ajustements effectués. Toutefois, jusqu'à la clôture ou l'exécution d'un nouveau calcul du stock, les transactions de sortie sont validées au prix de revient moyen actuel calculé. 

Après la clôture du stock, vous ne pouvez plus valider des périodes antérieures à la date de clôture que vous avez définie, sauf si vous contrepassez un processus de clôture de stock terminé. Par exemple, si la clôture du stock est effectuée pour la période qui se termine le 31 janvier, vous ne pouvez pas valider les transactions associées à une date antérieure au 31 janvier. 

Les articles du stock sont affectés à l'un des deux types de stocks suivants : article ou service. La clôture du stock effectue les mêmes fonctions pour les deux types. Toutefois, pour des articles de service, la clôture de stock règlera toujours les sorties avec les réceptions. 

La fréquence à laquelle le processus de clôture du stock est effectué selon la société. Toutefois, le volume de transaction devrait permettre de déterminer la fréquence à laquelle vous devez exécuter la clôture de stock. Généralement, les sociétés effectuent la clôture du stock dans le cadre de leurs procédures de clôture et de rapprochement de fin de mois.

## <a name="inventory-recalculation-and-the-general-ledger"></a>Nouveau calcul du stock et de la comptabilité
Si des ajustements dans la comptabilité et le stock sont requis au cours d'un mois ou d'une autre période de stock, vous pouvez effectuer un nouveau calcul de stock à la place d'une clôture de stock. Cette procédure apporte des ajustements aux mouvements de stock sans les régler. 

Lors du nouveau calcul du stock, le stock disponible est ajusté, les mouvements de stock sont ajustés et les nouveaux calculs de stock ainsi que les clôtures de stock sont exécutés. Ces tâches affectent les comptes généraux liés au mouvement de stock d'origine. 

**Exemple** 

Lorsque vous créez une commande fournisseur à partir d'une commande client, les comptes généraux utilisés pour la commande client d'origine sont mis à jour. Même si les comptes généraux du groupe d'articles affecté à cet article ont changé après la validation de la commande client et qu'un nouveau calcul de stock a créé un montant d'ajustement, le montant d'ajustement est validé dans les comptes généraux d'origine. Le montant ajusté n'est pas validé dans les nouveaux comptes généraux affectés à l'article. 

À l'issue de la mise à jour, vous pouvez passer en revue le numéro de document comptable qui a été validé suite à l'une de ces tâches.

1.  Sur la page **Clôture et ajustement**, sous l'onglet **Vue d'ensemble**, sélectionnez la mise à jour à réviser.
2.  Cliquez sur **Détails**, puis sélectionnez **N° document**.

## <a name="effects-of-the-inventory-close-process-on-the-general-ledger"></a>Effets du processus de clôture de stock dans la comptabilité
Plusieurs tâches exécutables sur la page **Clôture et ajustement** engendrent à une mise à jour dans la comptabilité. La comptabilité est notamment mise à jour lorsque vous effectuez des ajustements des mouvements de stock, des ajustements de transaction de stock, un nouveau calcul de stock et une clôture de stock. 

Les comptes généraux mis à jour par ces tâches sont liés au mouvement de stock d'origine. Par exemple, si une commande client est réglée avec une commande fournisseur, les comptes généraux utilisés pour la commande client d'origine sont ajustés. Ce comportement se produit même si les comptes généraux pour le groupe d'articles affecté à cet article ont changé depuis la validation de la commande client. Après qu'une clôture de stock a créé un montant de règlement, le montant de règlement est toujours validé sur les comptes généraux d'origine, pas sur les nouveaux comptes généraux affectés à l'article. La comptabilité pourrait également être mise à jour si vous contrepassez une clôture de stock. 

**Remarques :**

-   Vous n'êtes plus obligé d'utiliser la méthode Évaluation du coût standard pour clôturer un stock.
-   Avant d'exécuter la procédure de clôture, vous pouvez afficher une liste d'articles impossibles à régler lors de la mise à jour.
-   Nous vous recommandons de clôturer le stock en dehors des heures de bureau afin de distribuer les ressources de calcul plus équitablement.

## <a name="the-inventory-close-log"></a> Journal des clôtures de stock
Une fois le processus de clôture de stock terminé, un message dans le centre des messages peut vous informer qu'un prix unitaire est incorrect si une transaction n'est pas entièrement réglée. 

Avant l'affichage de ce message, le système indique le numéro de l'article et la transaction affectée. Le message vous indique que le montant utilisé pour cette transaction n'a pas été mis à jour en raison de la clôture de stock. Ce message s'affiche lorsqu'une transaction du type sortie ne peut pas être réglée. 

Lors du processus de clôture de stock, le système vérifie chaque dimension financière afin de déterminer s'il y a plus de sorties que de réceptions à la date de clôture spécifiée. Ce type de déséquilibre peut survenir lorsque le mouvement de stock d'une commande fournisseur n'est pas complètement validé financièrement, soit parce que la facture fournisseur n'a pas été reçue, soit parce que des composants de nomenclature (BOM) inclus dans la fabrication sur un niveau supérieur ne sont pas validés financièrement. (La sous-production n'est pas calculée.) Dans ce cas, la clôture ultérieure n'ajustera pas toutes les sorties au prix de revient correspondant car les informations de réception disponibles sont insuffisantes. 

Pour chaque exécution de la procédure de clôture, le système indique si un journal contenant les avertissements est enregistré et peut être affiché. 

Si vous recevez plusieurs avertissements dans le message, nous vous recommandons d'exécuter les actions suivantes :

-   Mettez financièrement à jour les réceptions.
-   Avancez la date de clôture.
-   Réévaluez les procédures commerciales.

Dans certaines circonstances, vous ne pourrez peut-être pas résoudre les avertissements. Par exemple, si un marquage est utilisé et que la date financière de la commande fournisseur marquée est postérieure à la date de clôture, il est impossible de modifier la date de clôture.

## <a name="reversing-a-completed-inventory-close"></a>Contrepasser une clôture de stock terminée
Il se peut que vous deviez occasionnellement contrepasser une clôture de stock terminée pour redéfinir les règlements sur l'état où ils se trouvaient avant les ajustements. Lorsque vous contrepassez une clôture de stock terminée, le stock est rouvert pour permettre la validation dans la période couverte par la clôture de stock. Les modifications liées peuvent également être introduites dans la comptabilité. Après avoir apporté des ajustements, vous pouvez effectuer de nouveau une clôture de stock pour la période sur laquelle vous travaillez. 

**Remarque :** Seule la dernière période de stock clôturée peut être rouverte. Pour contrepasser une clôture de stock antérieure, vous devez contrepasser chaque clôture de stock une par une, en commençant par la plus récente.




