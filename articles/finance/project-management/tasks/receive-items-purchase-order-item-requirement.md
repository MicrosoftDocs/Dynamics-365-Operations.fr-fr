---
title: Recevoir des articles sur une commande fournisseur à partir d'une demande d'articles
description: Cette rubrique explique comment recevoir des articles sur une commande fournisseur à partir d'une demande d'articles.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174418"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Recevoir des articles sur une commande fournisseur à partir d'une demande d'articles

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette rubrique explique comment recevoir des articles sur une commande fournisseur à partir d'une demande d'articles.

En utilisant une demande d'article au lieu d'une transaction d'article, vous pouvez prévoir la livraison juste avant que l'article soit utilisé, créer une commande fournisseur, inclure l'article dans le cadre d'un accord commercial et inclure la demande d'article dans la planification de la production. 

Cette tâche utilise l'ensemble de données USSI.

1. Dans le volet de navigation, accédez à **Modules > Gestion et comptabilité du projet > Projets > Tous les projets**.
2. Dans la liste, sélectionnez le lien dans la ligne souhaitée.
3. Dans le volet Actions, sélectionnez **Planifier**.
4. Sélectionnez **Demandes d'articles**.
5. Sélectionnez **Nouveau**.
6. Dans la nouvelle ligne, saisissez ou sélectionnez une valeur dans le champ **Numéro d'article**.
7. Entrez un nombre dans le champ **Quantité**.
8. Sélectionnez **Enregistrer**.
9. Dans le volet Actions, sélectionnez **Gérer**.
10. Sélectionnez **Fonctions**.
11. Sélectionnez **Créer une commande fournisseur**.
12. Cochez la case **Tout inclure**.
13. Dans le champ **Compte fournisseur**, saisissez ou sélectionnez une valeur.
14. Cliquez sur **OK**.
15. Dans le volet de navigation, accédez à **Modules > Comptabilité fournisseur > Commandes fournisseur > Toutes les commandes fournisseur**.
16. Dans la liste, sélectionnez le lien dans la ligne souhaitée.
17. Dans le volet Action, sélectionnez **Achat**.
18. Sélectionnez **Confirmer**.
19. Dans le volet Actions, sélectionnez **Recevoir**.
20. Sélectionnez **Accusé de réception de marchandises**.
21. Dans le champ **Accusé de réception de marchandises**, tapez une valeur.
22. Cliquez sur **OK**.

