---
title: Configurer le mode de paiement pour le débit direct ISO20022
description: Cette procédure indique comment paramétrer le mode de paiement client pour le débit direct ISO20022 ou un autre type de paiement en utilisant les états électroniques.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9c6a692553867d7e8679099210dc44b9d9e4d0f1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838680"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>Configurer le mode de paiement pour le débit direct ISO20022

[!include [banner](../../includes/banner.md)]

Cette procédure indique comment paramétrer le mode de paiement client pour le débit direct ISO20022 ou un autre type de paiement en utilisant les états électroniques. 



Avant d’effectuer cette tâche, vous devez paramétrer les configurations du format d’exportation et les comptes de paiement.



Cette procédure a été créée à l’aide des données fictives de la société DEMF.



Il s’agit de la troisième des cinq procédures illustrant le processus de paiement client à l’aide des configurations de génération d’états électroniques.

1. Accédez à Comptabilité client > Paramétrage des paiements > Modes de paiement.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Mode de paiement. avec une valeur de « ÉLECTRONIQUE ».
3. Cliquez sur Modifier.
4. Dans le champ Compte de paiement, indiquez les valeurs DEMF OPER.
5. Développez la section Formats de fichier.
6. Sélectionnez Oui dans le champ États électroniques génériques.
7. Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.
    * Dans la liste, sélectionnez Débit direct ISO20022 (Allemagne).  Si cette liste est vide, la configuration du format d’exportation de paiement client n’est pas importée et active.  
8. Sélectionnez Oui dans le champ Demander un mandat.
    * Sélectionnez le paramètre Demander un mandat pour les formats de paiement client, qui nécessitent d’inclure les informations de mandat dans le message de paiement, par exemple le débit direct SEPA.  
9. Cliquez sur Enregistrer.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]