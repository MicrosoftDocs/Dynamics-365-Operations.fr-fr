---
title: Autoriser les modifications des données internes dans les documents de comptabilité
description: Cet article explique comment modifier les données internes sur les documents de comptabilité.
author: kweekley
ms.date: 08/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 6e346c6ff881d3a33743196b45247493fd19ed1d
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573249"
---
# <a name="allow-edits-to-internal-data-on-general-ledger-vouchers"></a>Autoriser les modifications des données internes dans les documents de comptabilité

[!include[banner](../includes/banner.md)]


Lorsque vous validez des écritures comptables dans le grand livre, le champ **Description** est souvent utilisé pour stocker des notes internes ou de la documentation. Si ces informations sont incorrectes, cela peut prêter à confusion et compliquer la clôture de l’exercice. Cette fonctionnalité permet au responsable comptable ou au superviseur comptable de corriger les erreurs en modifiant le champ **Description** sur les pièces validées en comptabilité.

Les modifications apportées aux documents de comptabilité validés sont limitées aux données de nature interne. Cette fonctionnalité ne vous permettra jamais de modifier des données telles que les montants, les dates de validation, les comptes généraux et la devise de transaction. Les modifications apportées à ces données auront une incidence sur la communication externe des états financiers et ne doivent être effectuées qu’au moyen de nouveaux documents de comptabilité.

> [!NOTE]
> Pour Dynamics 365 Finance version 10.0.29, cette fonctionnalité est limitée aux modifications apportées au champ **Description**.

## <a name="edit-internal-data-on-general-ledger-vouchers"></a>Modifications des données internes dans les documents de comptabilité

Avant de pouvoir modifier les données internes des documents de comptabilité, vous devez activer la fonctionnalité **Autoriser les modifications des données internes sur les documents de comptabilité** dans l’espace de travail **Gestion des fonctionnalités**.
Une fois la fonctionnalité activée, l’utilisateur qui modifiera les documents validés doit être affecté au rôle de responsable comptable ou de superviseur comptable. Vous pouvez également ajouter des autorisations à d’autres rôles en personnalisant les rôles de sécurité.

Le processus de modification n’est autorisé qu’à partir de la page Pièces comptables.

1. Allez dans **Comptabilité** > **Recherches et états** > **Pièces comptables**.
2. Dans la boîte de dialogue **SysQuery**, entrez les critères de recherche pour sélectionner les pièces comptables.
3. Sélectionnez les lignes des pièces comptables que vous souhaitez modifier, puis sélectionnez **Modifier les pièces comptables** > **Modifier les données internes de la pièce comptable**.

    [![Page Pièces comptables.](./media/voucher-transactions-page.png)](./media/voucher-transactions-page.png)
    
Sur la page **Modifier les données internes du document**, les données suivantes sont affichées pour chaque ligne que vous avez sélectionnée :
  
  - Compte général
  - Intitulé du compte
  - N° document
  - Description actuelle
  - Nouvelle description

    [![N° document de journal.](./media/edit-internal-voucher-data.png)](./media/edit-internal-voucher-data.png)
    
> [!NOTE]
> Seul le champ **Nouvelle description** peut être modifié. Par défaut, la valeur correspond à la valeur du champ **Description actuelle** afin que vous puissiez rapidement corriger les erreurs mineures dans la description.

4. Modifiez le champ **Nouvelle description** sur chaque ligne ou supprimez la description de chaque ligne.

   Si plusieurs lignes doivent être mises à jour avec la même valeur, vous pouvez également procéder comme suit :

      1. Sélectionnez les lignes à modifier, puis **Mettre à jour en bloc les enregistrements sélectionnés**.
      2. Dans le champ **Champ à modifier**, sélectionnez le champ à modifier. Actuellement, la recherche inclut uniquement le champ **Nouvelle description**.
      3. Dans le champ **Nouvelle valeur**, entrez une nouvelle description.
      4. Sélectionnez **Mettre à jour**. Tous les enregistrements sélectionnés sont mis à jour avec la nouvelle valeur.

      [![Boîte de dialogue Mettre à jour en bloc des enregistrements sélectionnés.](./media/bulk-update-selected-records.png)](./media/bulk-update-selected-records.png)
    
5. Dans le champ **Motif de la modification**, saisissez une remarque pour expliquer la modification. Cette remarque s’affiche sur la page **Piste d’audit des modifications de documents**.

   Plusieurs modifications peuvent être apportées au même document, et chaque modification fera l’objet d’un suivi.

## <a name="audit-trail-of-voucher-edits"></a>Piste d’audit des modifications de document

Une piste d’audit est conservée spécifiquement pour suivre les modifications apportées via cette fonctionnalité. Vous pouvez accéder à la piste d’audit des modifications de documents de deux manières :

  - Allez dans **Comptabilité** > **Recherches et états** > **Pièces comptables**. Sur la page **Demandes relatives aux documents**, sélectionnez **Modifier le document** > **Piste d’audit des modifications de documents**. La piste d’audit s’affiche uniquement pour l’enregistrement du document sélectionné. 
   
    En ouvrant la demande de cette manière, vous pouvez vous concentrer sur toutes les modifications apportées à un seul enregistrement de document.
  
  - Accédez à **Comptabilité** > **Tâches périodiques** > **Piste d’audit des modifications de documents**. Dans la boîte de dialogue, saisissez des critères pour spécifier les documents pour lesquels vous souhaitez afficher la piste d’audit des modifications. Pour afficher la piste d’audit de tous les documents, laissez les critères vides et sélectionnez **OK**. 
    
    En ouvrant la demande de cette manière, vous pouvez filtrer les modifications apportées à une date spécifique ou par un utilisateur spécifique.

La **Piste d’audit des modifications** affiche les informations suivantes :

- **Date et heure de création** – La date et l’heure de la modification.
- **Motif de la modification** – La raison de la modification saisie par l’utilisateur.
- **Créé par** – L’utilisateur qui a procédé à la modification.

Pour afficher les détails de chaque piste d’audit, explorez la valeur **Date et heure de création**. La page **Afficher les propriétés modifiées du document** affiche les mêmes informations que la page de modification d’origine, y compris la description précédente et la description mise à jour.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
