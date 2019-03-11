---
title: Limites de crédit pour les clients
description: Cet article présente une vue d'ensemble de la procédure les limites de crédit dans Microsoft Dynamics 365 for Finance and Operations.
author: omulvad
manager: AnnBe
ms.date: 09/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8fd7022eb1ed2671fcfc2861eb8ec7504ebf9f98
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2019
ms.locfileid: "312667"
---
# <a name="credit-limits-for-customers"></a>Limites de crédit pour les clients

[!include [banner](../includes/banner.md)]

La définition d'une limite de crédit permet de spécifier le montant maximal de crédit accordé à vos clients. Si une limite de crédit est spécifiée, elle est vérifiée automatiquement lorsqu'un utilisateur tente de mettre à jour un document. Si la limite de crédit est dépassée, un message s'affiche pour l'utilisateur. Cet article fournit une vue d'ensemble de la façon dont fonctionnent les limites de crédit et répond aux questions suivantes :

-   Dans quels documents et dans quels processus puis-je vérifier les limites de crédit ?

-   Où puis-je configurer la manière dont le crédit restant du client est calculé ?

-   Où se trouvent les informations concernant le crédit restant utilisé d'un client ?

-   Où puis-je spécifier si l'identification est requise pour que le crédit soit accordé à un client, et où puis-je définir le montant de la limite de crédit qui nécessite une identification ?

-   Où puis-je spécifier l'affichage d'un avertissement ou d'un message d'erreur si la limite de crédit est dépassée ?

-   Comment puis-je spécifier la limite de crédit pour un client spécifique ?

-   Comment puis-je vérifier manuellement les limites de crédit sur les commandes client ?

**Dans quels documents et dans quels processus puis-je vérifier les limites de crédit ?**

Utilisez l'écran **Paramètres de la comptabilité client** pour spécifier pour quels documents vérifier les limites de crédit. Vous devez être membre du rôle de sécurité Administrateur système (- SYSADMIN-) pour modifier cet écran. Vous pouvez vérifier les limites de crédit dans les documents et les processus suivants :

-   les factures des commandes client, lorsque vous les validez ;

-   les bons de livraison des commandes client, lorsque vous les mettez à jour ;

-   les commandes client, lorsque vous ajoutez des lignes dans l'écran **Commande client**

-   les commandes client, lorsqu'elles sont créées via un service ;

-   les factures financières, lorsque vous validez les factures.

Les limites de crédit sont automatiquement vérifiées si l'une des options suivantes est définie :

-   Dans l'écran **Paramètres de la comptabilité client**, le champ **Type de limite de crédit** est défini sur une autre valeur que **Aucun**. Les limites de crédit sont vérifiées pour tous les clients.

-   Dans l'écran **Paramètres de la comptabilité client**, le champ **Type de limite de crédit** est défini sur **Aucun** et **Limite de crédit obligatoire** est activée pour un client dans l'écran **Clients**. Les limites de crédit sont vérifiées uniquement au niveau de clients spécifiques.

Pour vérifier les limites de crédit pour les documents suivants, vous devez spécifier des paramètres supplémentaires.

|    Document                                    |    Paramétrage supplémentaire                                                                                                             |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|    Facture   financière                         |    Dans l'écran Comptabilité client, dans la zone Degré de solvabilité, sélectionnez Vérifier la limite de crédit sur la facture   financière.     |
|    Commande   client (saisie manuelle)            |    Dans l'écran Comptabilité client, dans la zone Degré de solvabilité, sélectionnez Vérifier la limite de crédit sur la commande   client.           |
|    Commande   client (reçue par voie électronique)     |    Dans l'écran Comptabilité client, dans la zone EIA, sélectionnez Vérifier la limite de crédit pour les commandes client.                     |

**Où puis-je configurer la manière dont le crédit restant d'un client est calculé ?**

Vous pouvez configurer Dynamics 365 pour calculer le crédit restant d'un client de l'une des manières suivantes :

-   En comparant la limite de crédit avec solde du client.

