---
title: Configurer et utiliser la fonctionnalité de connexion étendue
description: Cet article décrit comment configurer et utiliser la fonctionnalité de connexion étendue de l’application PDV (Point de vente) de Microsoft Dynamics 365 Commerce.
author: boycezhu
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.industry: Retail
ms.search.form: RetailFunctionalityProfile
ms.openlocfilehash: e2fc39b1b7fb34f49c061dcc324c28cf5a89277c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283693"
---
# <a name="set-up-and-use-the-extended-logon-capability"></a>Configurer et utiliser la fonctionnalité de connexion étendue

[!include [banner](includes/banner.md)]

Cet article décrit comment configurer et utiliser la fonctionnalité de connexion étendue de l’application PDV (Point de vente) de Microsoft Dynamics 365 Commerce.

Cloud POS (CPOS) et Modern POS (MPOS) offrent une capacité de connexion étendue qui permet aux employés des magasins de détail de se connecter à l’application de PDV en scannant un code-barres ou en glissant une carte à l’aide d’un lecteur de bande magnétique (MSR).

## <a name="set-up-extended-logon"></a>Configurer la connexion étendue

Pour configurer une connexion étendue pour les caisses enregistreuses de PDV dans un magasin de détail, procédez comme suit.

1. Dans Commerce Headquarters, accédez à **Commerce et vente au détail \> Paramétrage du canal \> Paramétrage POS \> Profils POS \> Profils de fonctionnalité**. 
2. Dans le volet de navigation de gauche, sélectionnez le profil de fonctionnalité associé au magasin de vente au détail.
3. Dans le raccourci **Fonctions**, sous **Options d’authentification de connexion supplémentaires**, définissez les options suivantes sur **Oui** ou **Non** selon le cas :

    - **Connexion par code-barres du personnel** : définissez cette option sur **Oui** si vous souhaitez que vos employés se connectent au PDV en scannant un code-barres. 
    - **La connexion par code-barres du personnel nécessite un mot de passe** : définissez cette option sur **Oui** si vous souhaitez que vos employés saisissent un mot de passe quand ils se connectent au PDV en scannant un code-barres.
    - **Connexion par carte du personnel** : définissez cette option sur **Oui** si vous souhaitez que vos employés se connectent au PDV en glissant une carte.
    - **La connexion par carte du personnel nécessite un mot de passe** : définissez cette option sur **Oui** si vous souhaitez que vos employés saisissent un mot de passe quand ils se connectent au PDV en glissant une carte.

Le code-barres ou la carte est associé à des informations d’identification qui peuvent être attribuées à un employé. Les informations d’identification doivent comporter au moins six caractères. La chaîne qui contient les cinq premiers caractères doit être unique et est considérée comme un *ID d’identification* qui est utilisé pour rechercher un employé. Les caractères restants sont utilisés pour la vérification de sécurité. Par exemple, vous avez deux cartes, dont l’une a les informations d’identification 12345DGYDEYTDW et l’autre a les informations d’identification 12345EWUTBDAJH. Étant donné que ces deux cartes ont le même ID d’identification, 12345, elles ne peuvent pas être toutes les deux attribuées avec succès à des employés.

## <a name="assign-extended-logon"></a>Affecter une connexion étendue

Par défaut, seuls les responsables peuvent affecter une connexion étendue aux collaborateurs. Pour affecter une connexion étendue, accédez à **Connexion étendue** dans le PDV. Recherchez ensuite un collaborateur en entrant son ID de collaborateur dans le champ de recherche. Sélectionnez le collaborateur, puis cliquez sur **Affecter**. Sur la page suivante, faites glisser ou scannez la connexion étendue à affecter au collaborateur. Si cette opération permet une lecture correcte, le bouton **OK** devient disponible. Cliquez sur **OK** pour enregistrer la connexion étendue pour ce collaborateur.

## <a name="delete-extended-logon"></a>Supprimer une connexion étendue

Pour supprimer la connexion étendue affectée à un collaborateur, recherchez le collaborateur à l’aide de l’opération **Connexion étendue**. Sélectionnez le collaborateur, puis cliquez sur **Annuler l’affectation**. Toutes les informations d’identification de la connexion étendue associées à ce collaborateur sont supprimées.

## <a name="use-extended-logon"></a>Utiliser une connexion étendue

Une fois la connexion étendue configurée, et qu’un code-barres ou une carte magnétique a été affectée à un collaborateur, celui-ci doit juste faire glisser ou scanner sa carte lorsque la page de connexion de PDV s’affiche. Si un mot de passe est également requis pour pouvoir continuer, le collaborateur est invité à entrer son mot de passe.

## <a name="extend-extended-logon"></a>Étendre la connexion étendue

L’implémentation prête à l’emploi de la fonctionnalité de connexion étendue nécessite que les informations d’identification aient une longueur minimale de six caractères et que les cinq premiers caractères (l’ID d’identification) soient uniques. Cela était à l’origine conçu comme un exemple personnalisable par les développeurs pour répondre aux exigences d’une implémentation spécifique. (Par exemple, il pouvait être personnalisé pour prendre en charge plus de caractères ou utiliser différentes règles de vérification de sécurité.) Pour des informations détaillées sur la façon de créer des extensions pour la connexion étendue, voir [Extension de la fonctionnalité de connexion étendue pour MPOS et Cloud POS](https://cloudblogs.microsoft.com/dynamics365/no-audience/2018/12/14/extending-the-extended-logon-functionality-for-mpos-and-cloud-pos/).

Le service de connexion peut également être étendu pour prendre en charge les périphériques de connexion étendue supplémentaires, tels que des scanneurs de paume. Pour plus d’informations, voir la [documentation sur l’extensibilité de PDV](dev-itpro/pos-extension/pos-extension-overview.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
