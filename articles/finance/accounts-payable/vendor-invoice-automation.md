---
title: Automatisation des factures fournisseur
description: Cette rubrique explique les fonctionnalités disponibles pour l'automatisation de bout en bout des factures fournisseur, y compris les factures contenant des pièces jointes.
author: abruer
manager: AnnBe
ms.date: 05/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoiceHeaderStagingListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4560d7b61fa8f014f9a1185da087df8b1c8e61ba
ms.sourcegitcommit: b7af921189048d9f2eb4d3fd57c704c742bc96e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2020
ms.locfileid: "3396007"
---
# <a name="vendor-invoice-automation"></a>Automatisation des factures fournisseur

[!include [banner](../includes/banner.md)]

Cette rubrique explique les fonctionnalités disponibles pour l'automatisation de bout en bout des factures fournisseur, y compris les factures contenant des pièces jointes.

Les organisations qui souhaitent simplifier leurs processus de compatibilité fournisseur identifient souvent le traitement des factures comme l'un des principaux domaines de processus dont l'efficacité doit être améliorée. Dans de nombreux cas, ces organisations confient le traitement des factures papier à un fournisseur de services de reconnaissance optique des caractères (OCR) tiers. Elles reçoivent ensuite les métadonnées de facture dans un format lisible par une machine avec une image numérisée de chaque facture. Pour faciliter l'automatisation, une solution de « dernier kilomètre » est créée pour activer la consommation de ces artefacts dans le système de facturation. L'automatisation de ce « dernier kilomètre » est maintenant activée, via une solution d'automatisation des factures.

## <a name="solution-context"></a>Contexte de la solution

La solution d'automatisation des factures active une interface standard qui peut accepter des métadonnées de facture pour l'en-tête et les lignes de facture, ainsi que des pièces jointes applicables à la facture. Tout système externe capable de générer des artefacts conformes à cette interface pourra envoyer le flux pour le traitement automatique des factures et des pièces jointes.

L'illustration suivante présente un exemple de scénario d'intégration dans lequel Contoso a fait appel à un fournisseur de services OCR pour le traitement des factures fournisseur. Les fournisseurs de Contoso envoient les factures au fournisseur de services par courrier électronique. Par le biais du traitement OCR, le fournisseur de services génère des métadonnées de facture (en-tête et/ou lignes) et une image numérisée de la facture. Une couche d'intégration transforme ensuite ces artefacts afin qu'ils puissent être consommés.

