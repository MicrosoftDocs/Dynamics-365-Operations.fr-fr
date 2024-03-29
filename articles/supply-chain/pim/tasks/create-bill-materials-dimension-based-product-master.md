---
title: Créer une nomenclature pour un produit générique fondé sur les dimensions
description: Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f86625821f8a01a6d4949f9dca538a279f52ce9c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565586"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Créer une nomenclature pour un produit générique fondé sur les dimensions

[!include [banner](../../includes/banner.md)]

Pour cette procédure, vous devez avoir déjà suivi les 4 premiers guides de cette séquence de huit enregistrements. Les 4 premiers enregistrements paramètrent les données requises pour exécuter cette procédure. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF. Cette tâche est généralement gérée par le concepteur de produit.

## <a name="select-the-product"></a>Sélectionner le produit

1. Allez à **Gestion des informations sur les produits \> Produits \> Produits lancés**.
1. Dans la liste, marquer la ligne sélectionnée.
    * Recherchez le produit générique lancé avec la technologie de configuration basée sur les dimensions que vous avez créée dans le premier guide des tâches dans cette séquence.  
1. Dans le volet Actions, sélectionnez **Ingénieur**.
1. Sélectionnez **Versions de nomenclature**.

## <a name="create-new-bom-and-bom-version"></a>Créer une nomenclature et une version de nomenclature

1. Sélectionnez **Nouveau**.
1. Sélectionnez **Nomenclature et version de nomenclature**.
1. Tapez une valeur dans le champ **Nom**.
    * Paramétrage d’un site  
    * Dans cette procédure, nous ne définissons pas de site spécifique pour la nomenclature.  
1. Cliquez sur **OK**.
1. Sélectionnez **Nouveau**.
    * Dans cette procédure, nous ajouterons quatre lignes à la nomenclature. Deux lignes représentent les options de câble et deux lignes représentent les options de meuble.  
1. Dans la liste, marquez la ligne sélectionnée.
1. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
    * Sélectionnez le numéro d’article A0001, câbles HDMI 6’.  
1. Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.
    * Sélectionnez le groupe de configuration de câble créé dans le guide 4 de cette séquence.  
1. Sélectionnez **Nouveau**.
    * Sélectionnez le numéro d’article A0002, câbles HDMI 12’.  
1. Dans la liste, marquer la ligne sélectionnée.
1. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
1. Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.
    * Sélectionnez à nouveau le groupe de configuration de câble.  
1. Sélectionnez **Nouveau**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
    * Sélectionnez le numéro d’article Meuble D0002.  
1. Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.
    * Sélectionnez le groupe de configurations Meuble pour cette ligne de nomenclature.  
1. Sélectionnez **Nouveau**.
1. Dans la liste, marquer la ligne sélectionnée.
1. Entrez ou sélectionnez une valeur dans le champ **Numéro d’article**.
    * Sélectionnez le numéro d’article Meuble standard M0007 comme dernière ligne de nomenclature.  
1. Saisissez ou sélectionnez une valeur dans le champ **Groupe de configurations**.
    * Sélectionnez le groupe de configurations Meuble pour la dernière ligne de nomenclature.  

## <a name="approve-and-activate"></a>Approuver et activer

1. Fermez la page.
1. Sélectionnez **Approuver**.
1. Dans le champ **Approuvé par**, saisissez ou sélectionnez une valeur.
1. Sélectionnez *Oui* dans le champ **Voulez-vous également approuver les nomenclatures ?**.
1. Cliquez sur **OK**.
1. Sélectionnez **Activer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]