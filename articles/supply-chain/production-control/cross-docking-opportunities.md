---
title: Cross-docking des ordres de fabrication aux quais d’expédition
description: Cette rubrique décrit la procédure de gestion du processus du matériel de cross-docking qui est déclaré terminé d'une ligne de production à un quai de transport sortant.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockOpportunityPolicy, WHSReservationHierarchy, WHSInventTableReservationHierarchy, WHSItemGroupLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c408c0b0c32292c074bcabf3822a50a24bbdd301
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007289"
---
# <a name="cross-docking-from-production-orders-to-outbound-docks"></a>Cross-docking des ordres de fabrication aux quais d’expédition

[!include [banner](../includes/banner.md)]

Cette rubrique décrit la procédure de gestion du processus du matériel de cross-docking qui est déclaré terminé d'une ligne de production à un quai de transport sortant.

<a name="introduction"></a>Introduction
------------

Le cross-docking de la production à un emplacement sortant est approprié pour les fabricants qui produisent à fort débit et souhaitent idéalement expédier des produits finis dès qu'ils sont déclarés terminés au niveau des lignes de production. L'objectif est d'expédier des produits vers les centres de distribution qui sont physiquement proches de la demande client, au lieu de constituer un stock sur le site de fabrication.

Dans le cas où il n'y aurait aucune demande immédiate d'un produit, il doit être mis précisément aux emplacements d'entrepôt du site de fabrication. Ce processus est également appelé, *cross-docking opportuniste* qui signifie que s'il existe une demande d'accélérer le produit, cette opportunité doit être utilisée au lieu de placer le produit supplémentaire en stockage interne.

L’exemple suivant montre trois variations d’un flux qui commence à la fin de la ligne de production (2).

Un produit est déclaré terminé à l’emplacement de sortie de production (3) et un pilote du chariot élévateur déplacera la palette vers cet emplacement (3).

-   S’il existe une activité prévue (6) pour transférer le produit de la fabrication (1) vers un centre de distribution (7), le pilote du camion sera dirigé par le système pour placer la palette à un emplacement de porte de baie (4).
-   Si une remorque est déjà affectée à la porte de baie, le conducteur du camion sera dirigée pour charger le produit directement sur la remorque.
-   S’il n’existe aucune activité planifiée pour transférer le produit, le conducteur du chariot élévateur sera dirigé pour mettre le produit précisément à un emplacement dans l’entrepôt interne (5).

