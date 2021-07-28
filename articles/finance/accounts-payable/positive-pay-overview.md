---
title: Vue d’ensemble des paiements positifs
description: Cet article fournit des informations sur le paiement positif qui est utilisé pour générer une liste électronique de chèques devant être présentés à la banque.
author: panolte
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "88463"
- intro-internal
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f469cdbd74f228d235f9a84f52d9bd8656e97020
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2021
ms.locfileid: "6340275"
---
# <a name="positive-pay-overview"></a>Vue d’ensemble des paiements positifs

[!include [banner](../includes/banner.md)]

Cet article fournit des informations sur le paiement positif qui est utilisé pour générer une liste électronique de chèques devant être présentés à la banque. 

Vous pouvez utiliser le paiement positif pour générer la liste électronique des chèques devant être présentés à la banque. Des fichiers de paiement positifs peuvent aider les banques à empêcher les fraudes par chèque. Paramétrez le paiement positif pour générer une liste électronique de chèques chaque fois que des chèques sont imprimés. Puis, lorsqu’un chèque est présenté à la banque, la banque le compare avec la liste des chèques que vous avez précédemment envoyés. Si le chèque correspond à un chèque de la liste, la banque le compense. Si le chèque ne correspond pas à un chèque dans la liste, la banque le conserve pour examen.

Le salaire positif est également appelé SafePay. 

Les fichiers de paiement positif peuvent contenir des informations confidentielles sur les bénéficiaires et les montants des chèques. Veillez donc à utiliser les mesures de sécurité appropriées depuis la génération des fichiers jusqu’à leur réception par la banque. Les fichiers de paiement positif sont téléchargés en fonction des instructions de téléchargement pour le navigateur Web. 

Les fichiers de paiement positifs sont créés à l’aide d’entités de données. Avant de générer un fichier de paiement positif, vous devez définir les formats de transformation pour le XML qui traduit les données en un format que la banque peut consommer. 

Pour chaque compte bancaire pour lequel vous souhaitez générer des informations de paiement positif, vous devez affecter le format de paiement positif. Après avoir généré les paiements, vous pouvez générer un fichier de paiement positif pour une entité juridique unique et un compte bancaire unique. Sinon, vous pouvez générer des fichiers de paiement positif pour plusieurs entités juridiques et comptes bancaires en même temps. 

Lorsque les chèques répertoriés dans un fichier de paiement positif ont été payés, vous recevez un numéro de confirmation de la banque. Vous pouvez ensuite confirmer le fichier de paiement positif dans le système. 

Si vous devez modifier un fichier de paiement positif, vous pouvez le rappeler. Puis, pour chaque chèque présent dans un fichier de paiement positif, le champ qui indique si le chèque a été inclus dans un fichier de paiement positif est réinitialisé.

Pour plus d’informations, voir [Paramétrer et générer des fichiers de paiement positif](set-up-generate-positive-pay-files.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]