---
title: Synchronisation des évaluations de produit dans Dynamics 365 Commerce
description: Cette rubrique décrit comment synchroniser les classements de produit dans Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f2112c87912a1d130017c5804c4193b62c1e5a476be79bfd485640ec98b42f77
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730897"
---
# <a name="sync-product-ratings-in-dynamics-365-commerce"></a>Synchronisation des évaluations de produit dans Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Cette rubrique décrit comment synchroniser les classements de produit dans Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Vue d’ensemble

Pour consommer des classements de produit dans les omnicanaux, par exemple au point de vente (PDV) et dans les centres d’appels, les classements de produit du service de classements et d’évaluations doivent être importés dans la base de données du canal de commerce. Lorsque les classements de produit sont disponibles dans les omnicanaux, ils peuvent aider les clients indirectement lors de leurs interactions avec des vendeurs.

Cette rubrique décrit les tâches suivantes :

1. Configurez **Synchronisation les classements de produits** comme un traitement par lots pour synchroniser les classements de produits à partir de **Service de classements et d’évaluations**.
1. Vérifiez que le traitement par lots de la synchronisation de classement de produit a abouti.
1. Rendez les classements de produit disponibles dans le PDV.

## <a name="configure-a-batch-job-to-synchronize-product-ratings"></a>Configurer un traitement par lots pour synchroniser les classements de produit

> [!IMPORTANT]
> Avant de démarrer, vérifiez que la version 10.0.6 ou ultérieure de Dynamics 365 Commerce est installée.

### <a name="initialize-the-commerce-scheduler"></a>Initialiser le planificateur de commerce

Pour initialiser le planificateur de commerce, procédez comme suit.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Planificateur de commerce \> Initialiser le planificateur de commerce**. Sinon, faites une recherche sur « Initialiser le planificateur de commerce ».
1. Dans la boîte de dialogue **Initialiser le planificateur de commerce**, vérifiez que l’option **Supprimer la configuration existante** est définie sur **Non**, puis cliquez sur **OK**.

### <a name="verify-the-retailproductrating-subjob"></a>Vérifiez la sous-tâche RetailProductRating

Pour vérifier que la sous-tâche **RetailProductRating** existe, procédez comme suit.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Planificateur de commerce \> Sous-tâches du planificateur**. Sinon, recherchez des « Sous-tâches Planification. »
1. Dans la liste des sous-tâches, recherchez la sous-tâche **RetailProductRating**.

L’illustration suivante présente un exemple de détails de sous-tâche dans Commerce.

![Détails la sous-tâche RetailProductRating.](media/rnr-hq-ratings-sub-job.png)

> [!NOTE]
> Si vous ne trouvez pas la sous-tâche **RetailProductRating**, il est possible que vous ayez déjà exécuté la tâche **Synchroniser les classements de produits** et la tâche **1040 CDX** avant d’initialiser le planificateur de commerce. Dans ce cas, procédez comme suit pour exécuter la tâche **Synchronisation de données complète**.

> 1. Accédez à **Retail et Commerce \> Configuration du siège \> Planificateur de commerce \> Base de données des canaux**. Sinon, recherchez la « Base de données du canal. »
> 1. Sélectionnez la base de données du canal à synchroniser.
> 1. Sur le volet d’action, sélectionnez **Synchronisation complète des données**.
> 1. Dans la boîte de dialogue de menu déroulant **Sélectionner un programme de distribution**, sélectionnez **1040 - produits**, puis sélectionnez **OK**.
> 1. Répétez les étapes de la procédure précédente pour vérifier que la sous-tâche **RetailProductRating** a été créée.

### <a name="import-product-ratings"></a>Importer des classements de produits

Pour importer les classements de produits dans Commerce à partir du service de classements et d’évaluations, procédez comme suit.

