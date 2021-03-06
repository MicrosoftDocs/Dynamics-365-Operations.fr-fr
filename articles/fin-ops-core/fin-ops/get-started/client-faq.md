---
title: FAQ sur le client
description: Cet article fournit des réponses aux questions fréquemment posées sur le client Finance and Operations.
author: jasongre
ms.date: 09/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 12334
ms.assetid: a9a57f0e-a67c-46b1-83c9-5d6350fb3b86
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f4311e93505f1d59f6beeae01a2a2e796ad47cd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749219"
---
# <a name="client-faq"></a>FAQ sur le client

[!include [banner](../includes/banner.md)]

Cet article fournit des réponses aux questions fréquemment posées sur le client Finance and Operations.

## <a name="why-arent-symbols-loaded"></a>Pourquoi les symboles ne sont pas chargés ?

Les paramètres de sécurité de votre navigateur peuvent empêcher les symboles d’être chargés correctement. Pour résoudre ce problème, procédez comme suit :

- Si vous rencontrez ce problème dans Internet Explorer, cliquez sur **Outils**, puis sur **Options Internet**. Dans la boîte de dialogue Options Internet, sous l’onglet **Confidentialité**, cliquez sur **Niveau personnalisé** et vérifiez que l’option **Chargement des polices** est sélectionnée.
- Sinon, vous devrez peut-être ajouter le site de l’application à la liste des sites de confiance.

## <a name="i-miss-the-ribbon-from-dynamics-ax-2012-can-i-keep-action-pane-tabs-open-all-the-time"></a>Il me manque le ruban de Dynamics AX 2012. Puis-je conserver les onglets du volet Actions ouverts en permanence ?

Nous prévoyons d’implémenter cette fonction bientôt. Les utilisateurs pourront alors choisir de conserver les onglets du volet Actions ouverts en permanence. Sinon, les onglets seront réduits lorsqu’ils ne seront pas utilisés, permettant de conserver davantage d’espace d’écran pour la page.

## <a name="why-do-i-sometimes-see-different-shortcut-menus-when-i-right-click"></a>Pourquoi vois-je parfois différents menus contextuels lorsque je clique avec le bouton droit ?

Si vous cliquez avec le bouton droit sur un champ modifiable (ou si le texte est sélectionné), le menu contextuel du navigateur s’affiche. Ce menu vous donne accès aux commandes **Couper**, **Copier** et **Coller**. Nous pouvons ne pas inclure ces commandes dans les menus contextuels, car, pour des raisons de sécurité, les navigateurs ne nous permettent pas d’accéder par programme au presse-papiers du système.

Si vous cliquez avec le bouton droit sur lune étiquette de champ ou sur la valeur d’un contrôle en lecture seule, vous verrez le menu contextuel.

Pour faciliter l’accès au clavier, nous envisageons d’implémenter un raccourci clavier qui ouvrira le menu contextuel.

## <a name="where-is-the-view-details-functionality"></a>Où est la fonctionnalité Afficher les détails ?

L’option **Afficher les détails** est disponible de plusieurs manières :

- Si un contrôle a des fonctionnalités **Afficher les détails**, et si le contrôle a une valeur, cette valeur est affichée comme lien hypertexte. Vous pouvez cliquer sur le lien hypertexte pour ouvrir une page qui contient des informations supplémentaires.
- **Afficher les détails** est également une option des menus contextuels. Pour plus d’informations sur les affichage des menus contextuels après avoir cliqué sur le bouton droit, consultez la section précédente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]