---
title: Étendre Talent avec Power Apps et Power Automate
description: Cet article décrit quelques exemples de scénarios d’extensibilité pour Microsoft Dynamics 365 Human Resources utilisant Microsoft Power Apps et Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core;Experience Apps;Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2e89347829ccd6569d568db42c79b5fea2316ba3
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527024"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="95cba-103">Extension avec Power Apps et Power Automate</span><span class="sxs-lookup"><span data-stu-id="95cba-103">Extend with Power Apps and Power Automate</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="95cba-104">Cet article décrit quelques exemples de scénarios d’extensibilité pour Microsoft Dynamics 365 Human Resources utilisant Microsoft Power Apps et Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="95cba-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="95cba-105">Vous pouvez importer le module de solution associé à chaque exemple dans l’environnement de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="95cba-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="95cba-106">Vous pouvez ensuite utiliser les modules comme orientation ou comme point de départ pour implémenter les scénarios qui s’appliquent à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="95cba-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95cba-107">Pour utiliser les modèles et les applications décrits dans cette rubrique « en l’état », veillez à les tester pour vous assurer qu’ils couvrent tous les scénarios spécifiques à votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="95cba-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="95cba-108">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="95cba-108">Prerequisites</span></span>

- <span data-ttu-id="95cba-109">Pour importer des modules, les utilisateurs doivent avoir l’autorisation **Créateur d’environnement**.</span><span class="sxs-lookup"><span data-stu-id="95cba-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="95cba-110">Pour exporter ou importer des applications, les utilisateurs doivent disposer d’une licence Power Apps Plan 2 ou une licence d’essai Power Apps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="95cba-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-microsoft-365-power-automate"></a><span data-ttu-id="95cba-111">Intégration à Microsoft 365, Power Automate</span><span class="sxs-lookup"><span data-stu-id="95cba-111">Integration with Microsoft 365, Power Automate</span></span>

<span data-ttu-id="95cba-112">L’application **Intégration à Microsoft 365** peut être utilisée pour extraire les informations d’équipe pour les utilisateurs connectés à partir de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95cba-112">The **Integration with Microsoft 365** app can be used to extract team information for signed-in users from Microsoft 365.</span></span> <span data-ttu-id="95cba-113">Il fait référence aux employés de Human Resources pour extraire les types d’identification des employés.</span><span class="sxs-lookup"><span data-stu-id="95cba-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="95cba-114">Les responsables peuvent vérifier les dates d’expiration des types d’ID d’employé.</span><span class="sxs-lookup"><span data-stu-id="95cba-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="95cba-115">Ils peuvent également envoyer un rappel par e-mail si le type d’ID d’employé arrive à expiration.</span><span class="sxs-lookup"><span data-stu-id="95cba-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="95cba-116">Power Automate s’intègre à Power Apps pour envoyer ce rappel.</span><span class="sxs-lookup"><span data-stu-id="95cba-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="95cba-117">La confirmation sera renvoyée à Power Apps à partir de Power Automate lorsque le rappel est envoyé.</span><span class="sxs-lookup"><span data-stu-id="95cba-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="95cba-118">Les types d’identification comprennent le permis de conduire, le passeport et d’autres pièces d’identité acceptables.</span><span class="sxs-lookup"><span data-stu-id="95cba-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="95cba-119">Vous pouvez étendre cette application pour d’autres scénarios.</span><span class="sxs-lookup"><span data-stu-id="95cba-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="95cba-120">Par exemple, vous pouvez l’utiliser pour afficher les informations de congés d’équipe, les événements de calendrier, et tout événement spécifique à une équipe.</span><span class="sxs-lookup"><span data-stu-id="95cba-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="95cba-121">Pour télécharger l’application **Intégration à Microsoft 365, Power Automate**, accédez à [Intégration à Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95cba-121">To download the **Integration with Microsoft 365, Power Automate** app, go to [Integration with Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="95cba-122">Power Automate – Connexion et exécution SQL</span><span class="sxs-lookup"><span data-stu-id="95cba-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="95cba-123">Le modèle **Power Automate - Connexion et exécution SQL** se connecte à Microsoft SQL Server et active les requêtes SQL à exécuter.</span><span class="sxs-lookup"><span data-stu-id="95cba-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="95cba-124">Bien que ce modèle lise et mette à jour les tables SQL, vous pouvez l’étendre et l’utiliser pour d’autres scénarios.</span><span class="sxs-lookup"><span data-stu-id="95cba-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="95cba-125">Par exemple, vous pouvez l’utiliser pour remplir une table intermédiaire dans Common Data Service avec des enregistrements de SQL Server, et pour synchroniser périodiquement la table intermédiaire à l’aide d’un envoi incrémentiel de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="95cba-125">For example, you can use it to fill a staging table in Common Data Service with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="95cba-126">Advanced Query est intégré à Flow pour permettre la transformation des données et la transmission incrémentielle.</span><span class="sxs-lookup"><span data-stu-id="95cba-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="95cba-127">Pour télécharger le modèle **Power Automate – Connexion et exécution SQL**, accédez à [Power Automate – Connexion et exécution SQL](https://go.microsoft.com/fwlink/?linkid=2081789) dans le Centre de téléchargement Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95cba-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95cba-128">Ressources supplémentaires</span><span class="sxs-lookup"><span data-stu-id="95cba-128">Additional resources</span></span>

[<span data-ttu-id="95cba-129">Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="95cba-129">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>