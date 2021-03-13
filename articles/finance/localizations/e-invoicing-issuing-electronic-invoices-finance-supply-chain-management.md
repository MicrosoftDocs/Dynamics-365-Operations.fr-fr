---
title: Émettre des factures électroniques dans Finance et Supply Chain Management
description: Cette rubrique explique comment émettre des factures électroniques dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management via le module complémentaire de facturation électronique.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 187f5a20d088b4fcd7af2a6576357a69c2efc2c6
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104379"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Émettre des factures électroniques dans Finance et Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique explique comment émettre des factures électroniques dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management via le module complémentaire de facturation électronique.


## <a name="feature-activation"></a>Activation des fonctionnalités

Pour commencer à émettre des factures électroniques via le module complémentaire de facturation électronique, il est nécessaire d'activer la référence de fonctionnalité dans Finance et Supply Chain Management.

Chaque référence de fonctionnalité correspond à une fonctionnalité de facturation électronique spécifique conforme aux exigences de facturation électronique d'un pays/d'une région.

Le tableau suivant présente la liste des références de fonctionnalités prises en charge par le module complémentaire de facturation électronique.

| Référence de la fonctionnalité | Nom                                              | Pays/région |
|-------------------|---------------------------------------------------|----------------|
| BR-00053          | NF-e Federal - Facture électronique pour le Brésil       | Brésil         |
| BR-00095          | NFS-e Factures électroniques pour le Brésil               | Brésil         |
| DK-00001          | Facturation électronique du secteur public (OIOUBL) - DK    | Danemark        |
| EG-00008          | Facturation électronique pour l’Égypte                             | Égypte          |
| ES-00025          | Facture électronique du secteur public           | Espagne          |
| EUR-00023         | Union européenne Facturation électronique du secteur public       | Europe         |
| ITA-00036         | IT - Facturation électronique du secteur public (FatturaPA) | Italie          |
| MX-00010          | Facturation électronique de CFDI                                  | Mexique         |
| MX-00016          | Facturation électronique CFDI - procédure d'annulation           | Mexique         |

Lorsqu'il existe une fonctionnalité de facturation électronique héritée (prise en charge par l'ensemble des pays), l'activation de la référence de fonctionnalité permet d'émettre des factures électroniques via le module complémentaire de facturation électronique et de désactiver l'ancienne fonctionnalité.

## <a name="submit-electronic-documents"></a>Soumettre des documents électroniques

Le processus de soumission de documents électroniques représente le point de communication unique entre Finance et Supply Chain Management et le module complémentaire de facturation électronique. Lors de chaque événement de soumission, la communication circule dans les deux sens :

- **Entre Finance et Supply Chain Management et le module complémentaire de facturation électronique** - Finance et Supply Chain Management envoie les factures abstraites au module complémentaire de facturation électronique. Au besoin, ils envoient également le contenu des variables qui ont été configurées dans le cadre des fonctionnalités de facturation électronique.
- **Entre le module complémentaire de facturation électronique et Finance and Supply Chain Management** - En fonction de la fonction de facturation électronique, Finance et Supply Chain Management reçoivent des mises à jour du module complémentaire de facturation électronique sur les résultats du traitement des factures précédemment soumises. Ils reçoivent également le contenu des variables qui ont été configurées dans le cadre des fonctionnalités de facturation électronique.

Pour soumettre des documents électroniques au module complémentaire de facturation électronique, dans Finance et Supply Chain Management, accédez à **Administration d’organisation &gt; Périodique &gt; Documents électroniques &gt; Envoyer des documents électroniques**.

Le point de départ est une facture imputée. Cette facture peut provenir de différentes origines, telles que des commandes client, des factures de projet ou des factures en texte libre.

Le processus de soumission peut être exécuté manuellement ou en arrière-plan.

- **Exécution manuelle** - Pour une exécution manuelle, vous devez utiliser l'option **Filtre** pour définir la plage de documents à soumettre. Sur la page **Filtres**, vous pouvez configurer votre propre requête pour sélectionner les factures validées qui doivent être soumises. Une fois la sélection effectuée, vous devez démarrer manuellement l'exécution du traitement et attendre qu'il se termine. Une fois le traitement terminé, un message dans le Centre d'action indique le nombre de documents électroniques qui ont été soumis avec succès.
- **Exécution en arrière-plan** - L'exécution en arrière-plan s'exécute sans que vous soyez connecté ou que la boîte de dialogue de soumission reste ouverte. Vous pouvez planifier l'exécution du processus et définir la fréquence d'exécution.

## <a name="view-the-submission-logs"></a>Afficher les journaux d’envoi

Dans Finance et Supply Chain Management, vous pouvez utiliser les journaux d'envoi pour afficher les résultats du traitement de la soumission au module complémentaire de facturation électronique. Accédez à **Administration d'organisation &gt; Périodique &gt; Documents électroniques &gt; Envoi de documents électroniques**, puis, dans le champ **Type de document**, sélectionnez une valeur pour filtrer le type de factures affichées dans les journaux.

Il existe trois statuts de soumission possibles :

- **Planifié** - Le module complémentaire de facturation électronique a reçu la soumission de Finance et Supply Chain Management, et le traitement de la fonction de facturation électronique est en cours.
- **Terminé** - Le module complémentaire de facturation électronique a traité avec succès la fonction de facturation électronique exactement comme prévu.
- **Échoué** - Le module complémentaire de facturation électronique a rencontré une erreur ou a été arrêté par une exception lors du traitement de la fonction de facturation électronique.

> [!IMPORTANT]
> Le statut de soumission fait référence au statut du traitement que le module complémentaire de facturation électronique effectue sur la fonction de facturation électronique. Il ne fait pas référence au statut final de la facture électronique elle-même.
>
> Par exemple, si une facture électronique doit être soumise à un service Web externe pour approbation, le statut de soumission peut être **Terminé**, mais le statut de la facture électronique peut être **Rejeté**. Dans ce cas, le module complémentaire de facturation électronique a pu traiter avec succès la fonction de facturation électronique exactement comme prévu. Cependant, la facture électronique a été rejetée car elle ne répondait pas aux critères définis par le service Web pour l'approbation des factures.

Les journaux d'envoi incluent les fonctions supplémentaires suivantes :

- **Détails de l'envoi** - Afficher les détails de l'envoi principal. La visualisation montre le journal d'exécution complet des actions qui sont configurées dans la fonction de facturation électronique. Elle permet également aux utilisateurs de télécharger les fichiers créés lors du traitement. Dans les scénarios où la facture doit être approuvée par un service Web externe, elle permet aux utilisateurs de visualiser le statut de la facture.
- **Soumissions connexes** - Afficher les détails des soumissions enfants.
- **Annuler les soumissions** - Cette fonction permet l'exécution d'un processus de soumission spécial dans les scénarios où la facture électronique doit être approuvée par un service Web externe. Elle demande au module complémentaire de facturation électronique d'envoyer au service Web un message spécifique destiné à annuler le statut d'une facture électronique approuvée dans la base de données du service Web.
- **Soumettre à nouveau le document** - Soumettez à nouveau un document électronique qui a déjà été soumis au module complémentaire de facturation électronique. Un nouveau journal est créé sur la page **Détails de l'envoi**.
- **Envoyer une soumission associée**
