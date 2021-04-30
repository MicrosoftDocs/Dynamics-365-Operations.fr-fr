---
title: Copier une instance
description: Vous pouvez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour copier une base de données Microsoft Dynamics 365 Human Resources dans un environnement de bac à sable.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44df05083cd3c91e5dcbdb3062665c2145d92a7e
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889810"
---
# <a name="copy-an-instance"></a><span data-ttu-id="dce00-103">Copier une instance</span><span class="sxs-lookup"><span data-stu-id="dce00-103">Copy an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="dce00-104">Vous pouvez utiliser Microsoft Dynamics Lifecycle Services (LCS) pour copier une base de données Microsoft Dynamics 365 Human Resources dans un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="dce00-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="dce00-105">Si vous avez un autre environnement de bac à sable, vous pouvez également copier la base de données de cet environnement vers un environnement cible de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="dce00-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="dce00-106">Pour copier une instance, gardez à l’esprit les conseils suivants :</span><span class="sxs-lookup"><span data-stu-id="dce00-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="dce00-107">L’instance Human Resources que vous souhaitez remplacer doit être un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="dce00-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="dce00-108">Les environnements à partir desquels vous copiez doivent être situés dans la même région.</span><span class="sxs-lookup"><span data-stu-id="dce00-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="dce00-109">Vous ne pouvez pas copier entre les régions.</span><span class="sxs-lookup"><span data-stu-id="dce00-109">You can't copy across regions.</span></span>