-   En comparant la limite de crédit avec le solde du client et les montants du bon de livraison.

-   En comparant la limite de crédit avec le solde du client et toutes les activités de transaction en cours. Cela inclut les montants du bon de livraison et les montants de la commande client.

Utilisez l'écran **Paramètres de la comptabilité client** pour spécifier les informations à comparer. Vous devez être membre du rôle de sécurité Administrateur système (- SYSADMIN-) pour modifier cet écran. Dans le champ **Type de limite de crédit**, indiquez si vous souhaitez vérifier la limite de crédit et quelles informations de transaction doivent être incluses lorsque la limite de crédit est vérifiée. Vous pouvez sélectionner l'une des options suivantes :

-   **Aucun** – Ne pas vérifier les limites de crédit. Vous pouvez remplacer cette option pour un client spécifique en activant la case à cocher **Limite de crédit obligatoire** dans l'écran **Clients**. Dans ce cas, la limite de crédit est vérifiée par rapport au solde du client.

-   **Solde** – La limite de crédit est vérifiée par rapport au solde du client.

-   **Solde + bon de livraison ou accusé de réception de marchandises** – La limite de crédit est vérifiée par rapport au solde client et aux livraisons.

-   **Solde+Tout** – La limite de crédit est vérifiée par rapport au solde du client, aux livraisons et aux commandes en cours.

**Où se trouvent les informations concernant le crédit restant utilisé d'un client ?**

