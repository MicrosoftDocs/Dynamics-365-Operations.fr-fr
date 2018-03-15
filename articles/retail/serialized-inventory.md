---
title: "Améliorations apportées aux PDV pour les produits sérialisés"
description: "Cette rubrique répertorie les améliorations apportées aux produits sérialisés pour vous permettre de gagner du temps et d'être plus productif."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 74a27761c065e475fa7c10c5812f0307df9f570e
ms.contentlocale: fr-fr
ms.lasthandoff: 02/07/2018

---

# <a name="pos-improvements-for-serialized-products"></a>Améliorations apportées aux PDV pour les produits sérialisés

[!include[banner](includes/banner.md)]

## <a name="overview"></a>Vue d'ensemble 
En fonction des paramètres de Retail Headquarters, les produits peuvent être classés comme étant sérialisés ou non sérialisés. Lorsque des produits sont sérialisés, chaque article peut recevoir un numéro unique qui permet de suivre les garanties, de tracer les articles et de confirmer la propriété. Bien que, la capacité à fournir des numéros de série pour les produits sérialisés existait dans notre point de vente (PDV) moderne/cloud, certaines améliorations ont été ajoutées pour permettre aux caissiers de gagner du temps et d'être plus productifs.  

## <a name="pos-improvements"></a>Améliorations apportées aux PDV

- **Les numéros de série ne sont pas obligatoires avant l'extraction** – Auparavant, un caissier qui ajoutait un produit sérialisé à la transaction devait fournir un numéro de série. Cette exigence est devenue un problème dans les scénarios de clientélisme, si les caissiers et les vendeurs ont eu la possibilité de vendre des produits. Jusqu'à l'étape du paiement, les produits étaient souvent mis à jour dans le panier. Par conséquent, chaque fois qu'un caissier ajoutait un nouveau produit, le système lui demandait de saisir le numéro de série. La boîte de dialogue du numéro de série comprend désormais un bouton **Ajouter ultérieurement**. Par conséquent, les chargés de vente peuvent ajouter l'article à la transaction, mais peuvent fournir le numéro de série ultérieurement. Les chargés de vente peuvent rapidement ajouter et remplacer des articles sérialisés dans le panier, puis fournir le numéro de série juste avant de passer à la caisse. Si le numéro de série n'est pas fourni pour les produits sérialisés, un caissier qui tente de terminer la transaction reçoit un message d'erreur. Ce message indique que le caissier doit fournir les numéros de série manquants pour pouvoir continuer.

    Pour chaque article sérialisé où le numéro de série a été ignoré, un commentaire apparaît sous la ligne de transaction. Ce commentaire indique que le numéro de série n'a pas été indiqué pour l'article. Par conséquent, le caissier peut rapidement rechercher les articles n'ayant pas de numéro de série.

    Une nouvelle opération **Ajouter un numéro de série** fournit également le numéro de série pour les articles n'ayant pas de numéro de série. Une fois que le numéro de série est fourni, il ne peut pas être modifié. Le caissier doit annuler la ligne et ajouter à nouveau le produit. 
    
- **Les numéros de série ne sont pas obligatoires pour passer des commandes client** – Les commandes client peuvent être passées dans un magasin et exécutées par un autre. Un caissier qui passe une commande client n'a pas à fournir de numéro de série. Le numéro de série devra être fourni au cours de l'étape de prélèvement. Toutefois, un numéro de série doit être indiqué pour toutes les lignes si le type de livraison **Exécuter** est sélectionné. Sinon, la transaction ne peut pas être effectuée.    
- **Les produits sérialisés ne sont pas regroupés dans l'écran de transaction** – Le paramètre **Regrouper des produits** dans le groupe de champs **Terminal** sur la page **Profil de la fonctionnalité** vous permet de regrouper les mêmes produits non sérialisés dans l'écran de transaction. Lorsque les mêmes produits sont regroupés, il est plus simple de les afficher dans la grille de transaction. Toutefois, comme les numéros de série sont généralement uniques et que les chargés de vente ne doivent pas saisir de numéro de série avant l'extraction, le paramètre **Regrouper des produits** ne s'applique pas aux produits sérialisés. Par conséquent, les produits sérialisés ne sont pas regroupés dans l'écran de transaction si le paramètre **Regrouper des produits** est sélectionné.
- **Possibilité de rechercher les journaux par numéro de série** - Les journaux peuvent aussi faire l'objet d'une recherche par numéro de série. Pour ce faire, ouvrez l'opération « Journaux » et appuyez sur le bouton « Recherche avancée » dans la barre d'application. À l'aide du bouton « Ajouter un filtre », un filtre peut être appliqué pour rechercher aussi les numéros de série.