1. Accédez à **Retail et Commerce \> Paramétrage de Siège \> Planificateur de commerce \> Synchroniser les classements de produits**. Sinon, recherchez « Synchroniser les classements de produits. »
1. Dans la boîte de dialogue **Extraire les classements de produits**, sous l’organisateur **Exécuter en arrière-plan**, sélectionnez **Récurrence**.
1. Dans la boîte de dialogue **Définissez la récurrence**, paramétrez un modèle de répétition. (La valeur suggérée est de deux heures.) Ne planifiez pas une récurrence inférieure à une heure.
1. Cliquez sur **OK**.
1. Définissez l’option **Traitement par lots** sur **Oui**. Ce paramètre permet de garantir que vous pouvez auditer les journaux et vérifier le statut des exécutions de traitement par lots.
1. Sélectionnez **OK** pour planifier le traitement par lots.

L’illustration suivante présente un exemple de configuration de traitement par lots dans Commerce.

![Configuration du traitement par lots de synchronisation des évaluations de produits.](media/rnr-hq-batchjob-recurrence.png)

## <a name="verify-that-the-batch-job-for-product-rating-synchronization-was-successful"></a>Vérifiez que le traitement par lots de la synchronisation de classement de produit a abouti

Pour vérifier que le traitement par lots **Synchroniser les classements de produits** a abouti, procédez comme suit.

1. Accédez à **Retail et Commerce \> Administrateur système \> Recherches \> Traitements par lots** ou, si vous utilisez à une unité de gestion de stock (SKU) réservée à Commerce, accédez plutôt à **Retail et Commerce \> Recherches et états \> Traitements par lots**. Sinon, recherchez des « Traitements par lots ».
1. Pour afficher les détails du traitement par lots, dans la liste de traitement par lots, dans la colonne **Description de la tâche**, recherchez une description qui contient « Extraire les classements de produits ».
1. Sélectionnez l’ID tâche pour afficher les détails du traitement par lots, tels que la date et l’heure prévues de début et le texte de récurrence.

L’illustration suivante donne un exemple de détails de traitement par lots dans Commerce lorsque le traitement par lots est programmé pour une exécution à des intervalles de deux heures.

![Détails du traitement par lots de synchronisation des évaluations de produits.](media/rnr-hq-batchjob-status-checking.png)

## <a name="make-product-ratings-available-at-the-pos"></a>Rendez les classements de produit disponibles dans le PDV

La solution de classements et d’évaluations dans Dynamics 365 Commerce est une solution omnicanale. Toutefois, les classements de produits ne sont pas affichés au niveau du PDV par défaut. Pour aider les clients dans les magasins à afficher les classements et les évaluations lorsqu’ils sont aidés par des vendeurs, vous devez activer les classements de produits dans le PDV.

Pour activer les classements de produits dans le PDV, procédez comme suit.

1. Accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres de commerce**. Sinon, faites une recherche sur « Paramètres de commerce ».
1. Dans l’onglet **Paramètres de configuration**, sélectionnez **Nouveau**.
1. Entrez un nom tel que **RatingsAndReviews.EnableProductRatingsForRetailStores**, et définissez la valeur sur **vrai**.
1. Sélectionnez **Enregistrer**.
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**. Sinon, recherchez « Programme de distribution ».
1. Dans la liste de tâches, sélectionnez **1110** (**Configuration globale**), puis sélectionnez **Exécution maintenant**.
1. Lorsque la tâche correctement exécuté, vérifiez que les classements de produits s’affichent dans le PDV.

L’illustration suivante donne un exemple de la configuration des paramètres de commerce pour activer les classements de produits au PDV.

![Configuration des paramètres de commerce pour les évaluations de produit au PDV.](media/rnr-hq-enable-ratings-in-pos.png)

L’illustration suivante montre un exemple de classements de produits dans PDV.

![Classements de produits dans le PDV.](media/rnr-pos-catalog-ratings.png)

L’illustration suivante montre un exemple de classements de produits dans les canaux de centres d’appels.

![Classements de produits dans un canal de centre d’appels.](media/rnr-call-center-ratings.png)

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des évaluations et avis](ratings-reviews-overview.md)

[Choix d’utilisation des évaluations et avis](opt-in-ratings-reviews.md)

[Gestion des évaluations et avis](manage-reviews.md)

[Configuration des évaluations et avis](configure-ratings-reviews.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]