---
title: Importer les catalogues fournisseur
description: Cette rubrique décrit le processus pour importer les données du catalogue fournisseur.
author: mkirknel
manager: tfehr
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 608d2b57bb4d5ab80d75b22ed5c8a4df5263e5f3
ms.sourcegitcommit: 86052c58e3c365c443bd6f37ad1054bea395e21b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2020
ms.locfileid: "3338306"
---
# <a name="import-vendor-catalogs"></a>Importer les catalogues fournisseur

[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a>Importation des catalogues fournisseur

Dans Dynamics 365 Supply Chain Management, les acheteurs peuvent créer et mettre à jour des catalogues que les employés de la société peuvent utiliser lorsqu'ils commandent des articles et des services pour un usage interne. Pour créer un catalogue d'approvisionnement, vous pouvez ajouter les articles et les services que vous voulez rendre disponibles pour les employés, soit en important les données du catalogue de produits, soit en ajoutant les données de catalogue de produits dans le produit générique manuellement. 

Vous pouvez charger les données de catalogue envoyées par un fournisseur depuis le client Microsoft Dynamics 365.

Les données du produit envoyées par un fournisseur sous forme de fichier DMC (demande de mise à jour de catalogue) doivent être au format XML. Le fichier DMC doit contenir les détails des produits que le fournisseur propose à votre société.

## <a name="import-vendor-catalog-data"></a>Importer les données de catalogue fournisseur

Pour importer les données d'un catalogue fournisseur, procédez comme suit :

1. Paramétrez un projet dans l'espace de travail Gestion des données dans lequel vous avez défini les règles de mise en correspondance des données. Sélectionnez **Gestion des données** puis **Définir les rôles des projets de données**.

2. Paramétrez une hiérarchie des catégories d'approvisionnement, puis affectez vos fournisseurs aux catégories d'approvisionnement. Si vous utilisez des codes marchandise, ajoutez-les aux catégories d'approvisionnement. Pour plus d'informations sur le paramétrage d'une hiérarchie des catégories d'approvisionnement, voir [Paramétrer une hiérarchie des catégories d'approvisionnement](../procurement/tasks/set-up-procurement-category-hierarchy.md).

3. Configurez le fournisseur pour l'importation du catalogue. Sélectionnez un fournisseur, puis **Approvisionnement** > **Paramétrage** > **Configurer le fournisseur pour l'importation de catalogues**.

4. Configurez le workflow pour l'importation du catalogue. Créez un modèle de fichier DMC et partagez-le avec votre fournisseur.

5. Sélectionnez **Approvisionnements** \> **Commun** \> **Catalogues** \> **Catalogues fournisseur** pour créer un catalogue fournisseur. Les fichiers DMC envoyés par le fournisseur sont regroupés dans ce catalogue. 

6. Téléchargez le fichier DMC.

7. Révisez, approuvez ou rejetez les produits du catalogue fournisseur. Les produits sont automatiquement mis en correspondance avec les catégories d'approvisionnement. 

Les produits approuvés sont ajoutés au produit générique et sont lancés dans les entités juridiques sélectionnées. Seuls les produits approuvés peuvent être ajoutés au catalogue d'approvisionnement.

## <a name="generate-a-catalog-import-file-template"></a>Génération d'un modèle de fichier d'importation de catalogue

Le modèle de fichier d'importation de catalogue est un fichier XSD que vous pouvez utiliser pour créer un fichier DMC pour les produits d'un fournisseur. Le fichier DMC que vous créez permet de créer, de remplacer ou de modifier un catalogue.

1. Sélectionnez **Approvisionnements** \> **Catalogues** \> **Catalogues fournisseur** et double-cliquez sur le catalogue à utiliser.

2. Téléchargez un modèle d'importation de catalogue actif (fichier XSD). Sur la page **Mettre à jour le catalogue**, dans le **Volet Actions**, sous l'onglet **Catalogues**, dans le groupe **Informations associées**, cliquez sur **Générer un modèle de catalogue** et sélectionnez **Catégorie d'approvisionnement**.

    - Avec l'option **Catégorie d'approvisionnement**, vous pouvez générer un modèle de catalogue incluant les catégories d'approvisionnement dans lesquelles le fournisseur est autorisé à livrer des produits.

3. Dans la boîte de dialogue **Enregistrer sous**, sélectionnez l'emplacement de stockage du modèle de fichier de catalogue et enregistrez le fichier.

Pour plus d'informations et pour obtenir des exemples, consultez ce billet de blog : [Catalogues fournisseur dans Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).
