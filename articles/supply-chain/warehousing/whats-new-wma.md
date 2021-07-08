---
title: Nouveautés ou modifications dans l’application mobile Warehouse Management
description: Cette rubrique répertorie les fonctionnalités nouvelles et modifiées pour chaque version publiée de l’application mobile Warehouse Management pour Microsoft Dynamics 365 Supply Chain Management.
author: ivanv-microsoft
ms.date: 06/07/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 61124728942c0b8162de9f687ae752773c47d07e
ms.sourcegitcommit: 4cbd83e21a78459e4711a2dedba0f5a7acc3c841
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2021
ms.locfileid: "6261776"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="6ff15-103">Nouveautés ou modifications dans l’application mobile Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="6ff15-103">What's new or changed in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ff15-104">Cette rubrique répertorie les nouvelles fonctionnalités, les correctifs, les améliorations et les problèmes connus pour chaque version publiée de l’application mobile Warehouse Management pour Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="6ff15-104">This topic lists new features, fixes, improvements, and known issues for each released version of the Warehouse Management mobile app for Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="version-2060"></a><span data-ttu-id="6ff15-105">Version 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="6ff15-105">Version 2.0.6.0</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2060"></a><span data-ttu-id="6ff15-106">Nouvelles fonctionnalités, correctifs et améliorations dans la version 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="6ff15-106">New features, fixes, and improvements in version 2.0.6.0</span></span>

