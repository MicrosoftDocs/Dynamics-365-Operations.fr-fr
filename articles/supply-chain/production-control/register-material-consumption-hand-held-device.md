---
title: Enregistrement de la consommation de matières à l'aide d'un appareil mobile
description: Cette rubrique décrit un workflow qui active l'enregistrement de la consommation de matières premières dans la production à l'aide d'un appareil portable.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67fbb8eebb637a96638c574373441213c66e9ddc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211259"
---
# <a name="register-material-consumption-using-a-mobile-device"></a>Enregistrement de la consommation de matières à l'aide d'un appareil mobile

[!include [banner](../includes/banner.md)]

Cette rubrique décrit un workflow qui active l'enregistrement de la consommation de matières premières dans la production à l'aide d'un appareil portable.

<a name="introduction"></a>Introduction
------------

Ce workflow est utile s'il y a une obligation stricte de traçabilité des matières. Dans ces cas, pour assurer la traçabilité des matières, le temps et la quantité exacts doivent être déclarés pour la consommation. Ce processus peut être considéré comme opposé aux opérations de préconsommation ou postconsommation, où il existe un décalage entre le moment de l'enregistrement et le moment de la consommation réelle. Cela explique pourquoi une stratégie de consommation automatique ne peut pas être utilisée pour certaines matières soumises à des obligations de traçabilité. Examinons un scénario simple qui explique comment paramétrer un workflow pour activer l'enregistrement de la consommation de matières premières dans la production à l'aide d'un appareil portable. [![paramétrer un workflow pour activer l'enregistrement de la consommation de matières premières à l'aide d'un périphérique portable](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a>Détails du scénario

Un processus de production continue (5) consomme la matière première contrôlée par lots RM-100. La matière est disponible à l'emplacement Bulk-001 (1) sur le contenant PL-1 avec deux lots, B1 et B2, tous deux d'une quantité de 100 kilos. Le travail d'entrepôt (2) est lancé et traité pour RM-100, et la matière est prélevée de Bulk-001 vers l'emplacement d'entrée en production PIL-01 (3), qui est défini comme un emplacement qui ne fait pas l'objet d'un contrôle de contenant. L'opérateur pèse la matière dans l'emplacement d'entrée en production (3) et enregistre le poids et le numéro de lot comme étant consommés (4). Dans l'emplacement d'entrée en production, une partie de la matière est ajoutée manuellement au processus de production à des intervalles de temps définis. Lorsque l'opérateur ajoute la matière, elle est pesée sur une échelle et le numéro de lot est enregistré.

## <a name="set-up-theworkflow-to-register-consumption-using-a-handheld-device"></a>Paramétrer le workflow pour enregistrer la consommation à l'aide d'un appareil portable
Créez un produit fini, FG-100, avec une nomenclature contenant la matière première contrôlée par lots RM-100. Ajoutez deux lots, B1 et B2, de RM-100 d'une quantité de 100 à l'emplacement : Bulk-001 sur le contenant : PL-1. Le principe d'effacement sur la ligne de nomenclature pour RM-100 est défini sur **Manuel**. Définissez l'emplacement d'entrée en production sur PIL-01. Pour ce faire, sélectionnez cet emplacement comme emplacement d'entrée en production par défaut dans l'entrepôt 51.

1.  Créez une option de menu d'appareil mobile : 

-    **Nom de l'option de menu** - Permet d'enregistrer la consommation de matières. 
-    **Titre** - Permet d'enregistrer la consommation de matières. 
-    **Mode** - Indirect. 
-    **Code d'activité** – Permet d'enregistrer la consommation de matières.

2.  Ajoutez l'option de menu au menu d'appareil mobile **Production mobile**.
3.  Créez un ordre de fabrication pour le produit fini : 

-    **Numéro d'article** - FG-100 
-    **Site** - 5 
-    **Entrepôt** - 51 
-    **Quantité** - 150

L'ordre de fabrication est **Estimé** et **Lancé** et le travail d'entrepôt est créé.

4.  Terminez le travail à l'aide du workflow pour le prélèvement des matières premières pour l'appareil portable.

Les matières sont transférées de l'emplacement de stockage en gros vers l'emplacement d'entrée en production PIL-01. Une fois le travail terminé, les matières ont le statut **Prélevé sur l'emplacement d'entrée en production**. Le statut après traitement du travail peut être **Prélevé** ou **Physique réservé**. Ceci est configuré avec le paramètre **Statut de sortie après placement dans l'écran Entrepôt**.

5.  Démarrez l'ordre de fabrication à partir du client ou de l'appareil portable à l'aide de l'option de menu **Démarrage de la production**.

Une fois l'ordre de fabrication démarré, vous pouvez enregistrer la consommation de matières avec le workflow pour l'appareil portable. Commençons par enregistrer la consommation de 25 kilos du lot B1.

6.  Sélectionnez l'option de menu **Enregistrer la consommation de** **matières** et, dans le menu de l'appareil portable, entrez les informations suivantes : 

-    Numéro de l'ordre de fabrication. 
-    Emplacement dans lequel les matières seront consommées, dans ce cas PIL-01. 
-    Numéro d'article RM-100. 
-    Numéro de lot B1. 
-    Quantité 25.

7.  Sélectionnez **OK**.

Notez que le message « La ligne de journal est créée » apparaît sur l'écran. Sur l'ordre de fabrication, il existe un journal en cours de type **Prélèvement de production** pour le numéro d'article RM-100 et le numéro de lot B1. 

Vous pouvez maintenant choisir de continuer votre enregistrement, par exemple sur le numéro de lot B2, et chaque fois que vous sélectionnez **OK**, une nouvelle ligne de journal est ajoutée au journal en cours. 

Après avoir terminé votre enregistrement, sélectionnez **Terminé** pour valider le journal et terminer le workflow.

### <a name="additional-comments"></a>Commentaires supplémentaires 

-   Si un utilisateur annule le workflow après la création d'une ligne de journal, le journal est à l'état non validé, mais si l'utilisateur utilise le workflow pour le même ordre de fabrication à un moment ultérieur, les lignes sont ajoutées au journal en cours et non à un nouveau journal.
-   Le nouveau workflow prend également en charge l'enregistrement de numéros de série.
-   Il est uniquement possible d'enregistrer un numéro d'article défini dans la nomenclature ou dans la formule pour l'ordre de fabrication ou le lot de commandes sélectionné.
-   Les matières peuvent être surconsommées. Par exemple, si les matières sont estimées pour être utilisées avec la quantité de 100 kilos, elles peuvent être surconsommées avec une quantité de 105 kilos, par exemple.


