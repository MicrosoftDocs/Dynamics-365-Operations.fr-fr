---
title: Utilisation de Power Portal avec le modèle de données de partie
description: Cette rubrique décrit les modifications apportées aux rôles web de Power Portal en raison du modèle de données de partie en double écriture.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833088"
---
# <a name="using-power-portal-with-the-party-data-model"></a><span data-ttu-id="a3357-103">Utilisation de Power Portal avec le modèle de données de partie</span><span class="sxs-lookup"><span data-stu-id="a3357-103">Using Power Portal with the Party data model</span></span>

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a3357-104">La solution d’orchestration de l’application de double écriture, version 2.0.999.0 et versions ultérieures, inclut des modifications du modèle de données pour le carnet d’adresses global et de partie pour les tables Compte et Contact.</span><span class="sxs-lookup"><span data-stu-id="a3357-104">The Dual-write application orchestration solution version 2.0.999.0 and later includes data model changes to party and global address book for the Account and Contact tables.</span></span> <span data-ttu-id="a3357-105">Les modifications autorisent les relations plusieurs-à-plusieurs qui prennent en charge des scénarios d’entreprise avancés.</span><span class="sxs-lookup"><span data-stu-id="a3357-105">The changes allow many-to-many relationships that support advanced business scenarios.</span></span> <span data-ttu-id="a3357-106">Ces modifications ne sont pas prises en charge par les rôles web du portail, notamment du portail client, qui sont livrés prêts à l’emploi ou qui existaient dans votre environnement avant l’installation de la double écriture.</span><span class="sxs-lookup"><span data-stu-id="a3357-106">These changes are not supported by portal web roles, including the customer portal, that are shipped out-of-the-box or that existed in your environment before you installed dual-write.</span></span> <span data-ttu-id="a3357-107">Pour que les rôles web fonctionnent comme prévu, vous devez créer de nouveaux rôles web à l’aide du nouveau modèle de données.</span><span class="sxs-lookup"><span data-stu-id="a3357-107">For the web roles to work as expected, you need to create new web roles using the new data model.</span></span> 

<span data-ttu-id="a3357-108">En résumé, la façon dont les tables interagissent a changé, mais les autorisations de table dans le portail client n’ont pas changé.</span><span class="sxs-lookup"><span data-stu-id="a3357-108">In summary, the way the tables interact has changed, but the table permissions in the customer portal haven't changed.</span></span> <span data-ttu-id="a3357-109">Cette rubrique explique comment créer de nouveaux rôles web qui fonctionnent avec le nouveau modèle de données avancé.</span><span class="sxs-lookup"><span data-stu-id="a3357-109">This topic explains how to create new web roles that work with the new advanced data model.</span></span>

<span data-ttu-id="a3357-110">Ce schéma montre la relation de table **sans** le modèle de données du carnet d’adresses global et de partie :</span><span class="sxs-lookup"><span data-stu-id="a3357-110">This diagram shows the table relationship **without** the party and global address book data model:</span></span>

   ![sans modèle de partie](media/without-party-model.PNG)

