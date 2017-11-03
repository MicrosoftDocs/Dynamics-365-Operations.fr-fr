---
title: Dates limites de saisie de commande
description: "Cet article fournit des informations sur les dates limites de saisie de commande. Un date limite de saisie de commande est une heure limite qui détermine si une commande client est traitée (et exécutée) comme si elle avait été reçue le jour même ou le lendemain."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOrderEntryDeadlineGroup, InventOrderEntryDeadlineParameters, InventOrderEntryDeadlineTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 7151
ms.assetid: bbc4f9a2-df4b-4d92-9f18-25282a85541f
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9e9d1912abf9a356542ce2c317fa717bc991dbf9
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="order-entry-deadlines"></a>Dates limites de saisie de commande

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur les dates limites de saisie de commande. Un date limite de saisie de commande est une heure limite qui détermine si une commande client est traitée (et exécutée) comme si elle avait été reçue le jour même ou le lendemain.

Dans de nombreuses sociétés, seules les commandes client reçues avant une certaine heure de la journée sont traitées comme si elles étaient reçues ce jour. Les commandes reçues après cette heure sont traitées comme si elles sont reçues le jour ouvrable suivant. Cette heure limite pour les commandes est appelée date limite de saisie de commande.  

Les dates limites de saisie de commande sont utilisées comme entrée pour la promesse de commande. Par conséquent, elles vous permettent de gérer les attentes des clients concernant les livraisons de commande. Par exemple, les clients peuvent voir que, s'ils passent une commande avant une certaine heure, vous vous engagez à expédier les marchandises le même jour. Toutefois, s'ils ne respectent pas cette date limite, les marchandises ne sont expédiées que le jour ouvrable suivant. Vous définissez les dates limites de saisie de commande en fonction des capacités de votre entrepôt et des plannings du transporteur.  

Dans la page **Dates limites de saisie de commande**, vous paramétrez l'heure limite de saisie des commandes pour tous les jours de la semaine. Si les commandes sont reçues après l'heure spécifiée, elles sont traitées comme si elles sont reçues le jour suivant. Par défaut, l'heure limite est fixée à 23h59, c'est-à-dire une minute avant minuit à la fin de la journée concernée. Vous pouvez modifier l'heure par défaut afin qu'elle coïncide avec les heures limites réelles d'expédition ou de réception.  

Vous pouvez définir des dates limites de saisie de commande pour un groupe spécifique de clients. Par exemple, vous souhaitez qu'un groupe spécifique de clients bénéficie de dates limites de saisie de commande plus souples que la majorité de vos clients. Dans ce cas, vous définissez d'abord des groupes pour les dates limites de saisie de commande dans la page **Groupes de dates limites de saisie de commande**. Vous affectez ensuite les groupes aux clients dans la page **Clients**.  

Si votre société comporte plusieurs sites, vous pouvez paramétrer des dates limites de saisie de commande pour chaque site. Si les sites sont situés dans différents fuseaux horaires, les dates limites de saisie de commande doivent être paramétrées dans le fuseau horaire de chaque site. Cependant, lors du traitement des commandes client et des devis de vente, la date limite de saisie de commande est convertie en une date appropriée à votre fuseau horaire dans la page **Dates d'expédition et de réception disponibles**.  

Dans la page **Activer les combinaisons de dates limites de saisie de commande**, vous définissez les combinaisons autorisées de sites et de groupes de dates limites de saisie de commande.

## <a name="example-order-entry-deadline"></a>Exemple : date limite de saisie de commande
La date limite de saisie de commande les mardis a été fixée à 16h00. Un mardi, à 17h00, vous essayez de définir la date du jour comme date d'expédition. (Notez qu'il n'existe aucun délai pour cet exemple.) Si la case à cocher **Vérification de la date de livraison** est activée, vous recevez un avertissement indiquant que la date n'est pas valide. Cet avertissement s'affiche dans la page **Dates d'expédition et de réception disponibles**, dans laquelle vous pouvez sélectionner d'autres dates.

## <a name="example-different-order-entry-deadlines-per-site"></a>Exemple : dates limites de saisie de commande différentes pour chaque site
Votre société comporte deux sites. Les sites sont situés dans différents fuseaux horaires, comme indiqué dans le tableau suivant.

| Site A                      | Site B                      |
|-----------------------------|-----------------------------|
| Californie                  | Floride                     |
| Pacifique | Est |

Les sites A et B ont défini les dates limites de saisie de commande suivantes.

| Jour de la semaine             | A : Dates limites de saisie de commande (Pacifique) | B : Dates limites de saisie de commande (Est) |
|-----------------------------|--------------------------------|--------------------------------|
| Lundi                      | 13h00                          | 14h00                          |
| Mardi                     | 13h00                          | 14h00                          |
| Mercredi                   | 13h00                          | 14h00                          |
| Jeudi                    | 13h00                          | 14h00                          |
| Vendredi                      | 13h00                          | 14h00                          |

Vous êtes chargé de traiter les commandes dans l'État de l'Utah, où le fuseau horaire est « heure standard des Rocheuses ». Ainsi, vous respectez les dates limites de saisie de commande pour les deux sites à condition que vous passez des commandes avant 14h00 pour le site A (heure standard des Rocheuses) et avant 12h00 pour le site B (heure standard des Rocheuses).  

Le tableau suivant indique comment les dates limites de saisie des commandes pour les sites A et B sont converties en heure standard des Rocheuses.

| Site A : Pacifique         | Site A : Rocheuses        | Site B : Est           | Site B : Rocheuses        |
|---------------------|--------------------|-----------------------|--------------------|
| 13h00               | 14h00              | 14h00                 | 12h00              |

**Remarque :** si l'heure d'été est appliquée, les dates limites de saisie de commande sont ajustées en conséquence.

## <a name="example-same-order-entry-deadline-per-site"></a>Exemple : même date limite de saisie de commande pour tous les sites
Votre société comporte deux sites. Les sites sont situés dans différents fuseaux horaires, comme indiqué dans le tableau suivant.

| Site A                      | Site B                      |
|-----------------------------|-----------------------------|
| Californie                  | Floride                     |
| Pacifique | Est |

Les sites A et B ont défini les dates limites de saisie de commande suivantes.

| Jour de la semaine | Pacifique et Est |
|-----------------|-------------|
| Lundi          | 13h00       |
| Mardi         | 13h00       |
| Mercredi       | 13h00       |
| Jeudi        | 13h00       |
| Vendredi          | 13h00       |

Vous êtes chargé de traiter les commandes dans l'État de l'Utah, où le fuseau horaire est « heure standard des Rocheuses ». Ainsi, vous respectez les dates limites de saisie de commande pour les deux sites à condition que vous passez des commandes avant 14h00 pour le site A (heure standard des Rocheuses) et avant 11h00 pour le site B (heure standard des Rocheuses). 

Le tableau suivant indique comment les dates limites de saisie des commandes pour les sites A et B sont converties en heure standard des Rocheuses.

| Site A : Pacifique         | Site A :Rocheuses        | Site B : Est           | Site B : Rocheuses        |
|---------------------|--------------------|-----------------------|--------------------|
| 13h00               | 14h00              | 13h00                 | 11h00              |

**Remarque :** si l'heure d'été est appliquée, les dates limites de saisie de commande sont ajustées en conséquence.

<a name="see-also"></a>Voir également :
--------

[Plans de livraison](delivery-schedules.md)




