---
title: Opérations du point de vente (PDV), en ligne et hors connexion
description: Cette rubrique fournit les détails relatifs aux opérations du PDV dans Microsoft Dynamics 365 for Retail. Elle spécifie où dans l'application les opérations peuvent être invoquées, et si elles sont disponibles dans le mode hors ligne.
author: jblucher
manager: AnnBe
ms.date: 10/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 85708c7197a71e6ad9b814e2e63d62122c8890f6
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "842720"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Opérations du point de vente (PDV), en ligne et hors connexion

[!include [banner](includes/banner.md)]

La plupart des actions que l'utilisateur exécute dans le point de vente (PDV) sont considérées comme des opérations. Les opérations sont configurées et gérées dans les services administratifs de Microsoft Dynamics 365 for Retail. De nombreuses opérations peuvent être ajoutées aux boutons du groupe de boutons du PDV. Les utilisateurs peuvent ensuite sélectionner les boutons pour appeler les opérations et effectuer leur fonction. D'autres opérations font partie de l'application de PDV principale, et sont appelées par les boutons à l'écran ou dans le cadre d'autres workflows ou processus.

Le tableau suivant fournit les détails relatifs aux opérations disponibles dans Retail Modern POS et Cloud POS pour Dynamics 365 for Retail. Le tableau spécifie où dans l'application les opérations peuvent être invoquées, et si elles sont disponibles lorsque le PDV est dans le mode hors ligne.

Certains opérations ne sont actuellement pas disponibles dans Retail Modern POS ou Cloud POS pour Dynamics 365 for Retail. Certaines de ces opérations sont des opérations spécifiques aux paramètres régionaux qui nécessitent des extensions et une configuration supplémentaires. D'autres sont des fonctions de Microsoft Dynamics AX 2012 qui ne sont actuellement pas prises en charge.

Les colonnes suivantes indiquent où les opérations peuvent être invoquées :

- **Groupe de boutons** – L'opération peut être affectée aux boutons dans les groupes de boutons du PDV, qui font partie d'une mise en page de l'écran du PDV.
- **Écran de transaction** – L'opération peut être invoquée à partir des groupes de boutons du PDV configurés sur l'écran de transaction du PDV.
- **Écran de bienvenue** – L'opération peut être invoquée à partir des groupes de boutons du PDV configurés sur l'écran de bienvenue.

> [!NOTE]
> Les opérations répertoriées ci-dessous s'appliquent à la version la plus récente de Dynamics 365 for Retail. Certaines opérations peuvent avoir été modifiées ou ne pas être disponibles dans les versions précédentes.

