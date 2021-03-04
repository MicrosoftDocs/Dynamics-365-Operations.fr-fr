---
title: Amortissement de la prime
description: Cet article offre une vue d’ensemble de la fonctionnalité d’amortissement de la prime.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 687ba57042ad65d3a1ff4ad92f0da774c6751eac
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443051"
---
# <a name="bonus-depreciation"></a>amortissement de la prime

[!include [banner](../includes/banner.md)]

Cet article offre une vue d’ensemble de la fonctionnalité d’amortissement de la prime.

Pour l’amortissement de la prime, vous pouvez prendre des montants d’amortissement exceptionnel ou de la prime au cours de la première année de mise en service et d’amortissement de l’immobilisation. L’amortissement de la prime doit être pris avant tout autre calcul d’amortissement. Par conséquent, il est recommandé d’utiliser l’amortissement de la prime avec des registres pour lesquels la fonctionnalité Valider dans la comptabilité est désactivée. Vous pouvez utiliser l’option **Supprimer les transactions non validées dans la comptabilité** pour supprimer les transactions historiques des registres qui ne sont pas validés dans la comptabilité. Vous pouvez ensuite utiliser l’amortissement de la prime plus tard au cours du cycle de vie de l’immobilisation en supprimant les transactions d’amortissement précédemment validées. 

Vous pouvez calculer un amortissement de la prime à l’aide du processus de proposition, ou créer des transactions manuelles d’amortissement de la prime. Vous ne pouvez pas créer de transaction d’amortissement de la prime si des transactions d’amortissement ou d’ajustement de l’amortissement existent pour ce registre d’actifs.

Si vous utilisez le processus de proposition pour calculer un amortissement de prime, toutes les transactions de prime existantes sont incluses dans le calcul de la base. Le calcul inclut également tout amortissement de prime précédent entré manuellement pour l’immobilisation. 

Si plusieurs amortissements de prime doivent être pris pour une immobilisation, la priorité est prise en considération. Chaque prime réduit la base des actifs pour la prime suivante. La valeur résiduelle n’est pas prise en compte dans la base des actifs pour les calculs d’amortissement de la prime, et la convention d’amortissement ne s’applique pas pour l’amortissement de la prime. 

Actuellement, aux États-Unis, certaines propriétés sont qualifiées comme propriétés de la section 179. La déduction au titre de la section 179 vous permet de récupérer tout ou partie du coût de certaines propriétés, dans une certaine limite. Vous pouvez récupérer le coût en le déduisant au cours de l’année pendant laquelle la propriété a été mise en service.

## <a name="example"></a>Exemple
Les amortissements de prime suivants sont associés à un registre des immobilisations :

-   **Section 179 :** 1 000,00, Priorité 1
-   **Zone de Liberty :** 30 %, Priorité 2

Le coût d’acquisition d’immobilisation est de 5 000,00 USD. Lors du calcul de l’amortissement de la prime, le premier montant d’amortissement est de 1 000,00 pour l’amortissement au titre de la section 179. 

Le montant d’amortissement de la prime suivant (pour l’amortissement dans la zone de Liberty) est calculé comme suit : 

Coût d’acquisition – 1 000 (amortissement au titre de la section 179) x 30 % = 1 200 

Si le montant d’amortissement de la prime est supérieur au coût d’acquisition restant, le montant d’amortissement de la prime est le plus bas des montants suivants : calcul d’amortissement de la prime ou coût d’acquisition restant. 

Si le coût d’acquisition restant est égal ou inférieur à 0 (zéro), aucune transaction d’amortissement de prime n’est générée. 

En cas de calcul de l’amortissement de la prime à l’aide du processus de proposition, une transaction d’amortissement de prime est créée pour tous les enregistrements d’amortissement de la prime applicables associés au registre des immobilisations. 

Vous pouvez créer un nombre illimité d’enregistrements d’amortissement de la prime. Une fois que vous affectez ces enregistrements à un registre de groupe d’immobilisations, ils sont appliqués au registre des immobilisations. 

L’amortissement de la prime est entré comme pourcentage ou montant fixe. Lorsque vous validez des propositions d’amortissement, les transactions d’amortissement de la prime sont validées dans le registre comme transactions distinctes des transactions d’amortissement.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]