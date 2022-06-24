---
title: Créer une commande client intersociétés pour un usage interne
description: Cet article explique comment créer une commande client intersociétés pour un usage interne
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a37b8ab1b3df10cdbd3bbb87410bc3dc70dc0ed0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873519"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>Créer une commande client intersociétés pour un usage interne

[!include [banner](../../includes/banner.md)]

Généralement, une commande client intersociétés est créée automatiquement à partir d'une commande fournisseur intersociétés. Vous pouvez également créer manuellement une commande client intersociétés, ce qui génère ensuite une commande fournisseur intersociétés dans l'entité juridique du client intersociétés.

![Processus de vente interne intersociétés](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>Création manuelle d'une commande client intersociétés

Procédez comme suit dans l'entité juridique B, comme le montre l'illustration.

1. Accédez à **Comptabilité client \> Commandes client \> Toutes les commandes client**.
1. Dans le Volet Actions, sélectionnez **Commande client** pour créer une commande client.
1. Sur la page **Créer une commande client**, sélectionnez un compte client. Dans le raccourci **Général**, assurez-vous que la case à cocher **Intersociétés** est activée. Ceci indique que le client sélectionné est un client intersociétés.
1. Entrez ou modifiez les informations, sélectionnez **OK**, puis complétez les lignes de commande comme d'habitude.

    La valeur de champ **Adresse de livraison** est copiée de l'en-tête de commande client intersociétés vers l'en-tête de commande fournisseur intersociétés. La valeur de champ **Numéro d'article**, y compris les dimensions de produit, et les valeurs de champs **Date de livraison** et **Code devise** sont copiées des lignes de commande client intersociétés vers les lignes de commande fournisseur intersociétés.

1. Dans l'en-tête de commande, sélectionnez **Intersociétés** pour afficher la commande fournisseur intersociétés associée.
1. Dans les lignes de commande, sélectionnez **Intersociétés** pour afficher des informations sur le stock intersociétés disponible.

> [!TIP]
> Vous pouvez afficher les commandes client intersociétés sur la page **Commandes intersociétés**.

> [!NOTE]
> Lorsque vous travaillez avec des intersociétés, nous vous recommandons de décocher la case **Supprimer la commande après facturation** sur la page **Paramètres des comptes clients**. Sinon, la commande fournisseur associée est supprimée. Nous vous recommandons également de décocher la case **Supprimer la commande fournisseur après facturation** sur la page **Paramètres de la comptabilité fournisseur**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
