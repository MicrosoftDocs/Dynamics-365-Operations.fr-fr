---
title: Affecter un modèle de facture financière à un client
description: Cette tâche montre comment affecter un modèle de facture financière à un client.
author: ShivamPandey-msft
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49074c11659ae30fd2decdb93b4721441edff2c5
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780523"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Affecter un modèle de facture financière à un client

[!include [banner](../../includes/banner.md)]

Cette tâche montre comment affecter un modèle de facture financière à un client. La société fictive USMF est citée en exemple dans cette tâche qui est destinée à l’utilisateur chargé de gérer et de traiter des factures de comptes clients.

1. Dans le **volet de navigation**, allez dans **Modules > Comptabilité client > Clients > Tous les clients**.
2. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
3. Cliquez sur **Facture** dans le volet **Actions**.
4. Cliquez sur **Factures récurrentes**. Cet écran permet d’affecter des modèles de facture financière à des clients et de spécifier la fréquence de l’envoi des factures au client.  
5. Cliquez sur **Nouveau** pour affecter un nouveau modèle au client.
6. Dans le champ **Modèle**, sélectionnez le modèle de facture financière à affecter au client.
7. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Dans le champ **Date de début de facturation**, entrez la date à laquelle la première facture est générée.
10. Dans la section **Fin de la répétition**, entrez une date de fin récurrente.  
    Sélectionnez l’une des options suivantes : 
    - **Pas de date de fin** : pour générer indéfiniment les factures jusqu’à ce que le modèle soit supprimé du compte client.
    - **Date de fin de facturation** : pour entrer la dernière date à laquelle la facture peut être générée.  
11. Dans le champ **Montant cumulatif maximal**, entrez le montant cumulatif maximal après lequel la génération de factures s’arrêtera. Permet d’entrer le montant cumulatif maximal pouvant être atteint à l’aide du modèle sélectionné. Par exemple, si vous entrez 1 000,00 et que vous générez des factures mensuelles de 100,00, la génération de factures s’arrêtera après la dixième facture.  
12. Dans la section **Générer des factures récurrentes à l’aide des valeurs par défaut provenant de**, sélectionnez soit du modèle de facture financière soit du compte client. Permet d’indiquer si vous souhaitez utiliser le modèle de facture financière ou le compte client pour déterminer les valeurs par défaut pour la langue, le profil de validation, le groupe de taxe, le groupe de taxe d’article, le code liste, le pays/la région de la livraison, la devise, les conditions de paiement, le mode de paiement, la spécification de paiement, l’échéancier de paiement, l’escompte de règlement, les dimensions financières et le bordereau de transfert d’argent du virement lorsque des factures sont créées.  
13. Dans le champ **Périodicité**, sélectionnez le modèle de répétition.
    - **Quotidiennement** : sélectionnez cette option et entrez le nombre de jours dans le champ Par. Par exemple, si vous entrez 15, une facture est générée tous les 15 jours pour ce client.
    - **Hebdomadaire** : sélectionnez cette option et entrez le nombre de semaines dans le champ Par. Par exemple, si vous entrez 2, une facture est générée toutes les 2 semaines pour ce client.
    - **Mensuel** : sélectionnez cette option et entrez le nombre de mois dans le champ Par. Par exemple, si vous entrez 6, une facture est générée tous les 6 mois pour ce client.
    - **Annuel** : sélectionnez cette option et entrez le nombre d’années dans le champ Par. Par exemple, si vous entrez 2, une facture est générée tous les 2 ans pour ce client.  
14. Entrez un numéro dans le champ **Par**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
