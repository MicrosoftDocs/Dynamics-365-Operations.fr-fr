---
title: Planifier des chargements et des expéditions à l'aide de l'atelier Planification des chargements
description: Cette rubrique indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4fdff8bdc383a85d604fa6e545c625d5782241f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976811"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planifier des chargements et des expéditions à l'aide de l'atelier Planification des chargements

[!include [banner](../../includes/banner.md)]

Cette rubrique indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client. Il est indispensable de créer la commande client en premier. Cette procédure fait partie du travail quotidien pour le coordinateur de transport. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-sales-order"></a>Créer une commande client
1. Allez dans **Volet de navigation > Modules > Comptabilité client > Commandes > Toutes les commandes client**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Compte client**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Sélectionnez le compte **US-004**.
5. Cliquez sur **OK**.
6. Dans le champ **Numéro d'article**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Sélectionnez l'article **A0001**. **A0001** est activé pour la gestion du transport.  
8. Dans le champ **Site**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche, puis sélectionnez un article.
9. Entrez un nombre dans le champ **Quantité**.
10. Dans le champ **Entrepôt**, entrez « 24 » pour cet exemple. Cet entrepôt est activé pour la gestion du transport et la gestion avancée des entrepôts.  
11. Sélectionnez **Enregistrer**.
12. Fermez la page.

## <a name="create-a-new-load"></a>Créer une charge
1. Allez dans **Volet de navigation > Modules > Gestion du transport > Planification > Console de planification des charges**.
2. Sélectionnez l'onglet **Lignes de vente**. Désormais, vous établirez la charge pour la commande client que vous venez de créer. Les charges peuvent être établies selon l'offre et de la demande des commandes fournisseurs, des ordres de transfert et des commandes client.  
3. Dans le volet Actions, sélectionnez **Approvisionnement et demande**.
4. Sélectionnez **Dans une nouvelle charge**.
5. Dans le champ **ID du modèle de charge**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. Le modèle de charge définit les mesures maximales pour le poids et le volume de la charge entière. Par exemple, le modèle de charge peut représenter la taille d'un conteneur ou d'un camion. Permet de sélectionner un article.
6. Cliquez sur **OK**.

## <a name="rate-and-route-the-load"></a>Classer et acheminer la charge
1. Sélectionnez **Classement et acheminement**.
2. Sélectionnez **Atelier des routes et frais**.
3. Sélectionnez **Magasin de taux**.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Sélectionnez **Assigner**.
6. Fermez la page.

