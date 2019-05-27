---
title: Configurer une option de menu d'appareil mobile pour terminer le travail du type commande fournisseur
description: Cette procédure montre comment configurer une option du menu Appareil mobile.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFAutoConfirm, WHSRFMenu
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 326a0039d2769ee5f459a87c302c93604d2379aa
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545877"
---
# <a name="set-up-a-mobile-device-menu-item-for-completing-work-of-type-purchase-order"></a>Configurer une option de menu d'appareil mobile pour terminer le travail du type commande fournisseur

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment configurer une option du menu Appareil mobile. Dans cet exemple, l'option de menu est utilisée pour effectuer le travail de type commande fournisseur. La classe de travail associée à l'option de menu qui détermine quel travail est valide. Vous pouvez utiliser ce guide dans les données de démonstration de la société fictive USMF. Cette procédure est généralement effectuée par un gestionnaire de l'entrepôt.


## <a name="create-a-mobile-device-menu-item"></a>Créer une option de menu d'appareil mobile
1. Accédez aux options de menu Appareil mobile.
2. Cliquez sur Nouveau.
3. Saisissez une valeur dans le champ Nom de l'option de menu.
    * Entrer une valeur unique. Par exemple, vous pouvez taper POMove. N’oubliez pas cette valeur, vous en aurez besoin ultérieurement.  
4. Tapez une valeur dans le champ Titre.
    * Il s'agit du titre qui sera affiché sur l'appareil mobile. Par exemple, vous pouvez taper PO Move.  
5. Dans le champ Mode, Sélectionnez « Travail ».
6. Sélectionnez Oui dans le champ Utiliser un travail existant.
    * Cet article de menu d'appareil mobile est utilisé pour effectuer un travail existant. Par conséquent, vous devez définir cette valeur sur Oui.  
    * Le champ Afficher le statut de stock détermine si l’état du stock disponible sera affiché pour le magasinier sur l'appareil mobile.  
7. Dans le champ Dirigé par, sélectionnez « Regroupement système ».
    * Quand vous choisissez quelque chose dans le champ Dirigé par, les champs supplémentaires apparaissent dans la section générale de cette page. Les champs qui apparaissent dépendent de ce que vous avez choisi. Lorsque vous sélectionnez Regroupement système, deux nouveaux champs sont ajoutés. Ces options sont expliquées ci-dessous.  
8. Dans le champ Regroupement système, sélectionnez « WorkPoolID ».
    * Lorsque les magasiniers ouvrent cet article du menu, ils sont invités à analyser un ID pool de travail. Tous les ordres d'exécution avec cet ID pool de travail et ces lignes d'ordre de travail en cours avec l'une des classes de travail ajoutées à cet article du menu seront envoyés à l’utilisateur.  
9. Dans le champ Étiquette de regroupement système, entrez une valeur.
    * Ce texte s'affiche pour l'utilisateur de l'appareil mobile. Par exemple, vous pouvez taper Pool de travail.  
10. Sélectionnez Oui dans le champ Remplacer le contenant lors du placement.
    * Cette option permet aux magasiniers de remplacer la plaque d’immatriculation cible lorsque les articles sont placés sur un emplacement de plaque d’immatriculation contrôlé.  
11. Sélectionnez Oui dans le champ Rangement du groupe.
    * Si toutes les lignes de placement sur l'ordre d'exécution partagent le même emplacement, l’utilisateur recevra une instruction de placement combinée pour toutes les lignes.  
    * ID modèle d’audit : un modèle d’audit de travail vous permet de spécifier que le processus de travail pour un article du menu doit être interrompu pour qu’une autre opération puisse être effectuée. Par exemple, si cette option de menu est pour le travail entrant, le modèle d'audit peut exiger que le collaborateur vérifie la température. Le point où le processus est interrompu est spécifié dans le modèle d'audit et peut être, par exemple, lorsque le travail est lancé ou terminé, ou lorsque le statut est modifié.  
12. Développez la section Classes de travail.
13. Cliquez sur Nouveau.
14. Tapez « Achat » dans le champ ID classe de travail.
    * Le pool de travail restreint le travail pour lequel l’article du menu peut être utilisé. Dans ce cas il sera utilisé pour les lignes de commande de travail en cours qui portent l'ID classe de travail d'achat.  
15. Cliquez sur Enregistrer.

## <a name="set-up-work-confirmation"></a>Configurer la confirmation du travail
1. Cliquez sur Paramétrage de la confirmation du travail.
2. Dans le champ Type de travail, sélectionnez « Prélever ».
3. Activez la case à cocher Confirmation automatique.
    * L’instruction de travail avec le type de travail Prélèvement sera automatiquement confirmée. Cette instruction ne sera pas être présentée à l’utilisateur.  
4. Cliquez sur Nouveau.
5. Dans le champ Type de travail, sélectionnez « Put ».
6. Activez la case à cocher Confirmation d'emplacement.
    * Le magasinier sera invité à effectuer une analyse de confirmation de l’emplacement, lorsque l’article est placé.  
7. Cliquez sur Enregistrer.
8. Fermez la page.
9. Fermez la page.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>Ajouter l'option de menu à un menu d'appareil mobile
1. Accédez au menu Appareil mobile.
2. Cliquez sur Modifier.
3. Utilisez le Filtre rapide pour rechercher les enregistrements. Par exemple, filtrez sur le champ Nom avec le valeur « Inbound ».
    * Vous souhaitez trouver le menu que vous utilisez pour les articles de menu entrant. Dans USMF, ce champ est appelé Entrant.  
4. Sélectionnez une valeur dans l'arborescence.
5. Cliquez sur la flèche qui pointe vers la droite.
6. Cliquez sur Enregistrer.
7. Fermez la page.

