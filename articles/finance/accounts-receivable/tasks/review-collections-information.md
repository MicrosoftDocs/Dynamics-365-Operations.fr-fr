---
title: Réviser les informations de recouvrement
description: Cette rubrique explique comment réviser les informations de recouvrement et utiliser diverses options relatives au paramétrage et aux transactions de recouvrement.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bbfb6537118a9936c127018427b0516e7ea002a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971526"
---
# <a name="review-collections-information"></a>Réviser les informations de recouvrement

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment réviser les informations de recouvrement et utiliser diverses options relatives au paramétrage et aux transactions de recouvrement. La société fictive USMF sert d’exemple dans cette procédure.

## <a name="create-customer-pools"></a>Créer des regroupements de clients
1. Dans le volet de navigation, accédez à **Modules > Crédit et recouvrements > Paramétrage > Regroupements de clients**.
- Cette page permet de paramétrer des regroupements de clients, lesquels constituent des requêtes qui définissent un groupe de comptes client pouvant être affichés et gérés pour les processus liés aux recouvrements ou aux balances âgées. Les regroupements de clients permettent de filtrer des informations dans la page de liste **Recouvrements** et dans les pages de liste associées. Les regroupements de clients vous permettent également de filtrer les comptes client inclus lors de la création des instantanés de balance âgée.  
- Les regroupements de clients vous permettent de filtrer les comptes client inclus lors de la création des instantanés de balance âgée.  
2. Sélectionnez **Nouveau**.
3. Dans le champ **ID de regroupement**, tapez une valeur.
4. Dans le champ **Description du regroupement**, tapez une valeur.
5. Cliquez sur **Sélectionner le critère de regroupement**.
6. Tapez une valeur dans le champ **Critères**.
7. Cliquez sur **OK**.
8. Sélectionnez **Regroupement de clients précédent**.

## <a name="create-collections-agents"></a>Créer des agents de recouvrement
1. Dans le volet de navigation, accédez à **Modules > Crédit et recouvrements > Paramétrage > Agents de recouvrement**.  
- Cette page permet de paramétrer des collaborateurs comme agents de recouvrement et éventuellement de leur affecter des regroupements de clients. Un *agent de recouvrement* est une personne qui travaille avec les clients pour s’assurer que les paiements sont collectés en temps voulu.  
- Les agents de recouvrement paramétrés sur cette page sont automatiquement ajoutés à une équipe de recouvrement. Si une équipe est sélectionnée dans le champ **Équipe** de la page **Paramètres de la comptabilité client**, les agents de recouvrement y sont ajoutés. Si aucune équipe n’est sélectionnée, une nouvelle équipe appelée Recouvrements est créée automatiquement et les agents de recouvrement y sont ajoutés.  
2. Sélectionnez l’agent souhaité, puis sélectionnez **Ajouter** dans la page.
3. Dans le champ **ID de regroupement**, sélectionnez l’enregistrement souhaité dans le menu déroulant.
4. Cochez ou décochez la case **Regroupement par défaut**.
- Activez cette option pour inclure tous les regroupements de clients dans les listes des filtres pour l’agent de recouvrement sélectionné. Si cette option n’est pas activée, seuls les regroupements de clients affectés à l’agent de recouvrement sont disponibles dans les listes des filtres.  

