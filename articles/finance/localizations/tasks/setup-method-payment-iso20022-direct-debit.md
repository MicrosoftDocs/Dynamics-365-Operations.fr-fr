---
title: Configurer le mode de paiement pour le débit direct ISO20022
description: Cette procédure indique comment paramétrer le mode de paiement client pour le débit direct ISO20022 ou un autre type de paiement en utilisant les états électroniques.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d3c6d8157803e0a8d33520a0cd64fb725e8c9a3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174861"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>Configurer le mode de paiement pour le débit direct ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment paramétrer le mode de paiement client pour le débit direct ISO20022 ou un autre type de paiement en utilisant les états électroniques. 



Avant d'effectuer cette tâche, vous devez paramétrer les configurations du format d'exportation et les comptes de paiement.



Cette procédure a été créée à l'aide des données fictives de la société DEMF.



Il s'agit de la troisième des cinq procédures illustrant le processus de paiement client à l'aide des configurations de génération d'états électroniques.

1. Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Mode de paiement. avec une valeur de « ÉLECTRONIQUE ».
3. Cliquez sur Modifier.
4. Dans le champ Compte de paiement, indiquez les valeurs DEMF OPER.
5. Développez la section Formats de fichier.
6. Sélectionnez Oui dans le champ États électroniques génériques.
7. Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.
    * Dans la liste, sélectionnez Débit direct ISO20022 (Allemagne).  Si cette liste est vide, la configuration du format d'exportation de paiement client n'est pas importée et active.  
8. Sélectionnez Oui dans le champ Demander un mandat.
    * Sélectionnez le paramètre Demander un mandat pour les formats de paiement client, qui nécessitent d'inclure les informations de mandat dans le message de paiement, par exemple le débit direct SEPA.  
9. Cliquez sur Enregistrer.
