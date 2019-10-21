---
title: Paramétrage de signatures électroniques
description: Utilisez cette procédure pour configurer des signatures électroniques.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysConfiguration, SIGParameters, SIGReasonCode, SIGProcSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1ad4ef067841511e235dcf538c720b72283d31c3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177806"
---
# <a name="set-up-electronic-signatures"></a>Paramétrage de signatures électroniques

[!include [task guide banner](../../includes/task-guide-banner.md)]

Utilisez cette procédure pour configurer des signatures électroniques. Une signature électronique confirme l'identité d'une personne qui va commencer ou approuver une procédure informatique. La société fictive de démonstration utilisée pour créer cette procédure est DAT.


## <a name="enable-the-electronic-signature-configuration-key"></a>Activez la clé de configuration Signature électronique
1. Accédez à Administration système > Paramétrage > Configuration des licences.
2. Dans l'arborescence, développez « Administration ».
    * Vérifiez que la case à cocher Signature électronique est activée.  
    * Si la case à cocher Signature électronique n'est pas activée, vous devez activer le mode maintenance. Le mode de maintenance peut être activé dans cet environnement en exécutant une tâche de maintenance à partir de Lifecycle Services ou en utilisant localement l'outil Deployment.Setup.  
3. Fermez la page.

## <a name="set-up-electronic-signature-parameters"></a>Définition des paramètres de signature électronique
1. Accédez à Administration d'organisation > Paramétrage > Signature électronique > Paramètres de signature électronique.
2. Cliquez sur Modifier.
3. Dans le champ Remarque, tapez une valeur.
    * Entrez l'avis que les signataires reçoivent lorsqu'une signature est demandée. Vous pouvez entrer un texte. Généralement, ce texte explique à l'utilisateur en quoi consiste la signature électronique d'un document.  
    * Si vous souhaitez entrer le texte de la remarque dans d'autres langues, cliquez sur le bouton Traductions.  
4. Cliquez sur Enregistrer.
5. Fermez la page.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>Paramétrage de codes motif pour les signatures électroniques
1. Accédez à Administration d'organisation > Paramétrage > Signature électronique > Codes motif des signatures électroniques.
2. Cliquez sur Nouveau.
    * Vous devez paramétrer des codes motif avant d'utiliser les signatures électroniques. Un code motif valide est obligatoire lors de la signature d'un document.     Un signataire sélectionne un code motif pour spécifier l'objectif d'une signature électronique. Par exemple, un code de motif peut être utilisé pour indiquer l'approbation légale.  
3. Dans le champ Code motif, tapez une valeur.
4. Dans le champ Description, entrez une valeur.
    * Entrez les codes motif supplémentaires, si nécessaire.  
5. Cliquez sur Enregistrer.
6. Fermez la page.

## <a name="require-electronic-signatures-for-existing-processes"></a>Demander des signatures électroniques pour des processus existants
1. Accédez à Administration d'organisation > Paramétrage > Signature électronique > Demandes de signature électronique.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Sélectionnez un processus nécessitant des signatures électroniques.  
3. Activez ou désactivez la case à cocher Signature.
    * Répétez ces étapes pour chaque processus qui exige des signatures électroniques.  
4. Cliquez sur Enregistrer.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>Créer une demande personnalisée pour des signatures électroniques
1. Cliquez sur Nouveau.
2. Activez ou désactivez la case à cocher Signature.
3. Dans le champ Nom, entrez un nom pour le processus qui nécessite des signatures électroniques.
4. Dans le champ Nom de table, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
5. Dans la liste, localisez et sélectionnez la table dans laquelle les données à signer sont stockées.
6. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
7. Dans le champ Nom du champ, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
8. Dans la liste, localisez et sélectionnez le champ de la table à surveiller.
9. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
    * Spécifiez le moment auquel une signature est obligatoire.     Sélectionnez Toujours si une signature est obligatoire lorsque les données d'un champ sont modifiées.     Sélectionnez Uniquement pour spécifier qu'une signature n'est obligatoire que dans certaines conditions. Si vous sélectionnez Uniquement, vous devez également sélectionner l'une des options suivantes : Lorsqu'un enregistrement est inséré, Lorsqu'un enregistrement est mis à jour, ou Lorsqu'un enregistrement est supprimé.  
10. Cliquez sur Enregistrer.
11. Fermez la page.

