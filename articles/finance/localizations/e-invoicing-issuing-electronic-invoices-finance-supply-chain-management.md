---
title: Émettre des factures électroniques dans Finance et Supply Chain Management
description: Cette rubrique explique comment émettre des factures électroniques dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management via le module complémentaire de facturation électronique.
author: gionoder
manager: AnnBe
ms.date: 02/26/2021
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
ms.openlocfilehash: 099ebb56710e920f7b1453f32f23f59a80486ebf
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5486951"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Émettre des factures électroniques dans Finance et Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Cette rubrique explique comment émettre des factures électroniques dans Microsoft Dynamics 365 Finance et Dynamics 365 Supply Chain Management via le module complémentaire de facturation électronique.


## <a name="feature-activation"></a>Activation des fonctionnalités

Pour émettre des factures électroniques via le module complémentaire de facturation électronique, vous devez activer la fonctionnalité dans Finance et Supply Chain Management.

Chaque fonctionnalité correspond à une fonctionnalité de facturation électronique spécifique conforme aux exigences de facturation électronique pour un pays/une région.

Le tableau suivant présente la liste des fonctionnalités qui peuvent être prises en charge par le module complémentaire de facturation électronique.

| Nom                                              | Pays/région |
|---------------------------------------------------|----------------|
|Facture électronique autrichienne                        |Autriche         |
|Facture électronique belge                         |Belgique         |
|NF-e  Federal - facture électronique brésilienne       |Brésil          |
|NFS-e - Facture électronique du service brésilien (ville)|Brésil          |
|Facture électronique danoise                          |Danemark         |
|Facture électronique égyptienne                        |Égypte           |
|Facture électronique estonienne                        |Estonie         |
|Facture électronique finlandaise                         |Finlande         |
|Facture électronique française                          |France          |
|Facture électronique allemande                          |Allemagne         |
|PEPPOL - Facture électronique globale                 |Général          |
|Facture électronique italienne                         |Italie           |
|CFDI - Facture électronique italienne                  |Mexique          |
|Facture électronique néerlandaise                           |Pays-Bas     |
|Facture électronique norvégienne                       |Norvège          |
|Facture électronique espagnole                         |Espagne           |

Lorsqu’il existe une fonctionnalité de facturation électronique héritée prise en charge dans l’ensemble des localisations d’un pays/d’une région, l’activation de l’une de ces fonctionnalités désactive la fonctionnalité héritée et permet d’émettre des factures électroniques via le module complémentaire de facturation électronique.

> [!IMPORTANT]
> Une fois que la fonctionnalité d’intégration du module complémentaire de facturation électronique est activée, la nouvelle expérience de facturation électronique est désactivée par défaut. Vous pouvez utiliser le concept de fonctionnalité pour activer de manière sélective de nouvelles expériences pour les entités juridiques à l’aide de fonctionnalités spécifiques au pays/à la région. L’option **Global** contrôle la nouvelle expérience pour les pays ou les régions restants qui ne sont pas spécifiquement répertoriés dans le tableau.

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
