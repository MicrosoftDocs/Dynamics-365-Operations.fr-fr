---
title: Créer des articles empruntés
description: Les articles empruntés sont des enregistrements qui permettent de suivre les articles physiques (comme des téléphones ou des ordinateurs) que votre société prête aux collaborateurs.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26bf5a83a6d25e99996ec4219c5fbbeed806e22d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693722"
---
# <a name="create-loan-items"></a>Créer des articles empruntés


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Les articles empruntés sont des enregistrements qui permettent de suivre les articles physiques (comme des téléphones ou des ordinateurs) que votre société prête aux collaborateurs. Chaque article physique doit avoir un article de prêt correspondant. Chaque enregistrement d’article emprunté doit décrire la nature de l’emprunt, le responsable de l’emprunt et le nombre de jours d’emprunt de l’article. Vous pouvez créer plusieurs articles empruntés, tels que des clés, cartes d’accès ou uniformes, simultanément. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-loan-types"></a>Créer des types d’emprunt
1. Allez dans **Ressources humaines** > **Collaborateurs** > **Articles empruntés** > **Types d’emprunt**.
2. Cliquez sur **Nouveau**.
3. Tapez une valeur dans le champ **Type d’emprunt**.
4. Tapez une valeur dans le champ **Description**.
5. Entrez le nombre de jours pendant lesquels les articles associés à ce type d’emprunt peuvent être en retard. 
6. Cliquez sur **Enregistrer**.
7. Fermez la page.
8. Actualisez la page.

## <a name="create-loan-items"></a>Créer des articles empruntés
1. Allez dans **Ressources humaines** > **Collaborateurs** > **Articles empruntés** > **Articles empruntés**.
2. Cliquez sur **Créer des articles empruntés**.
3. Dans le champ **Qté**, saisissez un nombre.
4. Tapez une valeur dans le champ **Description**.
5. Dans le champ **Type d’emprunt**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
6. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
7. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
8. Permet d’entrer le nombre de jours pendant lesquels un article peut être emprunté.
    * La valeur par défaut du champ Retour prévu de la page Équipement emprunté est calculée comme suit : date du jour plus ce nombre.  
9. Dans le champ **Responsable**, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
10. Cliquez sur **Sélectionner**.
11. Entrez un nombre dans le champ **Valeur de début**.
12. Entrez un nombre dans le champ **Intervalle**.
13. Tapez une valeur dans le champ **Format**.
    * Par exemple, si le numéro de départ pour un article emprunté est 10, entrez deux symboles numériques dans le champ **Format**.  
14. Cliquez sur **OK**.
15. Actualisez la page.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
