--- 
title: "Paramétrer la réaffectation des articles pour les prélèvements partiels"
description: "Cette procédure décrit comment les magasiniers peuvent trouver rapidement d'autres emplacements si le stock n'est pas suffisant à l'emplacement où ils ont été redirigés."
author: YuyuScheller
manager: AnnBe
ms.date: 10/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: fedd815cddfea4e00ed61ec6e176b633468c8fb2
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-short-picking-item-reallocation"></a>Paramétrer la réaffectation des articles pour les prélèvements partiels

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment les magasiniers peuvent trouver rapidement d'autres emplacements si le stock n'est pas suffisant à l'emplacement où ils ont été redirigés. Il est possible d'utiliser un processus de réaffectation automatique, qui utilise des instructions d'emplacement pour récupérer les marchandises si elles sont disponibles dans un autre emplacement. Lorsque la réaffectation manuelle est utilisée, la liste des emplacements avec la quantité disponible est affichée sur l'appareil mobile, ce qui permet au magasinier de choisir l'emplacement à partir duquel utiliser le stock. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.


## <a name="set-up-work-exceptions"></a>Définir des exceptions de travail
1. Allez dans Gestion des entrepôts > Paramétrage > Travail > Exceptions de travail.
2. Cliquez sur Nouveau.
    * Il est possible de définir plusieurs exceptions de travail avec différentes stratégies de réaffectation des articles pour permettre au magasinier d'en choisir une selon les besoins de l'expédition qu'il traite.  
3. Dans le champ Code d'exception de travail, tapez une valeur.
    * Donnez à l'exception de travail un titre pour indiquer son utilité. Par exemple, Prélèvement partiel manuel.  
4. Dans le champ Description, entrez une valeur.
5. Dans le champ Type d'exception, sélectionnez « Prélèvement partiel ».
6. Activez la case à cocher Ajuster le stock.
    * Cette option signifie que le stock est automatiquement ajusté sur 0 à l'emplacement de prélèvement partiel.  
7. Dans le champ Code type d'ajustement par défaut, entrez ou sélectionnez une valeur.
    * Par exemple, dans USMF, vous pouvez sélectionner « Supprimer Res Adj Out ».  
8. Dans le champ Réaffectation des articles, sélectionnez « Manuel ».
    * Si vous sélectionnez Manuel ou Automatique et manuel, le magasinier doit être autorisé à utiliser la réaffectation manuelle.  

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Paramétrer un collaborateur pour utiliser la réaffectation manuelle des articles
1. Fermez la page.
2. Allez dans Gestion des entrepôts > Paramétrage > Collaborateur.
3. Cliquez sur Modifier.
4. Dans la liste, sélectionnez le collaborateur 24.
5. Développez la section Travail.
6. Sélectionnez Oui dans le champ Autoriser la réaffectation manuelle des articles.


