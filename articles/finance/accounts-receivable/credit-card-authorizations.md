---
title: Paramétrage, autorisation et capture de carte de crédit
description: Cet article présente une vue d'ensemble de l'autorisation de la carte de crédit dans Microsoft Dynamics 365 Finance. Il inclut des informations sur le paramétrage d'un service de paiement, l'ajout d'une carte de crédit à une commande client et l'annulation d'une autorisation.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a06159f3d26cbaddc1417e863d7e665c2bfb424
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2177774"
---
# <a name="credit-card-setup-authorization-and-capture"></a>Paramétrage, autorisation et capture de carte de crédit

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

Cet article présente une vue d'ensemble de l'autorisation de la carte de crédit dans Microsoft Dynamics 365 Finance. Il inclut des informations sur le paramétrage d'un service de paiement, l'ajout d'une carte de crédit à une commande client et l'annulation d'une autorisation.

<a name="setting-up-the-credit-card-payment-service"></a>Paramétrage du service de paiement par carte de crédit
------------------------------------------

Pour utiliser les cartes de crédit, vous devez paramétrer et activer un service de paiement sur la page Services de paiement. Un service de paiement agit comme une passerelle entre votre entité juridique et la banque qui traite les frais de carte de crédit d'un client. Vous devez travailler avec un fournisseur de carte de crédit répertorié dans le champ Connecteur de paiement et paramétrer un compte avec ce fournisseur. Vous devez ensuite paramétrer les autres options sur la page Services de paiement, paramétrer les types de carte de crédit pour American Express, Discover, MasterCard sur la page Types de carte de crédit, et activer le fournisseur comme fournisseur par défaut. Vous devez également suivre ces étapes pour terminer votre configuration :
-   Sur la page Paramètres des ventes, spécifiez les paramètres pour utiliser les autorisations de carte de crédit.
-   Sur la page Conditions de paiement, paramétrez les conditions de paiement pour les cartes de crédit. Dans le champ Type de paiement, sélectionnez Carte de crédit.
-   Sur la page Cartes de crédit client, saisissez les informations de carte de crédit pour les clients.

## <a name="adding-a-new-credit-card"></a>Ajout d'une nouvelle carte de crédit
Vous pouvez créer des enregistrements de carte de crédit sur la page Clients à l'aide des paramètres Client, Paramétrage, Carte de crédit. Vous pouvez également créer des enregistrements de carte de crédit lorsque vous entrez des commandes client sur la page Commande client à l'aide des paramètres Gérer, Client, Carte de crédit, Enregistrer.

<a name="adding-a-credit-card-to-a-sales-order"></a>Ajout d'une carte de crédit à une commande client
-------------------------------------

Vous pouvez ajouter une carte de crédit à une commande client en sélectionnant une carte de crédit dans la recherche de carte de crédit sur l'organisateur Prix et remises sur la page Commande client. Pour démarrer le processus d'autorisation, dans le Volet Actions, sous l'onglet Gérer, sélectionnez Carte de crédit et Autoriser.

<a name="authorizing-a-credit-card"></a>Autorisation de carte de crédit
-------------------------

Lors d'une autorisation d'une carte de crédit, le numéro de la carte et le nom de son titulaire sont vérifiés, et le solde créditeur disponible est confirmé. Le cas échéant, la valeur de vérification de la carte de crédit et l'adresse du titulaire sont vérifiés. Le montant de la facture est alors déduit du solde créditeur disponible du client. Le service de paiement indique alors si la carte a été acceptée ou refusée. Lors de la facturation de la commande client, le montant facturé est débité (capturé) de la carte de crédit.

### <a name="card-verification-value"></a>Valeur de la vérification de la carte

Vous pouvez demander le numéro de vérification de carte, parfois appelé code de sécurité de la carte. Pour les cartes American Express, il s'agit d'une valeur à quatre chiffres. Pour les cartes Discover, MasterCard et Visa, il s'agit d'une valeur à trois chiffres.

### <a name="address-verification"></a>Vérification de l'adresse

Les informations de vérification d'adresse sont toujours envoyées au fournisseur de paiement. Vous pouvez choisir la quantité d'informations requises pour qu'une transaction soit acceptée. Vérifiez auprès de votre fournisseur pour déterminer s'il accepte ces informations. Voici les options pour la vérification de l'adresse :
-   **Toujours accepter la transaction** – Permet d'accepter la transaction, quel que soit le résultat de la vérification d'adresse.
-   **Titulaire du compte** – Permet de comparer le nom du titulaire de la carte dans la transaction aux informations de la société émettrice de la carte de crédit.
-   **Adresse de facturation** – Permet de comparer le nom et l'adresse de facturation du titulaire de la carte pour la transaction aux informations de la société émettrice de la carte de crédit.
-   **Code postal de facturation** – Permet de comparer le nom, l'adresse de facturation et le code postal du titulaire de la carte pour la transaction aux informations de la société émettrice de la carte de crédit.

## <a name="data-support"></a>Prise en charge des données
Vous pouvez spécifier le niveau de prise en charge des données pour chaque type de carte de crédit accepté. Le niveau contrôle la quantité d'informations concernant une transaction transférée au service de paiement. Vérifiez auprès de votre fournisseur pour déterminer s'il peut fournir ces informations. Voici les options du niveau de la prise en charge de données :
-   **Niveau 1** – Permet de transférer la date de la transaction, le montant de la transaction et la description.
-   **Niveau 2** – Permet de transférer les informations de niveau 1, ainsi que les adresses d'expédition et du commerçant, et les informations fiscales.
-   **Niveau 3** – Permet de transférer les informations de niveau 2, ainsi que les informations de ligne de commande.

## <a name="partial-payments"></a>Paiements partiels
Si vous expédiez une partie d'une commande, le montant de la commande partielle est capturé, et l'autorisation, qui concernant le montant de la commande entière, est clôturée. Une nouvelle autorisation est ensuite soumise pour le montant restant de la commande qui n'a pas été expédié.

## <a name="voiding-an-authorization"></a>Annulation d'une autorisation 
Pour annuler une autorisation de carte de crédit, vous pouvez modifier le mode de paiement avec un autre mode ne disposant pas d'un type de carte de crédit.





