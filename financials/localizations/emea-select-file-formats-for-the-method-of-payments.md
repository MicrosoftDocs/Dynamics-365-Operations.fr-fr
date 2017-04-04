---
title: Formats de fichier des modes de paiement
description: "Cette rubrique décrit les deux méthodes pour les formats de fichier de lecture que vous pouvez utiliser pour les modes de paiement."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 262514
ms.assetid: 72ea2018-5a49-419c-93d0-755e5ff2722f
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 54af22f1f2ec779bf947ae584a3ae09c20e6a364
ms.lasthandoff: 03/31/2017


---

# <a name="file-formats-for-methods-of-payment"></a>Formats de fichier des modes de paiement

Cette rubrique décrit les deux méthodes pour les formats de fichier de lecture que vous pouvez utiliser pour les modes de paiement.

Deux méthodes que vous pouvez utiliser les formats des formats de fichier de lecture à utiliser avec des modes de paiement, les formats de fichier de déclarations électroniques de (ER) ou X++ fichier. Lorsque vous paramétrez un mode de paiement pour un client ou un fournisseur, vous indiquez que les formats et les normes du fichier doit être utilisé pour les paiements et de traitement des paiements est traité. Vous pouvez choisir parmi les types de formats :

-   Exportation
-   Importation
-   Retourner
-   Remise

### <a name="method-1-electronic-reporting-file-formats"></a>Méthode 1 : Formats de fichier électronique de génération d'états

Pour les formats de fichier qui sont basées sur des configurations d'ER, vous devez importer les configurations des Lifecycle Services (LCS). Pour plus d'informations, voir [des configurations électroniques de génération d'états de téléchargement de Lifecycle Services] (/dynamics365/operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs). Après avoir importé les configurations de génération d'états pour ces formats de fichier, les formats importés sont disponibles sous ** des modes de paiement ** la page. Le processus d'importation et sélectionner les formats de fichier pour Europe est similaire à la procédure pour le Japon. <!---For more details, see [Enable the JBA payment file format](https://ax.help.dynamics.com/en/wiki/enable-the-jba-payment-file-format/).-->

### <a name="method-2-x-file-formats"></a>Méthode 2 : Formats de fichier X++

Pour sélectionner les formats de fichier qui sont basées sur le code X++, procédez comme suit.

1.  Allez ** des modes de paiement ** à la page.
2.  Sous ** des formats de fichier ** l'organisateur, cliquez sur ** paramétrage **.
3.  Sélectionnez l'onglet correspondant au type de format de fichier.
4.  Sélectionnez un format de fichier de ** disponible ** le répertorient et associée au ** sélectionné ** liste avec le contrôle de flèche.
5.  Fermez ** les formats de fichier des modes de paiement ** la page.
6.  Sous ** des formats de fichier ** l'organisateur, sélectionnez le format de fichier à utiliser pour le mode de paiement dans le champ approprié de format de fichier. Les options électroniques générales de génération d'états doivent être définies ** aucun ** pour les formats de fichier X++.



