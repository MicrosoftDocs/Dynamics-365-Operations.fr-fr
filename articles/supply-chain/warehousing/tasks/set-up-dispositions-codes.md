---
title: Paramétrer les codes disposition
description: Cette procédure se concentre sur le paramétrage du code disposition qui peut être utilisé sur un périphérique portable pour l'ordre de retour recevant le processus.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d84699e8e4323792ac67b69236d264e33eeaf28
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4428275"
---
# <a name="set-up-dispositions-codes"></a>Paramétrer les codes disposition

[!include [banner](../../includes/banner.md)]

Cette procédure se concentre sur le paramétrage du code disposition qui peut être utilisé sur un périphérique portable pour l'ordre de retour recevant le processus. Les codes disposition sont une collection de règles qu'il est possible d'utiliser lorsque des articles endommagés sont reçus. Par exemple, lorsqu'un utilisateur du travail utilise un périphérique portable pour recevoir les articles qui ont été endommagés, l'utilisateur doit numériser un code disposition pour les articles endommagés. Le statut du stock des marchandises reçues, le modèle de travail et la directive d'emplacement peuvent être déterminés à partir du code disposition numérisé. Pour la commande fournisseur recevant le processus et le rapport de l'ordre de fabrication comme étant terminés, l'utilisation de code disposition est facultative. Pour le processus de réception de retour de commande client, si les articles sont stockés à l'aide d'un périphérique mobile, l'utilisation de code disposition est obligatoire.  Ce guide a été créé à l'aide des données fictives de la société USMF. Cette procédure est destinée au gestionnaire d'entrepôts. 

1. Accédez à Gestion des entrepôts > Paramétrage > Appareil mobile > Codes disposition.
2. Cliquez sur Nouveau.
    * Créez un code disposition à utiliser pour les retours client.  
3. Dans le champ Disposition, tapez une valeur.
4. Dans la zone Statut du stock, sélectionnez le statut du stock dans lequel il existe blocage du stock.
    * Si vous utilisez le USMF, sélectionnez « Blocage ». Vous pouvez ajouter un statut de stock au code disposition pour remplacer le statut par défaut basé sur les lignes de commande.  
5. Dans le champ Modèle de travail, tapez une valeur.
    * Facultatif : sélectionnez un code de modèle de travail associé à un ordre de retour. Si aucune valeur n'est fournie, le modèle de travail est résolu à l'aide des règles standard configurées dans votre système. La sélection d'un modèle de travail limitera les processus dans lesquels ce code disposition pourra être utilisé. Par exemple, si le code disposition a un modèle de travail avec un ordre d'entretien de type commande fournisseur, il ne peut pas être utilisé pour enregistrer les retours clients.  
6. Dans le champ Disposition des retours, tapez une valeur.
    * Le code disposition de retour détermine le reste du processus d'ordre de retour pour les articles enregistrés. Dans cet exemple, le client doit recevoir un avoir. Ajoutez un code disposition de retours qui contient un crédit d'action.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]