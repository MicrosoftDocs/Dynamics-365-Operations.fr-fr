---
title: Créer un compte bancaire fournisseur
description: Cette procédure décrit comment créer un compte bancaire pour un fournisseur.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: deb3587667ac13b95617ec219995bfef931df00c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546131"
---
# <a name="create-a-vendor-bank-account"></a>Créer un compte bancaire fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment créer un compte bancaire pour un fournisseur. Vous pouvez utiliser cette procédure dans les données fictives de la société USMF.

1. Accédez à Approvisionnements > Fournisseurs > Tous les fournisseurs.
2. Choisissez le fournisseur pour lequel vous voulez créer un compte bancaire, puis cliquez sur le lien sur l'ID compte fournisseur.
3. Cliquez sur Fournisseur dans le volet Actions.
4. Cliquez sur Comptes bancaires.
5. Cliquez sur Nouveau.
6. Tapez une valeur dans le champ Compte en banque.
    * Cette identification sera employée pour identifier le compte bancaire sur l'enregistrement fournisseur.  
7. Tapez une valeur dans le champ Nom.
8. Dans le champ Groupes de banques, saisissez ou sélectionnez une valeur.
9. Sélectionnez une option dans le champ Type de numéro d'acheminement.
    * Il s'agit du type de numéro d'acheminement utilisé pour les paiements internationaux.  
10. Tapez une valeur dans le champ Numéro de compte bancaire.
11. Tapez une valeur dans le champ Code SWIFT.
12. Tapez une valeur dans le champ IBAN.
    * Le numéro IBAN doit être dans un format correct. Par exemple, vous pouvez utiliser DE89370400440532013000.  
    * Le statut du compte bancaire est Actif si la date active a été atteinte, et si la date d'échéance n'a pas été dépassée. Elle est également active si les champs Date active et Date d'expiration sont vides. Si les dates des champs Date active et Date d'expiration se situent dans le futur, les paiements électroniques ne sont pas disponibles. Les autres types de paiements sont disponibles et le compte bancaire est actif.  
13. Développez la section Paramétrage.
14. Tapez une valeur dans le champ Code texte.
    * Ce champ spécifie un code qui apparaîtra sur le relevé bancaire du destinataire.  
15. Tapez une valeur dans le champ Message pour la banque.
16. Tapez une valeur dans le champ Référence de change.
    * Il s'agit du numéro de référence d'un taux de change à terme ou fixe.  
17. Dans le champ Devise, saisissez ou sélectionnez une valeur.
    * Quand des notes préliminaires sont publiées, cette section fournit un aperçu de leur statut (en attente ou approuvé).  
18. Développez la section Adresse.
19. Développez la section Notes préliminaires.
20. Développez la section Informations de contact.
21. Dans le champ Téléphone, tapez une valeur.
22. Fermez la page.
23. Cliquez sur Modifier.
24. Développez la section Paiement.
25. Dans le champ Compte bancaire, choisissez le compte que vous venez de créer.
26. Cliquez sur Enregistrer.
    * L'adresse peut être héritée du groupe bancaire, s'il est spécifié, ou vous pouvez l'ajouter ici.  