## <a name="create-aging-period-definition"></a>Créer une définition de plage âgée.
1. Dans le volet de navigation, accédez à **Modules > Crédit et recouvrements > Paramétrage > Définitions des plages âgées**.
- Les plages âgées permettent d’analyser l’échéance des comptes client et fournisseur en fonction de la date entrée. Chaque plage âgée paramétrée pour la définition de plage âgée correspond à une colonne de la page de liste, de l’écran ou de l’état lors de l’analyse.  
2. Sélectionnez **Nouveau**.
3. Entrez une valeur dans le champ **Définition de la plage âgée**.
4. Tapez une valeur dans le champ **Description**.
- Permet de spécifier le nom, l’unité et l’intervalle de chaque plage âgée à inclure dans la définition de plage âgée. La ligne qui présente la valeur 0 (zéro) dans le champ Unité indique la date d’exécution de l’analyse. Les lignes figurant avant le zéro présentent la valeur - 1, et celles après le zéro, la valeur 1 en tant qu’entrée par défaut dans le champ Unité, mais il est possible de les modifier. Sélectionnez **Haut** et **Bas** pour réorganiser les lignes. La ligne 0 (zéro) ne peut pas être déplacée.  
- Placez le pointeur à l’endroit où vous souhaitez insérer une nouvelle ligne, puis sélectionnez **Ajouter**.  
- Sélectionnez un indicateur pour représenter la plage âgée dans l’écran **Recouvrements** et la page de liste. Par exemple, vous pouvez sélectionner un indicateur vert pour une période actuelle, un indicateur jaune pour les 30 jours suivant la plage et un indicateur rouge pour les 90 jours suivant la plage.  
- Permet de sélectionner le sens d’impression de la définition de plage âgée. Cette sélection détermine l’ordre d’affichage des colonnes dans la Balance âgée des clients ou la Balance âgée des fournisseurs.  
  - En avant : les colonnes sont imprimées dans le même ordre que celui de l’affichage des en-têtes dans la table, en commençant par la ligne du haut.  
  - En arrière : les colonnes sont imprimées dans l’ordre inverse de celui dans lequel les en-têtes sont affichés dans la table, en commençant par la ligne du bas.    

## <a name="setup-collections-parameters"></a>Configurer les paramètres de recouvrement
1. Dans le volet de navigation, accédez à **Modules > Crédit et recouvrements > Paramétrage > Paramètres de la comptabilité client**.
2. Sélectionnez l’onglet **Recouvrements**.
3. Développez ou réduisez la section **Valeurs par défaut des relances**.
- Sélectionnez une définition de plage âgée pour l’instantané de balance âgée par défaut qui sera utilisé dans l’écran **Recouvrements**.  
- Sélectionnez une équipe à laquelle sont affectés des agents de recouvrement dans l’écran **Agent de recouvrement**. Seules les équipes de type Recouvrements sont affichées dans la liste.  
4. Développez ou réduisez la section **Annulation**.
- Sélectionnez le nom de journal, paramétré pour les journaux comptables quotidiens, à utiliser lorsqu’une transaction est annulée par le biais de l’écran **Recouvrements** ou des listes de page associées.  
- Sélectionnez le code motif par défaut à utiliser lorsque des transactions d’annulation sont créées par le biais de l’écran **Recouvrements** ou des pages de liste associées.  
- Activez cette option afin de créer une ligne de journal distincte pour les montants de taxe lorsque des transactions d’annulation sont créées par le biais de la page **Recouvrements** ou des pages de liste associées. Si vous sélectionnez cette option, vous pouvez plus facilement effectuer le suivi des montants de taxe impliqués dans les transactions d’annulation. Afin d’ajuster plus aisément votre impôt à payer sur la période concernée, vous pouvez suivre les montants de taxe séparément.  
5. Développez ou réduisez la section **Modèle d’e-mail**.
- Sélectionnez le modèle d’e-mail à utiliser lorsque vous envoyez un e-mail par le biais de l’action **Courrier électronique > Transactions** vers contact, dans l’écran **Recouvrements**.  
- Sélectionnez le modèle d’e-mail à utiliser lorsque vous envoyez un relevé client en pièce jointe par le biais de l’action **Courrier électronique > Relevé** vers contact, dans l’écran **Recouvrements**.  
- Sélectionnez le modèle d’e-mail à utiliser lorsque vous envoyez un e-mail par le biais de l’action **Courrier électronique > Transactions** vers vendeur, dans l’écran **Recouvrements**.  

## <a name="age-customer-balance"></a>Solde client âgé
1. Dans le volet de navigation, accédez à **Modules > Crédit et recouvrements > Tâches périodiques > Soldes client échus**.
- Sélectionnez une définition de plage âgée. Le processus d’instantané de balance âgée calcule l’échéance des transactions selon les plages âgées définies dans la définition de plage âgée sélectionnée.  
- Permet de sélectionner un regroupement de clients ou, en laissant ce champ vide, de créer un instantané de balance âgée pour tous les clients. Si un regroupement de clients est sélectionné, le processus d’instantané de balance âgée est appliqué aux seuls comptes client faisant partie du regroupement de clients. Le regroupement de clients sélectionné doit être de type Instantané de balance âgée.  
- Permet de sélectionner le type de date sur lequel baser l’instantané de balance âgée.  
  - Date de transaction : calculer l’échéance de chaque transaction en fonction de sa date de transaction.    
  - Date d’échéance : calculer l’échéance de chaque transaction en fonction de sa date d’échéance.    
  - Date de document : calculer l’échéance de chaque transaction en fonction de sa date de document.  
