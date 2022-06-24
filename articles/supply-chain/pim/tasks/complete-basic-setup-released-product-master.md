---
title: Finaliser le paramétrage de base d’un produit générique lancé
description: Cet article indique comment terminer la configuration minimale requise avant que le produit générique puisse être utilisé dans les versions de nomenclature.
author: t-benebo
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a403600bfdc257587441b5b5a907981d5eebaf58
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844850"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Finaliser le paramétrage de base d’un produit générique lancé

[!include [banner](../../includes/banner.md)]

Cet article indique comment terminer la configuration minimale requise avant que le produit générique puisse être utilisé dans les versions de nomenclature.

Il s’agit de la troisième procédure (parmi les huit) qui explique comment créer des combinaisons pour la configuration basée sur les dimensions. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

1. Accédez à **Volet de navigation > Modules > Gestion d’informations sur les produits > Produits > Produits lancés**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Sélectionnez le produit générique que vous avez lancé dans la deuxième procédure. Ce produit générique est créé avec la technologie de configuration basée sur les dimensions.  
3. Dans le volet Actions, sélectionnez **Produit**.
4. Sélectionnez **Groupes de dimensions** pour ouvrir la boîte de dialogue.
5. Dans le champ **Groupe de dimensions de stockage**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Le groupe de dimensions de stockage détermine les dimensions de stockage utilisées pour la transaction de produit. Sélectionnez **Site** pour cette procédure.  
7. Dans le champ **Groupe de dimensions de suivi**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Le groupe de dimensions de suivi détermine les dimensions de suivi utilisées pour la transaction de produit. Sélectionnez **Aucun** pour cette procédure.  
9. Cliquez sur **OK**.
10. Cliquez sur **Modifier**.
11. Dans le champ **Groupe de modèles d’articles**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
12. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Les groupes de modèles d’articles contiennent des paramètres qui déterminent la manière dont les articles sont contrôlés et gérés au niveau des réceptions et sorties d’articles. Ils déterminent également le mode de calcul de la consommation d’articles. Sélectionnez **FIFO** pour cette procédure.  
13. Développez la section **Gérer les coûts**.
14. Dans le champ **Groupe d’articles**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
15. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité. Les groupes d’articles sont utilisés pour gérer le stock en divisant les articles en stock en groupes. Sélectionnez **CarAudio** pour cette procédure.  
16. Dans le volet Actions, sélectionnez **Planifier**.
17. Sélectionnez **Paramètres de commande par défaut**.
18. Dans le champ **Type de commande par défaut**, sélectionnez une option. Sélectionnez **Production** pour spécifier que l’option d’approvisionnement par défaut pour ce produit générique est de le produire.  
19. Sélectionnez **Enregistrer**.
20. Fermez la page.
21. Fermez le formulaire **Détails des produits lancés**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]