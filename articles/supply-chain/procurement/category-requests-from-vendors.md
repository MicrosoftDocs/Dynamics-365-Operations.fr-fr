---
title: Demandes de catégorie des fournisseurs
description: Cette rubrique décrit comment les fournisseurs peuvent demander des catégories d'approvisionnement pour leur compte. Elle décrit également le processus d'approbation exécuté par les agents d'approvisionnement.
author: GalynaFedorova
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9874151a5d82cc3441741489065877b78bab7bf5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671194"
---
# <a name="category-requests-from-vendors"></a>Demandes de catégorie des fournisseurs

[!include [banner](../includes/banner.md)]

Le processus de demande de catégorie permet aux fournisseurs de demander que de nouvelles catégories d'approvisionnement soient associées à leur compte. Ces catégories d'approvisionnement peuvent ensuite être utilisées par les processus d'approvisionnement et de sourçage connexes. (Pour plus d’informations, voir [Vue d’ensemble des catalogues d’approvisionnement](procurement-catalogs.md).)

Les demandes de catégorie sont initiées par les fournisseurs dans l'espace de travail **Informations fournisseur**. Elles sont ensuite soumises à votre agence pour examen et approbation. Les catégories approuvées sont ajoutées à la liste des catégories d'approvisionnement pour le compte du fournisseur.

## <a name="turn-the-category-requests-from-vendors-feature-on-or-off"></a>Activer ou désactiver la fonction de demandes de catégorie des fournisseurs

