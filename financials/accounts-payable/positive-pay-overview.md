---
title: Vue d&quot;ensemble des paiements positifs
description: "Cet article fournit des informations sur le paiement positif qui est utilisé pour générer une liste électronique de chèques devant être présentés à la banque."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 5cd2bf3525c99d41c30cdee3002cb08951dbd03d
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="positive-pay-overview"></a>Vue d'ensemble des paiements positifs

[!include[banner](../includes/banner.md)]


Cet article fournit des informations sur le paiement positif qui est utilisé pour générer une liste électronique de chèques devant être présentés à la banque. 

Vous pouvez utiliser le paiement positif pour générer la liste électronique des chèques devant être présentés à la banque. Des fichiers de paiement positifs peuvent aider les banques à empêcher les fraudes par chèque. Paramétrez le paiement positif pour générer une liste électronique de chèques chaque fois que des chèques sont imprimés. Puis, lorsqu'un chèque est présenté à la banque, la banque le compare avec la liste des chèques que vous avez précédemment envoyés. Si le chèque correspond à un chèque de la liste, la banque le compense. Si le chèque ne correspond pas à un chèque dans la liste, la banque le conserve pour examen.

Le salaire positif est également appelé SafePay. 

Les fichiers de paiement positif peuvent contenir des informations confidentielles sur les bénéficiaires et les montants des chèques. Veillez donc à utiliser les mesures de sécurité appropriées depuis la génération des fichiers jusqu'à leur réception par la banque. Les fichiers de paiement positif sont téléchargés en fonction des instructions de téléchargement pour le navigateur Web. 

Les fichiers de paiement positifs sont créés à l'aide d'entités de données. Avant de générer un fichier de paiement positif, vous devez définir les formats de transformation pour le XML qui traduit les données en un format que la banque peut consommer. 

Pour chaque compte bancaire pour lequel vous souhaitez générer des informations de paiement positif, vous devez affecter le format de paiement positif. Après avoir généré les paiements, vous pouvez générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique. Sinon, vous pouvez générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires en même temps. 

Lorsque les chèques répertoriés dans un fichier de paiement positif ont été payés, vous recevez un numéro de confirmation de la banque. Vous pouvez ensuite confirmer le fichier de paiement positif dans Microsoft Dynamics 365 for Operations. 

Si vous devez modifier un fichier de paiement positif, vous pouvez le rappeler. Puis, pour chaque chèque présent dans un fichier de paiement positif, le champ qui indique si le chèque a été inclus dans un fichier de paiement positif est réinitialisé.

Pour plus d'informations, voir [Paramétrer et générer des fichiers de paiement positif](set-up-generate-positive-pay-files.md).




