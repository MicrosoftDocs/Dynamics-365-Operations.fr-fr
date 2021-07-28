---
title: Régularisation des coûts de projet dans les réceptions d’achat
description: Cette rubrique décrit comment les coûts de projet régularisés depuis les réceptions d’achat peuvent être suivis dans Microsoft Dynamics 365 Finance.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: roschlom
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 888ce67f1feba9876f71d2988268b47c9a4ca1dd
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358879"
---
# <a name="project-cost-accrual-on-purchase-receipts"></a>Régularisation des coûts de projet dans les réceptions d’achat

[!include [banner](../includes/banner.md)]

Cette rubrique décrit comment les coûts de projet régularisés depuis les réceptions d’achat peuvent être suivis dans Microsoft Dynamics 365 Finance. 

Les factures pour un projet arrivent souvent plus tard que les marchandises et les services livrés, ce qui peut avoir un impact considérable sur des indicateurs de performance clé (KPIs) du projet. Il est important de pouvroir suivre ces transactions dans des rapports financiers et de projet.

L’exemple de scénario suivant illustre cela. 

Contoso Consulting a démarré un nouveau projet de déploiement de cloud. Une commande fournisseur est créée pour acheter un ordinateur pour le projet. L’ordinateur évalue le coût à $1500 et les services d’installation à $150. Le fournisseur a livré et installé l’ordinateur, mais la facture n’est pas encore arrivée chez Contoso Consulting. Le chef de projet souhaite voir la régularisation du coût du projet de $1650 pour que la facture soit remise. Le coût doit également être pris en compte dans les tableaux d’analyse du mois de la société. 

Les charges à payer doivent être enregistrées au niveau financier et au niveau du projet pour la génération d’états. La mise à jour financière de l’accusé de réception de marchandises peut être appliquée à l’article et aux catégories d’approvisionnement. 

Pour les articles, sur la page **Paramètres de la comptabilité fournisseur**, sélectionnez l’option de **publication des reçus de produits dans la comptabilité**.
[![Page Paramètres de la comptabilité fournisseur.](./media/accruals1-1024x409.png)](./media/accruals1.png) 

Pour les catégories d’approvisionnement, sur la page **Règle de stratégie de catégorie**, sélectionnez les politiques **d’achat**, puis sélectionnez **Provisionner les dépenses d’achat à la réception** pour chaque catégorie d’approvisionnement.
[![Page de la règle de stratégie de catégorie.](./media/accruals2-1024x569.png)](./media/accruals2.png) 

Les comptes **Dépenses d’achat, non facturées** et **Régularisation d’achat** dans **Paramétrage de la validation** seront utilisés lorsque les documents associés à l’accusé de réception de marchandises seront publiés.

En utilisant ce même scénario, voyons comment la publication d’un reçu de produit aura une incidence sur les informations de comptabilité et de projet. 

**Étape 1 :** Création et confirmation d’un nouveau bon de commande pour le projet afin d’enregistrer l’achat d’un ordinateur pour $1500 et les services d’installation pour $150.
[![Créer une commande fournisseur.](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Lorsque la commande fournisseur est confirmée, les transactions pour le coût engagé sont créées pour le projet. 
[![Transactions créées.](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> Les transactions pour le coût engagé auront le champ **Origine de la transaction** défini sur **Bon de commande**. La création et la confirmation d’une commande fournisseur ne créent pas de transaction pour un projet. 

**Étape 2 :** Les marchandises et les services sont livrés et un accusé de réception de marchandises est enregistré. 

Valider un accusé de réception de marchandises génère et valide un document dans la comptabilité. Le N° document débite le compte non facturée de dépense d’achat et le compte de régularisation des achats à crédit. 
[![Pièces comptables.](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> L’affichage d’un reçu de produit utilisera la configuration de publication pour les catégories et produits d’approvisionnement, et non la configuration de publication pour les catégories de projet. Afin de refléter correctement l’impact financier des régularisations d’achat, cette configuration doit être alignée. 

Il est possible de mettre en correspondance des catégories d’approvisionnement avec des catégories de projet sur la page **Catégorie d’approvisionnement**.
[![Page de catégorie d’approvisionnement.](./media/accruals7-1024x390.png)](./media/accruals7.png)

**Étape 3 :** Création d’un brouillon de facture fournisseur. 

La validation d’un accusé de réception de marchandises ne concerne pas les informations de projet. Comme contournement, vous pouvez générer un brouillon de facture fournisseur après avoir validé la réception. Accédez à la page **Commande fournisseur** &gt; **Onglet Facture** &gt; **Générer** &gt; **Facture**. Cette action crée un document de facture en attente qui met les informations de projet à jour. 

La création d’un brouillon de facture fournisseur génère des transactions de projet en attente. 
[![Transactions de projet en attente.](./media/accruals8-1024x225.png)](./media/accruals8.png) 

Dans la page **Coût engagé**, les enregistrements créés à l’étape 1 seront fermés et de nouveaux enregistrements seront créés pour refléter l’engagement de coût provenant de la facture du fournisseur en attente. Le champ **Origine de la transaction** pour le coût engagé est défini sur **Facture fournisseur**.
[![Pages des coûts engagés.](./media/accruals9-1024x200.png)](./media/accruals9.png)

La facture fournisseur reste à l’état d’attente en attendant l’arrivée de la facture fournisseur réelle.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]