- <span data-ttu-id="dce00-110">Vous devez être administrateur dans l’environnement cible afin de pouvoir vous y connecter après avoir copié l’instance.</span><span class="sxs-lookup"><span data-stu-id="dce00-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="dce00-111">Lorsque vous copiez la base de données des ressources humaines, vous ne copiez pas les éléments (applications ou données) contenus dans un environnement Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="dce00-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="dce00-112">Pour plus d’informations sur la copie d’éléments dans un environnement Power Apps, voir [Copier un environnement](/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="dce00-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="dce00-113">L’environnement Power Apps que vous souhaitez remplacer doit être un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="dce00-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="dce00-114">Vous devez être un administrateur de locataire global pour basculer un environnement Power Apps de production vers un environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="dce00-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="dce00-115">Pour plus d’informations sur la modification d’un environnement Power Apps, voir [Basculer une instance](/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="dce00-115">For more information about changing a Power Apps environment, see [Switch an instance](/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="dce00-116">Si vous copiez une instance dans votre environnement bac à sable et souhaitez intégrer votre environnement bac à sable à Dataverse, vous devez réappliquer les champs personnalisés aux tables Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dce00-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span> <span data-ttu-id="dce00-117">Voir [Appliquer des champs personnalisés à Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="dce00-117">See [Apply custom fields to Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="dce00-118">Effets de la copie d’une base de données Human Resources</span><span class="sxs-lookup"><span data-stu-id="dce00-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="dce00-119">Les événements suivants se produisent lorsque vous copiez une base de données Human Resources :</span><span class="sxs-lookup"><span data-stu-id="dce00-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="dce00-120">Le processus de copie efface la base de données existante dans l’environnement cible.</span><span class="sxs-lookup"><span data-stu-id="dce00-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="dce00-121">Une fois le processus de copie terminé, vous ne pouvez pas récupérer la base de données existante.</span><span class="sxs-lookup"><span data-stu-id="dce00-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="dce00-122">L’environnement cible ne sera pas disponible tant que le processus de copie n’est pas terminé.</span><span class="sxs-lookup"><span data-stu-id="dce00-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="dce00-123">Les documents dans le stockage Microsoft Azure Blob n’est pas copié d’un environnement à un autre.</span><span class="sxs-lookup"><span data-stu-id="dce00-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="dce00-124">En conséquence, tous les documents et modèles joints ne seront pas copiés et resteront dans l’environnement source.</span><span class="sxs-lookup"><span data-stu-id="dce00-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="dce00-125">Tous les utilisateurs sauf l’utilisateur Admin et les autres comptes d’utilisateurs de service interne seront désactivés.</span><span class="sxs-lookup"><span data-stu-id="dce00-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="dce00-126">L’utilisateur Admin peut supprimer ou masquer les données avant que d’autres utilisateurs ne soient autorisés à réintégrer le système.</span><span class="sxs-lookup"><span data-stu-id="dce00-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="dce00-127">L’utilisateur Admin doit apporter les modifications de configuration requises, telles que la reconnexion des points de terminaison d’intégration à des services ou URL spécifiques.</span><span class="sxs-lookup"><span data-stu-id="dce00-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="dce00-128">Copier la base de données Human Resources</span><span class="sxs-lookup"><span data-stu-id="dce00-128">Copy the Human Resources database</span></span>

<span data-ttu-id="dce00-129">Pour terminer cette tâche, vous devez d’abord copier une instance, puis vous connecter au Centre d’administration Microsoft Power Platform pour copier votre environnement Power Apps.</span><span class="sxs-lookup"><span data-stu-id="dce00-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="dce00-130">Lorsque vous copiez une instance, la base de données est effacée dans l’instance cible.</span><span class="sxs-lookup"><span data-stu-id="dce00-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="dce00-131">L’instance cible n’est pas disponible pendant ce processus.</span><span class="sxs-lookup"><span data-stu-id="dce00-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="dce00-132">Connectez-vous à LCS et sélectionnez le projet LCS qui contient l’instance que vous souhaitez copier.</span><span class="sxs-lookup"><span data-stu-id="dce00-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="dce00-133">Dans votre projet LCS, sélectionnez la vignette **Gestion de l’application Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="dce00-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="dce00-134">Sélectionnez l’instance à copier, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="dce00-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="dce00-135">Dans le volet des tâches **Copier une instance**, sélectionnez l’instance à remplacer, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="dce00-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="dce00-136">Attendez que la valeur du champ **Statut de la copie** affiche **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="dce00-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="dce00-137">Sélectionner l’instance à remplacer</span><span class="sxs-lookup"><span data-stu-id="dce00-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="dce00-138">Sélectionnez **Power Platform**, et aconnectez-vous au Centre d’administration Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="dce00-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="dce00-139">Sélectionner Power Platform</span><span class="sxs-lookup"><span data-stu-id="dce00-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="dce00-140">Sélectionnez l’environnement Power Apps à copier, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="dce00-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="dce00-141">Une fois le processus de copie terminé, connectez-vous à l’instance cible et activez l’intégration Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dce00-141">When the copy process is completed, sign in to the target instance, and enable Dataverse integration.</span></span> <span data-ttu-id="dce00-142">Pour plus d’informations et instructions, voir [Configurer l’intégration Dataverse](./hr-admin-integration-common-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="dce00-142">For more information and instructions, see [Configure Dataverse integration](./hr-admin-integration-common-data-service.md).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="dce00-143">Éléments de données et statuts</span><span class="sxs-lookup"><span data-stu-id="dce00-143">Data elements and statuses</span></span>

<span data-ttu-id="dce00-144">Les éléments de données suivants ne sont pas copiés lorsque vous copiez une instance Human Resources :</span><span class="sxs-lookup"><span data-stu-id="dce00-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="dce00-145">Adresses e-mail dans la table **LogisticsElectronicAddress**</span><span class="sxs-lookup"><span data-stu-id="dce00-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="dce00-146">Historique des traitements par lots dans les tables **BatchJobHistory**, **BatchHistory**, et **BatchConstraintHistory**</span><span class="sxs-lookup"><span data-stu-id="dce00-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="dce00-147">Le mot de passe SMTP (Simple Mail Transfer Protocol) dans la table **SysEmailSMTPPassword**</span><span class="sxs-lookup"><span data-stu-id="dce00-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="dce00-148">Le serveur SMTP Relay dans la table **SysEmailParameters**</span><span class="sxs-lookup"><span data-stu-id="dce00-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="dce00-149">Paramètres de gestion d’impression dans les tables **PrintMgmtSettings** et **PrintMgmtDocInstance**</span><span class="sxs-lookup"><span data-stu-id="dce00-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="dce00-150">Enregistrements spécifiques à l’environnement dans les tables **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, et **BatchServerGroup**</span><span class="sxs-lookup"><span data-stu-id="dce00-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="dce00-151">Pièces jointes dans la table DocuValue.</span><span class="sxs-lookup"><span data-stu-id="dce00-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="dce00-152">Ces pièces jointes comprennent tous les modèles Microsoft Office qui ont été remplacés dans l’environnement source</span><span class="sxs-lookup"><span data-stu-id="dce00-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="dce00-153">Chaîne de connexion dans la table **PersonnelIntegrationConfiguration**</span><span class="sxs-lookup"><span data-stu-id="dce00-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="dce00-154">Certains de ces éléments ne sont pas copiés, car ils sont spécifiques à l’environnement.</span><span class="sxs-lookup"><span data-stu-id="dce00-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="dce00-155">Les exemples comprennent les enregistrements **BatchServerConfig** et **SysCorpNetPrinters**.</span><span class="sxs-lookup"><span data-stu-id="dce00-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="dce00-156">Les autres éléments ne sont pas copiés en raison du volume des tickets de support.</span><span class="sxs-lookup"><span data-stu-id="dce00-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="dce00-157">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="dce00-157">For example:</span></span>

- <span data-ttu-id="dce00-158">Des e-mails en double peuvent être envoyés, car SMTP est toujours activé dans l’environnement de test d’acceptation utilisateur (bac à sable).</span><span class="sxs-lookup"><span data-stu-id="dce00-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="dce00-159">Des messages d’intégration non valides peuvent être envoyés, car les tâches par lots sont toujours activées.</span><span class="sxs-lookup"><span data-stu-id="dce00-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="dce00-160">Les utilisateurs peuvent être activés avant que les administrateurs puissent effectuer des actions de nettoyage post-actualisation.</span><span class="sxs-lookup"><span data-stu-id="dce00-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="dce00-161">De plus, les statuts suivants changent lorsque vous copiez une instance :</span><span class="sxs-lookup"><span data-stu-id="dce00-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="dce00-162">Tous les utilisateurs sauf Admin sont définis sur **Désactivé**.</span><span class="sxs-lookup"><span data-stu-id="dce00-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="dce00-163">Tous les traitements par lots, à l’exception de certains traitements système, sont définis sur **Retenir**.</span><span class="sxs-lookup"><span data-stu-id="dce00-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="dce00-164">Administrateur de l’environnement</span><span class="sxs-lookup"><span data-stu-id="dce00-164">Environment admin</span></span>

<span data-ttu-id="dce00-165">Tous les utilisateurs de l’environnement de bac à sable cible, y compris les administrateurs, sont remplacés par les utilisateurs de l’environnement source.</span><span class="sxs-lookup"><span data-stu-id="dce00-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="dce00-166">Avant de copier une instance, assurez-vous que vous êtes administrateur dans l’environnement source.</span><span class="sxs-lookup"><span data-stu-id="dce00-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="dce00-167">Si ce n’est pas le cas, vous ne pouvez pas vous connecter à l’environnement de bac à sable cible une fois la copie terminée.</span><span class="sxs-lookup"><span data-stu-id="dce00-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="dce00-168">Tous les utilisateurs non administrateurs de l’environnement de bac à sable cible sont désactivés pour empêcher les connexions indésirables dans l’environnement de bac à sable.</span><span class="sxs-lookup"><span data-stu-id="dce00-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="dce00-169">Les administrateurs peuvent réactiver les utilisateurs si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="dce00-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-dataverse"></a><span data-ttu-id="dce00-170">Appliquer des champs personnalisés à Dataverse</span><span class="sxs-lookup"><span data-stu-id="dce00-170">Apply custom fields to Dataverse</span></span>

<span data-ttu-id="dce00-171">Si vous copiez une instance dans votre environnement bac à sable et souhaitez intégrer votre environnement bac à sable à Dataverse, vous devez réappliquer les champs personnalisés aux tables Dataverse.</span><span class="sxs-lookup"><span data-stu-id="dce00-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span>

<span data-ttu-id="dce00-172">Pour chaque champ personnalisé exposé sur des tables Dataverse, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="dce00-172">For each custom field that's exposed on Dataverse tables, do the following steps:</span></span>

1. <span data-ttu-id="dce00-173">Accédez au champ personnalisé et sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="dce00-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="dce00-174">Désélectionnez le champ **Activé** pour chaque entité cdm_\* sur laquelle le champ personnalisé est activé.</span><span class="sxs-lookup"><span data-stu-id="dce00-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="dce00-175">Sélectionnez **Appliquer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="dce00-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="dce00-176">Sélectionnez à nouveau **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="dce00-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="dce00-177">Sélectionnez le champ **Activé** pour chaque entité cdm_\* sur laquelle le champ personnalisé est activé.</span><span class="sxs-lookup"><span data-stu-id="dce00-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="dce00-178">Sélectionnez à nouveau **Appliquer les modifications**.</span><span class="sxs-lookup"><span data-stu-id="dce00-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="dce00-179">Le processus de désélection, d’application des modifications, de resélection et de réapplication des modifications invite le schéma à se mettre à jour dans Dataverse pour inclure les champs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="dce00-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Dataverse to include the custom fields.</span></span>

<span data-ttu-id="dce00-180">Pour plus d’informations sur la création de champs personnalisés, voir [Créer et utiliser des champs personnalisés](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span><span class="sxs-lookup"><span data-stu-id="dce00-180">For more information about custom fields, see [Create and work with custom fields](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dce00-181">Voir également :</span><span class="sxs-lookup"><span data-stu-id="dce00-181">See also</span></span>

[<span data-ttu-id="dce00-182">Mettre en service Human Resources</span><span class="sxs-lookup"><span data-stu-id="dce00-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="dce00-183">Supprimer une instance</span><span class="sxs-lookup"><span data-stu-id="dce00-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="dce00-184">Processus de mise à jour</span><span class="sxs-lookup"><span data-stu-id="dce00-184">Update process</span></span>](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]