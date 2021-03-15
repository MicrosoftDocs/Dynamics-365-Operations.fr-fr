---
title: Définir et tenir à jour les canaux de vente au détail
description: Cette rubrique fournit une vue d'ensemble du processus de paramétrage des magasins traditionnels, qui sont appelés des magasins dans Dynamics 365 Commerce. Il inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré un magasin.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 51524ad6918d962d70a8a700f135f96e236f7d34
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000873"
---
# <a name="define-and-maintain-retail-channels"></a>Définir et tenir à jour les canaux de vente au détail

[!include [banner](includes/banner.md)]

Cette rubrique fournit une vue d'ensemble du processus de paramétrage des magasins traditionnels, qui sont appelés des magasins dans Dynamics 365 Commerce. Il inclut des informations sur les tâches que vous devez effectuer avant et après avoir paramétré un magasin.

Commerce prend en charge plusieurs canaux, tels que les magasins en ligne, les centres d'appels et les magasins traditionnels. Les magasins physiques sont également appelés magasins. Chaque magasin peut proposer son propre mode de paiement, ses propres groupes de prix, ses propres caisses enregistreuses de PDV, ses propres comptes de revenus et de dépenses et son propre personnel. Vous devez définir tous ces éléments pour un magasin avant de le créer. Une fois le magasin créé, vous affectez les produits dont vous souhaitez la présence dans ce magasin. Vous affectez également des employés, des caisses enregistreuses et des clients au magasin. Enfin, vous ajoutez le nouveau magasin à une hiérarchie d'organisation.

## <a name="setting-up-stores"></a>Paramétrage des magasins

Avant de paramétrer un magasin dans Commerce, vous devez exécuter certaines tâches préalables. Vous pouvez ensuite créer le magasin et ajouter des informations.

### <a name="prerequisites"></a>Conditions préalables

Vous devez exécuter certaines tâches préalables avant de paramétrer un magasin :

1. configurez votre structure d'organisation et paramétrez des hiérarchies d'organisation pour les assortiments de vente au détail, le réapprovisionnement et la génération d'états.
2. paramétrez un entrepôt qui représente le magasin.
3. Paramétrez des souches de numéros pour les magasins, les relevés bancaires, et documents de relevé.
4. Configurez les paramètres pour Commerce.
5. Paramétrez les modes de paiement acceptés par le magasin.
6. Pour traiter les transactions de carte de crédit sur les caisses enregistreuses de point de vente (PDV), vous pouvez également paramétrer des services de paiement.
7. Paramétrez les groupes de taxes.
8. Paramétrez les produits. Dans le cadre de cette tâche, vous paramétrez également des hiérarchies des produits, des variantes de produit et des assortiments de produits.
9. Configurez les groupes de prix de produits.
10. Paramétrez la tarification des produits. Dans le cadre de cette tâche, vous paramétrez également des ajustements de prix, des remises et des périodes de remise.
11. Paramétrez les membres du personnel.

    > [!NOTE]
    > Vous devez également attribuer des autorisations appropriées aux collaborateurs pour qu'ils puissent se connecter et effectuer des tâches pour le système PDV.

12. Configurez les profils PDV à affecter au magasin. Cette tâche inclut plusieurs autres tâches, comme le paramétrage des registres, le paramétrage des profils hors ligne, et le paramétrage des formats de réception et les profils.

Examinez toutes les tâches incluses dans les conditions préalables et n'effectuez que celles qui vous concernent.

### <a name="set-up-a-store"></a>Paramétrez un magasin

Après avoir réalisé les tâches nécessaires, effectuez ces tâches pour paramétrer les détails du magasin :

1. Créez un magasin.
2. Affectez un groupe de taxe au magasin.
3. Affectez les modes de paiement acceptés au magasin.
4. Ajoutez des détails aux descriptions des produits que vous proposez dans vos magasins. Par exemple, vous pouvez ajouter du texte enrichi et des images. Ces détails des produits apparaissent dans divers contextes, par exemple dans la caisse enregistreuse du PDV ou sur les étiquettes imprimées.
5. Ajoutez le magasin à la hiérarchie d'organisation par défaut affectée à un objectif **Assortiment de vente au détail**, **Réassort de la vente au détail**, ou **Génération d'états sur les ventes au détail**.

### <a name="after-you-set-up-a-store"></a>Après le paramétrage d'un magasin

Une fois les détails du magasin entrés, réalisez ces tâches pour envoyer les données du nouveau magasin à PDV :

1. Configurez les caisses enregistreuses des points de vente (PDV) pour le magasin.
2. Affectez des assortiments de produits au magasin.
3. Traitez les assortiments pour générer la liste des produits inclus dans l'assortiment et pour rendre les produits disponibles dans le magasin.
4. Envoyez les données telles que les souches de numéros, les profils matériel et les mises en page d'écran de PDV aux Caisses enregistreuses de PDV.
5. Publiez le magasin pour envoyer les données du magasin à PDV.
6. Exécutez les tâches pour envoyer les données sur PDV.

## <a name="organization-hierarchies"></a>Hiérarchies de l'organisation

Commerce utilise des hiérarchies d'organisation pour structurer les canaux. Les hiérarchies d'organisation représentent les relations entre les organisations qui composent votre entreprise. Lorsque vous paramétrez des magasins, vous pouvez les ajouter à une hiérarchie d'organisation. Les magasins partagent ensuite les données utilisées pour les assortiments, le réapprovisionnement et la génération d'états.

> [!NOTE]
> Pour utiliser la fonctionnalité de vente de Commerce, la clé de configuration pour **Expédition multiple** doit être activée. Cette clé de configuration se trouve dans les clés **Configuration Commerce** sous **Administration du système**\> **Configurer** \> **Configuration de licence**. Cela est nécessaire en raison de diverses validations basées sur l'adresse de livraison configurée au niveau de la ligne de commande client.



[!INCLUDE[footer-include](../includes/footer-banner.md)]