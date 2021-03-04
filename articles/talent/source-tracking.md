---
title: Suivre des sources de candidats dans Attract
description: Cette rubrique fournit des informations sur la remontée à la source des profils et des candidatures des candidats.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461149"
---
# <a name="track-candidate-sources-in-attract"></a>Suivre des sources de candidats dans Attract

[!include [banner](includes/banner.md)]

> [!NOTE] 
> La fonctionnalité décrite dans cette rubrique est accessible dans le cadre d'une version préliminaire. Le contenu et la fonctionnalité peuvent faire l'objet de modifications. Pour utiliser cette fonction, demandez à un administrateur de l'activer à l'aide des **Paramètres d'administrateur** dans Attract. Une version future fournira des états de suivi de la source. Pour plus d'informations, voir [Accéder aux fonctions d'aperçu de Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

Lorsque des candidats postulent à un emploi, Attract remonte automatiquement à la source de leur candidature. Cela vous donne des informations précieuses pour cibler vos initiatives de recrutement. Les recruteurs et les responsables du recrutement peuvent également sélectionner une source de candidature lorsqu'ils ajoutent manuellement un candidat à un emploi ou à un vivier de talents.

Vous pouvez afficher la source de la candidature dans les détails des activités de candidature sous l'onglet **Activité**, ainsi que dans l'historique de candidature disponible sous **Profil** dans les viviers de talents. Vous pouvez trouver la source du profil d'un candidat dans les détails du candidat sous l'onglet **Profil** dans les candidatures et les viviers de talents.

> [!NOTE] 
> Vous pouvez trouver des modèles de traitement dans le [Module complémentaire Recrutement complet](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).

## <a name="pre-configured-sources"></a>Sources préconfigurées

La liste de sources par défaut contient les sources de candidature courantes. Certains types de sources, tels que **Site d'emplois** et **Réseau social**, comportent des détails de source supplémentaires. Par exemple, **Réseau social** inclut Facebook et Twitter. Le type de source **Recommandation** permet de spécifier un employé interne comme parrain. La liste de sources par défaut comprend les sources préconfigurées suivantes :

-   Site de carrière Attract

-   Agence

-   Salon de l'emploi

-   Marketing de la société

-   Conférences et salons commerciaux

-   Association professionnelle

-   Site d'emploi

    -   Indeed

    -   Seek

    -   CareerBuilder

    -   Google Jobs

    -   Xing

    -   Glassdoor

    -   Monster

-   Magazines et publications

-   Réseau social

    -   Facebook

    -   Twitter

-   Recrutement universitaire

-   LinkedIn

-   Petites annonces

-   Renvoi

-   Ajouté par le recruteur

-   Autre/s

## <a name="customize-the-source-list"></a>Personnaliser la liste des sources 

Vous pouvez étendre la liste des sources pour inclure des sources de candidature supplémentaires. Pour personnaliser cette liste, suivez les instructions de [Étendre les ensembles d'options dans Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract). Modifiez l'entité **TalentSource** pour inclure des sources supplémentaires. 

Pour éviter d'affecter négativement l'interface utilisateur (IU), ne modifiez ni ne supprimez les valeurs d'énumération **TalentCategory** (pas les noms) pour :

- **Renvoi**
- **LinkedIn**
- **Autre/s**

Au lieu de cela, vous pouvez étendre l'énumération **TalentSource** pour ajouter d'autres types de sources.


[!INCLUDE[footer-include](../includes/footer-banner.md)]