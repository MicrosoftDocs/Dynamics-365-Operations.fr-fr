---
title: Établir les commissions de paiement client
description: Créez des frais de paiement pour les paiements client.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5acb202d46ef39376a01ca592f60926786d11186
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "354826"
---
# <a name="establish-customer-payment-fees"></a>Établir les commissions de paiement client

[!include [task guide banner](../../includes/task-guide-banner.md)]

Créez des frais de paiement pour les paiements client.

La société fictive USMF est citée en exemple dans cette tâche.

1. Accédez à Comptabilité client > Paramétrage des paiements > Frais de paiement.
2. Cliquez sur Nouveau.
3. Entrez un ID frais dans le champ ID frais.
    * ID frais s'affiche sur les journaux des paiements, vous devez donc le rendre descriptif pour comprendre les frais qui sont imputés.  
4. Entrez un nom de frais dans le champ Nom.
5. Entrez une description des frais dans le champ Description des frais.
6. Sélectionnez si les frais seront facturés au client ou un compte général.
    * Si les frais sont imputés au client, sélectionnez Client. Si les frais seront imputés à votre organisation en tant que dépense, sélectionnez Comptabilité. Pour cette tâche, sélectionnez Client.  
7. Sélectionnez le type de journal qui peut utiliser ces frais de paiement.
    * Si ces frais sont utilisés pour les paiements client, le type de journal sera certainement Client - Paiements.  
8. Cliquez sur Enregistrer.
9. Cliquez sur Paramétrage des frais de paiement.
    * Le paramétrage des frais de paiement permet de définir les critères pour l'évaluation des frais de paiement.  Par exemple, vous pouvez indiquer que les frais seront calculés si le compte bancaire est USMF OPER, et le mode de paiement est le chèque.  
10. Sélectionnez Tableau, Groupe ou Tout pour définir sur quels comptes bancaires ces frais seront imputés.
    * Si vous sélectionnez Tous, ces frais pourraient être imputés sur tous les comptes bancaires.  Si vous sélectionnez Tableau, ces frais seront imputés sur le compte bancaire sélectionné uniquement. Si vous sélectionnez Groupe, ces frais peuvent uniquement être imputés aux comptes bancaires du groupe de banques sélectionné.  
11. Sélectionnez un groupe de banques ou un compte bancaire.
    * Si vous avez sélectionné Tableau, la recherche affiche les comptes bancaires. Si vous avez sélectionné Groupe, la recherche affiche les groupes de banques.  
12. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
13. Sélectionnez le mode de paiement pour lequel ces frais seront imputés.
    * Par exemple, vous pouvez imputer des frais à vos clients s'ils effectuent des paiements par chèque et non par paiement électronique.  
14. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
15. Le cas échéant, entrez une devise de paiement.
    * La devise de paiement est utilisée comme un critère supplémentaire si les frais sont imputés.  Par exemple, votre banque peut facturer des frais supplémentaires pour les paiements reçus en USD, si elle traite normalement uniquement les transaction en EUR.  
16. Sélectionnez si les frais seront un pourcentage, un montant ou un intervalle.
17. Entrez soit le pourcentage ou le montant des frais.
    * Si le champ Pourcentage/montant est Pourcentage, la valeur entrée ici sera un pourcentage. Si le champ Pourcentage/montant est Montant, la valeur entrée ici sera un montant. Si le champ Pourcentage/montant est Intervalle, utilisez l'onglet Intervalle pour définir les niveaux.  
18. Sélectionnez la devise des frais dans le champ Devise des frais.
    * Il s'agit de la devise dans laquelle les frais seront créés.  
19. Cliquez sur Enregistrer.