[![Cross-docking d'opportunités](./media/scenario1.png)](./media/scenario1.png)

## <a name="configure-cross-docking"></a>Configurer le cross-docking
Configurez le processus de cross-docking dans **Stratégies de travail**. Une stratégie de travail inclut un type d'ordre d'exécution, un emplacement et un produit. Dans l'exemple suivant, le cross-docking est configuré pour le produit X et l'emplacement Y.

#### <a name="work-order-types"></a>Types d'ordre d'exécution

-   Type d'ordre d'exécution : Rangement des produits finis
-   Méthode de création de travail : Cross-docking
-   Nom de la stratégie de cross-docking : Ordres de transfert

#### <a name="inventory-locations"></a>Emplacement de stockage

-   Entrepôt : 51
-   Entrepôt : Y

#### <a name="products"></a>Produits

-   Numéro d'article : X

Actuellement, le cross-docking peut être configuré pour uniquement deux types d'ordres d'exécution :

-   Rangement des produits finis
-   Rangement des coproduits et des sous-produits

Dans **Stratégie de cross-docking**, définissez les types de document s'appliquant au cross-docking. Actuellement, le seul type de document qui est pris en charge est **Ordres de transfert**. L'exemple suivant montre la configuration d'une stratégie de cross-docking.

### <a name="cross-docking-policy-name-transfer-order"></a>Nom de la stratégie de cross-docking : Ordre de transfert

- Numéro de souche : 10
  -   Type d'ordre d'exécution : Sortie de transfert
- Demande de cross-docking nécessite un emplacement : Faux
- Stratégie de cross-docking : Date et heure

### <a name="sequence-number"></a>Souche de N°

Le **numéro de souche** indique la priorité du type de document. Actuellement, **Sortie de transfert** est le seul type qui est pris en charge. Par conséquent, le numéro de souche devient pertinent que si plusieurs types d'ordres d'exécution sont pris en charge.

### <a name="cross-docking-policy"></a>Stratégie de cross-docking

La stratégie de cross-docking définit également la stratégie pour la priorité de la demande d'ordre de transfert. Par exemple, si plusieurs ordres de transfert existent pour le même produit, la date et l'heure prévues définies pour la charge et associées à l'ordre de transfert, déterminent la priorité entre les commandes. La date et l'heure prévues peuvent être définies directement sur la charge, ou être définies dans un **programme de rendez-vous** associé à la charge. La priorité est déterminée par la stratégie de cross-docking. Actuellement, il n'existe qu'une stratégie : **Date et heure**.

### <a name="cross-docking-demand-requires-location"></a>La demande de cross-docking nécessite un emplacement

Dans la stratégie de cross-docking, vous pouvez paramétrer un critère pour exiger que les ordres de transfert aient un emplacement affecté afin d'être habilités au cross-docking. Ce critère est défini dans le champ **La demande de cross-docking nécessite un emplacement**. L'emplacement dans le programme de rendez-vous qui est associé à la charge est utilisé comme l'emplacement final des marchandises faisant l'objet de cross-docking. L'emplacement final des marchandises faisant l'objet de cross-docking est déterminé par l'instruction d'emplacement de **Sortie de transfert** pour le type d'ordre d'exécution **Placer**. Vous pourriez trouver utile de définir le champ **La demande de cross-docking nécessite un emplacement** dans un scénario où les produits finis ne doivent faire l'objet de cross-docking que si une remorque est affectée à une porte de baie. Dans ce cas, les marchandises sont entrées directement de la ligne de production dans la remorque. Lorsqu'une remorque est affectée à la porte de baie, un utilisateur affecte l'emplacement au programme de rendez-vous et rend l'emplacement applicable au cross-docking. Les sections suivantes vous guident via deux exemples.

#### <a name="scenario-1--cross-docking-from-production-to-transfer-orders"></a>Scénario 1 - Cross-docking des ordres de fabrication aux ordres de transfert

Une fois le produit déclaré terminé dans la ligne de production, il est transféré vers un emplacement de porte de baie où il est chargé sur un camion, puis transféré vers un centre de distribution. Utilisez la société USMF.

1.  Activez une souche de numéros pour le cross-docking. Accédez à la page **Souches de numéros**, puis sélectionnez le bouton **Générer**. Un assistant vous guide tout au long du processus.
2.  Créez une stratégie de cross-docking. Accédez à la page **Stratégie de cross-docking**, puis créez une nouvelle stratégie nommée **Cross-docking à l'ordre de transfert**. Notez que le seul type d'ordre d'exécution que vous pouvez sélectionner est **Sortie de transfert**, et la seule stratégie de cross-docking disponible est **Date et heure**.
3.  Créez une stratégie de travail. Accédez à la page **Stratégies de travail**, puis créez une nouvelle stratégie de travail nommée **Cross Dock L0101**.
4.  Paramétrez les charges afin qu'elles soient créées automatiquement pour les ordres de transfert. Dans les paramètres d'entrepôt, le paramétrage effectue le chargement afin qu'ils soient créés automatiquement lorsque les ordres de transfert sont créés. Une charge est une condition préalable à effectuer pour que l'ordre de transfert soit éligible au cross-docking.
5.  Configurez la mise en correspondance du chargement d'articles. Accédez à la page **Mise en correspondance de charge d'article**, puis paramétrez un modèle standard de charge du groupe d'élément **CarAudio**. Cette mise en correspondance insèrera automatiquement le modèle de charge sur la charge lorsque l'ordre de transfert est créé.
6.  Créez un ordre de transfert. Créez l’ordre de transfert pour le numéro d’article L0101. Quantité = 20.
7.  Lancez l'ordre de transfert depuis l'atelier de planification des chargements. Dans l'onglet **Expédier**, sélectionnez l'option de menu pour l'atelier de planification des chargements, puis dans le menu **Lancer** de la ligne de chargement, sélectionnez **Libérer dans l'entrepôt**. Une ligne de vague en cours du type **Sortie de transfert** existe désormais pour l'ordre de transfert.
8.  Créez un ordre de fabrication. Accédez à la page de liste **Ordre de fabrication**, puis créez un ordre de fabrication pour le produit L0101. Quantité = 20. Estimez et démarrez l'ordre de fabrication. Notez que le champ **Valider immédiatement les prélèvements** reste défini sur **Non**.
9.  Déclarer comme terminé à partir de l'appareil mobile. Accédez au portail de l'appareil mobile et sélectionnez l'option de menu **Déclarer comme terminé et ranger**. Maintenant, déclarez L0101 comme terminé à partir de l'appareil portable. Quantité = 10. Notez que l'emplacement de rangement est **BAYDOOR**. Cet emplacement se trouve dans l'instruction d'emplacement **Sortie de transfert** pour le type d'ordre de fabrication **Placer**. Notez également que ce travail du type **Sortie de transfert** a été créé et exécuté. Accédez aux détails du travail d'ordre de transfert pour vérifier le travail.
10. Déclarez maintenant 10 pièces supplémentaires de l'appareil mobile. Notez que l'emplacement de rangement est à nouveau **BAYDOOR**. Notez également qu'un nouveau travail du type **Sortie de transfert** a été créé pour les 10 pièces.
11. Essayez maintenant de commencer 20 pièces de plus sur l’ordre de production, puis essayez de déclarer 20 comme terminé en utilisant l’appareil portable. Cette fois, l'emplacement **LP-001** est suggéré comme emplacement de rangement. Cet emplacement figure dans l'instruction d'emplacement de **Rangement des produits finis**. Cette instruction d'emplacement est utilisée, car aucune opportunité pour le cross-docking n'existe. L'ordre de transfert pour LP-001 a été entièrement exécuté par les deux activités de cross-docking à l'étape 9 et 10. Notez que le travail du type **Rangement des produits finis** a été créé et traité.

#### <a name="scenario-2---cross-docking-from-production-to-transfer-orders-with-an-appointment-schedule"></a>Scénario 2 - Cross-docking entre les ordres de production et les ordres de transfert avec un programme de rendez-vous

Une fois que le produit est déclaré terminé à la ligne de production, il est transféré vers un emplacement de porte de baie identifié par un programme de rendez-vous pour les emplacements de porte de baie. Utilisez la société USMF.

1.  Modifiez la stratégie de cross-docking. Modifiez la stratégie de cross-docking que vous avez créée dans le scénario 1 en activant la case à cocher **La demande de cross-docking nécessite un emplacement**.
2.  Créez un ordre de transfert.
3.  Ouvrez l'**Atelier de planification des chargements**.
4.  Dans l'atelier de planification des chargements, accédez à la section **Charges**, puis sélectionnez **Planifier un rendez-vous** dans le menu **Transport** pour créer un nouveau programme de rendez-vous. Notez que le programme de rendez-vous a une référence à l'ordre de transfert dans le champ **Numéro de commande**. Dans le champ **Date/heure de début prévues à l'emplacement**, vous pouvez définir la date et l'heure du rendez-vous. Ces date et heure seront utilisées lorsque la demande de cross-docking est classée par priorité lors du processus de cross-docking. Les date et heure définies dans ce champ mettront à jour le champ **Date et heure prévue d'expédition** sur la charge correspondante. L'emplacement dans l'organisateur **Détails d'expédition** détermine l'emplacement vers lequel l'ordre de transfert est expédié.
5.  Dans le champ **Atelier de planification des chargements**, libérez l'objet vers l'entrepôt.
6.  Créez un ordre de fabrication pour le numéro d’article **L0101**, puis définissez le statut sur **Commencé**, avec une quantité de 20.
7.  Déclarer comme terminé à partir de l'appareil mobile.
8.  Accédez au portail de l'appareil mobile et sélectionnez l'option de menu **Déclarer comme terminé et ranger**.
9.  Déclarez le numéro d'article **L0101** comme terminé à partir de l'appareil portable. Notez que l'emplacement de rangement est maintenant **BAYDOOR 2**. Cet emplacement se trouve dans la planification des rendez-vous au lieu de l'instruction d'emplacement **Réception du transfert**.

### <a name="additional-information"></a>Informations supplémentaires

-   Le scénario de cross-docking est pris en charge pour les articles contrôlés par lot et de série, avec les dimensions de lot et de numéro de série définies au-dessus de l'emplacement dans la hiérarchie de réservation. 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]