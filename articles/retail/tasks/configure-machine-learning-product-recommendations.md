--- 
title: " Configurer des recommandations de produit exécutées par Machine Learning"
description: "Cette procédure actualise les données du magasin des entités qui sont utilisées par le système Machine Learning exécutant les recommandations de produit, puis active les recommandations de produit pour les clients POS."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: c51c5f82efb50db1e238f4046506920975f33218
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="configure-machine-learning-powered-product-recommendations"></a> Configurer des recommandations de produit exécutées par Machine Learning

[!include[task guide banner](../includes/task-guide-banner.md)]

Cette procédure actualise les données du magasin des entités qui sont utilisées par le système Machine Learning exécutant les recommandations de produit, puis active les recommandations de produit pour les clients POS. Cette procédure utilise la société USRT dans les données de démonstration.

1. Accédez à Administration système > Paramétrage > Magasin des entités.
2. Dans la liste, recherchez et sélectionnez l'enregistrement « RetailSales ».
3. Cliquez sur Actualiser.
4. Cliquez sur OK.
5. Fermez la page.
6. Accédez à Commerce et vente au détail > Configuration du siège > Paramètres > Paramètres des ventes au détail.
7. Cliquez sur l'onglet Machine Learning.
8. Sélectionnez Oui dans le champ Activer les recommandations produit.
    * Si vous recevez le message « Impossible de récupérer les modèles de recommandation », cela est dû au fait que vous avez actualisé le magasin des entités très récemment et le système n'a peut-être pas terminé d'assimiler les nouvelles données. Patientez 2 ou 3 heures et recommencez.  
9. Cliquez sur Enregistrer.
10. Fermez la page.

