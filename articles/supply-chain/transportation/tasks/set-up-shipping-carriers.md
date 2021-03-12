---
title: Paramétrer des transporteurs
description: Cette rubrique décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 124f7473cbdae8890f74115d461603f50cc58be8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004875"
---
# <a name="set-up-shipping-carriers"></a>Paramétrer des transporteurs

[!include [banner](../../includes/banner.md)]

Cette rubrique décrit comment paramétrer un transporteur et définir des détails tels que le service, le mode d'expédition, l'offre de transport, les contraintes de transport, et les frais de livraison. Un coordinateur de transport pourra ensuite affecter un transporteur à une charge entrante ou sortante.


## <a name="create-a-new-shipping-carrier"></a>Créer un transporteur
1. Accédez à **Volet de navigation > Modules > Gestion du transport > Paramétrage > Transporteurs > Transporteurs**.
2. Sélectionnez **Nouveau** dans le volet Actions.
3. Dans le champ **Transporteur**, saisissez une valeur.
4. Tapez une valeur dans le champ **Nom**.
5. Dans le champ **Mode**, sélectionnez une option dans le menu déroulant.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Renseigner les informations générales du transporteur
1. Activez ou désactivez l'extension de la section **Vue d'ensemble**.
2. Activez ou désactivez la case à cocher **Activation du transporteur**.
3. Dans le champ **Compte fournisseur**, sélectionnez une option dans le menu déroulant. Sélectionnez le compte fournisseur à affecter au transporteur.  
4. Dans le champ **Type d'offre de transport**, sélectionnez une option. Sélectionnez **Manuel** pour utiliser la page Offre de transport ou sélectionnez **EDI** pour mettre à jour l'offre à l'aide de l'échange de données informatisé (EDI).  
5. Activez ou désactivez la case à cocher **Activer le classement du transporteur**.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Créer les services nécessaires pour le transporteur
1. Activez ou désactivez l'extension de la section **Services**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Service de transporteur**, tapez une valeur.
4. Tapez une valeur dans le champ **Nom**.
5. Dans le champ **Mode de transport**, sélectionnez une option dans le menu déroulant.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Paramétrer l'adresse du transporteur (facultatif)
1. Activez ou désactivez l'extension de la section **Adresses**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Nom ou description**, saisissez une valeur.
4. Dans le champ **Pays/Région**, sélectionnez une option dans le menu déroulant.
5. Dans le champ **ZIP/Code postal**, sélectionnez une option dans le menu déroulant.
6. Dans le champ **Rue**, tapez une valeur.
7. Cliquez sur **OK**.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Paramétrer le profil de classement du transporteur
1. Activez ou désactivez l'extension de la section **Profils de classement**.
2. Sélectionnez **Nouveau**.
3. Dans le champ **Profil de classement**, tapez une valeur.
4. Tapez une valeur dans le champ **Nom**.
5. Dans le champ **Site**, sélectionnez une option dans le menu déroulant.
6. Dans le champ **Entrepôt**, sélectionnez une option dans le menu déroulant.
7. Dans le champ **Moteur de frais**, sélectionnez une option dans le menu déroulant. Sélectionnez le moteur de frais correspondant au contrat que vous avez avec le transporteur.  
8. Dans le champ **Données principales du taux**, sélectionnez une option dans le menu déroulant.
9. Dans le champ **Moteur de temps de transit**, sélectionnez une option dans le menu déroulant.
10. Sélectionnez **Enregistrer**.