<span data-ttu-id="a3357-112">Ce schéma montre la relation de table **avec** le modèle de données du carnet d’adresses global et de partie :</span><span class="sxs-lookup"><span data-stu-id="a3357-112">This diagram shows the table relationship **with** the party and global address book data model:</span></span>

   ![avec modèle de partie](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a><span data-ttu-id="a3357-114">Créer une nouvelle autorisation de table</span><span class="sxs-lookup"><span data-stu-id="a3357-114">Create a new table permission</span></span>

<span data-ttu-id="a3357-115">Pour créer ces nouvelles autorisations de table, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a3357-115">To create these new table permissions, follow these steps:</span></span>

1. <span data-ttu-id="a3357-116">Connectez-vous à [Power Apps](https://make.powerapps.com) et accédez à vos applications.</span><span class="sxs-lookup"><span data-stu-id="a3357-116">Sign in to [Power Apps](https://make.powerapps.com), and go to your apps.</span></span>
2. <span data-ttu-id="a3357-117">Sélectionnez votre application de gestion du portail.</span><span class="sxs-lookup"><span data-stu-id="a3357-117">Select your Portal Management app.</span></span>
3. <span data-ttu-id="a3357-118">Dans la barre latérale, sélectionnez **Sécurité > Autorisations de table**.</span><span class="sxs-lookup"><span data-stu-id="a3357-118">In the side bar, select **Security > Table permissions**.</span></span>

    <span data-ttu-id="a3357-119">Vous devez créer trois nouvelles autorisations :</span><span class="sxs-lookup"><span data-stu-id="a3357-119">You must create three new permissions:</span></span>

    + <span data-ttu-id="a3357-120">Connexion Contact à Partie</span><span class="sxs-lookup"><span data-stu-id="a3357-120">Contact to Party connection</span></span>
    + <span data-ttu-id="a3357-121">Connexion Partie à Compte</span><span class="sxs-lookup"><span data-stu-id="a3357-121">Party to Account connection</span></span>
    + <span data-ttu-id="a3357-122">Connexion Compte à Commande</span><span class="sxs-lookup"><span data-stu-id="a3357-122">Account to Order connection</span></span>

4. <span data-ttu-id="a3357-123">Créez et enregistrez une nouvelle autorisation pour la connexion de Contact à Partie, en définissant ces paramètres :</span><span class="sxs-lookup"><span data-stu-id="a3357-123">Create and save a new permission for the Contact to Party connection, setting these parameters:</span></span>

    + <span data-ttu-id="a3357-124">**Nom** : Connexion Partie à Compte (ou votre choix)</span><span class="sxs-lookup"><span data-stu-id="a3357-124">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="a3357-125">**Nom de la table** : msdyn_contactforparty</span><span class="sxs-lookup"><span data-stu-id="a3357-125">**Table Name**: msdyn_contactforparty</span></span>
    + <span data-ttu-id="a3357-126">**Site web** : Portail client</span><span class="sxs-lookup"><span data-stu-id="a3357-126">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="a3357-127">**Étendue** : Contact</span><span class="sxs-lookup"><span data-stu-id="a3357-127">**Scope**: Contact</span></span>
    + <span data-ttu-id="a3357-128">**Privilèges** : Tout sélectionner</span><span class="sxs-lookup"><span data-stu-id="a3357-128">**Privileges**: Select all</span></span>
    + <span data-ttu-id="a3357-129">**Rôles web** : Utilisateurs authentifiés, Représentant du client (ou votre choix)</span><span class="sxs-lookup"><span data-stu-id="a3357-129">**Web roles**: Authenticated Users, Customer Representative (or your choice)</span></span>

5. <span data-ttu-id="a3357-130">Créez et enregistrez une nouvelle autorisation pour la connexion de Partie à Compte, en définissant ces paramètres :</span><span class="sxs-lookup"><span data-stu-id="a3357-130">Create and save a new permission for the Party to Account connection, setting these parameters:</span></span>

    + <span data-ttu-id="a3357-131">**Nom** : Connexion Partie à Compte (ou votre choix)</span><span class="sxs-lookup"><span data-stu-id="a3357-131">**Name**: Party to Account Connection (or your choice)</span></span>
    + <span data-ttu-id="a3357-132">**Nom de la table** : account</span><span class="sxs-lookup"><span data-stu-id="a3357-132">**Table Name**: account</span></span>
    + <span data-ttu-id="a3357-133">**Site web** : Portail client</span><span class="sxs-lookup"><span data-stu-id="a3357-133">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="a3357-134">**Étendue** : Parent</span><span class="sxs-lookup"><span data-stu-id="a3357-134">**Scope**: Parent</span></span>
    + <span data-ttu-id="a3357-135">**Privilèges** : Tout sélectionner</span><span class="sxs-lookup"><span data-stu-id="a3357-135">**Privileges**: Select all</span></span>
    + <span data-ttu-id="a3357-136">**Autorisation de la table parent** : Connexion Contact à Partie</span><span class="sxs-lookup"><span data-stu-id="a3357-136">**Parent Table Permission**: Contact to Party Connection</span></span>

6. <span data-ttu-id="a3357-137">Créez et enregistrez une nouvelle autorisation pour la connexion de Compte à Commande, en définissant ces paramètres :</span><span class="sxs-lookup"><span data-stu-id="a3357-137">Create and save a new permission for the Account to Order connection, setting these parameters:</span></span>

    + <span data-ttu-id="a3357-138">**Nom** : Connexion Compte à Commande (ou votre choix)</span><span class="sxs-lookup"><span data-stu-id="a3357-138">**Name**: Account to Order Connection (or your choice)</span></span>
    + <span data-ttu-id="a3357-139">**Nom de la table** : salesorder</span><span class="sxs-lookup"><span data-stu-id="a3357-139">**Table Name**: salesorder</span></span>
    + <span data-ttu-id="a3357-140">**Site web** : Portail client</span><span class="sxs-lookup"><span data-stu-id="a3357-140">**Website**: Customer Portal</span></span>
    + <span data-ttu-id="a3357-141">**Étendue** : Parent</span><span class="sxs-lookup"><span data-stu-id="a3357-141">**Scope**: Parent</span></span>
    + <span data-ttu-id="a3357-142">**Privilèges** : Tout sélectionner</span><span class="sxs-lookup"><span data-stu-id="a3357-142">**Privileges**: Select all</span></span>
    + <span data-ttu-id="a3357-143">**Autorisation de la table parent** : Connexion Partie à Compte</span><span class="sxs-lookup"><span data-stu-id="a3357-143">**Parent Table Permission**: Party to Account Connection</span></span>

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