À compter de la version 10.0.25 de Supply Chain Management, cette fonctionnalité sera activée par défaut. Les administrateurs peuvent activer ou désactiver cette fonctionnalité en recherchant la fonctionnalité *Autoriser les fournisseurs à postuler pour les catégories d’approvisionnement grâce à la collaboration des fournisseurs* dans l’espace de travail [Gestion des fonctionnalités](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Si cette fonctionnalité est activée, vous pouvez toujours ajouter manuellement des catégories d’approvisionnement aux comptes fournisseurs. Pour plus d'informations, consultez [Approuver les fournisseurs pour des catégories d’approvisionnement spécifiques](tasks/approve-vendors-specific-procurement-categories.md).

## <a name="vendor-collaboration-requirements"></a>Configuration requise pour la fonctionnalité de collaboration fournisseur

Avant qu'un fournisseur puisse interagir avec des demandes de catégorie, la fonctionnalité de collaboration fournisseur doit être configurée.

Le fournisseur doit disposer d'au moins un utilisateur affecté à la collaboration fournisseur. Seuls les utilisateurs fournisseurs avec le rôle de sécurité *Administrateur du fournisseur (externe)* peuvent créer et soumettre des demandes de catégorie.

Pour plus d’informations, voir [Paramétrer et mettre à jour la collaboration fournisseur](set-up-maintain-vendor-collaboration.md).

## <a name="set-up-the-vendor-category-request-workflow"></a>Configuration du workflow de demande de catégorie fournisseur

Le workflow de *Demande de catégorie fournisseur* doit être configuré dans les workflows d'approvisionnement et de sourçage. Les fournisseurs soumettront de nouvelles demandes de catégorie que vous pourrez examiner et approuver. Les catégories d'approvisionnement demandées sont ajoutées à un compte fournisseur après l'approbation d'une demande de catégorie.

L'exemple suivant montre comment configurer un workflow simple *Demande de catégorie fournisseur* qui a un seul approbateur. Vous devez examiner vos processus internes pour déterminer la configuration de workflow appropriée pour votre agence.

1. Accédez à **Approvisionnements\> Configuration \> Workflows d’approvisionnements**.
1. Dans le volet Actions, sélectionnez **Nouveau**.
1. Dans la boîte de dialogue, sélectionnez **Workflow de demande de catégorie fournisseur** pour ouvrir l'éditeur de workflow.
1. Connectez-vous à l'éditeur de workflow.
1. Dans le volet Actions, cliquez sur **Propriétés**.
1. Sur la page **Propriétés** du workflow, dans le champ **Instructions de soumission**, entrez le texte de l'instruction. Les instructions seront affichées aux fournisseurs lorsqu'ils soumettront une demande de catégorie.
1. Fermez la page **Propriétés**.
1. Faites glisser l'élément de workflow **Approuver la nouvelle demande de catégorie** sur le canevas.
1. Faites glisser un lien depuis l'élément de workflow **Démarrer** vers l'élément de workflow **Approuver la nouvelle demande de catégorie**.
1. Faites glisser un lien depuis l'élément de workflow **Approuver la nouvelle demande de catégorie** vers l'élément de workflow **Fin**.
1. Appuyez deux fois (ou double-cliquez) sur l'élément de workflow **Approuver la nouvelle demande de catégorie**.
1. Sélectionnez et maintenez la sélection (ou cliquez avec le bouton droit) sur l'élément de workflow **Étape 1**, puis sélectionnez **Propriétés**.
1. Sur la page **Propriétés** de l'élément de workflow, dans le champ **Objet de l’élément de travail**, entrez le texte de l'objet. Ce texte sera affiché dans la valeur du champ **Objet** dans la page **Éléments de travail qui me sont affectés**.
1. Entrez le texte de l'instruction dans le champ **Instructions de l’élément de travail**. Les instructions seront visibles par les approbateurs lorsqu'ils sélectionneront **Workflow** dans le volet Actions d'une demande de catégorie.
1. Dans le volet gauche, sélectionnez **Affectation**.
1. Sur l'onglet **Type d'affectation**, définissez **Attribuer des utilisateurs à cet élément de workflow** sur *Utilisateur*.
1. Sur l'onglet **Utilisateur**, dans la liste **Utilisateurs disponibles**, sélectionnez un approbateur. Par exemple, sélectionnez un utilisateur du service Achats.
1. Sélectionnez la flèche droite (**\>**) pour déplacer l'approbateur vers la liste **Utilisateurs sélectionnés**.
1. Fermez la page **Propriétés**.
1. Sélectionnez **Enregistrer et fermer**.
1. Dans le champ **Notes de version**, entrez des notes sur le workflow.
1. Cliquez sur **OK** pour enregistrer le workflow.
1. Si vous êtes prêt à commencer à tester le workflow, sélectionnez **Activer la nouvelle version**. Sinon, sélectionnez **Ne pas activer la nouvelle version**.
1. Sélectionnez **OK** pour terminer la configuration du workflow.

> [!TIP]
> Si votre agence n'exige pas l'approbation des demandes de catégorie, vous devez configurer le workflow pour approbation automatique.

Pour plus d’informations sur l configuration des workflows, voir [Vue d’ensemble du système des workflows](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

## <a name="create-and-submit-a-category-request"></a>Création et soumission d'une demande de catégorie

Cette section décrit comment les fournisseurs peuvent utiliser l'espace de travail **Informations fournisseur** pour créer, modifier, afficher et soumettre des demandes de catégorie.

### <a name="start-a-new-request"></a>Démarrer une nouvelle demande

Pour démarrer une nouvelle demande de catégorie, procédez comme suit.

1. Dans l'espace de travail **Informations fournisseur**, sélectionnez la mosaïque **Demandes de catégorie**.
1. Sur la page **Demandes de catégorie**, dans le volet Actions, sélectionnez **Nouvelle demande de catégorie**.
1. Dans la boîte de dialogue **Nouvelle demande de catégorie**, recherchez la catégorie que vous souhaitez soumettre en naviguant dans l'arborescence et / ou en utilisant le filtre en haut de la liste. Cochez la case de chaque catégorie appropriée.

    Notez les points suivants :

    - Les catégories actuellement actives sur votre compte fournisseur sont affichées comme sélectionnées et ne peuvent pas être supprimées.
    - Vous pouvez demander plusieurs catégories d'approvisionnement dans une seule demande de catégorie.

1. Sélectionnez **OK** pour créer le brouillon de demande.

    La nouvelle demande de brouillon apparaît maintenant sur la page **Demandes de catégorie**.

1. Ouvrez le nouveau brouillon de demande pour l'examiner et le modifier si nécessaire.

    - Pour afficher la liste des catégories actuellement incluses dans la demande, sélectionnez le raccourci **Catégories demandées**.
    - Pour afficher vos catégories actives, ouvrez le raccourci **Catégories actives** sur le côté droit de la page.
    - Pour ajouter une catégorie à la demande, sélectionnez **Ajouter** dans la barre d'outils du raccourci **Catégories demandées**.
    - Pour supprimer une catégorie de la demande, sélectionnez la catégorie sur le raccourci **Catégories demandées**, puis sélectionnez **Supprimer** dans la barre d'outils.
    - Pour joindre un document à la demande, sélectionnez **Pièces jointes** dans le volet Actions. Les documents joints seront consultables par les approbateurs lorsqu'ils examineront la demande de catégorie.
    - Pour supprimer de la demande un document joint, sélectionnez **Pièces jointes** dans le volet Actions. Sélectionnez le document à supprimer, puis sélectionnez **Supprimer** dans le volet Actions.

1. Si vous êtes prêt à soumettre la demande, sélectionnez **Soumettre** dans le volet Actions. Sinon, fermez simplement la page et ignorez les étapes restantes de cette procédure. Vous pouvez toujours revenir à la demande plus tard.
1. Lisez les instructions de soumission qui s'affichent, puis sélectionnez **Soumettre**.
1. Dans la zone **Commentaire**, entrez les informations supplémentaires nécessaires. Puis, sélectionnez **Soumettre** pour terminer la demande.

### <a name="edit-a-draft-or-recalled-request"></a>Modifier un brouillon ou une demande rappelée

Pour modifier un brouillon ou une demande de catégorie rappelée, procédez comme suit.

1. Dans l'espace de travail **Informations fournisseur**, sélectionnez la mosaïque **Demandes de catégorie**.
1. Sélectionnez le brouillon ou la demande rappelée pour l'ouvrir.
1. Modifiez la demande comme requis, puis fermez-la ou soumettez-la comme décrit dans la procédure précédente.

### <a name="submit-a-draft-or-recalled-request"></a>Soumettre un brouillon ou une demande rappelée

Pour soumettre un brouillon ou une demande de catégorie rappelée, procédez comme suit.

1. Dans l'espace de travail **Informations fournisseur**, sélectionnez la mosaïque **Demandes de catégorie**.
1. Sélectionnez le brouillon ou la demande rappelée que vous souhaitez soumettre.
1. Dans le volet Actions, sélectionnez **Soumettre**.
1. Lisez les instructions de soumission qui s'affichent, puis sélectionnez **Soumettre**.
1. Dans la zone **Commentaire**, entrez les informations supplémentaires nécessaires. Puis, sélectionnez **Soumettre** pour terminer la demande.

    Le statut de la demande de catégorie est remplacé par l'une des valeurs suivantes :

    - _Révision en attente_ – La demande est dans le workflow.
    - _Approbation en attente_ - Une approbation est requise.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>Rappeler une demande soumise qui n'a pas encore été approuvée

Pour rappeler une demande de catégorie qui a été soumise mais qui n'a pas encore été approuvée, procédez comme suit.

1. Dans l'espace de travail **Informations fournisseur**, sélectionnez la mosaïque **Demandes de catégorie**.
1. Sélectionnez la demande en attente que vous souhaitez rappeler.
1. Dans le volet Actions, sélectionnez **Rappeler**.
1. Dans la zone **Entrez un commentaire**, entrez les informations supplémentaires nécessaires. Puis, sélectionnez **Soumettre** pour terminer la demande.

    Le statut de la demande de catégorie est remplacé par _Annulé_. La demande restera dans cet état jusqu'à ce que vous la supprimiez ou la soumettiez à nouveau.

### <a name="delete-a-draft-or-recalled-request"></a>Supprimer un brouillon ou une demande rappelée

Pour supprimer un brouillon ou une demande de catégorie rappelée, procédez comme suit.

1. Dans l'espace de travail **Informations fournisseur**, sélectionnez la mosaïque **Demandes de catégorie**.
1. Sélectionnez le brouillon ou la demande rappelée que vous souhaitez supprimer.
1. Dans le volet Actions, sélectionnez **Supprimer**.
1. Sélectionnez **Oui** pour confirmer la suppression.

### <a name="view-completed-requests"></a>Afficher les demandes terminées

Pour afficher les demandes terminées, ouvrez l'espace de travail **Informations fournisseur** et sélectionnez la mosaïque **Demandes de catégorie**. Les demandes de catégorie qui ont été traitées auront l'un des statuts suivants :

- _Approuvé_ – La demande a été approuvée. Pour afficher les nouvelles catégories ajoutées, revenez à l'espace de travail **Informations fournisseur**, ouvrez la liste déroulante **Plus de détails** dans le volet gauche, puis sélectionnez **Catégories**.
- _Rejeté_ – La demande a été rejetée. Vous pouvez créer une nouvelle demande de catégorie selon vos besoins.

## <a name="review-category-requests"></a>Réviser les demandes de catégorie

Cette section explique comment approuver, rejeter et déléguer les demandes de catégorie soumises par les fournisseurs et comment afficher les demandes terminées. Ces actions de workflow concernent l'ensemble de la demande de catégorie.

### <a name="view-category-requests"></a>Afficher les demandes de catégorie

Pour afficher les demandes de catégorie, procédez comme suit.

1. Accédez à **Approvisionnements \> Fournisseurs \> Demandes de collaboration fournisseur \> Demandes de catégorie**.

    La page **Demandes de catégorie** apparaît. La vue de page par défaut affiche les demandes de catégorie dont le statut est *Action en cours*.

1. Pour afficher toutes les demandes, sélectionnez *Toutes* dans le champ **Afficher les demandes**.
1. Ouvrez une demande pour l'examiner et la modifier si nécessaire.

    - Pour afficher la liste des catégories actuellement incluses dans la demande, sélectionnez le raccourci **Catégories demandées**.
    - Pour afficher les catégories actives, ouvrez le raccourci **Catégories actives** sur le côté droit de la page.
    - Si des documents ont été soumis, le bouton **Pièces jointes** (trombone) du volet Actions affiche le nombre de documents joints. Pour afficher les documents joints, sélectionnez le bouton **Pièces jointes**. Sélectionnez ensuite le document à afficher et sélectionnez **Ouvrir** pour le voir.
    - Pour joindre un document à la demande, sélectionnez **Pièces jointes** dans le volet Actions. Les documents joints seront consultables par les approbateurs lorsqu'ils examineront la demande de catégorie.
    - Pour supprimer de la demande un document joint, sélectionnez **Pièces jointes** dans le volet Actions. Sélectionnez le document à supprimer, puis sélectionnez **Supprimer** dans le volet Actions.
    - Dans le volet Actions, sélectionnez **Workflow** pour voir l'historique du workflow. Dans les options de workflow, sélectionnez **Plus**, puis **Historique du workflow**. La page **Historique du workflow** apparaît.

### <a name="approve-a-pending-category-request"></a>Approuver une demande de catégorie en attente

Pour approuver une demande de catégorie en attente, procédez comme suit.

1. Accédez à **Approvisionnements \> Fournisseurs \> Demandes de collaboration fournisseur \> Demandes de catégorie**.
1. Sélectionnez la demande en attente à approuver.
1. Révisez la demande de catégorie.
1. Facultatif : sur le raccourci **Général**, dans le champ **Code motif**, sélectionnez un code de motif. Puis, dans le champ **Commentaire du motif**, entrez un commentaire sur le code de motif.
1. Dans le volet Actions, sélectionnez **Workflow**.
1. Dans les options de workflow, sélectionnez **Approuver**.
1. Dans le champ **Commentaire**, entrez les informations supplémentaires nécessaires. Puis, sélectionnez **Approuver** pour terminer la demande.

    Le statut de la demande de catégorie est changé en _Approuvé_ et les catégories d'approvisionnement sont ajoutées au compte fournisseur.

### <a name="reject-a-pending-category-request"></a>Rejeter une demande de catégorie en attente

Pour rejeter une demande de catégorie en attente, procédez comme suit.

1. Accédez à **Approvisionnements \> Fournisseurs \> Demandes de collaboration fournisseur \> Demandes de catégorie**.
1. Sélectionnez la demande en attente à rejeter.
1. Révisez la demande de catégorie.
1. Dans le volet Actions, sélectionnez **Modifier**.
1. Sur le raccourci **Général**, dans le champ **Code motif**, sélectionnez un code de motif. Puis, dans le champ **Commentaire du motif**, entrez un commentaire sur le code de motif.
1. Dans le volet Actions, sélectionnez **Enregistrer**.
1. Dans le volet Actions, sélectionnez **Workflow**.
1. Dans les options de workflow, sélectionnez **Plus**, puis **Rejeter**.
1. Dans le champ **Commentaire**, entrez les informations supplémentaires nécessaires. Puis, sélectionnez **Rejeter** pour terminer la demande.

    Le statut de la demande de catégorie est remplacé par _Rejeté_. À ce stade, le fournisseur peut créer une nouvelle demande de catégorie s'il le souhaite.

### <a name="delegate-a-pending-category-request"></a>Déléguer une demande de catégorie en attente

Pour déléguer une demande de catégorie en attente à un autre utilisateur, procédez comme suit.

1. Accédez à **Approvisionnements \> Fournisseurs \> Demandes de collaboration fournisseur \> Demandes de catégorie**.
1. Sélectionnez la demande en attente que vous souhaitez approuver.
1. Dans le volet Actions, sélectionnez **Workflow**.
1. Dans les options de workflow, sélectionnez **Plus**, puis **Déléguer**.
1. Dans le champ **Utilisateur**, sélectionnez l'utilisateur auquel attribuer la demande de catégorie pour examen.
1. Dans le champ **Commentaire**, entrez les informations supplémentaires nécessaires.
1. Pour terminer la délégation, sélectionnez **Déléguer**. L'utilisateur sélectionné peut maintenant examiner la demande de catégorie.

### <a name="view-procurement-categories-for-a-vendor"></a>Afficher les catégories d'approvisionnement pour un fournisseur

Pour afficher les catégories d'approvisionnement pour un fournisseur après l'approbation d'une demande de catégorie, suivez ces étapes.

1. Accédez à **Approvisionnements \> Fournisseurs \> Tous les fournisseurs**.
1. Sur la page **Tous les fournisseurs**, sélectionnez le fournisseur pour lequel vous souhaitez afficher les catégories d'approvisionnement.
1. Dans le volet Actions, ouvrez l’onglet **Général** et, dans le groupe **Paramétrer**, sélectionnez **Catégories**.

    La page **Catégories** apparaît. Le raccourci **Approvisionnement** affiche les catégories d'approvisionnement qui ont été ajoutées via la demande de catégorie.

1. Sur le raccourci **Approvisionnement**, vous pouvez apporter des modifications si nécessaire. Par exemple, vous pouvez définir le champ **Statut de la catégorie fournisseur** sur _Préféré_.
