--- 
title: "Planifier les chargements et les expéditions à l'aide de l'atelier Planification des chargements"
description: "Cette procédure indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f840a4c15305af5f55451ae7f1cec2da25e685a4
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Planifier les chargements et les expéditions à l'aide de l'atelier Planification des chargements

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment utiliser la console de planification des chargements pour créer une charge pour une commande client. Il est indispensable de créer la commande client en premier. Cette procédure fait partie du travail quotidien pour le coordinateur de transport. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-sales-order"></a>Créer une commande client
1. Accédez à Comptabilité client > Commandes > Toutes les commandes client.
2. Cliquez sur Nouveau.
3. Dans le champ Compte client, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
4. Sélectionnez US-004.
5. Cliquez sur OK.
6. Dans le champ Numéro d'article, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
7. Sélectionner l'article A0001.
    * A0001 est activé pour la gestion du transport.  
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ Quantité, entrer un numéro.
10. Dans le champ Entrepôt, tapez « 24 ».
    * Dans cet exemple sélectionnez l'entrepôt 24. Cet entrepôt est activé pour la gestion du transport et la gestion avancée des entrepôts.  
11. Cliquez sur Enregistrer.
12. Fermez la page.

## <a name="create-a-new-load"></a>Créer une charge
1. Accédez à Gestion du transport > Planning > Console de planification des charges.
2. Cliquez sur l'onglet Lignes de vente.
    * Désormais vous établirez la charge pour la commande client que vous venez de créer. Les charges peuvent être établies selon l'offre et de la demande des commandes fournisseurs, des ordres de transfert et des commandes client.  
3. Dans le volet Actions, cliquez sur Approvisionnement et demande.
4. Cliquez sur À une nouvelle charge.
5. Dans le champ ID du modèle de charge, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Le modèle de charge définit les mesures maximales pour le poids et le volume de la charge entière. Par exemple, le modèle de charge peut représenter la taille d'un conteneur ou d'un camion.  
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Cliquez sur OK.

## <a name="rate-and-route-the-load"></a>Classer et acheminer la charge
1. Cliquez sur Classement et acheminement.
2. Cliquez sur Atelier des routes et frais.
3. Cliquez sur Magasin de taux.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Cliquez sur Affecter.
6. Fermez la page.
7. Fermez la page.


