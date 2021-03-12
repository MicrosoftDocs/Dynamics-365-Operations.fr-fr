---
title: FAQ sur le client
description: Cet article fournit des réponses aux questions fréquemment posées sur le client Finance and Operations.
author: jasongre
manager: AnnBe
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6fe6da2575b7de866de614ad399c8ad5c0110d9a
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798497"
---
# <a name="client-faq"></a><span data-ttu-id="7f4fa-103">FAQ sur le client</span><span class="sxs-lookup"><span data-stu-id="7f4fa-103">Client FAQ</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7f4fa-104">Cet article fournit des réponses aux questions fréquemment posées sur le client Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-104">This article provides answers to frequently asked questions about the Finance and Operations client.</span></span>

## <a name="why-arent-symbols-loaded"></a><span data-ttu-id="7f4fa-105">Pourquoi les symboles ne sont pas chargés ?</span><span class="sxs-lookup"><span data-stu-id="7f4fa-105">Why aren't symbols loaded?</span></span>

<span data-ttu-id="7f4fa-106">Les paramètres de sécurité de votre navigateur peuvent empêcher les symboles d’être chargés correctement.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-106">The security settings on your browser might prevent the symbols from being loaded correctly.</span></span> <span data-ttu-id="7f4fa-107">Pour résoudre ce problème, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="7f4fa-107">To resolve this issue, try the following steps:</span></span>

- <span data-ttu-id="7f4fa-108">Si vous rencontrez ce problème dans Internet Explorer, cliquez sur **Outils**, puis sur **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-108">If you're experiencing this issue in Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span> <span data-ttu-id="7f4fa-109">Dans la boîte de dialogue Options Internet, sous l’onglet **Confidentialité**, cliquez sur **Niveau personnalisé** et vérifiez que l’option **Chargement des polices** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-109">In the Internet Options dialog box, on the **Privacy** tab, click **Custom level**, and make sure the **Font download** option is selected.</span></span>
- <span data-ttu-id="7f4fa-110">Sinon, vous devrez peut-être ajouter le site de l’application à la liste des sites de confiance.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-110">Otherwise, you might have to add the app site to the list of trusted sites.</span></span>

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a><span data-ttu-id="7f4fa-111">Il me manque le ruban de Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-111">I miss the ribbon from Dynamics AX 2012.</span></span> <span data-ttu-id="7f4fa-112">Puis-je conserver les onglets du volet Actions ouverts en permanence ?</span><span class="sxs-lookup"><span data-stu-id="7f4fa-112">Can I keep Action Pane tabs open all the time?</span></span>

<span data-ttu-id="7f4fa-113">Nous prévoyons d’implémenter cette fonction bientôt.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-113">We are planning to implement this feature soon.</span></span> <span data-ttu-id="7f4fa-114">Les utilisateurs pourront alors choisir de conserver les onglets du volet Actions ouverts en permanence.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-114">Users will then be able to choose to keep the tabs on Action Panes open all the time.</span></span> <span data-ttu-id="7f4fa-115">Sinon, les onglets seront réduits lorsqu’ils ne seront pas utilisés, permettant de conserver davantage d’espace d’écran pour la page.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-115">Otherwise, the tabs will be collapsed when they aren't being used, to gain more screen space for the page.</span></span>

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a><span data-ttu-id="7f4fa-116">Pourquoi vois-je parfois différents menus contextuels lorsque je clique avec le bouton droit ?</span><span class="sxs-lookup"><span data-stu-id="7f4fa-116">Why do I sometimes see different shortcut menus when I right click?</span></span>

<span data-ttu-id="7f4fa-117">Si vous cliquez avec le bouton droit sur un champ modifiable (ou si le texte est sélectionné), le menu contextuel du navigateur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-117">If you right-click in an editable field (or if text is selected), the browser's shortcut menu is displayed.</span></span> <span data-ttu-id="7f4fa-118">Ce menu vous donne accès aux commandes **Couper**, **Copier** et **Coller**.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-118">This menu gives you access to the **Cut**, **Copy**, and **Paste** commands.</span></span> <span data-ttu-id="7f4fa-119">Nous pouvons ne pas inclure ces commandes dans les menus contextuels, car, pour des raisons de sécurité, les navigateurs ne nous permettent pas d’accéder par programme au presse-papiers du système.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-119">We can't embed these commands into the shortcut menus because, for security reasons, browsers don't allow us to programmatically access the system clipboard.</span></span>

<span data-ttu-id="7f4fa-120">Si vous cliquez avec le bouton droit sur lune étiquette de champ ou sur la valeur d’un contrôle en lecture seule, vous verrez le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-120">If you right-click a field label or the value of a read-only control, you'll see the shortcut menu.</span></span>

<span data-ttu-id="7f4fa-121">Pour faciliter l’accès au clavier, nous envisageons d’implémenter un raccourci clavier qui ouvrira le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-121">To make keyboard access easier, we plan to implement a keyboard shortcut in the future that will open the shortcut menu.</span></span>

## <a name="where-is-the-view-details-functionality"></a><span data-ttu-id="7f4fa-122">Où est la fonctionnalité Afficher les détails ?</span><span class="sxs-lookup"><span data-stu-id="7f4fa-122">Where is the View details functionality?</span></span>

<span data-ttu-id="7f4fa-123">L’option **Afficher les détails** est disponible de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="7f4fa-123">The **View details** option is available in a couple of ways:</span></span>

- <span data-ttu-id="7f4fa-124">Si un contrôle a des fonctionnalités **Afficher les détails**, et si le contrôle a une valeur, cette valeur est affichée comme lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-124">If a control has **View details** capabilities, and if the control has a value, that value is displayed as a hyperlink.</span></span> <span data-ttu-id="7f4fa-125">Vous pouvez cliquer sur le lien hypertexte pour ouvrir une page qui contient des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-125">You can click the hyperlink to open a page that contains additional details.</span></span>
- <span data-ttu-id="7f4fa-126">**Afficher les détails** est également une option des menus contextuels.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-126">**View details** is also an option on shortcut menus.</span></span> <span data-ttu-id="7f4fa-127">Pour plus d’informations sur les affichage des menus contextuels après avoir cliqué sur le bouton droit, consultez la section précédente.</span><span class="sxs-lookup"><span data-stu-id="7f4fa-127">For more information about when shortcut menus are displayed when you right-click, see the previous section.</span></span>