- Permet de sélectionner la date à utiliser comme date du jour pour l’instantané de balance âgée. Les plages âgées sont calculées en fonction de cette date.    
  - Date du jour : utilisez la date système. Utilisez cette option si le traitement est paramétré pour intervenir dans un traitement par lots récurrent. Si vous utilisez cette date, le traitement par lots récurrent peut être exécuté périodiquement et la date système du jour est utilisée.    
  - Date sélectionnée : utilisez une date que vous spécifiez. Si vous sélectionnez cette option, entrez une date âgée.  
2. Cliquez sur **OK**.

## <a name="view-aged-customer-balances"></a>Afficher les soldes client âgés
1. Dans le volet de navigation, accédez à **Modules > Crédit et recouvrements > Recouvrements > Soldes échus**.
- Cette page de liste permet d’afficher les soldes client et montants âgés par plage âgée. Ces informations sont stockées dans un instantané de balance âgée. Les plages âgées sont déterminées par la définition de plage âgée utilisée. La définition de plage âgée est extraite du regroupement de clients éventuellement spécifié pour la requête de regroupement. Si le regroupement de clients ne dispose pas de définition de plage âgée, la définition de plage âgée par défaut spécifiée dans l’écran Paramètres de la comptabilité client est utilisée.  
2. Développez le récapitulatif **Contact**. Ici, vous pouvez afficher les informations de contact :
- Contact de recouvrement du client.  
- Vendeur du client.  
3. Développez le récapitulatif **Limite de crédit**.
- Le récapitulatif **Informations crédit** permet d’afficher les informations de limite de crédit et de solde actuel pour le client.  

## <a name="view-customer-collections-details"></a>Afficher les détails des recouvrements client
1. Assurez-vous que l’enregistrement souhaité est sélectionné.
2. Développez les récapitulatifs **Adresse**, **Contact**, **Balance âgée** et **Limite de crédit** pour afficher les informations données.
3. Dans le volet Actions, sélectionnez **Recouvrir**.
- Mettez à jour l’instantané de balance âgée pour le client, en utilisant la date actuelle comme date âgée avec laquelle les dates de transaction sont comparées. Si l’instantané de balance âgée contient des informations sur plusieurs entités juridiques, l’instantané de balance âgée mis à jour inclut des informations relatives au même ensemble d’entités juridiques. Les montants sont stockés dans la monnaie de compte de l’entité juridique à laquelle vous êtes connecté lorsque vous mettez à jour l’instantané de balance âgée.  
- Sélectionnez une définition de plage âgée. Par défaut, la définition de plage âgée associée à l’instantané de balance âgée pour le client s’affiche. La définition de plage âgée contrôle les plages âgées et les montants affichés dans les récapitulatifs **Soldes chronologiques** et **Informations crédit**.  
- Ouvrez un menu contenant les options suivantes :    
  - Société : Affichez les montants dans les récapitulatifs Soldes chronologiques et Informations crédit dans la devise comptable de l’entité juridique.  
  - Client : affichez les montants dans les récapitulatifs Soldes chronologiques et Informations crédit dans la devise du client.  
