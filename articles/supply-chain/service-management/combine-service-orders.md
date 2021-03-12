---
title: Combiner les commandes de service
description: Vous pouvez combiner les commandes de service.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 55de251f7f9cdbae99eaec13d4ddd7d3bf26b2bb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996675"
---
# <a name="combine-service-orders"></a>Combiner les commandes de service   

[!include [banner](../includes/banner.md)]


Lorsque vous créez des lignes de commande automatiquement dans l'écran **Accords de service**, vous avez le choix entre les options suivantes pour spécifier la manière selon laquelle vous souhaitez les regrouper.

  - **Par accord de service**

  - **Par tâche de service**

  - **Par employé**

  - **Par objet de service**

## <a name="example"></a>Exemple

Créez un accord de service pour lequel la date de début est le 31-03-2007. Dans le champ **Combiner les commandes de service**, spécifiez **Par objet de service**. Créez ensuite les lignes d'accord de service suivantes :

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Numéro de ligne d'accord</p></th>
<th><p>Type de transaction</p></th>
<th><p>Description</p></th>
<th><p>Intervalle</p></th>
<th><p>Objet du service</p></th>
<th><p>Date de début</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p><strong>Heure</strong></p></td>
<td><p>LAS1</p></td>
<td><p>Hebdomadairement</p></td>
<td><p>X-1</p></td>
<td><p>01-04-2007</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p><strong>Heure</strong></p></td>
<td><p>LAS2</p></td>
<td><p>Bimensuel</p></td>
<td><p>X-2</p></td>
<td><p>01-04-2007</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p><strong>Heure</strong></p></td>
<td><p>LAS3</p></td>
<td><p>Hebdomadairement</p></td>
<td><p>X-2</p></td>
<td><p>01-04-2007</p></td>
</tr>
</tbody>
</table>


Vous ne devez pas spécifier de fenêtre Délai pour les lignes d'accord de service. Par conséquent, les lignes de commande de service ne bougent plus à partir du jour d'échéance calculé.

Ensuite, vous devez générer des lignes de commande de service à partir de l'écran **Créer des commandes de service** du 01-04-2007 au 30-04-2007.

En tout, dix commandes de service sont créées. Étant donné que le paramétrage combiné que vous avez sélectionné était **Par objet de service**, toutes les commandes de service créées ne possèdent que des lignes de commande de service avec un objet de service spécifique. Les lignes de commande de service générées à partir de l'accord de service et présentant la même date de service et le même objet sont combinées dans la même commande de service.


> [!NOTE]
> <P>Dans cet exemple, le calendrier spécifié dans l'écran <STRONG>Paramètres de gestion des services</STRONG> ne contient pas de jours clôturés.</P>



Un regroupement supplémentaire de lignes de commande de service en commandes de service a lieu avec toutes les fenêtres Délai spécifiées dans les lignes de l'accord de service.

## <a name="see-also"></a>Voir également :

[Création de commandes de service automatiquement](create-service-orders-automatically.md)

  


