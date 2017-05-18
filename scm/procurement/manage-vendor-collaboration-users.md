---
title: "Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur"
description: "Cette rubrique décrit comment vous pouvez demander la mise en service de nouveaux utilisateurs de collaboration fournisseur, et comment ajouter de nouveaux contacts de collaboration fournisseur."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 1f1df1e69f3933125bff3eba73d14e8615d7a2a6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="manage-vendor-collaboration-users"></a>Gérer les utilisateurs de la fonctionnalité de collaboration du fournisseur

[!include[banner](../includes/banner.md)]


Cette rubrique décrit comment vous pouvez demander la mise en service de nouveaux utilisateurs de collaboration fournisseur, et comment ajouter de nouveaux contacts de collaboration fournisseur. 

L'interface de collaboration fournisseur de Microsoft Dynamics 365 for Operations expose des informations sur les commandes fournisseur, les factures, et le stock de consignation aux fournisseurs externes. Vous pouvez créer des contacts de collaboration fournisseur et demander que les nouveaux utilisateurs soient mis en service si vous travaillez comme fournisseur externe avec le rôle de sécurité **Administrateur Fournisseur (externe)**, ou des autorisations similaires. Vous pouvez également effectuer ces tâches si vous travaillez comme professionnel de l'approvisionnement. Dans cette rubrique, ce rôle fait référence à un professionnel de l'approvisionnement qui travaille au sein de la société qui est le propriétaire de l'instance de Dynamics 365 for Operations. Pour plus d'informations sur l'utilisation de la collaboration fournisseur si vous êtes un fournisseur externe, voir [Fournisseur avec des clients](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Pour plus d'informations sur l'utilisation de la collaboration fournisseur si vous êtes un professionnel de l'approvisionnement, voir [Collaboration fournisseur avec des fournisseurs externes](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Ajouter des contacts de collaboration fournisseur
Si vous souhaitez qu'un utilisateur ait accès à la collaboration fournisseur, il doit d'abord être ajouté en tant que contact de collaboration fournisseur. Vous pouvez également ajouter des contacts pour les employés de votre société qui n'utilisent pas la collaboration fournisseur. Par exemple, ils peuvent être le point de contact d'autres types d'informations d'approvisionnement. De nouveaux contacts sont ajoutés sur la page **Tous les contacts**, disponible sous le menu **Collaboration fournisseur** &gt; **Contacts**. Pour ajouter un nouveau contact :

1.  Cliquez sur **Nouveau.**
2.  Entrez les détails de la personne principale à contacter.
3.  Sélectionnez l'entité juridique qu'elle représente dans votre société, et quelle entité juridique elle utilisera dans la société avec laquelle elle collaborera. Pour celà, sélectionnez une paire **Entité juridique de ma société**/**Entité juridique de la société du client**.
4.  Cliquez sur **Créer.**

Pour supprimer un contact, il est uniquement possible de supprimer ceux que vous avez créés.

## <a name="vendor-collaboration-user-requests"></a>Demandes d'utilisateur de la fonctionnalité Collaboration du fournisseur
Les demandes d'utilisateur de collaboration fournisseur peuvent être effectuées par un professionnel de l'approvisionnement, ou par un administrateur de fournisseur externe.

-   Si vous êtes un fournisseur externe, vous envoyez des demandes depuis la page **Tous les contacts** dans le module **Collaboration fournisseur**.
-   Si vous êtes un professionnel de l'approvisionnement, vous envoyez des demandes depuis la page **Afficher les contacts**. Pour cela, dans l'enregistrement du fournisseur, dans la section **Paramétrage** du volet Actions, sélectionnez **Contacts** &gt; **Afficher les contacts**.

Vous pouvez effectuer une demande de mise en service d'un utilisateur, de désactivation d'un utilisateur, ou de modification de rôles de sécurité. Si vous êtes administrateur de fournisseur externe, vous devez être enregistré en tant que personne à contacter pour les comptes fournisseur pour lesquels vous souhaitez effectuer des demandes d'utilisateur, et vous devez avoir accès à l'interface de collaboration fournisseur pour ces comptes fournisseur.  

Lorsqu'une demande est envoyée, elle est ajoutée à la liste **Demandes d'utilisateur de la fonctionnalité Collaboration du fournisseur** du module **Collaboration du fournisseur**, et à la liste **Demande d'utilisateur de la fonctionnalité Collaboration du fournisseur** dans le module **Approvisionnements** (le module Approvisionnements n'est pas accessible aux utilisateurs externes).

### <a name="provision-a-user"></a>Mettre en service un utilisateur

Avant de demander qu'un nouvel utilisateur soit mis en service, cette personne doit être paramétrée comme contact pour un ou plusieurs comptes fournisseur. Pour créer une demande d'utilisateur de collaboration fournisseur :

1.  Sur la page **Tous les contacts**, cliquez sur **Mettre en service un utilisateur fournisseur**.
2.  Entrez une adresse électronique pour l'utilisateur. Cette adresse sera utilisée par l'utilisateur pour se connecter à Dynamics 365 for Operations. Si l'adresse de messagerie électronique appartient à un domaine enregistré comme un locataire de Microsoft Azure, celle-ci doit être un compte Azure Active Directory (ADD) existant pour que le processus demise en service réussisse. Si l'adresse de messagerie électronique n'appartient pas à un domaine enregistré dans Microsoft Azure, un compte ADD sera créé dans le cadre du processus de mise en service et le nouvel utilisateur recevra un message électronique d'invitation. Les adresses de messagerie électronique de consommateurs avec des domaines tels que @hotmail.com, @gmail.com ou @comcast.net ne peuvent pas être utilisés pour enregistrer un utilisateur Dynamics 365 for Operations.
3.  Définissez l'option **Accès autorisé à la collaboration fournisseur** sur **Oui** pour toutes les entités juridiques auxquelles l'utilisateur doit accéder.
4.  Dans la section **Affecter des rôles utilisateur**, activez la case à cocher **Affecter** des rôles de sécurité que le nouvel utilisateur doit avoir.
5.  Cliquez sur **Soumettre**.

Lorsque la demande d'utilisateur fournisseur est envoyée, le champ **Accès autorisé à la collaboration fournisseur** est défini sur **Oui** pour le compte fournisseur sélectionné et un workflow de demande d'utilisateur est démarré. Dans le cadre du workflow, un utilisateur est créé dans Dynamics 365 for Operations, et des rôles de sécurité sont affectés. En outre, un service Azur B2B est activé qui initie l'interaction avec le portail Azure et associe un compte AAD nouveau ou existant au compte d'utilisateur Dynamics 365 for Operations.

### <a name="inactivate-a-user"></a>Désactiver un utilisateur

Il existe deux manières de supprimer l'accès à la collaboration fournisseur pour un utilisateur :

-   Sur la page **Contacts** du fournisseur, définissez l'option **Accès autorisé à la collaboration fournisseur** sur **Non** pour le contact. Cela peut s'effectuer individuellement selon l'entité juridique dont la personne est un contact. Cette option peut être utilisée uniquement par des professionnels de l'approvisionnement.
-   Désactivez le compte d'utilisateur complet, en soumettant une demande **Désactiver un utilisateur fournisseur**.

Pour demander la désactivation d'un utilisateur :

1.  Sur la page **Tous les contacts**, cliquez sur **Désactiver** **l'utilisateur fournisseur**.
2.  Écrivez un commentaire dans le champ **Justification de la demande**.
3.  Cliquez sur **Soumettre**.

### <a name="modify-security-roles"></a>Modifier des rôles de sécurité

La page **Tenir à jour les rôles utilisateur fournisseur** est identique à la page **Mettre en service un utilisateur fournisseur** sauf que la liste des rôles de sécurité peut être modifiée.  

Pour demander que des rôles de sécurité sont modifiés pour un utilisateur :

1.  Sur la page **Tous les contacts**, cliquez sur **Tenir à jour** **les rôles d'utilisateur fournisseur**.
2.  Écrivez un commentaire dans le champ **Justification de la demande**.
3.  Dans la section **Tenir à jour les rôles d'utilisateur**, sélectionnez les rôles de sécurité que vous souhaitez affecter, ou désactivez ceux que vous souhaitez supprimer.
4.  Cliquez sur **Soumettre**.





