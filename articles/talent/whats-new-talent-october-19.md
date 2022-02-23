---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (16 octobre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d5f2aea5fcc81d0b4c1d8a392a3e56c888440a94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461135"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-16-2018"></a>Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (16 octobre 2018)

**Version 8.1.1067**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="allow-managers-to-update-time-off-requests"></a>Autoriser les responsables à mettre à jour les demandes de congés

Les demandes de congés des employés peuvent devoir être mises à jour après avoir été approuvées via le workflow. Dans de nombreux cas, le responsable effectue ces mises à jour au nom de l'employé. Cette nouvelle fonctionnalité offre aux responsables la fonctionnalité de mettre à jour ou d'annuler des demandes de congés au nom de leurs employés. Cette fonctionnalité est contrôlée par le paramètre **Travailler au nom de** qui peut être défini sur la page **Paramètres des ressources humaines**. 
 
## <a name="allow-hr-to-update-time-off-requests"></a>Autoriser les RH à mettre à jour les demandes de congés

Similaire à la fonctionnalité ci-dessus, les demandes de congés des employés peuvent devoir être mises à jour par les RH après avoir été préalablement approuvées via le workflow. Cette fonctionnalité permet aux utilisateurs des RH de mettre à jour les demandes de congés. La fonctionnalité est activée dans l'espace de travail **Personnes** et sur la page **Collaborateur**, en utilisant une nouvelle option **Afficher les congés**. Sur ces pages, les utilisateurs des RH peuvent afficher et mettre le temps à jour les transactions de congés, comme les responsables peuvent exécuter ces actions.

Le droit de sécurité qui contrôle l'accès à cette fonctionnalité est :
- Droit : Tenir à jour les processus de congé et d'absence spécifiques aux collaborateurs.
- Privilège : Tenir à jour les demandes de congés et d'absence pour tous les collaborateurs.

## <a name="other-changes"></a>Autres modifications
Les mises à jour suivantes ont été effectuées dans cette version :
- Modifications apportées à des actions d'embauche du collaborateur afin qu'il ne soit plus « coincé » à l'état **Workflow terminé**.
- Un enregistrement de l'emploi peut désormais être créé sans date de début de l'emploi.
- La date d'inscription à Dynamics 365 Talent pour un cours affiché dans le self-service des employés applique désormais le décalage de fuseau horaire à la date.
- Les fichiers Excel peuvent être importés à plusieurs reprises sans erreurs à l'aide de l'**Entité Employé**.

## <a name="known-issue"></a>Problème connu

- **Problème** : Lors de l'ajout d'une pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. 
- **Solution :** Avant d'ouvrir la page de la pièce jointe, assurez-vous que les récapitulatifs sur la page **Collaborateur** sont clôturés. Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés. (Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)
