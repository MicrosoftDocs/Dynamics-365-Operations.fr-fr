---
title: Créer des éléments de coût
description: Il existe plusieurs façons de créer des éléments de coût dans le contrôle de gestion.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMAXMainAccountDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c4c1e2aee7ba98c1cca378286afb643eaca1600
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810076"
---
# <a name="create-cost-elements"></a>Créer des éléments de coût 

[!include [banner](../../includes/banner.md)]

Il existe plusieurs façons de créer des éléments de coût dans le contrôle de gestion. Cette procédure indique comment créer des éléments de coût en important les comptes principaux via un connecteur de données. La société fictive USMF a été utilisée pour créer cette procédure. Cette procédure s’applique à une fonction du contrôle de gestion qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="create-new-cost-elements"></a>Créer des éléments de coût
1. Accédez à Contrôle de gestion > Dimensions > Dimensions d’éléments de coût.
2. Cliquez sur Nouveau.
3. Tapez une valeur dans le champ Nom.
4. Dans le champ Connecteur de données pour les membres de la dimension, entrez ou sélectionnez une valeur.
5. Dans le champ Description, entrez une valeur.
6. Cliquez sur Enregistrer.

## <a name="configure-the-data-connector"></a>Configurer le connecteur de données
1. Cliquez sur Configurer le fournisseur du membre de dimension.
2. Dans le champ Plan de comptes, entrez ou sélectionnez une valeur.
    * Sélectionnez Partagé pour utiliser le plan de comptes partagé.  
3. Cliquez sur Nouveau.
4. Dans la liste, marquez la ligne sélectionnée.
    * Vous pouvez appliquer des filtres aux comptes pour répondre à vos critères.  
5. Dans le champ Compte principal de départ, entrez ou sélectionnez une valeur.
6. Dans le champ Vers compte principal, entrez ou sélectionnez une valeur.
7. Cliquez sur OK.

## <a name="import-main-accounts"></a>Importer les comptes principaux
1. Cliquez sur Importer les membres de la dimension.
    * Les comptes principaux sont importés dans le contrôle de gestion et utilisés comme éléments de coût.  
2. Cliquez sur OK.

## <a name="view-the-imported-accounts-as-cost-elements"></a>Afficher les comptes importés en tant qu’éléments de coût
1. Cliquez sur Afficher les membres de la dimension.
    * Affichez les comptes généraux importés en tant qu’éléments de coût de votre entreprise vers lesquels les coûts peuvent se diriger.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]