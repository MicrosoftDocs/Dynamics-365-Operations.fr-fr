---
title: Retour de produits contrôlés par numéro de série dans le PDV
description: Cet article décrit les fonctionnalités de validation des articles à numéro de série dans le cadre du processus de retour dans l’application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9fa7e47b6d650370afe4b98d7eca01253bd1bc36
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268472"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a>Retour de produits contrôlés par numéro de série dans le PDV

[!include [banner](includes/banner.md)]

Cet article décrit les fonctionnalités de validation des articles à numéro de série dans le cadre du processus de retour dans l’application de point de vente (PDV) de Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Dans les versions 10.0.20 et ultérieures de Commerce, une nouvelle fonctionnalité nommée **Expérience unifiée du traitement des retours dans la PDV** est disponible. Pour utiliser la validation du numéro de série lors du traitement des retours dans le PDV, vous devez activer cette fonctionnalité. Pour plus d’informations sur les autres possibilités de cette fonctionnalité lorsqu’elle est activée, voir [Créer des retours dans le PDV](POS-returns.md).
>
> Une fois la fonctionnalité activée, elle ne peut pas être désactivée.

## <a name="options-for-validating-serialized-returns"></a>Options de validation des retours à numéro de série

Quand la fonctionnalité **Expérience unifiée du traitement des retours dans le PDV** est activée, les organisations peuvent réaliser la validation des retours d’articles contrôlés par numéro de série via le PDV. Cette fonctionnalité peut avertir les utilisateurs si le numéro de série renvoyé diffère du numéro de série d’origine qui a été vendu. Dans la version 10.0.20 et les versions ultérieures de Commerce, le message que les utilisateurs reçoivent est uniquement un message d’avertissement. Les utilisateurs peuvent continuer à traiter un retour avec un numéro de série différent du numéro de série initialement vendu.

Pour configurer la validation du numéro de série d’une organisation après avoir activé la fonctionnalité **Expérience unifiée du traitement des retours dans le PDV**, accédez à **Retail et Commerce \> Configuration du siège \> Paramètres \> Paramètres de Commerce** dans Commerce Headquarters. Sur l’onglet **Stock**, dans le raccourci **Opérations de stock du magasin**, définissez l’option **Activer la validation des numéros de série sur les retours au PDV** sur **Oui**.

## <a name="process-returns-for-serialized-items-in-pos"></a>Traiter les retours d’articles à numéro de série dans le PDV

Si l’option **Activer la validation des numéros de série sur les retours au PDV** a été définie sur **Oui**, lorsqu’un article contrôlé par numéro de série est retourné via le PDV, l’utilisateur peut saisir le numéro de série pour la ligne de retour dans le volet des détails de la page **Produits retournables**. Si le numéro de série entré ne correspond pas au numéro de série d’origine qui a été vendu lors de la transaction de vente, l’utilisateur reçoit un message d’avertissement. Cependant, l’application n’empêche pas l’utilisateur de continuer à valider le retour.

> [!NOTE]
> Actuellement, le PDV prend en charge la validation des numéros de série uniquement sur les lignes de retour où la quantité commandée d’origine n’est pas supérieure à un. Si la ligne de la commande client d’origine a été créée dans un canal autre que le PDV et si la quantité commandée pour l’article à numéro de série sur une ligne de vente donnée est supérieure à un, l’article ne peut pas être correctement retourné via le PDV.

## <a name="additional-resources"></a>Ressources supplémentaires

[Créer des retours dans le PDV](POS-returns.md)
