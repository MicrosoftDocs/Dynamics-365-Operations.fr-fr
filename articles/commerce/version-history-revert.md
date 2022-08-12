---
title: Afficher l’historique des versions pour rétablir les pages et les fragments
description: Cet article explique comment afficher l’historique des versions d’une page ou d’un fragment et revenir à une version antérieure dans le générateur de site Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 06/21/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: fa2ecdd9d9bc7e60b279d850573b5caa6df2c659
ms.sourcegitcommit: 9cfccb5c260ce56a3457f9ea12e80f54ea55a3b4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183674"
---
# <a name="view-version-history-to-revert-pages-and-fragments"></a>Afficher l’historique des versions pour rétablir les pages et les fragments

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Cet article explique comment afficher l’historique des versions d’une page ou d’un fragment et revenir à une version antérieure dans le générateur de site Microsoft Dynamics 365 Commerce.

Le générateur de site Commerce vous permet d’afficher l’historique des versions d’une page ou d’un fragment et de revenir à une version précédente spécifique d’un document si nécessaire. Lorsqu’un document est ouvert, vous pouvez sélectionner **Afficher l’historique** dans la barre de commandes pour ouvrir une boîte de dialogue **Historique des versions**, où l’onglet **Version** répertorie l’historique de toutes les versions et enregistre les activités de la page ou du fragment. Vous pouvez ensuite sélectionner une version précédente du document dans la liste, la prévisualiser et la restaurer en tant que version actuelle. L’onglet **Activité** de la boîte de dialogue répertorie l’historique complet des activités du document, y compris tous les événements d’enregistrement, de publication et d’annulation de la publication.

> [!NOTE]
> Une nouvelle version d’un document est créée chaque fois qu’un auteur de site apporte des modifications, puis sélectionne **Modification terminée** pour le document. 

Pour afficher l’historique des versions d’une page ou d’un fragment et revenir à une version précédente, procédez comme suit.

1. Dans le générateur de site, ouvrez la page ou le fragment dont vous souhaitez afficher l’historique des versions.
1. Dans la barre de commande, sélectionnez **Afficher l’historique**.

    ![Affichez le bouton d’historique.](./media/version-history-1.png)

1. Dans la boîte de dialogue **Historique des versions**, sur l’onglet **Version**, sélectionnez une version précédente du document. Le volet des propriétés sur la droite affiche un aperçu miniature de la version sélectionnée, ainsi que des informations sur qui l’a modifiée et quand.

    ![Vue de la liste de l’historique des versions.](./media/version-history-2.png)

1. Pour afficher un aperçu entièrement rendu de la version sélectionnée du document, sélectionnez **Aperçu**. Pour fermer l’aperçu et revenir à la boîte de dialogue **Historique des versions**, sélectionnez **Quitter l’aperçu**.
1. Pour restaurer une version précédente d’un document, sélectionnez-la dans la liste sur l’onglet **Version**, puis sélectionnez **Restaurer**. Une zone de message **Restaurer la version \<version number\>** apparaît et vous invite à confirmer l’action de restauration. 

    ![Bouton de restauration et boîte de message de confirmation.](./media/version-history-3.png)

1. Pour poursuivre l’action de restauration, sélectionnez **Restaurer**. Le générateur de site est actualisé et affiche la version restaurée de la page ou du fragment.
1. Pour publier la version restaurée, sélectionnez **Terminer la modification**, puis **Publier**.
