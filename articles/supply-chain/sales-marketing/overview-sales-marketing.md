---
title: Ventes et marketing
description: "Vous pouvez faire appel à ce module pour obtenir, stocker et utiliser différents types de données dans le cadre du flux commercial. Ces données vont de l'initiative commerciale de départ aux futures ventes réalisées, en passant par les actions de suivi."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 92303
ms.assetid: 65ca9992-bbfa-4224-bf0e-067a25c7e6a4
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d810ff4028884cce5089c59d424aa92981dc5673
ms.contentlocale: fr-fr
ms.lasthandoff: 09/29/2017

---

# <a name="sales-and-marketing"></a>Ventes et marketing

[!include[banner](../includes/banner.md)]


Vous pouvez faire appel à ce module pour obtenir, stocker et utiliser différents types de données dans le cadre du flux commercial. Ces données vont de l'initiative commerciale de départ aux futures ventes réalisées, en passant par les actions de suivi.

<a name="marketing"></a>Marketing
---------

Vous utilisez des campagnes et des activités marketing pour rechercher et établir des relations avec les clients potentiels, afin que les interactions initiales puissent évoluer vers des relations commerciales. Le flux de processus suivant présente le processus d'entreprise pour le marketing. [![Processus d'entreprise pour le marketing](./media/marketing01.jpg)](./media/marketing01.jpg)

### <a name="relationships"></a>Relations

Dans les ventes et le marketing, les interactions initiales que vous avez avec des clients potentiels peuvent se produire dans diverses situations. Par exemple, vous pouvez trouver un client potentiel quand vous participez à un salon ou vous pouvez avoir un prospect possible avec un client après l’exécution d’une campagne de publipostage par votre organisation. Il est très important de comprendre le flux de l’entité d’une partie avant que cette partie devienne un client. Le graphique suivant illustre le flux des relations d’entités à mesure qu'un prospect devient un client réel. [![SalesandMarketing01](./media/salesandmarketing01.jpg)](./media/salesandmarketing01.jpg)

### <a name="campaigns"></a>Campagnes

Une campagne cible les contacts (prospects, opportunités et clients) sélectionnés pour y participer. Dans Microsoft Dynamics 365 for Finance and Operations, vous pouvez créer plusieurs types de campagnes, comme le télémarketing, le publipostage, et les campagnes par courrier électronique, afin d’optimiser vos clients potentiels. À mesure que vos campagnes évoluent et que vous recevez des réponses positives, vous pouvez commencer le processus de vente avec les destinataires qui ont répondu positivement à la campagne.

## <a name="sales"></a>Ventes
La fonctionnalité de vente vous permet de créer des devis, des ventes de gamme supérieure et des ventes croisées pour les clients nouveaux et existants, de créer des commandes client et de créer des factures de vente pour les clients. Le flux de processus suivant présente le processus d'entreprise pour les ventes. [![Processus d'entreprise pour les ventes](./media/sales01.jpg)](./media/sales01.jpg)

### <a name="sales-quotations"></a>Devis de vente

Vous créez des devis de vente pour présenter aux clients une offre de biens ou de services que vous fournissez. Un client peut demander un devis, ou vous pouvez créer un devis en réponse à une demande d’un client existant ou potentiel. Lorsque le client approuve le devis de vente, vous pouvez le convertir en commande client.

### <a name="up-sellcross-sell"></a>Vente de gamme supérieure/croisée

La vente de gamme supérieure et la vente croisée sont des techniques de vente de produits lorsqu’une commande est entrée pour un client. Dans la vente de gamme supérieure, un autre produit est proposé au lieu du produit en cours. Dans la vente croisée, un autre produit est proposé en plus du produit en cours. Lorsque vous définissez des listes de produits, vous pouvez créer des règles spécifiques pour indiquer quand un produit doit être proposé sous la forme d’un produit de vente de gamme supérieure ou de vente croisée.

### <a name="sales-orders"></a>Commandes client

Lorsque vous créez une commande client, vous devez sélectionner le type de commande client à créer. Vous avez le choix entre cinq options. **Remarque :** après avoir créé une commande client, n’importe quel type de commande peut être modifié, sauf le type **Demandes d'articles** si la commande client a le statut **Remis**.

| Type de commande client  | Description                                                                                                                                                                                                                                                                                            |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Journal           | Utilisez ce type en tant que brouillon pour une commande client. Ce type n'a aucune incidence sur les quantités de stock et ne génère pas de transactions d'article.                                                                                                                                                                    |
| Abonnement      | Utilisez ce type pour les commandes récurrentes. À la facturation de la commande, son statut est automatiquement défini sur une commande en cours. La quantité livrée facturée et les livraisons restantes sont mises à jour. Vous ne pouvez pas utiliser ce type de commande client si vous utilisez la fonctionnalité Gestion des entrepôts. |
| Commande client       | Utilisez ce type lorsqu’un client a effectué ou confirmé une commande.                                                                                                                                                                                                                                        |
| Commande retournée    | Utilisez ce type lorsque le client retourne un article. Un code retour (code RMA) est affecté automatiquement.                                                                                                                                                                                            |
| Demandes d'articles | Ce type est créé automatiquement lorsque vous vendez des articles via un projet.                                                                                                                                                                                                                       |

### <a name="sales-agreements"></a>Contrats de vente

Un contrat de vente est un contrat qui engage le client à acheter une certaine quantité ou un certain montant de produit sur une période définie en échange de prix spéciaux et de remises. Les prix et les remises du contrat de vente sont prioritaires sur tous les autres prix et remises indiqués dans les autres contrats de vente pouvant exister. Un contrat de vente est valide pendant une durée définie. La date de livraison demandée qui est spécifiée pour une vente sur la page **Commande client** doit se trouver dans la période de validité. Par défaut, un contrat de vente est en attente. Vous pouvez uniquement passer une commande à partir d'un contrat de vente défini sur **Effectif**.

