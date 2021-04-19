---
title: Paramétrage d’une hiérarchie des catégories d’approvisionnement
description: Cette procédure vous indique comment créer de nouveaux nœuds dans une hiérarchie des catégories d’approvisionnement et comment configurer une catégorie d’approvisionnement à utiliser dans processus d’approvisionnement.
author: kamaybac
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 206dd5dc8f332268fe7665d84b005b5a7bfd1f9a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837703"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>Paramétrage d’une hiérarchie des catégories d’approvisionnement

[!include [banner](../../includes/banner.md)]

Cette procédure vous indique comment créer de nouveaux nœuds dans une hiérarchie des catégories d’approvisionnement et comment configurer une catégorie d’approvisionnement à utiliser dans processus d’approvisionnement. Ces tâches sont généralement effectuées par un responsable des achats. Avant de démarrer cette procédure, il doit y avoir une hiérarchie de catégories de type Approvisionnement. Si vous utilisez une société de données de démonstration, vous pouvez exécuter cette procédure à l’aide de la société USMF.


## <a name="add-a-new-procurement-category"></a>Ajouter une catégorie d’approvisionnement
1. Accédez au **Volet de navigation > Modules > Approvisionnements > Consignation > Catégories d’approvisionnement**.
2. Sélectionnez **Modifier la hiérarchie de catégories** dans le volet Actions. La hiérarchie des catégories d’approvisionnement actuelle s’affiche à la gauche de la page. Vous êtes sur le point de modifier la hiérarchie.  
3. Sélectionnez **Nouveau nœud de catégories** dans le volet Actions. Le système sélectionne le nœud supérieur par défaut. Si vous exécutez cette procédure en tant que guide des tâches, vous pouvez cliquer sur le bouton Déverrouiller et sélectionner un autre nœud parent dans lequel insérer votre nouveau nœud. Une fois que c’est fait, verrouillez à nouveau le guide de tâches, puis cliquez sur Nouveau nœud de catégorie.  
4. Tapez une valeur dans le champ **Nom**.
5. Tapez une valeur dans le champ **Description**.
6. Dans le champ **Nom convivial**, saisissez une valeur. Le nom convivial est facultatif. Il sera affiché dans les recherches de catégories avec le nom de la catégorie.  
7. Sélectionnez **Enregistrer**.

## <a name="add-products-to-your-new-procurement-category"></a>Ajouter des produits à une nouvelle catégorie d’approvisionnement
1. Accédez à **Approvisionnements > Consignation > Catégories d’approvisionnement**. Sélectionnez le nœud que vous venez d’ajouter. Si vous exécutez cette procédure en tant que guide des tâches, vous devrez peut-être déverrouiller le guide des tâches pour sélectionner le nœud.  
2. Activez ou désactivez l’extension de la section **Produits**.
3. Sélectionnez **Ajouter** pour associer des produits à la catégorie d’approvisionnement.
4. Sélectionnez les produits à ajouter à la catégorie d’approvisionnement.
5. Sélectionnez la flèche pour ajouter les produits à la table **Sélectionné**.
6. Cliquez sur **OK**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]