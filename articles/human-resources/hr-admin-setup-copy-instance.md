---
title: Copier une instance
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0bbe325edb65cad0c1912e0a6ade559e5675dc58
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008968"
---
# <a name="copy-an-instance"></a><span data-ttu-id="39fe0-102">Copier une instance</span><span class="sxs-lookup"><span data-stu-id="39fe0-102">Copy an instance</span></span>

<span data-ttu-id="39fe0-103">Vous pouvez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour copier une base de données Microsoft Dynamics 365 Human Resources dans un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="39fe0-103">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="39fe0-104">Si vous avez un autre environnement de bac à sable, vous pouvez également copier la base de données de cet environnement vers un environnement cible de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="39fe0-104">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="39fe0-105">Pour copier une instance, vous devez vous assurer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="39fe0-105">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="39fe0-106">L'instance Human Resources que vous souhaitez remplacer doit être un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="39fe0-106">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="39fe0-107">Les environnements à partir desquels vous copiez doivent être situés dans la même région.</span><span class="sxs-lookup"><span data-stu-id="39fe0-107">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="39fe0-108">Vous ne pouvez pas copier entre les régions.</span><span class="sxs-lookup"><span data-stu-id="39fe0-108">You can't copy across regions.</span></span>

- <span data-ttu-id="39fe0-109">Vous devez être administrateur dans l'environnement cible afin de pouvoir vous y connecter après avoir copié l'instance.</span><span class="sxs-lookup"><span data-stu-id="39fe0-109">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="39fe0-110">Lorsque vous copiez la base de données des ressources humaines, vous ne copiez pas les éléments (applications ou données) contenus dans un environnement Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="39fe0-110">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="39fe0-111">Pour plus d'informations sur la copie d'éléments dans un environnement PowerApps, voir [Copier un environnement](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="39fe0-111">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="39fe0-112">L'environnement PowerApps que vous souhaitez remplacer doit être un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="39fe0-112">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="39fe0-113">Vous devez être un administrateur de locataire global pour basculer un environnement PowerApps de production vers un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="39fe0-113">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="39fe0-114">Pour plus d'informations sur la modification d'un environnement PowerApps, voir [Basculer une instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="39fe0-114">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="39fe0-115">Effets de la copie d'une base de données Human Resources</span><span class="sxs-lookup"><span data-stu-id="39fe0-115">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="39fe0-116">Les événements suivants se produisent lorsque vous copiez une base de données Human Resources :</span><span class="sxs-lookup"><span data-stu-id="39fe0-116">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="39fe0-117">Le processus de copie efface la base de données existante dans l'environnement cible.</span><span class="sxs-lookup"><span data-stu-id="39fe0-117">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="39fe0-118">Une fois le processus de copie terminé, vous ne pouvez pas récupérer la base de données existante.</span><span class="sxs-lookup"><span data-stu-id="39fe0-118">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="39fe0-119">L'environnement cible ne sera pas disponible tant que le processus de copie n'est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="39fe0-119">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="39fe0-120">Les documents dans le stockage Microsoft Azure Blob n'est pas copié d'un environnement à un autre.</span><span class="sxs-lookup"><span data-stu-id="39fe0-120">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="39fe0-121">Par conséquent, tous les documents et modèles joints ne seront pas copiés et resteront dans l'environnement source.</span><span class="sxs-lookup"><span data-stu-id="39fe0-121">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="39fe0-122">Tous les utilisateurs sauf l'utilisateur Admin et les autres comptes d'utilisateurs de service interne seront désactivés.</span><span class="sxs-lookup"><span data-stu-id="39fe0-122">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="39fe0-123">Par conséquent, l'utilisateur Admin peut supprimer ou masquer les données avant que d'autres utilisateurs ne soient autorisés à réintégrer le système.</span><span class="sxs-lookup"><span data-stu-id="39fe0-123">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="39fe0-124">L'utilisateur Admin doit apporter les modifications de configuration requises, telles que la reconnexion des points de terminaison d'intégration à des services ou URL spécifiques.</span><span class="sxs-lookup"><span data-stu-id="39fe0-124">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="39fe0-125">Copier la base de données Human Resources</span><span class="sxs-lookup"><span data-stu-id="39fe0-125">Copy the Human Resources database</span></span>

<span data-ttu-id="39fe0-126">Pour terminer cette tâche, vous devez d'abord copier une instance, puis vous connecter au Centre d'administration Microsoft Power Platform pour copier votre environnement PowerApps.</span><span class="sxs-lookup"><span data-stu-id="39fe0-126">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="39fe0-127">Lorsque vous copiez une instance, la base de données est effacée dans l'instance cible.</span><span class="sxs-lookup"><span data-stu-id="39fe0-127">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="39fe0-128">L'instance cible n'est pas disponible pendant ce processus.</span><span class="sxs-lookup"><span data-stu-id="39fe0-128">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="39fe0-129">Connectez-vous à LCS et sélectionnez le projet LCS qui contient l'instance que vous souhaitez copier.</span><span class="sxs-lookup"><span data-stu-id="39fe0-129">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="39fe0-130">Dans votre projet LCS, sélectionnez la vignette **Gestion de l'application Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-130">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="39fe0-131">Sélectionnez l'instance à copier, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-131">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="39fe0-132">Dans le volet des tâches **Copier une instance**, sélectionnez l'instance à remplacer, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-132">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="39fe0-133">Attendez que la valeur du champ **Statut de la copie** affiche **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-133">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="39fe0-134">Sélectionner l'instance à remplacer</span><span class="sxs-lookup"><span data-stu-id="39fe0-134">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="39fe0-135">Sélectionnez **Power Platform**, et aconnectez-vous au Centre d'administration Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="39fe0-135">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="39fe0-136">Sélectionner Power Platform</span><span class="sxs-lookup"><span data-stu-id="39fe0-136">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="39fe0-137">Sélectionnez l'environnement PowerApps à copier, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-137">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="39fe0-138">Une fois le processus de copie terminé, connectez-vous à l'instance cible et activez l'intégration Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="39fe0-138">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="39fe0-139">Pour plus d'informations et instructions, voir [Configurer l'intégration Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="39fe0-139">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="39fe0-140">Éléments de données et statuts</span><span class="sxs-lookup"><span data-stu-id="39fe0-140">Data elements and statuses</span></span>

<span data-ttu-id="39fe0-141">Les éléments de données suivants ne sont pas copiés lorsque vous copiez une instance Human Resources :</span><span class="sxs-lookup"><span data-stu-id="39fe0-141">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="39fe0-142">Adresses e-mail dans la table **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="39fe0-142">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="39fe0-143">Historique des traitements par lots dans les tables **BatchJobHistory**, **BatchHistory**, et **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="39fe0-143">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="39fe0-144">Le mot de passe SMTP (Simple Mail Transfer Protocol) dans la table **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="39fe0-144">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="39fe0-145">Le serveur SMTP Relay dans la table **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="39fe0-145">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="39fe0-146">Paramètres de gestion d'impression dans les tables **PrintMgmtSettings** et **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="39fe0-146">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="39fe0-147">Enregistrements spécifiques à l'environnement dans les tables **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, et **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="39fe0-147">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="39fe0-148">Pièces jointes dans la table DocuValue.</span><span class="sxs-lookup"><span data-stu-id="39fe0-148">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="39fe0-149">Ces pièces jointes comprennent tous les modèles Microsoft Office qui ont été remplacés dans l'environnement source</span><span class="sxs-lookup"><span data-stu-id="39fe0-149">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="39fe0-150">Chaîne de connexion dans la table **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="39fe0-150">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="39fe0-151">Certains de ces éléments ne sont pas copiés car ils sont spécifiques à l'environnement.</span><span class="sxs-lookup"><span data-stu-id="39fe0-151">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="39fe0-152">Les exemples comprennent les enregistrements **BatchServerConfig** et **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-152">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="39fe0-153">Les autres éléments ne sont pas copiés en raison du volume des tickets de support.</span><span class="sxs-lookup"><span data-stu-id="39fe0-153">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="39fe0-154">Par exemple, des e-mails en double peuvent être envoyés car SMTP est toujours activé dans l'environnement de test d'acceptation des utilisateurs (bac à sable), des messages d'intégration non valides peuvent être envoyés car les traitements par lots sont toujours activés et les utilisateurs peuvent être activés avant que les administrateurs puissent effectuer des actions de nettoyage post-actualisation.</span><span class="sxs-lookup"><span data-stu-id="39fe0-154">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="39fe0-155">En outre, les statuts suivants changent lorsque vous copiez une instance :</span><span class="sxs-lookup"><span data-stu-id="39fe0-155">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="39fe0-156">Tous les utilisateurs sauf Admin sont définis sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-156">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="39fe0-157">Tous les traitements par lots, à l'exception de certains traitements système, sont définis sur **Retenir**.</span><span class="sxs-lookup"><span data-stu-id="39fe0-157">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="39fe0-158">Administrateur de l'environnement</span><span class="sxs-lookup"><span data-stu-id="39fe0-158">Environment admin</span></span>

<span data-ttu-id="39fe0-159">Tous les utilisateurs de l'environnement de bac à sable cible, y compris les administrateurs, sont remplacés par les utilisateurs de l'environnement source.</span><span class="sxs-lookup"><span data-stu-id="39fe0-159">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="39fe0-160">Avant de copier une instance, assurez-vous que vous êtes administrateur dans l'environnement cible.</span><span class="sxs-lookup"><span data-stu-id="39fe0-160">Before you copy an instance, be sure that you're an Administrator in the target environment.</span></span> <span data-ttu-id="39fe0-161">Si ce n'est pas le cas, vous ne pourrez pas vous connecter à l'environnement de bac à sable cible une fois la copie terminée.</span><span class="sxs-lookup"><span data-stu-id="39fe0-161">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="39fe0-162">Tous les utilisateurs non administrateurs de l'environnement de bac à sable cible sont désactivés pour empêcher les connexions indésirables dans l'environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="39fe0-162">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="39fe0-163">Les administrateurs peuvent réactiver les utilisateurs si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="39fe0-163">Administrators can reenable users if needed.</span></span>
