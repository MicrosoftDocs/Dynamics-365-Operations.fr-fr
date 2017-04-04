---
title: "Régularisation des coûts de projet dans les réceptions d&quot;achat"
description: "Cette rubrique décrit la manière dont les coûts de projet à des réceptions d&quot;achat peuvent être suivis dans Microsoft Dynamics 365 pour les opérations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 27a0a71095dce46c0119b32a92f8c4dce0f42e43
ms.lasthandoff: 03/31/2017


---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Régularisation des coûts de projet dans les réceptions d'achat

Cette rubrique décrit la manière dont les coûts de projet à des réceptions d'achat peuvent être suivis dans Microsoft Dynamics 365 pour les opérations. 

Les factures pour un projet arrive souvent plus tard que les marchandises et les services sont livrés, qui peuvent avoir un impact considérable sur des indicateurs de performance clé (KPIs) du projet. Il important pour pouvroir suivre ces transactions dans des rapports financiers et de projet.

Le scénario suivant d'exemple illustre cette opération. 

Le conseil de Contoso a commencé un nouveau projet de déploiement de cloud. Une commande fournisseur est créée d'acheter un ordinateur pour le projet. L'ordinateur évalue les coûts $1500 et les services d'installation évaluent les coûts $. Le fournisseur a donné et a installé l'ordinateur, mais la facture n'a pas encore été atteint le conseil de Contoso. Le chef de projet souhaite voir la régularisation de coût d'un projet de $1650 pour que la facture soit livrée. Le coût doit également être pris en compte dans les tableaux d'analyse du mois de la société. 

Les charges à payer doivent être enregistrées au niveau financier et le niveau du projet pour la génération d'états. Dans Dynamics 365 pour les opérations, la mise à jour financière de l'accusé de réception de marchandises peut être appliquée à l'article et les catégories d'approvisionnement. 

Pour les articles, sous ** des paramètres des achats ** la page, sélectionnez ** validez les accusés de réception de marchandises dans la comptabilité ** l'option.
![accruals1 [] (. /media/accruals1-1024x409.png)](. /media/accruals1.png) 

Pour les catégories d'approvisionnement, sous ** règle de stratégie de catégorie ** la page, sélectionnez ** d'achat ** les stratégies, puis sélectionnez ** provisionner les dépenses d'achat sur le ticket de caisse ** pour chaque catégorie d'approvisionnement.
![accruals2 [] (. /media/accruals2-1024x569.png)](. /media/accruals2.png) 

** Dépense d'achat non facturées ** et ** régularisation des achats ** des comptes dans ** paramétrage de la validation ** seront utilisés lorsque les documents associés à l'accusé de réception de marchandises sont validés.
![accruals3 [] (. /media/accruals3-1024x429.png)](. /media/accruals3.png) 

L'utilisation de ce même scénario, laissez- nous voir comment valider un accusé de réception de marchandises ont un impact sur la comptabilité et les informations de projet. 

** Étape 1 : ** Créez et confirmez une commande fournisseur pour le projet enregistre l'achat d'un ordinateur pour $1500 et des services d'installation pour $.
![accruals4 [] (. /media/accruals4-1024x497.png)](. /media/accruals4.png) 

Lorsque la commande fournisseur est confirmée, les transactions pour le coût engagé pour le projet. 
![accruals5 [] (. /media/accruals5-1024x219.png)](. /media/accruals5.png) 

> [!NOTE]
> Les transactions pour le coût engagé auront ** origine de la transaction ** le champ défini ** commande fournisseur **. Création et confirmant une commande fournisseur ne crée pas de transaction pour un projet. 

** Étape 2 : ** Les marchandises et les services obtiennent livrés et un accusé de réception de marchandises est enregistré. 

Valider un accusé de réception de marchandises génère et valide un document dans la comptabilité. Le document débit les dépenses d'achat, le compte des facturé, et le compte de régularisation des achats de crédit. 
![accruals6 [] (. /media/accruals6-1024x214.png)](. /media/accruals6.png)

> [!NOTE]
> La comptabilisation d'un accusé de réception de marchandises utilise le paramétrage de la validation pour les catégories d'approvisionnement et les produits, et non le paramétrage de la validation pour les catégories de projet. Afin de refléter correctement l'impact financier des régularisations d'achat, il les besoins définis d'être aligné. 

Il est possible de mettre des catégories d'approvisionnement aux catégories de projet sur ** catégorie d'approvisionnement ** la page.
![accruals7 [] (. /media/accruals7-1024x390.png)](. /media/accruals7.png)

** Étape 3 : ** Création d'une facture fournisseur temporaire. 

Dans Dynamics 365 pour les opérations, la validation d'un accusé de réception de marchandises ne concerne pas les informations de projet. Comme contournement, vous pouvez générer une facture fournisseur de brouillon {{juste:right_after}} {{après:right_after}} valider la réception. Allez ** commande fournisseur ** à la page &gt; ** onglet Facture ** &gt; ** se produisent ** &gt; ** facture **. Cette action crée un document de facture en attente qui met les informations de projet à jour. 

Créer une facture fournisseur d'effet se produit en attente des transactions de projet. 
![accruals8 [] (. /media/accruals8-1024x225.png)](. /media/accruals8.png) 

Dans ** coût engagé ** la page, les enregistrements créés à l'étape 1 sont terminées et de nouveaux enregistrements sont créés pour refléter l'engagement du coût provenant de la facture fournisseur en attente. ** Origine de la transaction ** le champ pour le coût engagé est défini ** facture fournisseur **.
![accruals9 [] (. /media/accruals9-1024x200.png)](. /media/accruals9.png)

La facture fournisseur reste dans un rapport en attente jusqu'à ce que la facture fournisseur arrive réelle.


