---
title: Gérer les utilisateurs des partenaires commerciaux sur les sites Web B2B à l’aide de Dynamics 365 Sales
description: Cet article décrit comment utiliser Microsoft Dynamics 365 Sales pour gérer les approbations de partenaires commerciaux pour les sites Web interentreprises (B2B) Dynamics 365 Commerce.
author: shajain
ms.date: 2/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ac4aa15f2c6e7f557105254c2c8ce743a9466985
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878619"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites-using-dynamics-365-sales"></a>Gérer les utilisateurs des partenaires commerciaux sur les sites Web B2B à l’aide de Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Cet article décrit comment utiliser Microsoft Dynamics 365 Sales pour gérer les approbations de partenaires commerciaux pour les sites Web interentreprises (B2B) Dynamics 365 Commerce. Les organisations qui ont déjà investi dans la solution Dynamics 365 Sales peuvent utiliser ses concepts de piste et d’opportunité pour le processus d’approbation des partenaires commerciaux e-commerce B2B.

Pour des informations générales sur le processus d’approbation des partenaires commerciaux B2B, voir [Gérer les utilisateurs des partenaires commerciaux sur les sites e-commerce B2B](manage-b2b-users.md).

Les partenaires commerciaux potentiels peuvent lancer le processus d’intégration sur un site e-commerce B2B en soumettant une demande d’intégration via un lien sur le site Web B2B. Une fois la demande soumise et les travaux pertinents (tels que **P-0001** et **Synchroniser les commandes et les demandes de canal**) sont exécutés dans Commerce Headquarters, la demande d’intégration est enregistrée sur la page **Tous les prospects** page dans Commerce Headquarters. Le processus d’approbation des prospects du partenaire commercial peut ensuite être exécuté dans Sales.

Une fois l’intégration entre Sales et Commerce activée, la création d’un prospect partenaire commercial dans Commerce entraîne la création d’un *prospect* dans Sales.

L’illustration suivante montre un exemple de page de création de prospect pour un prospect de partenaire commercial dans Sales.

![Page de création de prospect dans Dynamics 365 Sales.](../media/LeadInSales.png)

Dans l’illustration, la section **Contact** indique la personne qui a soumis la demande d’intégration, et la section **Compagnie** montre l’organisation. Une remarque dans la section **Chronologie** indique que le prospect a été généré par l’infrastructure à double écriture. Parce qu’il a été créé par l’infrastructure à double écriture, ce prospect n’apparaîtra pas dans la liste déroulante **Mes prospects en cours**. Au lieu de cela, il apparaîtra sous une nouvelle vue nommée **Tous les prospects B2B Commerce**.

Selon le processus standard de qualification des prospects dans Sales, lorsqu’un utilisateur "qualifie" le prospect, un enregistrement *opportunité*, un enregistrement *contact* et un enregistrement *Compte* sont créés. L’infrastructure à double écriture est utilisée pour écrire les enregistrements de contact et de compte dans Commerce. Le contact est créé en tant que client du type *personne*, et la société est créée en tant que client du type *organisation*. Si un utilisateur sélectionne **Fermer comme gagné** pour l’opportunité, le prospect est approuvé dans Commerce. L’approbation d’un prospect entraîne la création d’une hiérarchie de clients.

Tous les processus commerciaux restants se produisent dans Commerce. Ces processus incluent l’envoi d’e-mails au partenaire commercial, la définition de la gestion des limites de crédit pour les utilisateurs et l’ajout d’autres utilisateurs au site B2B. Toutefois, si un utilisateur disqualifie le prospect ou marque l’opportunité comme perdue au lieu de qualifier le prospect, le prospect dans Commerce est marqué comme rejeté et un e-mail d’intégration de refus est envoyé au demandeur.

## <a name="enable-integration-between-sales-and-commerce"></a>Activer l’intégration entre Sales et Commerce

L’intégration entre Sales et Commerce repose sur l’infrastructure à double écriture. Par conséquent, la double écriture doit être activée et fonctionner, afin que les clients créés dans un système soient écrits dans l’autre système. Pour plus d’informations sur l’infrastructure à double écriture, voir [Présentation de la double écriture](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview).

Une fois la configuration en double écriture terminée, le partenaire de mise en œuvre peut accéder à [Microsoft AppSource](https://appsource.microsoft.com/) et recherchez la solution nommée [Solutions Commerce à double écriture](https://partner.microsoft.com/dashboard/commercial-marketplace/offers/7ca1d8c9-dc79-4cb7-a82e-8dc96a25acca/overview). Installez le package à l’aide de l’assistant d’installation standard, puis testez-le en créant un prospect sur un site B2B. Une fois le prospect créé, vérifiez que la demande s’affiche dans **Tous les prospects** apparaît dans Commerce, puis vérifiez que le prospect s’affiche en tant que prospect dans Sales.

## <a name="additional-resources"></a>Ressources supplémentaires

[Gérer les partenaires commerciaux sur les sites Web de commerce électronique B2B](manage-b2b-users.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
