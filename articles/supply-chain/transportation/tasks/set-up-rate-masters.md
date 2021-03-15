---
title: Paramétrer des tables maître des taux
description: Cette procédure décrit le processus de paramétrage des données principales de taux.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47fa7edeba81d826a00668a2da74113f552437f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974258"
---
# <a name="set-up-rate-masters"></a>Paramétrer des tables maître des taux

[!include [banner](../../includes/banner.md)]

Cette procédure décrit le processus de paramétrage des données principales de taux. Le responsable logistique configure généralement les données principales de taux en fonction des contacts signés avec les transporteurs. Dans ce scénario vous paramètrerez des données principales de taux pour un transporteur aérien. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.

## <a name="set-up-break-master"></a>Paramétrer une table maître des pauses

1. Accédez à **Gestion du transport > Configurer > Taux > Table maître des pauses**. Les données principales des ruptures permettent de définir la structure de tarification et les points d'arrêt. La structure de tarification utilise la tarification progressive basée sur les dimensions physiques.  
1. Sélectionnez **Nouveau**.
1. Dans le champ **Table maître des pauses**, entrez une valeur.
1. Dans le champ **Nom**, entrez une valeur.
1. Dans le champ **Type de données**, sélectionnez le type de données.
1. Dans le champ **Comparaison**, saisissez le type de comparaison demandé (à l'aide des opérateurs).
1. Entrez le champ **Valeurs de pause** entrez l'unité de pause.
1. Dans la section **Détails**, créez autant de pauses que nécessaire pour la structure de prix.
1. Sélectionnez **Enregistrer**.

## <a name="set-up-rate-master"></a>Paramétrer des données principales de taux

1. Accédez à **Gestion du transport > Configurer > Taux > Données principales de taux**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Données principales de taux**, saisissez une valeur.
1. Tapez une valeur dans le champ **Nom**.
1. Dans le champ **ID des métadonnées de taux**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche. L'ID des métadonnées de taux détermine les données nécessaires pour les données principales du taux, car cela définit les métadonnées attendues par le moteur de gestion des transports utilisant cette table maître des taux.  
1. Pour cette exemple, sélectionnez l'option P2P. Ceci est déjà défini dans les données de démonstration.
1. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
1. Sélectionnez **Enregistrer**.

## <a name="set-up-rate-base"></a>Paramétrer la base de taux

1. Sélectionnez la **base de taux**.
    * La base de taux détermine le taux du transporteur, et peut être utilisée pour paramétrer une structure tarifaire car elle structure les taux dans les points d'arrêt définis dans les données principales des ruptures.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **Base de taux**, saisissez une valeur.
4. Tapez une valeur dans le champ **Nom**.
5. Dans le champ **Données principales de pause**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Les données principales des ruptures permettent de définir la structure de tarification et les points d'arrêt. La structure de tarification utilise la tarification progressive basée sur les dimensions physiques.  
6. Pour cet exemple, utilisez le poids. Ceci est déjà défini dans les données de démonstration.
7. Dans la liste, sélectionnez le lien dans la ligne en surbrillance.
8. Développez la section **Détails**.
9. Sélectionnez **Nouveau**.
10. Dans le champ **Code postal du lieu de livraison de départ**, saisissez « 30301 ».
11. Dans le champ **Code postal de lieu de livraison d'arrivée**, saisissez « 30318 ».
12. Dans le champ **Région du pays de livraison**, saisissez « USA ».
13. Dans le champ **<1,00 Lb**, saisissez « 100 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 1 livre.  
14. Dans le champ **<5,00 Lb**, saisissez « 300 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 5 livres.  
15. Dans le champ **<20,00 Lb**, saisissez « 500 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 20 livres.  
16. Dans le champ **<100,00 Lb**, saisissez « 1000 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 100 livres.  
17. Dans le champ **<1 000,00 Lb**, saisissez « 3 000 ».
    * Insérez le taux par livres si le poids total de la charge est inférieur à 1 000 livres.  
18. Sélectionnez **Enregistrer**.
19. Fermez la page.

## <a name="assign-rate-base"></a>Affecter la base de taux

1. Développer la section **Affectations de base de taux**.
2. Sélectionnez **Nouveau**.
    * Vous pouvez avoir plusieurs affectations de base de taux pour chaque table maître des taux. Cela permet de créer différents niveaux de prix pour chaque transporteur selon les destinations, les services ou les bases de taux. Dans cette procédure, vous allez créer une seule affectation de base de taux.  
3. Tapez une valeur dans le champ **Nom**.
4. Dans le champ **Base de taux**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, sélectionnez le lien dans la ligne en surbrillance.
6. Dans le champ **Service**, sélectionnez le bouton de liste déroulante pour ouvrir la recherche.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, sélectionnez le lien dans la ligne en surbrillance.
9. Dans le champ **Code postal d'enlèvement**, saisissez « 98052 ».
    * Spécifiez le code postal à partir duquel cette affectation de base de taux doit être valide.
10. Dans le champ **Région du pays d'enlèvement**, saisissez « USA ».
11. Sélectionnez **Enregistrer**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]