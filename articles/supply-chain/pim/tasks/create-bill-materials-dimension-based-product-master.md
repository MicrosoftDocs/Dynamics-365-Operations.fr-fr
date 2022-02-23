---
title: Créer une nomenclature pour un produit générique fondé sur les dimensions
description: Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7961cfb4ad0e20c49d327d83f56c08811598ac1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427894"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Créer une nomenclature pour un produit générique fondé sur les dimensions

[!include [banner](../../includes/banner.md)]

Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements. Les 4 premiers enregistrements paramètrent les données requises pour exécuter cette procédure. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette tâche est généralement gérée par le concepteur de produit.


## <a name="select-the-product"></a>Sélectionner le produit
1. Cliquez sur Gestion des produits lancés.
2. Cliquez sur Produits lancés.
3. Dans la liste, marquez la ligne sélectionnée.
    * Recherchez le produit générique lancé avec la technologie de configuration basée sur les dimensions que vous avez créée dans le premier guide des tâches dans cette séquence.  
4. Cliquez sur Ingénieur dans le volet Actions.
5. Cliquez sur Versions de nomenclature.

## <a name="create-new-bom-and-bom-version"></a>Créer une nomenclature et une version de nomenclature
1. Cliquez sur Nouveau.
2. Cliquez sur Nomenclature et version de nomenclature.
3. Tapez une valeur dans le champ Nom.
    * Paramétrage d'un site  
    * Dans cette procédure, nous ne définissons pas de site spécifique pour la nomenclature.  
4. Cliquez sur OK.
5. Cliquez sur Nouveau.
    * Dans cette procédure, nous ajouterons quatre lignes à la nomenclature. Deux lignes représentent les options de câble et deux lignes représentent les options de meuble.  
6. Dans la liste, marquez la ligne sélectionnée.
7. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Sélectionnez le numéro d'article A0001, câbles HDMI 6'.  
8. Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.
    * Sélectionnez le groupe de configuration de câble créé dans le guide 4 de cette séquence.  
9. Cliquez sur Nouveau.
    * Sélectionnez le numéro d'article A0002, câbles HDMI 12'.  
10. Dans la liste, marquez la ligne sélectionnée.
11. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
12. Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.
    * Sélectionnez à nouveau le groupe de configuration de câble.  
13. Cliquez sur Nouveau.
14. Dans la liste, marquez la ligne sélectionnée.
15. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Sélectionnez le numéro d'article Meuble D0002.  
16. Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.
    * Sélectionnez le groupe de configurations Meuble pour cette ligne de nomenclature.  
17. Cliquez sur Nouveau.
18. Dans la liste, marquez la ligne sélectionnée.
19. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Sélectionnez le numéro d'article Meuble standard M0007 comme dernière ligne de nomenclature.  
20. Saisissez ou sélectionnez une valeur dans le champ Groupe de configurations.
    * Sélectionnez le groupe de configurations Meuble pour la dernière ligne de nomenclature.  

## <a name="approve-and-activate"></a>Approuver et activer
1. Fermez la page.
2. Cliquez sur Approuver.
3. Dans le champ Approuvé par, saisissez ou sélectionnez une valeur.
4. Sélectionnez Oui dans le champ Voulez-vous également approuver les nomenclatures ? .
5. Cliquez sur OK.
6. Cliquez sur Activer.

