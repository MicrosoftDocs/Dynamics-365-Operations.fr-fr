---
title: Ordres de travail et immobilisations
description: Cette rubrique explique les ordres de travail et les immobilisations dans le module Gestion des actifs.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 95fe394d22f9fe81511c230a2cf7b8ddf00d896f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250827"
---
# <a name="work-orders-and-fixed-assets"></a>Ordres de travail et immobilisations


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Dans le module Gestion des actifs, les actifs peuvent être associés aux immobilisations, et vous pouvez créer des ordres de travail pour ces actifs. Si vous utilisez cette fonction, vous pouvez obtenir une vue d'ensemble complète des immobilisations, des projets d'investissement associés et des coûts enregistrés sur les projets d'investissement dans le module **Gestion de projets et comptabilité** et le module **Immobilisations**.

>[!NOTE]
>Le champ **Numéro d'immobilisation** est renseigné uniquement dans le projet de tâche de l'ordre de travail si le type « Investissement » est sélectionné comme type de projet sur le projet de tâche de l'ordre de travail.

![Figure 1](media/24-work-orders.png)

La procédure suivante décrit la relation entre les actifs, les bons de travail, les projets de tâche de l'ordre de travail, et les immobilisations.

1. Vous créez un actif que vous associez à une immobilisation, comme illustré dans le graphique ci-dessous.

![Figure 2](media/25-work-orders.png)

2. Lorsque vous paramétrez des types d'ordre de travail (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Types d'ordre de travail**), vous créez un type d'ordre de travail pour gérer les investissements. Voir également [Types d'ordres de travail](../setup-for-work-orders/work-order-types.md).

![Figure 3](media/26-work-orders.png)

3. Lorsque vous configurez les groupes de projet de l'ordre de travail (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Paramétrage de projet** > **Groupe de projets**), vous créez une relation entre le type d'ordre de travail utilisé pour les investissements et le groupe de projets créé pour les investissements dans le module **Gestion de projets et comptabilité** (**Gestion de projets et comptabilité** > **Paramétrage** > **Validation** > **Groupes de projets**).

![Figure 4](media/27-work-orders.png)

4. Lorsque vous créez un ordre de travail qui est lié à un objet d'immobilisation, vous sélectionnez le type d'ordre de travail utilisé pour traiter les investissements, par exemple, « Investissement ».

5. Lorsque l'ordre de travail est créé, le type d'ordre de travail associé est affiché dans champ **Tous les ordres de travail**.

![Figure 5](media/28-work-orders.png)

6. Lorsque l'ordre de travail est créé, le projet lié à l'ordre de travail est créé dans **Gestion de projets et comptabilité** > **Tous les projets**. Vous pouvez consulter les informations relatives aux projets en cliquant sur le lien **ID projet** sur l'ordre de travail (dans **Gestion des actifs**, ouvrez l'ordre de travail dans la vue Détails > organisateur **Détails de ligne** > onglet **Général** > champ **ID projet**).

![Figure 6](media/29-work-orders.png)

7. Dans **Immobilisations**, vous pouvez afficher une vue d'ensemble des projets associés à une immobilisation (**Immobilisations** > **Immobilisations** > **Immobilisations** > cliquez sur l'immobilisation dans le champ **Numéro d'immobilisation** > affichez le contenu dans le volet **Informations associées** > section **Projets associés** ).

