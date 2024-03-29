---
title: Modifier les informations personnelles
description: Cet article décrit comment modifier des informations personnelles dans le libre service pour employés et pour responsables.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7e78873d0995334ac80ac22e8058b7fe0bc31ac
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686120"
---
# <a name="edit-personal-information"></a>Modifier les informations personnelles


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez modifier vos informations personnelles dans Dynamics 365 Human Resources dans l’espace de travail **Libre service pour employés**.

Les informations personnelles que vous pouvez modifier incluent :

- Adresses
- Détails du contact
- Contacts personnels
- Numéros d’identifications
- Mode de règlement
- Image utilisée dans Human Resources

>[!NOTE]
>Il se peut que vous ne puissiez pas modifier certains types d’informations personnelles, telles que les coordonnées professionnelles. Pour plus d’informations, consultez [Restreindre la modification des informations personnelles](hr-employee-self-service-restrict-editing.md).

Les paramètres définis dans la page **Paramètres du carnet d’adresses global** déterminent les rôles qui peuvent voir vos informations personnelles.

1. Dans Human Resources, sélectionnez **Libre service employé**.

2. Sélectionnez **Modifier les informations personnelles**.

3. Pour changer votre adresse, sélectionnez l’onglet **Adresses**. Les modifications que vous apportez apparaissent dans l’espace de travail **Gestion du personnel** pour alerter les ressources humaines.

    - Pour ajouter une nouvelle adresse, sélectionnez **Ajouter**.
    - Pour modifier une adresse existante, sélectionnez l’adresse, puis sélectionnez **Modifier**.
    - Pour afficher une carte, sélectionnez **Carte**.
    - Pour ajouter ou supprimer un contact, sélectionnez **Plus d’options**, puis sélectionnez **Avancé**. Sous **Informations de contact**, sélectionnez **Ajouter** ou **Supprimer** et modifiez les champs si nécessaire.
    - Pour définir votre fuseau horaire et votre emplacement, sélectionnez **Plus d’options**, puis sélectionnez **Avancé**. Sous **Général**, modifiez les champs si nécessaire.

4. Pour modifier vos coordonnées, sélectionnez l’onglet **Informations de contact**. Vous pouvez fournir différents types d’informations de contact, notamment le téléphone, l’e-mail et les liens vers les réseaux sociaux. Vous pouvez définir un contact comme principal, mais vous ne pouvez définir qu’un seul de chaque type comme principal.

    - Pour ajouter un nouveau contact, sélectionnez **Ajouter**. Modifiez les champs, si nécessaire.
    - Pour modifier des informations de contact existantes, sélectionnez l’adresse, puis sélectionnez **Modifier**. Modifiez les champs, si nécessaire.
    - Pour définir un détail de contact comme privé, sélectionnez l’élément, sélectionnez **Avancé**, puis définissez le bouton à bascule **Privé** sur **Oui**. Cliquez sur **OK**.
      >[!NOTE]
      >Le bouton **Avancé** n’est pas disponible si votre administrateur a activé la fonctionnalité **(version préliminaire) Empêchez les employés d’ajouter ou de modifier des adresses et des informations de contact à des fins spécifiques** dans votre environnement. Pour plus d’informations, consultez [Restreindre la modification des informations personnelles](hr-employee-self-service-restrict-editing.md).
  
5. Pour modifier vos contacts personnels, sélectionnez l’onglet **Contacts personnels**. Vous pouvez désigner des contacts d’urgence, des bénéficiaires et des personnes à charge. Un contact peut être une personne ou une organisation. La fonctionnalité **Gestion des avantages** utilise des informations de contact personnelles. Pour en savoir plus, voir [Configurer les options d’éligibilité des contacts personnels](hr-benefits-setup-contact-eligibility-options.md).

6. Pour modifier vos numéros d’identification, tels que le numéro de sécurité sociale, sélectionnez l’onglet **Numéros d’identification**. Les modifications peuvent passer par un processus d’approbation si votre organisation configure un workflow d’approbation.

    - Pour ajouter un numéro d’identification, sélectionnez **Nouveau**. Remplissez les champs si nécessaire et sélectionnez **Enregistrer**.
    - Pour modifier un numéro, sélectionnez **Modifier**. Modifiez les champs si nécessaire et sélectionnez **Enregistrer**.

7. Pour modifier les méthodes de paiement, sélectionnez l’onglet **Mes informations de paiement**. Cet onglet n’est disponible que si les modes de paiement sont activés dans la page **Paramètres de Human Resources**. Human Resources peut activer **Traites bancaires**, **Espèces**, **Chèque**, **Paiement électronique** ou **Autre**. Human Resources peut également désactiver la validation de paiement électronique (utilisée pour la paie américaine) et la validation de compte bancaire et de numéro de routage.

8. Pour modifier l’image qui s’affiche dans Human Resources pour votre profil, sélectionnez l’onglet **Image**. Selon les paramètres de votre organisation, les images peuvent être acheminées pour approbation.

    - Pour télécharger une image, sélectionnez **Télécharger une nouvelle image**.
    - Pour supprimer une image, sélectionnez-la, puis sélectionnez **Supprimer**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
