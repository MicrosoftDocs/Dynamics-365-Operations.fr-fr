---
title: Créer une commande client intersociétés pour un usage interne
description: Cette rubrique explique comment créer une commande client intersociétés pour un usage interne
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0718a1560ec42df2a0a12e8b81484aa3be46d2d8
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548259"
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