| ID | Opération | Description | Groupe de boutons | Écran de transaction | Écran de bienvenue | Disponible hors connexion | Spécifique aux paramètres locaux |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Activer le périphérique | Permet d'activer le périphérique actuel en permettant à un utilisateur authentifié de fournir des informations de connexion et affectez un ID de périphérique et de caisse enregistreuse. | N° | N° | N° | N° | N° |
| 134 | Ajouter une affiliation | Permet d'ajouter une adresse d'expédition à une transaction. Sélectionnez l'affiliation sur la page **Propriétés du bouton**. | Oui | Oui | N° | Oui | N° |
| 135 | Ajouter une affiliation à partir de la liste | Permet d'ajouter une affiliation à une transaction en la sélectionnant dans une liste. | Oui | Oui | Oui | Oui | N° |
| 137 | Ajouter une affiliation à un client | Ajouter une affiliation à un client sur la page **Détails du client**. | N° | N° | N° | Oui | N° |
| 138 | Supprimer une affiliation d'un client | Supprimer une affiliation sur la page **Détails du client**. | N° | N° | N° | Oui | N° |
| 643 | Ajouter un code coupon | Permet d'ajouter un coupon en entrant son code dans le PDV. | Oui | Oui | N° | Oui | N° |
| 117 | Ajouter une carte de fidélité | Permet d'inviter l'utilisateur à entrer un numéro de carte de fidélité qui sera ajouté à la transaction actuelle. | Oui | Oui | N° | Oui | N° |
| 136 | Ajouter un numéro de série | Cette opération permet à l'utilisateur de spécifier un numéro de série pour le produit sélectionné actuellement. | Oui | Oui | N° | Oui | N° |
| 1214 | Ajouter une adresse d'expédition | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 519 | Ajouter à la carte cadeau | Permet d'ajouter de l'argent à la carte cadeau spécifiée. | Oui | Oui | N° | N° | N° |
| 6 000 | Autoriser l'omission de l'enregistrement fiscal | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |
| 1 212 | Remise en banque | Permet d'enregistrer la somme d'argent envoyée à la banque ainsi que d'autres informations, telles que le numéro de sac de dépôt bancaire. | Oui | Oui | Oui | Oui | N° |
| 923 | Vérification des totaux bancaires | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |
| 915 | Opération vide | Cette opération représente un bouton personnalisable qui peut être modifié par un développeur logiciel pour réaliser n'importe quelle opération nécessaire à l'entreprise. | Oui | Oui | Oui | Oui | N° |
| 1 053 | Clôturer l'équipe de travail en aveugle | Permet de définir l'équipe actuelle à clôturer en aveugle, et de déconnecter l'utilisateur. Une équipe clôturée en aveugle est clôturée pour les transactions supplémentaires mais est toujours ouvertes pour les opérations de caisse enregistreuse, telles que le vidage et le comptage de la caisse. | Oui | Oui | Oui | N° | N° |
| 310 | Calculer le total | Lorsque le calcul de la remise est retardé, cette opération initie le calcul de la transaction actuelle. | Oui | Oui | N° | Oui | N° |
| 642 | Exécuter tous les produits | Permet de définir le mode de livraison de toutes les lignes sur **Exécuter**. | Oui | Oui | N° | Oui\* | N° |
| 641 | Exécuter les produits sélectionnés | Permet de définir le mode de livraison des lignes sélectionnées sur **Exécuter**. | Oui | Oui | N° | Oui\* | N° |
| 1 215 | Modifier le mot de passe | Cette opération permet à l'utilisateur du PDV de modifier son mot de passe. | Oui | Oui | Oui | N° | N° |
| 123 | Modifier l'unité de mesure | Permet de modifier l'unité de mesure de la ligne sélectionnée. | Oui | Oui | N° | Oui | N° |
| 639 | Effacer le représentant par défaut sur la transaction | Permet de supprimer le groupe de ventes de commission (commercial) de la transaction. | Oui | Oui | N° | Oui | N° |
| 106 | Effacer la quantité | Permet de réinitialiser la quantité de la ligne sélectionnée actuellement sur **1**. | Oui | Oui | N° | Oui | N° |
| 640 | Effacer le représentant sur la ligne | Permet de supprimer le groupe de ventes de commission (commercial) de la ligne sélectionnée actuellement. | Oui | Oui | N° | Oui | N° |
| 121 | Effacer le vendeur | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 1 055 | Clôturer l'équipe de travail | Permet de fermer l'équipe actuelle, d'imprimer un Z de caisse, et de déconnecter l'utilisateur du système. | Oui | Oui | Oui | N° | N° |
| 925 | Copier le chèque bancaire | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |
| 620 | Créer la commande client | Permet de convertir la transaction de PDV en commande client. | Oui | Oui | N° | Oui\* | N° |
| 621 | Créer un devis | Permet de convertir la transaction de PDV en devis de vente. | Oui | Oui | N° | Oui\* | N° |
| 636 | Créer une transaction de vente au détail | Cette opération permet à l'utilisateur de créer une transaction de vente standard lorsque le comportement par défaut du PDV consiste à créer des commandes client. | Oui | Oui | N° | Oui | N° |
| 600 | Client | Permet d'ajouter le client spécifié à la transaction. | N° | N° | N° | Oui | N° |
| 1 100 | Dépôt sur compte client | Permet d'effectuer un paiement sur un compte client. | Oui | Oui | Oui | Oui | Oui |
| 612 | Ajout d'un client | Cette opération permet à l'utilisateur de créer un enregistrement client. | Oui | Oui | Oui | Oui† | N° |
| 603 | Effacement du client | Permet de supprimer le client de la transaction actuelle. | Oui | Oui | N° | Oui | N° |
| 602 | Recherche du client | Cette opération permet à l'utilisateur de rechercher un enregistrement client en accédant à la page de recherche client dans le PDV. | Oui | Oui | Oui | Oui | N° |
| 609 | Transactions client | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 917 | Statut de connexion de la base de données | Cette opération permet à l'utilisateur d'afficher les paramètres de connexion actuels, et de basculer entre les modes en ligne et hors ligne. | Oui | Oui | Oui | Oui | N° |
| 1 200 | Déclarer le montant de départ | Permet de déclarer le montant présent dans le tiroir-caisse en début de journée ou d'équipe de travail. | Oui | Oui | Oui | Oui | N° |
| 132 | Remplacement de dépôt | Permet de remplacer le dépôt par défaut dans les commandes client. | Oui | Oui | N° | Oui\* | N° |
| 913 | Désactivation du mode de configuration | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 912 | Activation du mode de configuration | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 1 217 | Démonter les kits | Permet de démonter un kit en ses produits composants. | Oui | Oui | Oui | Oui | N° |
| 624 | Afficher les montants à rembourser | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |
| 513 | Afficher le total | Permet d'afficher le solde des transactions sur l'écran du client. | Oui | Oui | Oui | Oui | N° |
| 623 | Editer le client | Permet de modifier les détails du client actuel. | Oui | Oui | N° | N° | N° |
| 614 | Modifier la commande client | Permet de rappeler la commande sélectionnée afin qu'elle puisse être modifiée dans le PDV. | N° | N° | N° | N° | N° |
| 615 | Modifier le devis | Permet de rappeler le devis sélectionné afin qu'il puisse être modifié dans le PDV. | N° | N° | N° | N° | N° |
| 518 | Comptes de dépenses | Permet d'enregistrer la somme d'argent retirée du tiroir-caisse pour des dépenses occasionnelles. | Oui | Oui | Oui | Oui | N° |
| 919 | Connexion étendue | Permet d'affecter ou de supprimer l'autorisation de se connecter via la lecture d'un code-barres ou le passage d'une carte. | Oui | Oui | Oui | Oui | Non |
| 1201 | Entrée de fond de caisse | Cette opération permet à l'utilisateur d'ajouter de l'argent supplémentaire pour le tiroir-caisse ou à l'équipe actuels. | Oui | Oui | Oui | Oui | N° |
| 1 218 | Forcer le déverrouillage du périphérique | Le système utilise cette opération en interne pour déverrouiller les périphériques du PDV. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 520 | Solde de la carte cadeau | Permet d'afficher le solde d'une carte cadeau. | Oui | Oui | N° | N° | N° |
| 708 | Désactiver le périphérique | Permet de désactiver le périphérique actuel, afin qu'il ne puisse pas être utilisé comme caisse enregistreuse de PDV. | N° | N° | N° | N° | N° |
| 517 | Comptes de revenus | Permet d'enregistrer la somme d'argent placée dans le tiroir-caisse pour un autre motif qu'une vente. | Oui | Oui | Oui | Oui | N° |
| 801 | Recherche de stock | Permet de rechercher les quantités disponibles, en commande et disponibles à la vente (DAV) pour le magasin actuel et d'autres lieux disponibles. | Oui | Oui | Oui | N° | N° |
| 122 | Commentaire sur la facture | Cette opération permet à l'utilisateur d'entrer un commentaire sur la transaction actuelle. | Oui | Oui | N° | Oui | N° |
| 511 | Émettre un avoir | Permet de publier un avoir pour fournir un N° document au lieu d'un remboursement. | Oui | Oui | N° | N° | N° |
| 512 | Émettre une carte cadeau | Permet d'émettre une nouvelle carte cadeau pour le montant spécifié. | Oui | Oui | N° | N° | N° |
| 625 | Émettre une carte de fidélité | Permet d'émettre une carte de fidélité à un client afin qu'il puisse participer au programme de fidélité du magasin. | Oui | Oui | Oui | N° | N° |
| 300 | Montant de la remise ligne | Permet d'entrer un montant de la remise pour une ligne de la transaction. Cette opération s'applique uniquement aux articles qui peuvent bénéficier d'une remise, dans le respect des limites spécifiées. | Oui | Oui | N° | Oui | N° |
| 301 | Pourcentage de la remise ligne | Permet d'entrer un pourcentage de rermise pour une ligne de la transaction. Cette opération s'applique uniquement aux articles qui peuvent bénéficier d'une remise, dans le respect des limites spécifiées. | Oui | Oui | N° | Oui | N° |
| 703 | Verrouiller la caisse enregistreuse | Permet de verrouiller le registre actuel, afin qu'il ne puisse pas être utilisé, mais sans déconnecter l'utilisateur actuel. | N° | N° | N° | Oui | N° |
| 701 | Déconnexion | Permet de déconnecter l'utilisateur actuel du registre. | Oui | Oui | Oui | Oui | N° |
| 521 | Solde de points de la carte de fidélité | Permet d'afficher le solde de points de la carte de fidélité spécifiée. | Oui | Oui | N° | N° | N° |
| 918 | Gérer les équipes | Permet d'afficher une liste d'équipes actives, interrompues et clôturées en aveugle. | Oui | Oui | Oui | N° | N° |
| 914 | Réduire la fenêtre du PDV | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 1 000 | Ouvrir tiroir-caisse | Permet d'exécuter une opération sans vente, puis d'ouvrir le tiroir-caisse actuellement sélectionné. | Oui | Oui | Oui | Oui | N° |
| 928 | Exécution de l'ordre | Cette opération permet aux utilisateurs de prélever, emballer, expédier ou rappeler des commandes pour un retrait en magasin. | Oui | Oui | Oui | N° | N° |
| 129 | Remplacer la taxe sur le produit de la ligne | Permet de remplacer la taxe spécifiée par une autre sur la ligne sélectionnée. | Oui | Oui | N° | Oui | N° |
| 130 | Remplacer la taxe sur le produit de la ligne de la liste | Permet de remplacer la taxe sur la ligne sélectionnée par la taxe sélectionnée dans une liste par l'utilisateur. | Oui | Oui | N° | Oui | N° |
| 127 | Remplacer la taxe sur les transactions | Permet de remplacer la taxe spécifiée sur la transaction par une autre. | Oui | Oui | N° | Oui | N° |
| 128 | Remplacer la taxe sur les transactions de la liste | Permet de remplacer la taxe sur la transaction et d'utiliser la taxe sélectionnée dans une liste par l'utilisateur. | Oui | Oui | N° | Oui | N° |
| 131 | Bon de livraison | Permet de créer le bon de livraison pour la commande sélectionnée. | N° | N° | N° | N° | N° |
| 710 | Jumeler une station matérielle | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 201 | Payer par carte | Permet d'accepter une carte pour un paiement par carte de crédit ou de débit. | Oui | Oui | N° | Oui | N° |
| 200 | Payer en disponibilités | Permet d'accepter un paiement en disponibilités. | Oui | Oui | N° | Oui | N° |
| 206 | Payer rapidement en disponibilités | Permet d'exécuter la transaction en une étape, puis d'accepter le montant dû en espèces (appoint). | Oui | Oui | N° | Oui | N° |
| 204 | Payer par chèque | Permet d'accepter un chèque comme paiement. | Oui | Oui | N° | Oui | N° |
| 213 | Payer par avoir | Permet d'accepter un avoir (N° document) émis par le magasin. | Oui | Oui | N° | N° | N° |
| 203 | Payer en devises | Permet d'accepter un paiement dans différentes devises. | Oui | Oui | N° | Oui | N° |
| 202 | Payer sur le compte client | Permet de facturer la transaction sur le compte client. Ce mode de paiement n'est pas valide pour des dépôts de commande client. | Oui | Oui | N° | N° | N° |
| 214 | Payer par carte cadeau | Permet d'accepter une carte cadeau émise par le magasin. | Oui | Oui | N° | N° | N° |
| 207 | Payer par carte de fidélité | Permet d'accepter une carte de fidélité pour le paiement, et d'échanger les points contre des produits qualifiés. | Oui | Oui | N° | N° | N° |
| 634 | Historique des paiements | Permet d'afficher l'historique de paiement du client pour la commande client actuelle. | Oui | Oui | N° | N° | N° |
| 803 | Prélèvement et réception | Permet d'ouvrir la page **Prélèvement et réception**, sur laquelle vous pouvez sélectionner des ordres de prélèvement ou de réception dans le magasin. | Oui | Oui | Oui | N° | N° |
| 632 | Prélever tous les produits | Permet de définir la méthode d'exécution sur **Prélèvement en magasin** pour toutes les lignes. | Oui | Oui | N° | Oui\* | N° |
| 631 | Prélever les produits sélectionnés | Permet de définir la méthode d'exécution sur **Prélèvement en magasin** pour les lignes sélectionnées. | Oui | Oui | N° | Oui\* | N° |
| 400 | Menu contextuel | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 101 | Vérification de prix | Cette opération permet à l'utilisateur de rechercher le prix d'un produit spécifié. | Oui | Oui | Oui | Oui | N° |
| 104 | Prix manuel | Permet de remplacer le prix d'un produit si le paramétrage le permet. | Oui | Oui | N° | Oui | N° |
| 1 058 | Imprimer le X de caisse fiscal | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |
| 1 059 | Imprimer le Z de caisse fiscal | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |
| 927 | Imprimer une étiquette d'article | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 926 | Imprimer une étiquette de rayon | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 1 056 | Imprimer X | Permet d'imprimer un X de caisse pour l'équipe actuelle. | Oui | Oui | Oui | N° | N° |
| 103 | Commentaire produit | Permet d'ajouter un commentaire à la ligne sélectionnée dans la transaction. | Oui | Oui | N° | Oui | N° |
| 100 | Vente de produits | Permet d'ajouter un produit spécifié à la transaction. | Oui | Oui | Oui | Oui | N° |
| 108 | Recherche du produit | Cette opération permet à l'utilisateur de rechercher un produit en accédant à la page de recherche de produits dans le PDV. | Oui | Oui | Oui | Oui | N° |
| 633 | Date d'expiration du devis | Cette opération permet à l'utilisateur d'afficher ou de modifier la date d'expiration sur un devis de vente. | Oui | Oui | N° | Oui\* | N° |
| 627 | Recalculer | Permet de recalculer toutes les lignes et taxes de commande client, selon la configuration actuelle. | Oui | Oui | N° | Oui\* | N° |
| 515 | Rappeler la commande | Cette opération permet à l'utilisateur de rechercher et de rappeler des commandes client et des devis de vente. | Oui | Oui | Oui | N° | N° |
| 504 | Rappeler une transaction | Cette opération permet à l'utilisateur de rappeler une transaction préalablement interrompue dans le magasin actuel. | Oui | Oui | N° | Oui‡ | N° |
| 305 | Rembourser les points de fidélité | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |
| 635 | Rembourser les frais d'expédition | Cette opération permet à l'utilisateur de rembourser les frais d'expédition d'une commande annulée. | N° | N° | N° | N° | N° |
| 644 | Supprimer le code coupon | Permet d'inviter l'utilisateur à supprimer des coupons en les sélectionnant dans une liste de coupons actuellement associés à la transaction. | Oui | Oui | N° | Oui | N° |
| 1 057 | Réimprimer Z | Permet de réimprimer le Z de caisse pour l'équipe précédente ou une équipe sélectionnée. | Oui | Oui | Oui | N° | N° |
| 1 216 | Entrer un nouveau mot de passe | Cette opération permet à un utilisateur ayant une autorisation de réinitialisation de mot de passe de réinitialiser le mot de passe d'un autre employé à l'aide d'un mot de passe temporaire. | Oui | Oui | Oui | N° | N° |
| 1219 | Ouvrir une URL dans PDV | Cette opération permet à un utilisateur d'ouvrir une URL configurée par un administrateur dans le PDV. | Oui | Oui | Oui | Oui | N° | 
| 109 | Retourner le produit | Permet d'effectuer un retour de produits individuels. Le prochain produit scanné est affiché comme étant un produit retourné avec une quantité et un prix négatifs. | Oui | Oui | N° | Oui | N° |
| 114 | Transaction de retour | Permet de rappeler une transaction précédente par son numéro de ticket de caisse pour retourner certains ou tous les produits. | Oui | Oui | Oui | Oui§ | N° |
| 1 211 | Mise en coffre-fort | Permet de déplacer l'argent de la caisse vers un coffre-fort. | Oui | Oui | Oui | Oui | N° |
| 516 | Facture client | Cette opération permet au client d'effectuer des paiements pour la facture client sélectionnée. | Oui | Oui | N° | N° | N° |
| 502 | Commercial | Cette opération permet à l'utilisateur de définir la valeur **Acheteur** sur une commande client pour des commandes client dans le PDV. | Oui | Oui | N° | Oui\* | N° |
| 2 000 | Gestion du programme | Cette opération permet aux utilisateurs de créer, de modifier ou d'afficher les plannings des employés. | Oui | Oui | Oui | N° | N° |
| 2 001 | Demandes de programme | Cette opération permet à l'utilisateur de demander des congés, de changer d'équipe ou d'offrir des équipes à d'autres employés. | Oui | Oui | Oui | N° | N° |
| 622 | Rechercher des commandes | Cette opération permet aux utilisateurs de préconfigurer des boutons du PDV pour effectuer des recherches par article, client ou catégorie. | Oui | Oui | Oui | Oui | N° |
| 1 213 | Rechercher l'adresse d'expédition | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 709 | Sélectionner une station matérielle | Cette opération permet à l'utilisateur de sélectionner une station matérielle dans une liste de stations matérielles disponibles. | Oui | Oui | Oui | Oui | N° |
| 637 | Définir le représentant par défaut sur la transaction | Cette opération permet à l'utilisateur de sélectionner l'un des groupes de ventes de commission admissibles (commerciaux) comme commercial par défaut pour des lignes ajoutées ultérieurement. | Oui | Oui | N° | Oui | N° |
| 105 | Définir la quantité | Permet de modifier la quantité d'une ligne de la transaction. | Oui | Oui | N° | Oui | N° |
| 638 | Définir le représentant sur la ligne | Cette opération permet à l'utilisateur de sélectionner l'un des groupes de ventes de commission admissibles (commerciaux) pour la ligne sélectionnée actuellement. | Oui | Oui | N° | Oui | N° |
| 630 | Expédier tous les produits | Permet de définir le mode d'exécution **Expédition** pour toutes les lignes. | Oui | Oui | N° | Oui\* | N° |
| 629 | Expédier les produits sélectionnés | Permet de définir le mode d'exécution sur **Expédition** pour les lignes sélectionnées. | Oui | Oui | N° | Oui\* | N° |
| 115 | Afficher le journal | Permet d'afficher le journal du magasin. Vous pouvez afficher les transactions, imprimer les reçus et les reçus de cadeaux, et rappeler les retours. | Oui | Oui | Oui | Oui\*\* | N° |
| 802 | Inventaire | Cette opération permet à l'utilisateur de créer ou de modifier les journaux d'inventaire pour le stock physique ou les inventaires tournants. | Oui | Oui | Oui | N° | N° |
| 401 | Sous-menu | Cette opération dirige l'utilisateur vers un autre groupe de boutons lié. | Oui | Oui | Oui | Oui | N° |
| 1 054 | Suspendre l'équipe de travail | Permet d'interrompre l'équipe actuelle, afin qu'une nouvelle équipe ou une autre équipe puisse être activée dans le registre actuel. | Oui | Oui | Oui | N° | N° |
| 503 | Interrompre la transaction | Permet d'interrompre la transaction de vente actuelle, afin de pouvoir la rappeler plus tard dans le magasin. | Oui | Oui | N° | Oui‡ | N° |
| 1004 | Enregistreur de tâches | Permet d'ouvrir l'enregistreur de tâches pour enregistrer les étapes procédurales dans le PDV. | N° | N° | N° | Oui | N° |
| 1 052 | Comptage de caisse | Cette opération permet à l'utilisateur de spécifier la somme d'argent dans le tiroir-caisse pour chaque mode de paiement compté. | Oui | Oui | Oui | Oui | N° |
| 1 210 | Vider la caisse | Cette opération permet à l'utilisateur de supprimer de l'argent supplémentaire du tiroir-caisse ou de l'équipe actuelle. | Oui | Oui | Oui | Oui | N° |
| 920 | Horloge de pointage | Cette opération permet aux utilisateurs de pointer à l'arrivée/la sortie des équipes et des pauses. | Oui | Oui | Oui | N° | N° |
| 302 | Montant de remise totale | Permet d'entrer un montant de remise pour la transaction. Cette opération s'applique uniquement aux articles qui peuvent bénéficier d'une remise, dans le respect des limites spécifiées. | Oui | Oui | N° | Oui | N° |
| 303 | Pourcentage de remise totale | Permet d'entrer un pourcentage de remise pour la transaction. Cette opération s'applique uniquement aux articles qui peuvent bénéficier d'une remise, dans le respect des limites spécifiées. | Oui | Oui | N° | Oui | N° |
| 501 | Commentaire de transaction | Permet d'ajouter un commentaire à la transaction actuelle. | Oui | Oui | N° | Oui | N° |
| 922 | Afficher les détails du produit | Permet d'ouvrir la page de détails du produit pour la ligne sélectionnée actuellement. | Oui | Oui | N° | Oui | N° |
| 1003 | Afficher les rapports | Permet d'afficher les états qui ont été configurés pour l'utilisateur actuel. | Oui | Oui | Oui | N° | N° |
| 921 | Afficher les entrées de l'horloge de pointage | Permet d'afficher les entrées de l'horloge de pointage pour tous les travailleurs du magasin. | Oui | Oui | Oui | N° | N° |
| 211 | Annuler le paiement | Permet d'annuler la ligne de paiement sélectionnée actuellement de la transaction. | Oui | Oui | N° | Oui | N° |
| 102 | Annuler le produit | Permet d'annuler la ligne sélectionnée actuellement de la transaction. | Oui | Oui | N° | Oui | N° |
| 500 | Annuler la transaction | Permet d'annuler la transaction actuelle. | Oui | Oui | N° | Oui | N° |
| 916 | Windows Workflow Foundation | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | N° |
| 924 | X de caisse pour les cartes bancaires | Cette opération n'est pas prise en charge. | Non applicable | Non applicable | Non applicable | Non applicable | Oui |

\* L'opération est disponible dans le mode hors connexion uniquement lorsqu'une commande client ou un devis de vente est créé, et uniquement si la création hors connexion des commandes client et des devis de vente est configurée dans le profil de fonctionnalité du PDV. L'opération ne peut pas être effectuée lorsque des commandes sont créées à l'aide du service en temps réel, ou lorsque des commandes sont rappelées ou modifiés.

† L'opération peut être effectué dans le mode hors connexion uniquement lorsque le PDV est configuré pour autoriser la création hors connexion de clients dans le profil de fonctionnalité du PDV.

‡ Lorsque le PDV est hors connexion, les transactions interrompues peuvent être rappelées uniquement dans la base de données hors connexion du registre actuel. Les utilisateurs ne peuvent pas interrompre et rappeler des transactions sur plusieurs caisses enregistreuses.

§ Lorsque le PDV est hors connexion, seules les transactions dans la base de données hors connexion peuvent être rappelées pour un retour.

\*\* Lorsque le PDV est hors connexion, seules les transactions dans la base de données de canal hors connexion sont affichées dans le journal.
