---
title: Ajouter un emplacement et des types de relations de partie
description: Cette rubrique explique comment ajouter un nouvel emplacement et un nouveau type de relation de partie.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 13157700b9311e93aa035162ed89ed006e1453b5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228171"
---
# <a name="add-location-and-party-relationship-types"></a><span data-ttu-id="ea6e1-103">Ajouter un emplacement et des types de relations de partie</span><span class="sxs-lookup"><span data-stu-id="ea6e1-103">Add location and party relationship types</span></span> 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a><span data-ttu-id="ea6e1-104">Ajouter des rôles d’emplacement</span><span class="sxs-lookup"><span data-stu-id="ea6e1-104">Add location roles</span></span>

<span data-ttu-id="ea6e1-105">Vous pouvez ajouter un nouveau rôle d’emplacement pour les informations d’adresse et de contact de deux manières :</span><span class="sxs-lookup"><span data-stu-id="ea6e1-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="ea6e1-106">Utilisez la page **Objet des informations d’adresse et de contact**.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="ea6e1-107">Le nouveau rôle est enregistré dans la table **LogisticsLocationRole** avec type = 0, qui indique que le rôle n’est pas un rôle système défini dans l’énumération **LogisticsLocationRoleType** et ses extensions.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="ea6e1-108">Un utilisateur peut utiliser ce rôle lors de la création des informations d’adresse ou de contact.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Objet des informations d’adresse et de contact](media/Address-Contact.PNG)

-  <span data-ttu-id="ea6e1-110">Ajoutez-le à l’extension de l’énumération **LogisticsLocationRoleType**, puis renseignez les valeurs via le processus de synchronisation de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="ea6e1-111">Créez une extension à l’énumération **LogisticsLocationRoleType** et ajoutez le nouveau rôle dans l’extension.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![Extension à l’énumération LogisticsLocationRoleType](media/Logistics.PNG)

    2. <span data-ttu-id="ea6e1-113">Créez un fichier de ressource pour le nouveau rôle, puis affectez une valeur pour ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Nouveau fichier de ressource](media/Resource.PNG)
        
    3.  <span data-ttu-id="ea6e1-115">Créez une classe de remplissage des données et fournissez une méthode de gestionnaire pour renseigner le nouveau rôle.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Remplissage des données](media/Dirdata.PNG)

    4.  <span data-ttu-id="ea6e1-117">Pour tester le remplissage du nouveau rôle d’emplacement, vous pouvez créer une classe exécutable et appeler DirDataPopulation::insertLogisticsLocationRoles() dans Main().</span><span class="sxs-lookup"><span data-stu-id="ea6e1-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="ea6e1-118">Une fois ce processus terminé, le nouveau rôle est enregistré dans la table **LogisticsLocationRole** avec type \> 0.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="ea6e1-119">Le nouveau rôle s’affiche sur la page **Objet des informations d’adresse et de contact**.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Insérer un nouvel emplacement](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a><span data-ttu-id="ea6e1-121">Ajouter des types de relation de partie</span><span class="sxs-lookup"><span data-stu-id="ea6e1-121">Add party relationship types</span></span> 

<span data-ttu-id="ea6e1-122">Vous pouvez ajouter un nouveau type de relation de deux manières :</span><span class="sxs-lookup"><span data-stu-id="ea6e1-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="ea6e1-123">Utilisez la page **Types de relations**.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="ea6e1-124">La nouvelle relation est enregistrée dans **DirRelationshipTypeTable** avec systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Types de relations](media/Relationship.PNG)

-  <span data-ttu-id="ea6e1-126">Ajoutez-le à l’extension de l’énumération **DirSystemRelationshipType**, puis renseignez les valeurs via le processus de synchronisation de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="ea6e1-127">Créez une extension à l’énumération **DirSystemRelationshipType** et ajoutez le nouveau type de relation.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="ea6e1-128">Créez un initialiseur pour ce nouveau type.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-128">Create an initializer for this new type.</span></span> <span data-ttu-id="ea6e1-129">Vous trouverez plusieurs exemples dans le code principal, l’un d’eux est **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="ea6e1-130">Il s’agit d’une classe d’initialiseur pour le type de relation de partie « Enfant ».</span><span class="sxs-lookup"><span data-stu-id="ea6e1-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="ea6e1-131">Vous pouvez commencer par votre initialiseur en copiant-collant ce code et en mettant à jour les zones en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![Initialiseur DirRelationshipChild](media/DirRelationship.PNG)

    3.  <span data-ttu-id="ea6e1-133">Pour tester le remplissage du nouveau type de relation, vous pouvez créer une classe exécutable et appeler DirDataPopulation::insertDirRelationshipTypes() dans Main().</span><span class="sxs-lookup"><span data-stu-id="ea6e1-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="ea6e1-134">Le nouveau type de relation doit s’afficher dans la table **DirRelationshipTypeTable**, et il est disponible sur la page **Types de relations**.</span><span class="sxs-lookup"><span data-stu-id="ea6e1-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Classe exécutable](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]