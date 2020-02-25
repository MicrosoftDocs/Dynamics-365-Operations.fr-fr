---
title: Type de destination pour l'envoi d'états électroniques par e-mail
description: Cette rubrique fournit des informations sur la configuration d'une destination de messagerie pour chaque composant DOSSIER ou FICHIER d'un format d'état électronique (ER) configuré pour générer des documents sortants.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019766"
---
# <a name="EmailDestinationType">Destination du courrier électronique</a>

[!include [banner](../includes/banner.md)]

Vous pouvez configurer une destination de messagerie pour chaque composant DOSSIER ou FICHIER d'un format d'état électronique (ER) configuré pour générer des documents sortants. En fonction du paramètre de destination, un document généré est remis en tant que pièce jointe d'un courrier électronique.

Définissez **Activé** sur **Oui** pour envoyer un fichier de sortie par courrier électronique. Une fois cette option activée, vous pouvez spécifier les destinataires du message et modifier l'objet et le corps du courrier électronique. Vous pouvez paramétrer des textes constants pour l'objet et le corps du courrier électronique, ou vous pouvez utiliser des [formules](er-formula-language.md) de génération d'états électroniques pour créer dynamiquement les textes de courrier électronique. 

Vous pouvez configurer les adresses électroniques pour les états électroniques de deux manières. La configuration peut être effectuée de la même manière que pour la fonction de gestion de l'impression, ou vous pouvez résoudre une adresse e-mail en utilisant une référence directe à la configuration ER via une formule.

[![Activer la destination de l'e-mail](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>Types d'adresses électroniques

Lorsque vous sélectionnez **Modifier** dans les champs **À** ou **Cc**, la boîte de dialogue **E-mail à** s'affiche. Vous pouvez ensuite sélectionner le type d'adresse électronique à utiliser. Les types d'e-mail **E-mail de configuration** et **Gestion de l'impression** sont actuellement pris en charge.

[![Sélectionner un type d'e-mail](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management"></a>Gestion de l'impression

Si vous sélectionnez le type d'e-mail **Gestion de l'impression**, vous pouvez entrer des adresses électroniques fixes dans le champ **À**. 

[![Configurer des adresses e-mail fixes](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)

Pour utiliser des adresses électroniques non fixes, vous devez sélectionner le type de source du courrier électronique pour une destination de fichier. Les valeurs suivantes sont prises en charge : **Client**, **Fournisseur**, **Prospect**, **Contact**, **Concurrent**, **Collaborateur**, **Candidat**, **Fournisseur potentiel** et **Fournisseur non autorisé**. Après avoir sélectionné un type de source de courrier électronique, utilisez le bouton en regard **Compte source de l'e-mail** pour ouvrir l'écran **Concepteur de formule**. Vous pouvez utiliser cet écran pour joindre une formule qui renvoie au moment de l'exécution le **compte de partie** du type de source sélectionné du document traité à la destination de l'e-mail.

[![Configurer le compte source de messagerie](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)

Les formules sont spécifiques à la configuration de l'état électronique. Dans le champ **Formule**, entrez une référence spécifique au document pour un type de partie Client ou Fournisseur. Au lieu de taper, vous pouvez rechercher un nœud de source de données qui représente le compte client ou fournisseur, puis sélectionner **Ajouter une source de données** pour mettre la formule à jour. Par exemple, si vous utilisez la configuration **Virement bancaire ISO 20022**, le nœud représentant un compte fournisseur est : `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

Si vous entrez une valeur de chaîne, telle que `"DE-001"`, et enregistrez une formule, un e-mail sera envoyé à la personne de contact du vendeur, **DE-001**.


[![Page Concepteur de formule ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)

[![Configurer le compte source de messagerie](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)



### <a name="configuration-email"></a>E-mail de configuration

Utilisez ce type de courrier électronique si la configuration que vous utilisez a un nœud dans les sources de données qui retourne une **adresse électronique**. Vous pouvez utiliser les sources et fonctions de données du concepteur de formule pour obtenir une adresse électronique correctement mise en forme. Par exemple, si vous utilisez la configuration **Virement bancaire ISO 20022**, le nœud représentant l'adresse e-mail du contact du fournisseur est : `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurer la source d'adresse de messagerie](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="additional-resources"></a>Ressources supplémentaires

- [Vue d'ensemble des états électroniques](general-electronic-reporting.md)
- [Destinations pour la gestion des états électroniques](electronic-reporting-destinations.md)
- [Concepteur de formule dans les états électroniques (ER)](general-electronic-reporting-formula-designer.md)