![Exemple de scénario d'intégration](media/vendor_invoice_automation_01.png)

Plusieurs variations du scénario précédent sont possibles si l'intégration des factures est requise. La migration des données est un autre cas d'utilisation où cette interface peut être utilisée pour créer des factures et des pièces jointes.

### <a name="solution-components"></a>Composants de la solution

L'empreinte de la solution comprend les composants suivants :

+ Entités de données pour l'en-tête de facture, les lignes de facture et les pièces jointes de facture
+ Traitement des exceptions pour les factures
+ Visionneuse de pièce jointe côte à côte dans les factures

Le reste de cette rubrique fournit des descriptions détaillées des composants de la solution.

## <a name="data-entities"></a>Entités de données

Un package de données est l'unité de travail qui doit être envoyée, afin que les en-têtes de facture, les lignes de facture et les pièces jointes de facture puissent être créés. Les entités de données suivantes sont utilisées pour les artefacts qui composent le package de données :

+ En-tête de la facture fournisseur
+ Ligne de facture fournisseur
+ Ajout de document à la facture fournisseur

Les pièces jointes des documents de facture fournisseur sont une nouvelle entité de données introduite dans le cadre de cette fonctionnalité. L'entité En-tête de facture fournisseur a été modifiée pour prendre en charge les pièces jointes. L'entité Ligne de facture fournisseur n'a pas été modifiée pour cette fonctionnalité.

Pour des informations détaillées sur les packages de données, consultez [Vue d'ensemble de la gestion des données](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md). Pour plus d'informations sur la création de packages de données à l'aide de l'espace de travail de gestion des données, consultez [Traiter et consommer des packages de données dans la solution d'applications Dynamics 365 Finance and Operations](../../fin-ops-core/dev-itpro/lcs-solutions/process-data-packages-lcs-solutions.md).

Pour générer rapidement des données de test incluant des factures et des pièces jointes, procédez comme suit :

1. Connectez-vous à votre instance.
1. Accédez à **Comptabilité fournisseur** > **Factures** > **Factures fournisseur en cours**.
1. Créez des factures contenant des lignes et des pièces jointes.

    > [!NOTE]
    > Les pièces jointes doivent être des pièces jointes d'en-tête. Pour le moment, l'entité Pièces jointes des documents de facture fournisseur ne prend pas en charge les pièces jointes de ligne.

1. Ouvrez l'espace de travail **Gestion des données**.
1. Créez une tâche d'exportation contenant les entités En-tête de facture fournisseur, Ligne de facture fournisseur et Pièces jointes des documents de facture fournisseur.
1. Exportez les données.
1. Téléchargez les données exportées en tant que package. Vous pouvez à présent utiliser le package pour importer des données dans les instances cibles à des fins de test.

### <a name="determining-the-legal-entity-for-an-invoice"></a>Détermination de l'entité juridique pour une facture

Les factures importées via des packages de données peuvent être associées à l'entité juridique d'appartenance de deux manières :

+ La tâche d'importation qui traite la facture l'importe dans la même société que celle dans laquelle la tâche a été planifiée dans l'espace de travail **Gestion des données**. En d'autres termes, la société de la tâche détermine la société à laquelle la facture appartient.
+ Lorsque le package de données contenant des factures est envoyé dans Finance, l'appelant (c'est-à-dire, l'application d'intégration qui s'exécute en dehors de Finance) peut explicitement mentionner l'ID de société dans la requête HTTP. Dans ce cas, le contexte de société dans lequel la tâche de traitement s'exécute dans Finance est remplacé, et les factures sont importées dans la société transmise via la requête HTTP.

> [!NOTE]
> Ce comportement est le comportement de gestion des données standard. Il est expliqué ici, dans le contexte des factures, par souci d'exhaustivité.

## <a name="exception-processing"></a>Traitement des exceptions

Dans les scénarios où les factures fournisseur sont envoyées dans Finance and Operations par le biais de l'intégration, un membre de l'équipe de la comptabilité fournisseur doit pouvoir traiter facilement les exceptions ou les factures ayant échoué, et créer des factures en attente à partir des factures ayant échoué. Ce traitement des exceptions pour les factures fournisseur fait désormais partie de Finance and Operations.

### <a name="exceptions-list-page"></a>Page de liste des exceptions

La nouvelle page de liste pour les exceptions de facture est disponible sous **Comptabilité fournisseur** > **Factures** > **Échecs d'importation** > **Factures fournisseur qui n'ont pas été importées**. Cette page affiche tous les enregistrements d'en-tête de facture fournisseur à partir de la table intermédiaire de l'entité de données En-tête de facture fournisseur. Notez que vous pouvez afficher les mêmes enregistrements à partir de l'espace de travail **Gestion des données**, où vous pouvez également exécuter les mêmes actions que celles fournies dans la fonction de gestion des exceptions. Toutefois, l'interface utilisateur fournie par la fonction de gestion des exceptions est optimisée pour un utilisateur fonctionnel.

![Page de liste des exceptions](media/vendor_invoice_automation_02.png)

Cette page de liste contient les champs suivants qui sont disponibles via le flux :

+ **Société** – Société à laquelle la facture appartient.
+ **Message d'erreur** – Message d'erreur généré par l'infrastructure de gestion des données pour expliquer la raison pour laquelle la facture n'a pas pu être créée
+ **Numéro** – Numéro de la facture.
+ **Compte de facturation**
+ **Nom** – Nom du fournisseur
+ **Compte fournisseur**
+ **Commande fournisseur** – Numéro de la commande fournisseur pour la facture
+ **Date de validation**
+ **Date de facture**
+ **Description de la facture**
+ **Devise**
+ **Journal**
+ **Référence de ligne** – Identificateur provenant du système externe

    > [!NOTE]
    > La référence de ligne n'est pas l'ID de facture.

Cette page de liste a également un volet d'aperçu que vous pouvez utiliser de plusieurs manières :

+ Affichez l'ensemble du message d'erreur, afin qu'il ne soit pas nécessaire de développer la colonne **Message d'erreur** de la grille.
+ Affichez l'ensemble de la liste des pièces jointes pour la facture, si des documents sont joints à la facture.

La page de liste prend en charge les actions suivantes :

+ **Modifier** – Ouvrez l'enregistrement d'exception en mode Édition, afin de résoudre les problèmes.
+ **Options** – Accédez aux options standard disponibles dans les pages de liste. Vous pouvez utiliser l'option **Ajouter à l'espace de travail** pour épingler la page de liste des exceptions à votre espace de travail en tant que liste ou vignette.

### <a name="exception-details-page"></a>Page des détails de l'exception

Lorsque vous activez le mode Édition, la page des détails de l'exception pour la facture posant problème s'affiche. Si des documents sont joints, la facture et les pièces jointes par défaut s'affichent côte à côte sur la page des détails de l'exception.

![Page des détails de l'exception](media/vendor_invoice_automation_03.png)

Dans l'illustration précédente, aucune ligne n'était disponible pour l'en-tête de facture fournisseur fourni. Par conséquent, la section Lignes est vide.

La page des détails de l'exception prend en charge l'opération suivante :

+ **Créer une facture en attente** – Après avoir résolu les problèmes sur la facture dans le cadre du traitement des exceptions, vous pouvez cliquer sur ce bouton pour créer la facture en attente. Les factures en attente sont créées en arrière-plan (comme une opération asynchrone).

### <a name="shared-service-vs-organization-based-exception-processing"></a>Traitement des exceptions basées sur les services partagés et les organisations

La page de liste des exceptions prend en charge les constructions de sécurité standard prises en charge par l'espace de travail **Gestion des données** pour le traitement des enregistrements intermédiaires. La tâche d'importation de facture peut être sécurisée de plusieurs manières :

+ Par rôle d'utilisateur
+ Par utilisateur
+ Par entité juridique

![Importer une tâche sécurisée par rôle d'utilisateur et entité juridique](media/vendor_invoice_automation_04.png)

Si la sécurité est configurée pour la tâche d'importation de facture, la page de liste des exceptions honore ces paramètres. Les utilisateurs pourront visualiser uniquement les enregistrements d'exception de facture que ce paramétrage les autorise à voir.

Par exemple, Contoso a décidé de traiter les exceptions de facture par entité juridique. Par conséquent, la sécurité est configurée sur la tâche d'importation de facture de telle sorte qu'un utilisateur de l'entité juridique A puisse consulter uniquement les exceptions de facture dans l'entité juridique A, tandis qu'un utilisateur de l'entité juridique B peut consulter uniquement les exceptions de facture dans l'entité juridique B. Ce paramétrage permet la répartition des tâches de gestion des exceptions de facture.

Contoso peut également décider de ne pas appliquer de sécurité, afin que les mêmes utilisateurs puissent traiter les exceptions pour toutes les entités juridiques. Ce paramétrage active un scénario de services partagés pour la gestion des exceptions de facture.

## <a name="side-by-side-attachment-viewer"></a>Visionneuse de pièce jointe côte à côte

Pour faciliter l'affichage des pièces jointes pour les factures fournisseur, les pages suivantes utilisées dans le processus de facturation fournissent désormais une visionneuse de pièce jointe :

+ **Traitement des exceptions**
+ Page **Factures fournisseur en attente** (également disponible dans le processus de vérification des factures)
+ Page **Journal des factures** (pour les factures validées)

Voici les principales fonctionnalités fournies par la visionneuse de pièce jointe :

+ Afficher tous les types de pièces jointes pris en charge par le module Gestion des documents (fichiers, images, URL et notes).
+ Afficher les fichiers TIFF sur plusieurs pages.
+ Exécuter les actions suivantes sur les fichiers image :
  + Mettre en surbrillance des parties de l'image.
  + Bloquer des parties de l'image.
  + Ajouter des annotations à l'image.
  + Effectuer un zoom avant ou arrière sur l'image.
  + Effectuer un panoramique de l'image.
  + Annuler et répéter des actions.
  + Ajuster l'image à la taille.

> [!NOTE]
> Ces actions sont disponibles uniquement pour les fichiers image (JPEG, tiff, PNG, etc.). Les modifications apportées à une image à l'aide de ces actions sont enregistrées dans le fichier image. Pour le moment, la visionneuse de pièce jointe n'inclut pas les fonctions de contrôle de versions et d'audit.

### <a name="default-attachment"></a>Pièce jointe par défaut

Si une facture fournisseur contient plusieurs pièces jointes, vous pouvez définir un des documents comme pièce jointe par défaut sur la page **Documents joints**. L'option **Pièce jointe par défaut** est une nouvelle option qui a été ajoutée dans le cadre de cette fonctionnalité. Cette option est également exposée dans l'entité de données Pièces jointes des documents de facture fournisseur. Par conséquent, la pièce jointe par défaut peut être définie par le biais des intégrations.

Un seul document peut être défini comme pièce jointe par défaut. Après avoir défini un document comme pièce jointe par défaut, il s'affiche automatiquement dans la visionneuse de pièce jointe lorsque la facture est ouverte. Si vous ne définissez pas de document comme pièce jointe par défaut, la visionneuse n'affiche pas automatiquement de pièce jointe lorsque la facture est ouverte.

### <a name="showhide-invoice-attachments"></a>Afficher/masquer les pièces jointes de facture

Un nouveau bouton disponible sur les pages de recherche **Traitement des exceptions**, **Facture en attente** et **Journal des factures** permet d'afficher ou de masquer la visionneuse de pièce jointe.

### <a name="security"></a>Sécurité

Les actions suivantes dans la visionneuse de pièce jointe sont contrôlées via la sécurité basée sur les rôles :

+ Mise en surbrillance
+ Bloquer
+ Annotation

### <a name="pending-vendor-invoices-page"></a>Page Factures fournisseur en attente

Les privilèges suivants donnent un accès en lecture seule ou un accès en lecture/écriture à la visionneuse de pièce jointe pour les actions de mise en surbrillance, de blocage et d'ajout d'annotations :

+ **Tenir à jour l'image de la facture fournisseur** – Ce privilège offre un accès en lecture/écriture.
+ **Afficher l'image de la facture fournisseur** – Ce privilège offre un accès en lecture seule.

Les droits suivants donnent un accès en lecture seule ou un accès en lecture/écriture à la visionneuse de pièce jointe pour ces actions :

+ **Tenir à jour les factures fournisseur** – Le privilège Tenir à jour l'image de la facture fournisseur est affecté à ce droit.
+ **Recherche dans le statut des factures fournisseur** – Le privilège Afficher l'image de la facture fournisseur est affecté à ce droit.

Les rôles suivants donnent un accès en lecture seule ou un accès en lecture/écriture à la visionneuse de pièce jointe pour ces actions :

+ **Commis à la comptabilité fournisseur** et **Responsable Comptabilité fournisseur** – Le droit Tenir à jour les factures fournisseur est affecté à ces rôles.
+ **Commis à la comptabilité fournisseur**, **Responsable Comptabilité fournisseur**, **Commis au paiement centralisé de la comptabilité fournisseur** et **Commis au paiement de la comptabilité fournisseur** – Le privilège Recherche dans le statut des factures fournisseur est affecté à ces rôles.

### <a name="invoice-exception-details-page"></a>Page des détails d'exception de facture

Les privilèges suivants donnent un accès en lecture seule ou un accès en lecture/écriture à la visionneuse de pièce jointe pour les actions de mise en surbrillance, de blocage et d'ajout d'annotations.

> [!NOTE]
> Les rôles mentionnés dans cette section donnent automatiquement un accès en lecture seule aux images de facture dans la visionneuse de pièce jointe. Si un rôle doit également avoir un accès en écriture aux images, vous pouvez accorder un accès en écriture à ce rôle à l'aide du privilège et du droit décrits ici.

+ **Tenir à jour l'image de l'entité En-tête du journal des factures fournisseur** – Ce privilège donne un accès en lecture/écriture aux images de facture dans la visionneuse de pièce jointe.
+ **Afficher l'image de l'entité En-tête du journal des factures fournisseur** – Ce privilège donne un accès en lecture seule aux images de facture dans la visionneuse de pièce jointe.

Les droits suivants donnent un accès en lecture seule à la visionneuse de pièce jointe pour ces actions :

+ **Tenir à jour les factures fournisseur** – Le privilège Tenir à jour l'image de l'entité En-tête du journal des factures fournisseur est affecté à ce droit.

Les rôles suivants donnent un accès en lecture seule à la visionneuse de pièce jointe pour ces actions :

+ **Commis à la comptabilité fournisseur** et **Responsable Comptabilité fournisseur** – Le droit Tenir à jour les factures fournisseur est affecté à ces rôles.

Par défaut, si le rôle d'utilisateur donne des droits de modification sur n'importe quelle page, l'utilisateur aura également des droits de modification sur la visionneuse de pièce jointe pour les actions de mise en surbrillance, de blocage et d'ajout d'annotations. Toutefois, s'il existe des scénarios où un rôle spécifique doit avoir des droits de modification sur la page mais pas sur la visionneuse de pièce jointe, les privilèges appropriés de la liste précédente peuvent être utilisés pour respecter le cas d'utilisation.
