---
title: Paramétrer une fonctionnalité de connexion étendue pour MPOS et Cloud POS
description: Cette rubrique couvre les options de configuration de la connexion étendue pour Cloud POS et Retail Modern POS (MPOS).
author: rubencdelgado
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom: 92353
ms.assetid: 7473e237-fbc8-41d5-8ba0-920242747488
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: f9d8889581e2e11fa5261805c866a6014df57611
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027574"
---
# <a name="set-up-extended-logon-functionality-for-mpos-and-cloud-pos"></a>Paramétrer une fonctionnalité de connexion étendue pour MPOS et Cloud POS

[!include [banner](includes/banner.md)]

Cette rubrique couvre les options de configuration de la connexion étendue pour Cloud POS et Retail Modern POS (MPOS).

## <a name="setting-up-extended-logon"></a>Paramétrage d’une connexion étendue

Vous trouverez le paramétrage des masques de code-barres dans **Retail et Commerce** &gt; **Paramétrage du canal** &gt; **Paramétrage du PDV** &gt; **Profils PDV** &gt; **Profils de fonctionnalités**. L’organisateur **Fonctions** inclut les options suivantes relatives à la connexion étendue.

### <a name="staff-bar-code-logon"></a>Connexion du personnel par code-barres

Lorsque l’option **Connexion du personnel par code-barres** est activée, les collaborateurs qui ont une connexion étendue affectée à leurs informations d’identification de point de vente (PDV) peuvent se connecter à l’aide d’un code-barres.

### <a name="staff-bar-code-logon-requires-password"></a>La connexion du personnel par code-barres nécessite un mot de passe

Lorsque l’option **La connexion du personnel par code-barres nécessite un mot de passe** est activée, la connexion du personnel par code-barres sélectionne uniquement le collaborateur qui est affecté à la connexion étendue présentée. Les collaborateurs doivent toujours entrer leur mot de passe lorsque cette option est activée.

### <a name="staff-card-logon"></a>Connexion du personnel par carte

Lorsque l’option **Connexion du personnel par carte** est activée, les collaborateurs qui ont une connexion étendue affectée à leurs informations d’identification de PDV peuvent se connecter à l’aide d’une bande magnétique.

### <a name="staff-card-logon-requires-password"></a>La connexion du personnel par carte nécessite un mot de passe

Lorsque l’option **La connexion du personnel par carte nécessite un mot de passe** est activée, la connexion du personnel par carte sélectionne uniquement le collaborateur qui est affecté à la connexion étendue présentée. Les collaborateurs doivent toujours entrer leur mot de passe lorsque cette option est activée.

## <a name="assigning-an-extended-logon"></a>Affectation d’une connexion étendue

Par défaut, seuls les responsables peuvent affecter une connexion étendue aux collaborateurs. Pour affecter une connexion étendue, accédez à **Connexion étendue** dans le PDV. Recherchez ensuite un collaborateur en entrant son ID de collaborateur dans le champ de recherche. Sélectionnez le collaborateur, puis cliquez sur **Affecter**. Sur la page suivante, faites glisser ou scannez la connexion étendue à affecter au collaborateur. Si cette opération permet une lecture correcte, le bouton **OK** devient disponible. Cliquez sur **OK** pour enregistrer la connexion étendue pour ce collaborateur.

## <a name="deleting-an-extended-logon"></a>Suppression d’une connexion étendue

Pour supprimer la connexion étendue affectée à un collaborateur, recherchez le collaborateur à l’aide de l’opération **Connexion étendue**. Sélectionnez le collaborateur, puis cliquez sur **Annuler l’affectation**. Toutes les informations d’identification de la connexion étendue associées à ce collaborateur sont supprimées.

## <a name="extending-extended-logon"></a>Extension de connexion étendue

Le service de connexion peut être étendu pour prendre en charge les périphériques de connexion étendue supplémentaires, tels que des scanneurs de paume. Pour plus d’informations, voir la documentation sur l’extensibilité de PDV.

## <a name="using-extended-logon"></a>Utilisation d’une connexion étendue

Lorsque la connexion étendue est configurée, et qu’un collaborateur a été affecté à un code-barres ou une bande magnétique, celui-ci doit juste faire glisser ou scanner la carte du collaborateur lorsque la page de connexion de PDV s’affiche. Si un mot de passe est également requis pour pouvoir continuer la connexion, le collaborateur est invité à entrer son mot de passe.


[!INCLUDE[footer-include](../includes/footer-banner.md)]