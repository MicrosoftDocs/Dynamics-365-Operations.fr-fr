---
title: Configurer les droits d’accès d’un contrôleur d’objet de coût
description: Utilisez cette procédure pour configurer les droits d’accès d’un contrôleur d’objet de coût.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eef755dd9a44ce24d3bfb2953cf9a52e6a8ac849
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822877"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>Configurer les droits d’accès d’un contrôleur d’objet de coût

[!include [banner](../../includes/banner.md)]

Utilisez cette procédure pour configurer les droits d’accès d’un contrôleur d’objet de coût. Cet enregistrement utilise la société fictive USP2.


## <a name="assign-the-cost-object-controller-role"></a>Affecter le rôle Contrôleur d’objet de coût
1. Accédez à Administration système > Utilisateurs > Utilisateurs.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez le champ Nom d’utilisateur avec la valeur « alicia ».
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
4. Cliquez sur Affecter des rôles.
5. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
6. Cliquez sur OK.

## <a name="enable-access-list-security"></a>Activer la sécurité de la liste d’accès
1. Accédez à Contrôle de gestion > Dimensions > Hiérarchies des dimensions.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
    * Sélectionnez Organisation.  
3. Cliquez sur Modifier.
4. Sélectionnez Oui dans le champ Hiérarchie de la liste d’accès.
5. Cliquez sur Afficher la hiérarchie.

## <a name="assign-access-rights-to-user"></a>Affecter des droits d’accès à l’utilisateur
1. Cliquez sur Nouveau.
2. Dans la liste, marquez la ligne sélectionnée.
3. Saisissez ou sélectionnez une valeur dans le champ ID utilisateur.
    * Sélectionnez Administrateur.  
4. Dans l’arborescence, sélectionnez « Organisation\PDG\Directeur financier\FIM ».
5. Cliquez sur Nouveau.
6. Dans la liste, marquez la ligne sélectionnée.
7. Saisissez ou sélectionnez une valeur dans le champ ID utilisateur.
    * Sélectionnez Alicia.  
8. Cliquez sur Enregistrer.

## <a name="enable-access-rights-in-cost-accounting"></a>Activer les droits d’accès dans Contrôle de gestion
1. Accédez à Contrôle de gestion > Paramétrage > Paramètres.
2. Cliquez sur l’onglet Général.
3. Sélectionnez Oui dans le champ Activer l’affichage pour les membres de dimension d’objet de coût.
4. Cliquez sur Enregistrer.
5. Fermez la page.
6. Accédez à Contrôle de gestion > Paramétrage > Configuration de l’espace de travail de contrôle des coûts.
7. Cliquez sur Modifier.
8. Sélectionnez Oui dans le champ Publié.
    * Si vous sélectionnez Oui, un utilisateur affecté à l’un des quatre rôles suivants peut afficher les états dans l’espace de travail Contrôle des coûts : gestionnaire de contrôle de gestion, comptable, commis contrôleur de gestion et contrôleur d’objet de coût. Si vous sélectionnez Non, seul un utilisateur affecté à l’un des rôles suivants peut afficher les états : gestionnaire de contrôle de gestion, comptable et commis contrôleur de gestion.    
9. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]