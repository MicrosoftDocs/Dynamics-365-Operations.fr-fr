--- 
title: "Affecter un modèle de facture financière à un client"
description: "Cette tâche montre comment affecter un modèle de facture financière à un client."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3bcb59c6edd04877dc2a052002be513205ae840a
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Affecter un modèle de facture financière à un client

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette tâche montre comment affecter un modèle de facture financière à un client. La société fictive USMF est citée en exemple dans cette tâche qui est destinée à l'utilisateur chargé de gérer et de traiter des factures de comptes clients.

1. Accédez à Comptabilité client > Clients > Tous les clients.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans le volet Actions, cliquez sur Facture.
4. Cliquez sur Factures récurrentes.
    * Cet écran permet d'affecter des modèles de facture financière à des clients et de spécifier la fréquence de l'envoi des factures au client.  
5. Cliquez sur Nouveau pour affecter un nouveau modèle au client.
6. Sélectionnez le modèle de facture financière à affecter au client.
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Permet d'entrer la date de génération de la première facture.
    * Entrez une date de fin récurrente.  
    * Sélectionnez l'une des options suivantes : Pas de date de fin pour ne pas générer les factures avant que le modèle soit supprimé du compte client.  Date de fin de facturation : Sélectionnez cette option pour entrer la dernière date à laquelle la facture peut être générée.  
    * Montant cumulatif maximal après lequel la génération de factures s'arrêtera.  
    * Permet d'entrer le montant cumulatif maximal pouvant être atteint à l'aide du modèle sélectionné. Par exemple, si vous entrez 1 000,00 et que vous générez des factures mensuelles de 100,00, la génération de factures s'arrêtera après la dixième facture.  
    * Générez des factures récurrentes à l'aide des valeurs par défaut provenant du modèle de facture financière ou du compte client.  
    * Permet d'indiquer si vous souhaitez utiliser le modèle de facture financière ou le compte client pour déterminer les valeurs par défaut pour la langue, le profil de validation, le groupe de taxe, le groupe de taxe d’article, le code liste, le pays/la région de la livraison, la devise, les conditions de paiement, le mode de paiement, la spécification de paiement, l'échéancier de paiement, l'escompte de règlement, les dimensions financières et le bordereau de transfert d'argent du virement lorsque des factures sont créées.  
10. Permet de sélectionner le modèle de répétition.
    * Opérations diverses : Sélectionnez cette option et entrez le nombre de jours dans le champ Par. Par exemple, si vous entrez 15, une facture est générée tous les 15 jours pour ce client.  Hebdomadaire : Sélectionnez cette option et entrez le nombre de semaines dans le champ Par. Par exemple, si vous entrez 2, une facture est générée toutes les 2 semaines pour ce client.  Mensuel : Sélectionnez cette option et entrez le nombre de mois dans le champ Par. Par exemple, si vous entrez 6, une facture est générée tous les 6 mois pour ce client.  Annuel : Sélectionnez cette option et entrez le nombre d'années dans le champ Par. Par exemple, si vous entrez 2, une facture est générée tous les 2 ans pour ce client.  
11. Entrez un numéro dans le champ Par.


