---
title: " Ajustements de prix de la vente au détail"
description: Cette procédure décrit la création d'un ajustement du prix de vente au détail.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailDiscountPriceGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9427d3955e5442e301c416e2960e071ca5d85a3c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "366303"
---
# <a name="retail-price-adjustments"></a> Ajustements de prix de la vente au détail

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure décrit la création d'un ajustement du prix de vente au détail. Un ajustement du prix de vente au détail permet de définir directement le prix de vente d'un article, ou de modifier son prix de vente de base ou le prix de vente indiqué dans l'accord commercial. La société fictive USRT sert d'exemple dans cette procédure.

1. Cliquez sur Gestion de la tarification et des remises.
2. Cliquez sur l'onglet Ajustements de prix.
3. Cliquez sur Nouveau.
    * Vous pouvez créer toutes les règles de tarification et de remise les plus fréquemment utilisées, notamment les remises de vente au détail, les ajustements de prix, les journaux d'accords commerciaux et les règles de tarification de catégorie.  
4. Cliquez sur Ajustement de prix.
5. Tapez une valeur dans le champ Nom.
6. Développez la section Lignes.
7. Cliquez sur Ajouter.
    * Pour cet exemple, saisissez « 81126 » dans le champ Produit.    Ensuite, saisissez « 10.0 » dans le champ Pourcentage de remise.  
    * Un ajustement de prix de type Pourcentage de remise réduit un prix de vente de base ou le prix de vente indiqué dans l'accord commercial.  
8. Cliquez sur Ajouter.
    * Pour cet exemple, saisissez « 81125 » dans le champ Produit.    Ensuite, sélectionnez « Montant de l'escompte de règlement » dans le champ Méthode d'application de la remise.    Enfin, saisissez « 5.0 » dans le champ Montant de l'escompte de règlement.  
    * Le type de remise Montant de l'escompte de règlement est un montant déduit d'un prix de base ou du prix indiqué dans un accord commercial.  
9. Cliquez sur Groupes de prix.
    * Sélectionnez « RP-Houston » dans le champ Groupe de prix.  
    * L'ajustement de prix sera associé au magasin de Houston.  
10. Cliquez sur Enregistrer.
11. Fermez la page.
12. Dans le champ Statut, sélectionnez « Activé ».
13. Cliquez sur Enregistrer.
14. Fermez la page.
15. Actualisez la page.