### <a name="backorders"></a>Commandes en souffrance

Lors de la saisie et du contrôle des commandes, il se peut que vous deviez gérer des commandes en souffrance et des exceptions avant de réaliser la vente. Des reliquats sont des commandes non encore livrées par un fournisseur (commandes fournisseur) ou à un client (commandes client). Il est important de suivre les reliquats. Par exemple, si des produits sont retardés par un fournisseur, vous pouvez modifier la date de livraison au client et l'informer du retard. Vous pouvez afficher les reliquats par article, client ou fournisseur.

#### <a name="viewing-backorders-by-item"></a>Affichage des reliquats par article

En affichant les reliquats par article, vous pouvez suivre le futur flux de transactions prévu pour un article spécifique. Par exemple, vous pouvez vérifier les informations suivates :

-   le nombre de commandes client passées pour un article ;
-   si des livraisons d'articles en provenance de fournisseurs sont toujours manquantes ;
-   si davantage d'articles doivent être commandés afin d'assurer la livraison de toutes les commandes client en temps voulu.

En effectuant cette vérification, vous pouvez répondre aux demandes des clients à propos de la synchronisation de la livraison. En outre, vous pouvez classer les reliquats client par ordre de priorité et, le cas échéant, répartir les articles disponibles entre les commandes.

#### <a name="viewing-backorders-by-customer"></a>Affichage des reliquats par client

La vue d'ensemble des reliquats par client permet d'afficher le statut des commandes client restantes. Cette vérification est utile lorsque vous devez répondre aux clients qui sont en attente des articles qui ont été retardés.

#### <a name="viewing-backorders-by-vendor"></a>Affichage des commandes en souffrance par fournisseur

En affichant les reliquats par fournisseur, vous pouvez suivre les livraisons manquantes et afficher les dates de livraison prévues. Cette vérification vous permet également de définir des priorités lorsque des commandes en souffrance arrivent en provenance de fournisseurs et que les commandes client doivent être enlevées pour livraison.

### <a name="invoices"></a>Factures

Vous pouvez créer trois types de factures lors du processus de vente :

-   Facture client
-   Facture financière
-   Facture pro forma

#### <a name="customer-invoice"></a>Facture client

Une facture client est une facture remise par une société à un client dans le cadre d'une vente. Vous pouvez créer ce type de facture client sur la base d'une commande client, laquelle comporte un en-tête et une ou plusieurs lignes pour les articles ou les services. La facture client termine le cycle de la commande client, du bon de livraison et de la facture client.  

Vous pouvez valider et imprimer une facture client unique, basée sur une commande client ou le bon de livraison et la date. Vous pouvez aussi valider et imprimer plusieurs factures client ensemble sur la base des bons de livraison et des dates. Lorsque vous validez une facture client unique à l'aide de la commande client, la quantité **Solde de la facture** pour chaque article est mise à jour avec le total des quantités facturées pour la commande client sélectionnée.  

Si les quantités **Solde de la facture** et **Livrer quantité restante** pour tous les articles de la commande client ont la valeur 0 (zéro), le statut de la commande client passe à **Facturé**. Si la quantité de l'un des champs n'a pas la valeur zéro, le statut de la commande client reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci. Si vous souhaitez valider et imprimer une ou plusieurs factures client basées sur les bons de livraison, vous devez avoir déjà validé au moins un bon de livraison pour chaque commande client. La facture client est basée sur les bons de livraison et reflète les quantités qui sont répertoriées.  

Vous pouvez créer une facture client basée sur les articles de ligne du bon de livraison qui ont été expédiés jusqu'à présent, même si tous les articles pour une commande client particulière n'ont pas encore été expédiés. Vous pouvez procéder de la sorte si, par exemple, votre entité juridique émet une facture par client et par mois qui couvre toutes les expéditions que vous avez effectuées au cours de ce mois. Chaque bon de livraison représente l'expédition partielle ou complète des articles sur la commande client.  

Lorsque vous validez la facture, la quantité **Solde de la facture** pour chaque article est mise à jour avec le total des quantités expédiées pour les bons de livraison sélectionnés. Si les quantités **Solde de la facture** et **Livrer quantité restante** pour tous les articles de la commande client ont la valeur 0 (zéro), le statut de la commande client passe à **Facturé**. Si la quantité n'a pas la valeur zéro, le statut de la commande client reste inchangé et des factures supplémentaires peuvent être entrées pour celle-ci. Les mouvements de stock sont mis à jour avec le numéro de facture et le statut sur la ligne de la commande client devient **Facturé**.

#### <a name="free-text-invoice"></a>Facture financière

Une facture financière est une facture qui n'est pas liée à une commande client. Elle contient des lignes de commande comprenant des comptes généraux, des descriptions en texte libre ainsi qu'une valeur de vente. Vous ne pouvez pas entrer un numéro d’article sur ce type de facture, et vous devez entrer les informations de taxe appropriées. Un compte principal pour la vente est indiqué sur chaque ligne de facture. Le solde du client est validé dans le compte collectif en fonction du profil de validation utilisé pour la facture financière.

#### <a name="pro-forma-invoice"></a>Facture pro forma

Une facture pro forma est une facture préparée comme une estimation du montant de facture réel avant la validation de la facture. Vous pouvez imprimer une facture pro forma pour une facture client ou une facture financière.




