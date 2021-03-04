---
title: Ordres de travail et immobilisations
description: Cette rubrique explique les ordres de travail et les immobilisations dans le module Gestion des actifs.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ca7a5d88de4308d7be9c1bc749b9dbf1da027c2c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4428097"
---
# <a name="work-orders-and-fixed-assets"></a>Ordres de travail et immobilisations

[!include [banner](../../includes/banner.md)]


Dans le module Gestion des actifs, les actifs peuvent être associés aux immobilisations, et vous pouvez créer des ordres de travail pour ces actifs. Si vous utilisez cette fonction, vous pouvez obtenir une vue d'ensemble complète des immobilisations, des projets d'investissement associés et des coûts enregistrés sur les projets d'investissement dans les modules **Gestion de projets et comptabilité** et **Immobilisations** dans Microsoft Dynamics 365 for Finance and Operations.

>[!NOTE]
>Le champ **Numéro d'immobilisation** dans le projet de tâche de l'ordre de travail est renseigné uniquement si le type **Investissement** est sélectionné comme type de projet sur le projet de tâche de l'ordre de travail.

L'illustration ci-dessous montre la relation entre un projet d'investissement dans le module **Gestion de projets et comptabilité** et un projet de tâche d'ordre de travail.

![Figure 1](media/24-work-orders.png)

La procédure suivante décrit la relation entre les actifs, les bons de travail, les projets de tâche de l'ordre de travail, et les immobilisations.

1. Vous créez un actif que vous associez à une immobilisation.

![Figure 2](media/25-work-orders.png)

2. Lorsque vous paramétrez des types d'ordre de travail sur la page **Types d'ordres de travail** (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Types d'ordre de travail**), vous créez un type d'ordre de travail pour gérer les investissements. Voir également [Types d'ordres de travail](../setup-for-work-orders/work-order-types.md).

![Figure 3](media/26-work-orders.png)

3. Lorsque vous configurez les groupes de projet de l'ordre de travail sur l'onglet **Groupe de projets** de la page **Configuration du projet de l'ordre de travail** (**Gestion des actifs** > **Paramétrage** > **Ordres de travail** > **Paramétrage de projet**), vous créez une relation entre le type d'ordre de travail utilisé pour les investissements et le groupe de projets créé pour les investissements sur la page **Groupes de projets** dans le module **Gestion de projets et comptabilité** (**Gestion de projets et comptabilité** > **Paramétrage** > **Validation** > **Groupes de projets**).

![Figure 4](media/27-work-orders.png)

4. Lorsque vous créez un ordre de travail qui est lié à une immobilisation, vous sélectionnez le type d'ordre de travail utilisé pour traiter les investissements, par exemple, **Investissement**.

5. Lorsque l'ordre de travail est créé, le type d'ordre de travail associé est affiché sur la page **Tous les ordres de travail**.

![Figure 5](media/28-work-orders.png)

6. Lorsque l'ordre de travail est créé, le projet lié à l'ordre de travail est créé dans la page **Tous les projets** dans le module **Gestion de projets et comptabilité** (**Gestion de projets et comptabilité** > **Projets** > **Tous les projets**). Pour afficher les informations liées au projet, sélectionnez le lien dans le champ **ID projet** sur l'onglet **Général** sur l'organisateur **Détails de ligne** dans la vue détaillée de la page **Tous les ordres de travail** dans le module **Gestion des actifs** (**Gestion des actifs** > **Commun** > **Ordre de travail** > **Tous les ordres de travail**).

![Figure 6](media/29-work-orders.png)

7. Pour afficher une vue d'ensemble des projets associés à une immobilisation, sélectionnez **Immobilisations** > **Immobilisations** > **Immobilisations**, puis, dans le champ **Numéro d'immobilisation**, sélectionnez le lien pour l'immobilisation pour ouvrir la vue détaillée. Développez le volet **Informations associées** à droite de la page, puis sélectionnez l'organisateur **Projets associés**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]