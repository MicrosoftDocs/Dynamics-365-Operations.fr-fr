---
title: FAQ client Finance and Operations
description: "Cet article fournit des réponses aux questions fréquemment posées sur le client Microsoft Dynamics 365 for Finance and Operations."
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 55d4fa4629d203aa888fe6400126a872d2eee000
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="finance-and-operations-client-faq"></a><span data-ttu-id="0dc21-103">FAQ client Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="0dc21-103">Finance and Operations client FAQ</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0dc21-104">Cet article fournit des réponses aux questions fréquemment posées sur le client Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0dc21-104">This article provides answers to frequently asked questions about the Microsoft Dynamics 365 for Finance and Operations client.</span></span>

<a name="why-arent-symbols-loaded-when-i-use-finance-and-operations"></a><span data-ttu-id="0dc21-105">Pourquoi est-ce que les symboles ne sont pas chargés lorsque j'utilise Finance and Operations ?</span><span class="sxs-lookup"><span data-stu-id="0dc21-105">Why aren't symbols loaded when I use Finance and Operations?</span></span>
-----------------------------------------------------------------

<span data-ttu-id="0dc21-106">Les paramètres de sécurité de votre navigateur peuvent empêcher les symboles d'être chargés correctement.</span><span class="sxs-lookup"><span data-stu-id="0dc21-106">The security settings on your browser might prevent the symbols from being loaded correctly.</span></span> <span data-ttu-id="0dc21-107">Pour résoudre ce problème, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0dc21-107">To resolve this issue, try the following steps:</span></span>

-   <span data-ttu-id="0dc21-108">Si vous rencontrez ce problème dans Internet Explorer, cliquez sur **Outils**, puis sur **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="0dc21-108">If you're experiencing this issue in Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  <span data-ttu-id="0dc21-109">Dans la boîte de dialogue Options Internet, sous l'onglet **Confidentialité**, cliquez sur **Niveau personnalisé** et vérifiez que l'option **Chargement des polices** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="0dc21-109">In the Internet Options dialog box, on the **Privacy** tab, click **Custom level**, and make sure the **Font download** option is selected.</span></span>
-   <span data-ttu-id="0dc21-110">Sinon, vous devrez peut-être ajouter le site Finance and Operations à la liste des sites de confiance.</span><span class="sxs-lookup"><span data-stu-id="0dc21-110">Otherwise, you might have to add the Finance and Operations site to the list of trusted sites.</span></span>

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a><span data-ttu-id="0dc21-111">Il me manque le ruban de Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="0dc21-111">I miss the ribbon from Dynamics AX 2012.</span></span> <span data-ttu-id="0dc21-112">Puis-je conserver les onglets du volet Actions ouverts en permanence ?</span><span class="sxs-lookup"><span data-stu-id="0dc21-112">Can I keep Action Pane tabs open all the time?</span></span>
<span data-ttu-id="0dc21-113">Nous prévoyons d'implémenter cette fonction bientôt.</span><span class="sxs-lookup"><span data-stu-id="0dc21-113">We are planning to implement this feature soon.</span></span> <span data-ttu-id="0dc21-114">Les utilisateurs pourront alors choisir de conserver les onglets du volet Actions ouverts en permanence.</span><span class="sxs-lookup"><span data-stu-id="0dc21-114">Users will then be able to choose to keep the tabs on Action Panes open all the time.</span></span> <span data-ttu-id="0dc21-115">Sinon, les onglets seront réduits lorsqu'ils ne seront pas utilisés, permettant de conserver davantage d'espace d'écran pour la page.</span><span class="sxs-lookup"><span data-stu-id="0dc21-115">Otherwise, the tabs will be collapsed when they aren't being used, to gain more screen space for the page.</span></span>

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-rightclick"></a><span data-ttu-id="0dc21-116">Pourquoi vois-je parfois différents menus contextuels lorsque je clique avec le bouton droit ?</span><span class="sxs-lookup"><span data-stu-id="0dc21-116">Why do I sometimes see different shortcut menus when I rightclick?</span></span>
<span data-ttu-id="0dc21-117">Si vous cliquez avec le bouton droit sur un champ modifiable (ou si le texte est sélectionné), le menu contextuel du navigateur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="0dc21-117">If you right-click in an editable field (or if text is selected), the browser's shortcut menu is displayed.</span></span> <span data-ttu-id="0dc21-118">Ce menu vous donne accès aux commandes **Couper**, **Copier** et **Coller**.</span><span class="sxs-lookup"><span data-stu-id="0dc21-118">This menu gives you access to the **Cut**, **Copy**, and **Paste** commands.</span></span> <span data-ttu-id="0dc21-119">Nous pouvons ne pas inclure ces commandes dans les menus contextuels de Finance and Operations car, pour des raisons de sécurité, les navigateurs ne nous permettent pas d'accéder par programme au presse-papiers du système.</span><span class="sxs-lookup"><span data-stu-id="0dc21-119">We can't embed these commands into the Finance and Operations shortcut menus because, for security reasons, browsers don’t allow us to programmatically access the system clipboard.</span></span>

<span data-ttu-id="0dc21-120">Si vous cliquez avec le bouton droit sur une étiquette de champ ou sur la valeur d'un contrôle en lecture seule, vous verrez le menu contextuel de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0dc21-120">If you right-click a field label or the value of a read-only control, you'll see the Finance and Operations shortcut menu.</span></span>

<span data-ttu-id="0dc21-121">Pour faciliter l'accès au clavier, nous envisageons d'implémenter un raccourci clavier qui ouvrira le menu contextuel de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0dc21-121">To make keyboard access easier, we plan to implement a keyboard shortcut in the future that will open the Finance and Operations shortcut menu.</span></span>

## <a name="where-is-the-view-details-functionality-in-finance-and-operations"></a><span data-ttu-id="0dc21-122">Où est la fonctionnalité Afficher les détails dans Finance and Operations ?</span><span class="sxs-lookup"><span data-stu-id="0dc21-122">Where is the View details functionality in Finance and Operations?</span></span>
<span data-ttu-id="0dc21-123">L'option **Afficher les détails** est disponible de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="0dc21-123">The **View details** option is available in a couple of ways:</span></span>

-   <span data-ttu-id="0dc21-124">Si un contrôle a des fonctionnalités **Afficher les détails**, et si le contrôle a une valeur, cette valeur est affichée comme lien hypertexte.</span><span class="sxs-lookup"><span data-stu-id="0dc21-124">If a control has **View details** capabilities, and if the control has a value, that value is displayed as a hyperlink.</span></span> <span data-ttu-id="0dc21-125">Vous pouvez cliquer sur le lien hypertexte pour ouvrir une page qui contient des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="0dc21-125">You can click the hyperlink to open a page that contains additional details.</span></span>
-   <span data-ttu-id="0dc21-126">**Afficher les détails** est également une option des menus contextuels de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0dc21-126">**View details** is also an option on Finance and Operations shortcut menus.</span></span> <span data-ttu-id="0dc21-127">Pour plus d'informations sur les affichage des menus contextuels de Finance and Operations après avoir cliqué sur le bouton droit, consultez la section précédente.</span><span class="sxs-lookup"><span data-stu-id="0dc21-127">For more information about when Finance and Operations shortcut menus are displayed when you right-click, see the previous section.</span></span>





