---
title: Ajouter un emplacement et des types de relations de partie
description: Cette rubrique explique comment ajouter un nouvel emplacement et un nouveau type de relation de partie.
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 36c2c45c8f078abdc7e0bc40481a544491384245
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711490"
---
# <a name="add-location-and-party-relationship-types"></a>Ajouter un emplacement et des types de relations de partie 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>Ajouter des rôles d’emplacement

Vous pouvez ajouter un nouveau rôle d’emplacement pour les informations d’adresse et de contact de deux manières :

-  Utilisez la page **Objet des informations d’adresse et de contact**. Le nouveau rôle est enregistré dans la table **LogisticsLocationRole** avec type = 0, qui indique que le rôle n’est pas un rôle système défini dans l’énumération **LogisticsLocationRoleType** et ses extensions. Un utilisateur peut utiliser ce rôle lors de la création des informations d’adresse ou de contact.

    ![Objet des informations d’adresse et de contact.](media/Address-Contact.PNG)

-  Ajoutez-le à l’extension de l’énumération **LogisticsLocationRoleType**, puis renseignez les valeurs via le processus de synchronisation de la base de données.

    1.  Créez une extension à l’énumération **LogisticsLocationRoleType** et ajoutez le nouveau rôle dans l’extension. 
  
        ![Extension à l’énumération LogisticsLocationRoleType.](media/Logistics.PNG)

    2. Créez un fichier de ressource pour le nouveau rôle, puis affectez une valeur pour ses propriétés.
     
     ![Nouveau fichier de ressource.](media/Resource.PNG)
        
    3.  Créez une classe de remplissage des données et fournissez une méthode de gestionnaire pour renseigner le nouveau rôle. 

        ![Remplissage des données.](media/Dirdata.PNG)

    4.  Pour tester le remplissage du nouveau rôle d’emplacement, vous pouvez créer une classe exécutable et appeler DirDataPopulation::insertLogisticsLocationRoles() dans Main(). Une fois ce processus terminé, le nouveau rôle est enregistré dans la table **LogisticsLocationRole** avec type \> 0. Le nouveau rôle s’affiche sur la page **Objet des informations d’adresse et de contact**.

        ![Insérer un nouvel emplacement.](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>Ajouter des types de relation de partie 

Vous pouvez ajouter un nouveau type de relation de deux manières :

-   Utilisez la page **Types de relations**. La nouvelle relation est enregistrée dans **DirRelationshipTypeTable** avec systemtype = 0.

    ![Types de relations.](media/Relationship.PNG)

-  Ajoutez-le à l’extension de l’énumération **DirSystemRelationshipType**, puis renseignez les valeurs via le processus de synchronisation de la base de données.

    1.  Créez une extension à l’énumération **DirSystemRelationshipType** et ajoutez le nouveau type de relation.

    2. Créez un initialiseur pour ce nouveau type. Vous trouverez plusieurs exemples dans le code principal, l’un d’eux est **DirRelationshipTypeChildInitialize**. Il s’agit d’une classe d’initialiseur pour le type de relation de partie « Enfant ». Vous pouvez commencer par votre initialiseur en copiant-collant ce code et en mettant à jour les zones en surbrillance.
    
    ![Initialiseur DirRelationshipChild.](media/DirRelationship.PNG)

    3.  Pour tester le remplissage du nouveau type de relation, vous pouvez créer une classe exécutable et appeler DirDataPopulation::insertDirRelationshipTypes() dans Main(). Le nouveau type de relation doit s’afficher dans la table **DirRelationshipTypeTable**, et il est disponible sur la page **Types de relations**.

        ![Classe exécutable.](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