<span data-ttu-id="6ff15-107">Cette version introduit les nouvelles fonctionnalités, les correctifs et les améliorations suivants :</span><span class="sxs-lookup"><span data-stu-id="6ff15-107">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="6ff15-108">Le mode de démonstration affiche désormais toutes les étiquettes dans la langue de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6ff15-108">Demo mode now shows all labels in the device language.</span></span>
- <span data-ttu-id="6ff15-109">Vous êtes moins susceptible de recevoir le message d’erreur suivant : « Impossible de trouver une vue appropriée pour la taille spécifiée. »</span><span class="sxs-lookup"><span data-stu-id="6ff15-109">You're less likely to receive the following error message: "Cannot find a suitable view for the specified size."</span></span>
- <span data-ttu-id="6ff15-110">La hauteur minimale des fiches de travail a été augmentée (pour les cas où trois champs ou moins sont configurés pour la liste de travail).</span><span class="sxs-lookup"><span data-stu-id="6ff15-110">The minimum height for work cards has been increased (for cases where three or fewer fields are configured to appear in the work list).</span></span>
- <span data-ttu-id="6ff15-111">Les marges (le fondu) au bas des cartes de détails ont été améliorées.</span><span class="sxs-lookup"><span data-stu-id="6ff15-111">Margins (fade out) at the bottom of details cards have been improved.</span></span>
- <span data-ttu-id="6ff15-112">Les symboles non valides dans les fichiers XML échangés avec le serveur sont désormais gérés correctement.</span><span class="sxs-lookup"><span data-stu-id="6ff15-112">Invalid symbols in XML files that are exchanged with the server are now handled gracefully.</span></span> <span data-ttu-id="6ff15-113">(Par exemple, les caractères non imprimables sont désormais gérés correctement et n’empêchent plus l’application de répondre.)</span><span class="sxs-lookup"><span data-stu-id="6ff15-113">(For example, non-printable characters are now handled gracefully and no longer cause the app to stop responding.)</span></span>
- <span data-ttu-id="6ff15-114">Les erreurs HTTP (telles que « erreur 503 ») lorsqu’une requête serveur est soumise sont désormais traitées correctement.</span><span class="sxs-lookup"><span data-stu-id="6ff15-114">HTTP errors (such as "error 503") when a server request is submitted are now handled gracefully.</span></span>
- <span data-ttu-id="6ff15-115">Lorsqu’une erreur est affichée, la liste des options n’est plus affichée automatiquement pour les contrôles de zone de liste.</span><span class="sxs-lookup"><span data-stu-id="6ff15-115">While an error is being shown, the options list is no longer automatically shown for combo box controls.</span></span>
- <span data-ttu-id="6ff15-116">L’application ne cesse plus de répondre en raison de l’orientation d’affichage sélectionnée dans les paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6ff15-116">The app no longer stops responding because of the display orientation that is selected in user settings.</span></span>
- <span data-ttu-id="6ff15-117">Les images des produits sont désormais affichées dans des environnements en libre service.</span><span class="sxs-lookup"><span data-stu-id="6ff15-117">Product images are now shown in self-service environments.</span></span> <span data-ttu-id="6ff15-118">(Cette modification s’applique uniquement aux versions basse résolution.</span><span class="sxs-lookup"><span data-stu-id="6ff15-118">(This change applies to low-resolution versions only.</span></span> <span data-ttu-id="6ff15-119">Le service de gestion de fichiers ne prend pas en charge les images en taille réelle dans les environnements en libre service.)</span><span class="sxs-lookup"><span data-stu-id="6ff15-119">The file management service doesn't support full-sized images in self-service environments.)</span></span>
- <span data-ttu-id="6ff15-120">Un problème qui impliquait des prélèvements partiels de quantité nulle (zéro) a été corrigé.</span><span class="sxs-lookup"><span data-stu-id="6ff15-120">An issue that involved zero-quantity short picks has been fixed.</span></span>
- <span data-ttu-id="6ff15-121">L’application ne cesse plus de répondre lorsqu’une carte de détails affiche plusieurs champs identiques.</span><span class="sxs-lookup"><span data-stu-id="6ff15-121">The app no longer stops responding when a details card shows multiple identical fields.</span></span>

### <a name="known-issues-in-version-2060"></a><span data-ttu-id="6ff15-122">Problèmes connus dans la version 2.0.6.0</span><span class="sxs-lookup"><span data-stu-id="6ff15-122">Known issues in version 2.0.6.0</span></span>

<span data-ttu-id="6ff15-123">Cette version présente les problèmes connus suivants :</span><span class="sxs-lookup"><span data-stu-id="6ff15-123">The following known issues exist in this version:</span></span>

- <span data-ttu-id="6ff15-124">L’application (en particulier la liste de travail) devient plus lente au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="6ff15-124">The app (especially the work list) becomes slower over time.</span></span>
- <span data-ttu-id="6ff15-125">**Version Windows :** lorsqu’un pistolet USB est utilisé pour la lecture sous Windows, des résultats incohérents entraînent une confusion des symboles numérisés.</span><span class="sxs-lookup"><span data-stu-id="6ff15-125">**Windows version:** When a USB gun is used for scanning on Windows, inconsistent results cause scanned symbols to be mixed up.</span></span>

## <a name="version-2050"></a><span data-ttu-id="6ff15-126">Version 2.0.5.0</span><span class="sxs-lookup"><span data-stu-id="6ff15-126">Version 2.0.5.0</span></span>

<span data-ttu-id="6ff15-127">Cette version introduit les nouvelles fonctionnalités, les correctifs et les améliorations suivants :</span><span class="sxs-lookup"><span data-stu-id="6ff15-127">This version introduces the following new features, fixes, and improvements:</span></span>

- <span data-ttu-id="6ff15-128">Le secret client n’est plus masqué dans la configuration des paramètres de connexion.</span><span class="sxs-lookup"><span data-stu-id="6ff15-128">The client secret is no longer hidden in the connection settings setup.</span></span>
- <span data-ttu-id="6ff15-129">Vous pouvez maintenant appuyer longuement sur n’importe quel texte pour le voir complètement.</span><span class="sxs-lookup"><span data-stu-id="6ff15-129">You can now long-press on any text to see it fully.</span></span>
- <span data-ttu-id="6ff15-130">Le message d’erreur lorsque les autorisations de stockage sont absentes a été amélioré.</span><span class="sxs-lookup"><span data-stu-id="6ff15-130">The error message when storage permissions are missing has been improved.</span></span>
- <span data-ttu-id="6ff15-131">De nouvelles séquences de contrôle ont été ajoutées pour certains flux.</span><span class="sxs-lookup"><span data-stu-id="6ff15-131">New control sequences have been added for some flows.</span></span>
- <span data-ttu-id="6ff15-132">Le bouton d’envoi ne devient plus disponible de manière incorrecte en raison de la taille de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="6ff15-132">The submit button no longer incorrectly becomes available because of the window size.</span></span>
- <span data-ttu-id="6ff15-133">Les curseurs peuvent désormais fonctionner sur des écrans plus petits lorsque des tailles de boutons plus grandes sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="6ff15-133">Sliders can now proceed on smaller screens when larger button sizes are used.</span></span>
- <span data-ttu-id="6ff15-134">La superposition à quatre boutons n’est plus tronquée.</span><span class="sxs-lookup"><span data-stu-id="6ff15-134">The four-button overlay is no longer cut off.</span></span>
- <span data-ttu-id="6ff15-135">Le clavier prend désormais en charge le bouton Supprimer.</span><span class="sxs-lookup"><span data-stu-id="6ff15-135">The keyboard now supports the delete button.</span></span>
- <span data-ttu-id="6ff15-136">Un problème de luminosité pouvant survenir lors de l’utilisation du clavier a été corrigé.</span><span class="sxs-lookup"><span data-stu-id="6ff15-136">A brightness issue that could occur when the keyboard is pressed has been fixed.</span></span>
- <span data-ttu-id="6ff15-137">Divers problèmes des données de démonstration ont été corrigés.</span><span class="sxs-lookup"><span data-stu-id="6ff15-137">Various demo data issues have been fixed.</span></span>
- <span data-ttu-id="6ff15-138">Un problème qui affectait les champs numériques sur la page des détails a été corrigé.</span><span class="sxs-lookup"><span data-stu-id="6ff15-138">An issue that affected numeric fields on the details page has been fixed.</span></span>
- <span data-ttu-id="6ff15-139">Le clavier virtuel ne disparaît plus occasionnellement sur certains appareils.</span><span class="sxs-lookup"><span data-stu-id="6ff15-139">The screen keyboard no longer occasionally disappears on some devices.</span></span>
- <span data-ttu-id="6ff15-140">Divers bogues de l’interface utilisateur (IU) ont été corrigés, tels que des bogues affectant la couleur et le positionnement de l’arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="6ff15-140">Various user interface (UI) bugs have been fixed, such as bugs that affected the background color and positioning.</span></span>
- <span data-ttu-id="6ff15-141">L’interface utilisateur en russe a été améliorée.</span><span class="sxs-lookup"><span data-stu-id="6ff15-141">The Russian-language UI has been improved.</span></span>
- <span data-ttu-id="6ff15-142">Divers problèmes qui empêchaient le système de répondre ont été corrigés.</span><span class="sxs-lookup"><span data-stu-id="6ff15-142">Various issues that caused the system to stop responding have been fixed.</span></span>
- <span data-ttu-id="6ff15-143">Un problème lié à la réouverture de la calculatrice a été corrigé.</span><span class="sxs-lookup"><span data-stu-id="6ff15-143">An issue that was related to reopening the calculator has been fixed.</span></span>
- <span data-ttu-id="6ff15-144">**Version Android :** un problème en raison duquel Android 4.4 cessait de répondre au démarrage a été corrigé.</span><span class="sxs-lookup"><span data-stu-id="6ff15-144">**Android version:** An issue that caused Android 4.4 to stop responding on startup has been fixed.</span></span>
- <span data-ttu-id="6ff15-145">**Version Android :** la mise à l’échelle minimale a été réduite à 50 pour cent.</span><span class="sxs-lookup"><span data-stu-id="6ff15-145">**Android version:** Minimum scaling has been reduced to 50 percent.</span></span>

## <a name="version-2040"></a><span data-ttu-id="6ff15-146">Version 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="6ff15-146">Version 2.0.4.0</span></span>

<span data-ttu-id="6ff15-147">La version 2.0.4.0 était la première version en disponibilité générale de l’application mobile Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="6ff15-147">Version 2.0.4.0 was the first generally available release of the Warehouse Management mobile app.</span></span>

### <a name="new-features-fixes-and-improvements-in-version-2040"></a><span data-ttu-id="6ff15-148">Nouvelles fonctionnalités, correctifs et améliorations dans la version 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="6ff15-148">New features, fixes, and improvements in version 2.0.4.0</span></span>

<span data-ttu-id="6ff15-149">Cette version introduit les nouvelles fonctionnalités, correctifs et améliorations suivants qui n’étaient pas disponibles dans la version préliminaire :</span><span class="sxs-lookup"><span data-stu-id="6ff15-149">This version introduces the following new features, fixes, and improvements that weren't available in the preview version:</span></span>

- <span data-ttu-id="6ff15-150">Si une carte de détails comprend deux étiquettes portant des données identiques, l’une des étiquettes est masquée.</span><span class="sxs-lookup"><span data-stu-id="6ff15-150">If a details card includes two labels that have identical data, one of the labels is hidden.</span></span>
- <span data-ttu-id="6ff15-151">Les caractères spéciaux sont désormais affichés par défaut et l’option de les masquer a été supprimée des paramètres utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6ff15-151">Special characters are now shown by default, and the option to hide them has been removed from user settings.</span></span>
- <span data-ttu-id="6ff15-152">Les boutons d’envoi désactivés sont désormais affichés comme non disponibles dans la vue compacte à bout de bras.</span><span class="sxs-lookup"><span data-stu-id="6ff15-152">Disabled submit buttons are now shown as unavailable in compact arm-held view.</span></span>
- <span data-ttu-id="6ff15-153">Une modification de la logique de séquençage des contrôles garantit une mise à l’échelle plus fluide entre les appareils.</span><span class="sxs-lookup"><span data-stu-id="6ff15-153">A change to the sequencing logic for controls ensures smoother scaling across devices.</span></span> <span data-ttu-id="6ff15-154">Par conséquent, il est moins nécessaire d’ajuster la mise à l’échelle des polices ou des boutons.</span><span class="sxs-lookup"><span data-stu-id="6ff15-154">Therefore, there is less need to adjust the scaling of fonts or buttons.</span></span>
- <span data-ttu-id="6ff15-155">Le thème de couleur par défaut a été changé en *Sombre*.</span><span class="sxs-lookup"><span data-stu-id="6ff15-155">The default color theme has been changed to *Dark*.</span></span>
- <span data-ttu-id="6ff15-156">L’icône manquante pour le bouton d’envoi désactivé a été ajoutée dans la vue de ruban.</span><span class="sxs-lookup"><span data-stu-id="6ff15-156">The missing icon for the disabled submit button has been added in ribbon view.</span></span>
- <span data-ttu-id="6ff15-157">Les exceptions d’expiration de délai d’attente vous amènent désormais à la page de connexion au lieu d’afficher une erreur de connexion.</span><span class="sxs-lookup"><span data-stu-id="6ff15-157">Time-out exceptions now take you to the connection page instead of showing an in-line error.</span></span>
- <span data-ttu-id="6ff15-158">Si aucune action d’envoi n’est disponible (comme **OK**, **Oui**, **Accepter**, **Terminé** ou **Fini**), le bouton d’envoi est désactivé.</span><span class="sxs-lookup"><span data-stu-id="6ff15-158">If no submit action is available (such as **OK**, **Yes**, **Accept**, **Done**, or **Finished**), the submit button will be disabled.</span></span>
- <span data-ttu-id="6ff15-159">La stabilité de l’application a été améliorée.</span><span class="sxs-lookup"><span data-stu-id="6ff15-159">App stability has been improved.</span></span>
- <span data-ttu-id="6ff15-160">Il existe un correctif pour la vulnérabilité de la sécurité [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span><span class="sxs-lookup"><span data-stu-id="6ff15-160">There is a fix for security vulnerability [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).</span></span>
- <span data-ttu-id="6ff15-161">**Version Windows :** un problème sous Windows, où les menus ne répondaient plus après le redimensionnement de la fenêtre, a été corrigé.</span><span class="sxs-lookup"><span data-stu-id="6ff15-161">**Windows version:** An issue on Windows, where menus were unresponsive after the window was resized, has been fixed.</span></span>

### <a name="known-issue-in-version-2040"></a><span data-ttu-id="6ff15-162">Problème connu dans la version 2.0.4.0</span><span class="sxs-lookup"><span data-stu-id="6ff15-162">Known issue in version 2.0.4.0</span></span>

<span data-ttu-id="6ff15-163">Cette version présente le problème connu suivants :</span><span class="sxs-lookup"><span data-stu-id="6ff15-163">The following known issue exists in this version:</span></span>

- <span data-ttu-id="6ff15-164">Cette version présente un problème avec les appareils qui utilisent Android 4.4.</span><span class="sxs-lookup"><span data-stu-id="6ff15-164">This version has an issue with devices that use Android 4.4.</span></span> <span data-ttu-id="6ff15-165">Vous pouvez rencontrer des problèmes lorsque vous utilisez l’application sur cette version d’Android.</span><span class="sxs-lookup"><span data-stu-id="6ff15-165">You might experience issues when you use the app on this Android version.</span></span>
