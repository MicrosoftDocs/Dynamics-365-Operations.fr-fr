---
title: "Définir et tenir à jour les canaux de vente au détail"
description: "Cet article fournit une vue d'ensemble du processus de paramétrage des magasins traditionnels, qui sont appelés des magasins de vente au détail dans Microsoft Dynamics 365 for Retail. Il inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré un magasin de vente au détail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 3f0b566963574569cb40b72550e2337c9ba8a2ce
ms.contentlocale: fr-fr
ms.lasthandoff: 06/20/2017

---

# <a name="define-and-maintain-retail-channels"></a>Définir et tenir à jour les canaux de vente au détail

[!include[banner](includes/banner.md)]


Cet article fournit une vue d'ensemble du processus de paramétrage des magasins traditionnels, qui sont appelés des magasins de vente au détail dans Microsoft Dynamics 365 for Retail. Il inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré un magasin de vente au détail.

Dynamics 365 for Retail prend en charge plusieurs canaux de vente au détail, tels que les magasins en ligne, les centres d'appel et les magasins traditionnels. Les magasins physiques sont également appelés magasins de vente au détail. Chaque magasin de vente au détail peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel. Vous devez définir tous ces éléments pour un magasin de vente au détail avant de le créer. Une fois le magasin de vente au détail créé, vous affectez les produits dont vous souhaitez la présence dans ce magasin. Vous affectez également des employés, des caisses enregistreuses et des clients au magasin. Enfin, vous ajoutez le nouveau magasin à une hiérarchie d'organisation.

## <a name="setting-up-retail-stores"></a>Paramétrage des magasins de vente au détail
Avant de paramétrer un magasin de vente au détail dans Dynamics 365 for Retail, vous devez exécuter certaines tâches préalables. Vous pouvez ensuite créer le magasin de vente au détail et ajouter des informations.

### <a name="prerequisites"></a>Logiciels requis

Vous devez exécuter certaines tâches préalables avant de paramétrer un magasin de vente au détail :

1.  configurez votre structure d'organisation et paramétrez des hiérarchies d'organisation pour les assortiments de vente au détail, le réapprovisionnement et la génération d'états.
2.  paramétrez un entrepôt qui représente le magasin de vente au détail.
3.  Paramétrez des souches de numéros pour les magasins de vente au détail, les relevés bancaires, et documents de relevé.
4.  configurez les paramètres de Retail.
5.  Paramétrez les modes de paiement acceptés par le magasin.
6.  Pour traiter les transactions de carte de crédit sur les caisses enregistreuses de point de vente (PDV) au détail, vous pouvez également paramétrer des services de paiement.
7.  Paramétrez les groupes de taxes.
8.  Paramétrez les produits vendus au détail. Dans le cadre de cette tâche, vous paramétrez également des hiérarchies des produits vendus au détail, des variantes de produit et des assortiments de produits.
9.  Configurez les groupes de prix de produits.
10. Définissez la tarification des produits vendus au détail. Dans le cadre de cette tâche, vous paramétrez également des ajustements de prix, des remises et des périodes de remise.
11. Paramétrez les membres du personnel. **Remarque :** vous devez également attribuer des autorisations appropriées aux collaborateurs pour qu'ils puissent se connecter et effectuer des tâches dans Dynamics 365 for Retail pour le système Retail POS.
12. Configurez les profils Retail POS à affecter au magasin. Cette tâche inclut plusieurs autres tâches, comme le paramétrage des registres, le paramétrage des profils hors ligne, et le paramétrage des formats de réception et les profils.

Examinez toutes les tâches incluses dans les conditions préalables et n'effectuez que celles qui vous concernent.

### <a name="set-up-a-retail-store"></a>Paramétrage d'un magasin de vente au détail

Après avoir réalisé les tâches nécessaires, effectuez ces tâches pour paramétrer les détails du magasin de vente au détail :

1.  Créez un magasin de vente au détail.
2.  Affectez un groupe de taxe au magasin.
3.  Affectez les modes de paiement acceptés au magasin.
4.  Ajoutez des détails aux descriptions des produits que vous proposez dans vos magasins de vente au détail. Par exemple, vous pouvez ajouter du texte enrichi et des images. Ces détails des produits apparaissent dans divers contextes, par exemple dans la caisse enregistreuse du PDV ou sur les étiquettes imprimées.
5.  Ajoutez le magasin à la hiérarchie d'organisation par défaut affectée à un objectif **Assortiment de vente au détail**, **Réassort de la vente au détail**, ou **Génération d'états sur les ventes au détail**.

### <a name="after-you-set-up-a-retail-store"></a>Après le paramétrage d'un magasin de vente au détail

Une fois les détails du magasin de vente au détail, entreprenez ces tâches pour envoyer les données du nouveau magasin de vente au détail à Retail POS :

1.  Configurez les caisses enregistreuses des points de vente (PDV) pour le magasin.
2.  Affectez des assortiments de produits au magasin.
3.  Traitez les assortiments pour générer la liste des produits inclus dans l'assortiment et pour rendre les produits disponibles dans le magasin de vente au détail.
4.  Envoyez les données telles que les souches de numéros, les profils matériel et les mises en page d'écran de PDV aux caisses enregistreuses .
5.  Publiez le magasin de vente au détail pour envoyer les données du magasin à Retail POS.
6.  Exécutez les tâches pour envoyer les données à Retail POS.

## <a name="organization-hierarchies"></a>Hiérarchies de l'organisation
Retail utilise des hiérarchies d'organisation pour structurer les canaux de vente au détail. Les hiérarchies d'organisation représentent les relations entre les organisations qui composent votre entreprise. Lorsque vous paramétrez des magasins, vous pouvez les ajouter à une hiérarchie d'organisation. Les magasins partagent ensuite les données utilisées pour les assortiments, le réapprovisionnement et la génération d'états.