Le solde et le montant de crédit restant d'un client sont calculés et enregistrés lorsque vous créez un instantané de balance âgée, et sont affichés dans l'écran **Recouvrements**. Les montants affichés dans l'écran **Recouvrements** peuvent ne pas inclure toutes les activités de transaction tant qu'un nouvel instantané de balance âgée n'a pas été créé. Pour plus d'informations, voir [Recouvrements et crédit dans la Comptabilité client](https://technet.microsoft.com/en-us/library/hh209221.aspx).

En fonction des documents sélectionnés, les informations sur le solde d'un client et le montant créditeur restant sont calculés lorsque les commandes client, les bons de livraison et les factures client sont mis à jour. Si le montant du document sur lequel vous travaillez dépasse la limite de crédit, un message s'affiche.

**Où puis-je spécifier si l'identification est requise pour que le crédit soit accordé à un client, et où puis-je définir la limite de crédit qui nécessite une identification ?**

Utilisez l'écran **Paramètres de la comptabilité client** pour indiquer si l'identification est requise, ainsi que la limite de crédit qui nécessite l'identification.
Vous devez être membre du rôle de sécurité Administrateur système (- SYSADMIN-) pour modifier cet écran.

|    Champ                                    |    Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Demander   une identification avec crédit     |    Permet de sélectionner le type d'identification à entrer   pour les clients auxquels votre entité juridique accorde une extension de crédit. L'option sélectionnée dans ce champ détermine quand et le type d'informations nécessaires dans les champs d'identification du gouvernement dans l'écran   Clients :        Non - Aucune identification administrative n'est nécessaire, indépendamment de la limite de crédit du client.     Oui – Une        identification ou un numéro de licence émis par les autorités        administratives est nécessaire si la limite de crédit du client est supérieure        ou égale à zéro.     Limite inférieure – Une        identification ou un numéro de licence émis par les autorités        administratives est nécessaire si la limite de crédit du client est supérieure        ou égale à la limite entrée dans le champ Limite de cet        écran.        |
|    Limite                                    |    Permet d'entrer la limite de crédit à partir de   laquelle les clients doivent disposer d'une identification ou d'un numéro de licence émis par   les autorités administratives.    Par exemple, tapez 2000 afin qu'un   numéro d'identification, tel que le numéro de permis de conduire, soit exigé pour les clients   disposant d'une limite de crédit supérieure ou égale à 2 000.    Ce champ est disponible si vous avez sélectionné Limite   inférieure dans le champ Demander une identification avec crédit.                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Où puis-je spécifier l'affichage d'un avertissement ou d'un message d'erreur si la limite de crédit est dépassée ?**

Utilisez l'écran **Paramètres de la comptabilité client** pour spécifier l'affichage d'un avertissement ou d'un message d'erreur si la limite de crédit est dépassée. Cet avertissement ou erreur s'affiche lorsqu'un utilisateur entre ou valide des informations, ou bien est inclus dans un journal si les documents sont traités par un service électronique. Vous devez être membre du rôle de sécurité Administrateur système (- SYSADMIN-) pour modifier cet écran.

|    Champ                                                               |    Description                                                                                                                                                                                                                                                                                                                                                                                         |
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Message en cas de dépassement de la limite de crédit (dans la zone Degré de solvabilité)     |    Sélectionnez la manière dont les messages sur les limites de crédit   dépassées apparaissent aux utilisateurs. Sélectionnez l'une des options suivantes :        Erreur – Un        message d'erreur s'affiche. Cela bloque généralement l'opération en cours et        le conflit doit être résolu avant de poursuivre.     Avertissement – Un        message d'avertissement s'affiche mais le processus peut continuer.                     |
|    Message en cas de dépassement de la limite de crédit (dans la zone EIA)               |    Sélectionnez la façon dont les messages sur le   dépassement de la limite de crédit sont enregistrés dans un journal. Sélectionnez parmi les options suivantes :        Erreur - Un        message d'erreur s'affiche dans l'écran Exceptions et le        document ne sera pas traité tant que l'erreur n'aura pas été résolue.     Avertissement – Un        message d'avertissement est affiché dans l'écran Exceptions, mais le processus        peut continuer.        |

**Comment puis-je spécifier le montant de la limite de crédit pour un client spécifique ?**

Utilisez l'écran **Clients** pour spécifier le montant de la limite de crédit pour un client spécifique. Vous devez être membre d'un rôle de sécurité ayant le droit de Mettre à jour l'enregistrement principal du client (CustCustomersMaintain) pour apporter des modifications dans cet écran.

1.  Cliquez sur **Comptabilité client** \> **Commun** \> **Clients** \> **Tous les clients**. Double-cliquez sur un compte client.

2.  Dans l'écran **Clients**, dans le volet Actions, cliquez sur **Modifier**.

3.  Entrez un montant de devise dans le champ **Limite de crédit**. Cette valeur doit être supérieure à zéro (0). Elle sera utilisée comme montant limite de crédit.

4.  Si nécessaire, entrez un numéro de licence ou un numéro d'identification émis par les autorités administratives dans le champ **Identification du gouvernement**.

> [!NOTE]
> Dans l'écran **Paramètres de la comptabilité client**, un type de limite de crédit est généralement sélectionné. Toutefois, si le type de limite de crédit est défini sur **Aucun**, vous devez également activer la case à cocher **Limite de crédit obligatoire** dans l'écran **Clients** afin d'activer la limite de crédit du client par rapport à son solde. Pour plus d'informations sur les types de limite de crédit, voir « Dans quels documents et dans quels processus puis-je vérifier les limites de crédit ? » dans cette rubrique. 

**Comment puis-je vérifier manuellement les limites de crédit sur les commandes client ?**

Parfois, vous devez vérifier manuellement la limite de crédit d'un client. Par exemple, vous pouvez vérifier manuellement la limite de crédit d'un client avant de commencer à saisir une commande. Vous pouvez utiliser l'écran **Commande client** pour vérifier manuellement des limites de crédit. Vous devez être membre d'un rôle de sécurité ayant le droit de Mettre à jour la commande client (SalesOrderMaintain) pour apporter des modifications dans cet écran.

1.  Cliquez sur **Ventes et marketing** \> **Commun** \> **Commandes client** \> **Toutes les commandes client**. Double-cliquez sur une commande client.

2.  Dans l'écran **Commande client**, dans le volet Actions, sous l'onglet **Gérer**, cliquez sur **Vérifier la limite de crédit**.
