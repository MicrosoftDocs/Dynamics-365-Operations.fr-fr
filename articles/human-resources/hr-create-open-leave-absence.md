---
title: Créer un congé à durée indéterminée
description: Cet article explique comment créer un congé à durée indéterminée dans Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 08231d4139209387c3c76923fafdd2061fceb280
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805339"
---
# <a name="create-an-open-ended-leave-of-absence"></a>Créer un congé à durée indéterminée

> [!IMPORTANT]
> La fonctionnalité décrite dans cet article sera disponible sur l’infrastructure Finance dans le cadre d’une future version de Microsoft Dynamics 365 Finance 10.0.31.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Vous pouvez soumettre des demandes de congé à durée indéterminée et voir l’état de vos demandes de congé dans Dynamics 365 Human Resources.

## <a name="prerequisites"></a>Conditions préalables

1. Sous **Gestion des fonctionnalités**, assurez-vous que la fonctionnalité **Congé à durée indéterminée** est activée.

    > [!IMPORTANT]
    > Cette fonctionnalité ne peut pas être désactivée une fois qu’elle a été activée.

2. Créez un type de congé.
3. Entrez les détails tels que le type de congé, la description et l’ID de flux de travail.
4. Dans le champ **Type de demande**, sélectionnez **Congé**.
5. Dans la section des détails, pour les congés à durée indéterminée, définissez l’option **Durée indéterminée** sur **Oui**.
6. Définissez l’option **Avis de retour au travail** sur **Oui** ou **Non**.
7. Un avis de retour au travail peut éventuellement être exigé pour les demandes d’absence à durée indéterminée.

> [!NOTE]
> Une fois cette fonction activée, la fonctionnalité **Pièce jointe obligatoire** peut être activée.

## <a name="request-an-open-ended-leave-of-absence"></a>Demander un congé à durée indéterminée

1. Dans l’espace de travail **Libre-service employé**, sélectionnez **Plus** (...) dans la vignette **Soldes des congés**.
2. Pour soumettre une demande de congé, sélectionnez **Demander un congé**.
3. Entrez des informations dans les champs **Type de congé** et **Date de début**. Dans le champ **Date de fin**, entrez une date de fin provisoire.
4. Si vous devez soumettre des pièces justificatives, sélectionnez **Charger** sous **Pièces jointes**.
5. Si vous êtes prêt à soumettre votre demande, sélectionnez **Soumettre**. Sinon, sélectionnez **Enregistrer en tant que brouillon**.
6. Pour mettre à jour une demande de congé à durée indéterminée, sélectionnez la demande, entrez une date de fin dans le champ **Date de fin**, définissez l’option **Confirmer la date de fin** sur **Oui**, puis téléchargez la documentation.
7. Si l’option **Avis de retour au travail** est définie sur **Oui**, sélectionnez **Téléchargez**, puis cochez la case pour confirmer qu’un avis de retour au travail valide a été téléchargé.
8. Lorsque tous les détails ont été saisis, sélectionnez **Soumettre**.
