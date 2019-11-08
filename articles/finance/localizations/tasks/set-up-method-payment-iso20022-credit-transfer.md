---
title: Paramétrer le mode de paiement pour les virements ISO20022
description: Cette procédure indique comment paramétrer le mode de paiement fournisseur pour le virement ISO20022 ou un autre type de paiement en utilisant les états électroniques pour générer un fichier.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8bb54864c8d0a57510b4d47b00aed60c5be95512
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174864"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Paramétrer le mode de paiement pour les virements ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure indique comment paramétrer le mode de paiement fournisseur pour le virement ISO20022 ou un autre type de paiement en utilisant les états électroniques pour générer un fichier. 

Avant d'effectuer cette tâche, vous devez exporter les configurations de format et paramétrer les comptes de paiement.

Cette tâche a été créé à l'aide des données fictives de la société DEMF.

Il s'agit de la troisième des cinq procédures illustrant le processus de paiement fournisseur à l'aide des configurations de génération d'états électroniques. Cette procédure s'applique à une fonction qui a été ajoutée dans la version 1611 de Dynamics 365 for Operations.

1. Accédez à Comptabilité fournisseur > Paramétrage des paiements > Modes de paiement.
2. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Mode de paiement. avec une valeur de « SEPA CT ».
3. Cliquez sur Modifier.
4. Sélectionnez Total dans le champ Période.
5. Sélectionnez « Paiement électronique » dans le champ Type de paiement.
6. Développez la section Formats de fichier.
7. Sélectionnez Oui dans le champ États électroniques génériques.
8. Entrez ou sélectionnez une valeur dans le champ Exporter la configuration du format.
    * Dans la liste, sélectionnez la valeur du virement ISO20022 (DE). Si cette liste est vide, la configuration du format d'exportation de paiement fournisseur n'est pas importée et active.  
9. Sélectionnez Banque dans le champ Type de compte.
10. Dans le champ Compte de paiement, indiquez les valeurs DEMF OPER.
11. Cliquez sur Enregistrer.
