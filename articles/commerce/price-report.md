---
title: États sur les prix de vente au détail
description: Cet article fournit une vue d’ensemble de la fonction d’état de prix qui peut être utilisée pour afficher les changements de prix à venir pour les produits assortis.
author: ShalabhjainMSFT
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: global
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 09350d15660978126d36199a3b4e93f6be5fe157
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269025"
---
# <a name="retail-price-reports"></a>États sur le prix de vente au détail

[!include [banner](includes/banner.md)]


Afin de fournir des prix concurrentiels à leurs clients, les détaillants changent souvent les prix des produits. Les directeurs de magasins souhaitent pouvoir accéder facilement aux changements de prix récents ou à venir afin de pouvoir planifier les ressources requises pour mettre à jour les étiquettes de prix affichées sur les étagères en boutique. Avec la version 10.0 de Retail, un directeur de magasin peut ouvrir l’état **Prix** en accédant à **Tous les magasins \> Magasin \> État de prix** et en affichant les prix mis à jour pour les produits associés au magasin. 

Pour activer l’état de prix, le paramètre **Activer l’état de prix pour le magasin** doit être activé. Ce paramètre se trouve sous **Paramètres de commerce \> Remises \> Divers**. En ouvrant la page **État de prix**, une boîte de dialogue s’affiche avec différentes configurations. Les configurations disponibles sont répertoriées ci-dessous.

| Configuration | Description |
|---|---|
| Date de début/de fin| La plage de dates pour laquelle l’état de prix doit être généré. La durée est actuellement limitée à 7 jours. |
| Canal| Le magasin pour lequel l’état de prix doit être généré. |
| Afficher les produits avec le stock disponible| En définissant ce paramètre sur **Oui**, les prix s’affichent uniquement pour les produits avec un stock disponible en magasin. |
| Afficher les prix des variantes | En définissant ce paramètre sur **Oui**, les prix des variantes s’affichent ainsi que les produits génériques. Ce paramètre doit être défini sur **Activé** si vous avez des prix spécifiques aux variantes, car le nombre de lignes grandit de plus en plus. Dans les versions à venir, nous activerons les prix selon les dimensions, afin que le responsable du magasin puisse choisir les dimensions pour lesquelles les prix doivent être affichés. |
| Afficher les produits avec les modifications de prix | En définissant ce paramètre sur **Oui**, les prix s’affichent pour uniquement ces dates auxquelles le prix a été modifié. Le prix pour *un jour avant* la **Date de début** sélectionnée sera toujours affichée, de telle sorte que le responsable du magasin peut facilement identifier les produits dont les prix n’ont pas changé pendant l’intégralité de la durée, et peut également visualiser le prix actuel. |

Une fois l’état généré, le fichier Excel peut être téléchargé pour tout besoin de filtre supplémentaire. L’état de prix peut être également utilisé pour vérifier les prix historiques des produits pour les dates passées.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