- Sélectionnez une ou plusieurs entités juridiques dans l’instantané de balance âgée du client pour lequel afficher les informations. Les entités juridiques indiquées dans la liste ont été sélectionnées lors de la création de l’instantané de balance âgée.  
- Affichez le relevé du client au format Microsoft Excel. Vous pouvez sélectionner une date de début pour la plage de transactions à inclure dans le relevé et décider d’inclure uniquement les transactions en cours, ou les transactions en cours et réglées. Si l’instantané de balance âgée contient des informations relatives à plusieurs entités juridiques, les transactions sont incluses pour toutes les entités juridiques.  
- Ouvrez l’écran **Documents**, dans lequel vous pouvez créer ou modifier des documents ou des notes.  
4. Dans le volet Actions, sélectionnez **Communiquer**.  
- Ouvrez Outlook, où vous pouvez envoyer un e-mail au contact spécifié dans le champ Contact. Si aucun contact de recouvrement n’est spécifié, l’adresse principale du client est utilisée. Si aucun contact principal n’est spécifié, des messages électroniques sont envoyés à la première adresse répertoriée dans l’écran **Contacts**. Les transactions sélectionnées sont incluses comme pièce jointe. La pièce jointe est au format Excel et contient trois feuilles de calcul. Vous pouvez spécifier un modèle d’e-mail pour les messages aux contacts client dans l’écran **Paramètres de la comptabilité client**.  
- Ce bouton n’est pas disponible si aucune adresse e-mail n’est configurée pour le contact sélectionné dans cet écran.  
- Préparez un relevé et ouvrez Outlook, où vous pouvez envoyer un e-mail avec en pièce jointe un relevé à l’adresse spécifiée dans le champ **Contact**. Si aucun contact de recouvrement n’est spécifié, l’adresse principale du client est utilisée. Si aucun contact principal n’est spécifié, des messages électroniques sont envoyés à la première adresse répertoriée dans l’écran **Contacts**.  
- Ce bouton n’est pas disponible si aucune adresse e-mail n’est configurée pour le contact sélectionné dans cet écran.  
- Ouvrez Outlook, où vous pouvez envoyer un message e-mail à l’employé spécifié comme commercial pour le groupe de ventes affecté au client. Si des transactions sont sélectionnées, elles sont incluses comme pièce jointe. La pièce jointe est au format Excel et contient deux feuilles de calcul. Vous pouvez spécifier un modèle d’e-mail pour les messages aux commerciaux dans l’écran **Paramètres de la comptabilité client**.  
- Ce bouton n’est pas disponible si aucune adresse e-mail n’est configurée pour le commercial affiché dans cet écran.  
- Affichez et effectuez des actions sur les transactions pour le client. Si vous utilisez des paiements centralisés, les informations relatives à toutes les entités juridiques incluses dans l’instantané de balance âgée du client sont incluses. Vous pouvez limiter les informations sur une entité juridique en sélectionnant **Société** dans le groupe **Sélectionner** du volet Actions.  
- Modifiez le statut de recouvrement des transactions sélectionnées.    
  - Non litigieux : aucune action de recouvrement n’est survenue pour la transaction.    
  - Litigieux : le client vous a informé de l’existence d’un problème avec la transaction.    
  - Paiement promis : le client a accepté de payer le montant de la transaction.    
  - Résolu : tous les problèmes relatifs à la transaction ont été résolus et aucune autre action de recouvrement n’est requise.  
- Ouvrez un menu et sélectionnez l’une des options suivantes pour spécifier les transactions à afficher dans cet écran :    
  - En cours : permet d’afficher uniquement les transactions qui n’ont pas été réglées.    
  - En cours et clôturé : permet d’afficher toutes les transactions (réglées ou non).  
- Traitez le paiement sélectionné comme paiement des impayés.    
  - Ce bouton n’est disponible que si la transaction sélectionnée est un paiement (solde créditeur sans facture) entré dans un journal des paiements, si un compte bancaire est affecté à la transaction et si le paiement n’a pas précédemment été annulé.  
- Annulez les transactions sélectionnées.  
- Marquez les transactions sélectionnées pour le règlement les unes par rapport aux autres.  
- Ouvrez l’écran **Document d’origine**, dans lequel vous pouvez afficher et imprimer le document pour la transaction sélectionnée.  
- Ouvrez un **menu** contenant les options suivantes :    
  - Recouvrements : permet d’afficher uniquement les activités créées dans l’écran Recouvrements.    
  - Tout : permet d’afficher toutes les activités pour le client, quel que soit l’emplacement de création des activités.  
- Ouvrez un **menu** contenant les options suivantes :    
  - En cours : permet d’afficher uniquement les activités non clôturées.    
  - En cours et clôturé : permet d’afficher toutes les activités, quel que soit leur statut.  
- Sélectionnez une demande de devis de recouvrement affectée au client ou laissez ce champ vide. Si une demande de devis est sélectionnée, seules les transactions et les activités associées à celles-ci sont affichées dans cet écran.  
5. Sélectionnez **Afficher la liste**.
- Sélectionnez un compte client ou utilisez le compte par défaut. Par défaut, il s’agit du compte client sélectionné dans la page de liste ou l’écran à partir duquel vous avez ouvert cet écran. Si vous avez ouvert l’écran à partir d’une page de liste, les clients de la liste sont les clients inclus dans le regroupement de recouvrements utilisé dans la page de liste.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]