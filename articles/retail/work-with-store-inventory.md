<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="work-with-store-inventory.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>work-with-store-inventory.418f90.551a8408aa730bc1916f1c57b7cfd773966ce8bf.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>551a8408aa730bc1916f1c57b7cfd773966ce8bf</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>e2fb0846fcc6298050a0ec82c302e5eb5254e0b5</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/27/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\work-with-store-inventory.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Store inventory management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gestion des stocks du magasin</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the types of documents that you can use to manage inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique décrit les types de documents qui peuvent être utilisés pour gérer le stock.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Store inventory management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Gestion des stocks du magasin</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>When working with inventory in Dynamics 365 for Retail and using the POS application, it is important to note that POS provides limited support for inventory dimensions and certain inventory item types.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors de l'utilisation du stock dans Dynamics 365 for Retail et en utilisant l'application du PDV, il est important de noter que le PDV propose un support limité pour les dimensions de stock et certains types d'articles en stock.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The POS solution does not support the following item configurations:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La solution du PDV ne prend pas en charge les configurations d'article suivantes :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>BOM items (except kit products, which utilize some components of the BOM framework)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les articles de la nomenclature (hormis les produits de kit, qui utilisent certains composants du cadre de la nomenclature)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Catch weight items</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Articles en poids variable</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Batch-controlled items</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Articles contrôlés par lots</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>The POS application currently does not support the following tracking dimensions in the POS:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'application du PDV ne prend actuellement pas en charge les dimensions de suivi suivantes dans le PDV :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Batch tracking dimension</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dimension de suivi par lots</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Owner dimension</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dimension du propriétaire</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The POS solution provides limited support for the following dimensions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La solution pour PDV offre un support limité pour les dimensions suivantes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Limited support indicates that the POS may default some of these dimensions into inventory transactions automatically based on warehouse/store setup configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le support limité indique que le PDV peut transférer certaines de ces dimensions par défaut dans les transactions de stock automatiquement basées sur la configuration de l'entrepôt/du magasin.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>POS will not fully support the dimensions in the way they are supported if a sales transaction is manually entered into the ERP.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Le PDV ne prendra pas intégralement en charge les dimensions si une transaction commerciale est manuellement saisie dans l'ERP.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source><bpt id="p1">**</bpt>Warehouse Location<ept id="p1">**</ept> – Users will not have the ability to manage the receiving warehouse location for items received into a store warehouse when the store has not been configured to use the warehouse management process.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Emplacement de l'entrepôt<ept id="p1">**</ept> - Les utilisateurs n'ont pas la capacité de gérer l'emplacement de l'entrepôt de réception pour les articles reçus dans un entrepôt de magasin lorsque le magasin n'a pas été configuré pour utiliser le processus de gestion des entrepôts.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>A default receiving location defined on the store warehouse will be used for these items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un emplacement de réception par défaut défini dans l'entrepôt de magasin est utilisé pour ces articles.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>If the warehouse management process has been enabled for the store, limited support that prompts the user to choose a receiving location for the entire receipt will be triggered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le processus de gestion des entrepôts a été activé pour le magasin, le support limité qui invite l'utilisateur à sélectionner un emplacement de réception pour la réception entière est déclenché.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Items sold from the store will always be sold out of the default retail location as defined on the store warehouse setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les articles vendus par le magasin sont toujours vendus depuis l'emplacement de vente au détail par défaut comme défini dans le paramétrage d'entrepôt de magasin.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>The location for managing return inventory can be controlled through default return location definition on the store warehouse or based on return reason codes as defined in the return location policy.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">L'emplacement pour gérer le retour au stock peut être contrôlé par la définition d'emplacement de retour par défaut sur l'entrepôt du magasin ou selon des codes motif de retour comme défini dans la stratégie de l'emplacement de retour.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source><bpt id="p1">**</bpt>License plate<ept id="p1">**</ept> – License plates are only applicable when <bpt id="p2">**</bpt>Use warehouse management process<ept id="p2">**</ept> has been enabled on the item and the store warehouse.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Contenant<ept id="p1">**</ept> - Les contenants sont applicables uniquement quand <bpt id="p2">**</bpt>Utiliser les processus de gestion des entrepôts<ept id="p2">**</ept> a été activée sur l'article et l'entrepôt de stockage.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>In POS, if inventory is received into a store warehouse where the warehouse management process has been enabled, and the location chosen to receive the item into is tied to a location profile that requires license plate control, the POS application will systematically apply a license plate to the receiving line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans le POS, si le stock est reçu dans un entrepôt de magasin où le processus de gestion des entrepôts a été activé, et que l'emplacement choisi pour recevoir l'article dans est lié à un profil d'emplacement qui nécessite le contrôle des contenants, l'application POS appliquera systématiquement un contenant à la ligne de réception.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Users in POS will not have the ability to change or manage this license plate data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les utilisateurs de POS n'ont pas la possibilité de modifier ou de gérer ces données de contenant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>If full management of license plates is required, it is suggested the store use the WMS mobile application or the back office ERP client to manage the receipt of these items.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Si la gestion complète des contenants est nécessaire, il est suggéré que le magasin utilise l'application mobile WMS ou le client ERP de services administratifs pour gérer la réception de ces articles.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source><bpt id="p1">**</bpt>Serial number<ept id="p1">**</ept> – The POS application has limited support for single serial number to be registered on a transaction sales line for orders created in POS with serialized items.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Numéro de série<ept id="p1">**</ept> - L'application POS a une prise en charge limitée du numéro de série unique à enregistrer sur une ligne de vente de transaction pour les commandes créés dans POS avec des articles sérialisés.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>This serial number is not validated against registered serial numbers already in inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce numéro de série n'est pas validé par rapport à des numéros de série enregistrés déjà en stock.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>If a sales order is created in the call center channel or fulfilled through the ERP and multiple serial numbers are registered to a single sales line during the fulfillment process in the ERP, these serial numbers will not be able to be applied or validated if a return is processed in POS for these orders.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Si une commande client est créée dans le canal du centre d'appels ou exécutée via l'ERP et que plusieurs numéros de série sont enregistrés sur une ligne de vente lors du processus d'exécution dans l'ERP, ces numéros de série ne pourront pas être appliqués ou validés si un retour est traité dans POS pour ces commandes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source><bpt id="p1">**</bpt>Inventory status<ept id="p1">**</ept> – For items that use the warehouse management process and require an inventory status, this status field is not able to be set or modified through the POS application.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Statut du stock<ept id="p1">**</ept> - Pour les articles qui utilisent le processus de gestion des entrepôts et nécessitent un statut de stock, ce champ de statut ne peut pas être défini ou modifié par l'application POS.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>The default inventory status as defined on the store warehouse configuration will be used when items are received into inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le statut du stock par défaut défini dans la configuration de l'entrepôt de magasin sera utilisé lorsque des articles sont reçus dans le stock.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>All organizations must test item configurations through POS in development or test environments before deploying them to production.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toutes les organisations doivent tester les configurations d'article via le PDV en développement ou les environnements de test avant de les déployer en production.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Test your items by performing regular cash and carry sales transacting and creating customer orders (if applicable) through the POS with your items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Testez vos articles en effectuant des ventes cash and carry régulièrement en créant et en transférant les commandes client (le cas échéant) via le POS avec vos articles.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Testing must include running a full statement posting processes in your test environment and verifying that there are no issues.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les tests doivent inclure l'exécution des processus de validation des relevés dans votre environnement test et la vérification qu'il n'y a pas de problème.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Configuring items in a way that is not supported by the POS application, without proper testing, can result in your statement posting process failing in production without an easy way to correct the issues.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La configuration des articles de manière non prise en charge par l'application du PDV, sans tests appropriés, peut entraîner l'échec du processus de validation des relevés en production sans méthode facile pour corriger les problèmes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Partner or customer customizations to the application may optionally be considered to allow these posting processes to successfully complete.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Des personnalisations du partenaire ou du client de l'application peuvent être envisagées pour permettre la réussite de ces processus de validation.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>If customizations are not needed, the organization must ensure that the product configuration of your products has been done in a way that is supported by the standard POS application/order creation/statement posting process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si des personnalisations ne sont pas nécessaires, l'organisation doit s'assurer que la configuration de produit de vos produits a été faite de façon compatible avec l'application de PDV standard/création des commandes/processus de validation des relevés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>Purchase orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Commandes fournisseur</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>Purchase orders are created at the head office.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les commandes fournisseur sont créées au siège social.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail through the <bpt id="p1">**</bpt>Picking/Receiving<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si un entrepôt de détail est indiqué dans l'en-tête de la commande fournisseur, la commande peut être reçue au magasin à l'aide de Modern POS (MPOS) ou de Cloud POS dans Microsoft Dynamics 365 for Retail via l'opération <bpt id="p1">**</bpt>Prélèvement/réception<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>After the quantities that are received at the store are entered in the <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> field in POS for the purchase order document, they can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois les quantités reçues au magasin entrées dans le champ <bpt id="p1">**</bpt>Recevoir maintenant<ept id="p1">**</ept> dans POS pour le document de commande fournisseur, elles peuvent être enregistrées localement ou validées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Saving this data locally has no effect on in-stock inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Enregistrer ces données localement n'a aucun effet sur le stock disponible.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Saving should be done only if the user is not ready to post the receipt to HQ and just needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'enregistrement doit être fait que si l'utilisateur n'est pas prêt à valider la réception au siège et a juste besoin d'enregistrer temporairement les données <bpt id="p1">**</bpt>Recevoir maintenant<ept id="p1">**</ept> entrées précédemment.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>This saves the receive now data locally to the user's channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cela enregistre les données Recevoir maintenant localement dans la base de données du canal de l'utilisateur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>After the document is processed using the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option, the <bpt id="p2">**</bpt>Receive Now<ept id="p2">**</ept> data is sent to HQ and the purchase order receipt will be posted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois le document traité à l'aide de l'option <bpt id="p1">**</bpt>Valider<ept id="p1">**</ept>, les données <bpt id="p2">**</bpt>Recevoir maintenant<ept id="p2">**</ept> sont envoyées au siège et la réception d'une commande fournisseur est validée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Transfer orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ordres de transfert</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>A transfer order can specify that a particular store is the location that items can be shipped from or the location the inventory will be received into.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un ordre de transfert peut indiquer qu'un magasin particulier est l'emplacement depuis lequel les articles peuvent être expédiés ou l'emplacement où le stock sera réceptionné.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>If the POS user is the shipping warehouse for a transfer order, they will be able to enter <bpt id="p1">**</bpt>Ship Now<ept id="p1">**</ept> quantities from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si l'utilisateur POS est l'entrepôt d'expédition pour un ordre de transfert, il peut entrer des quantités <bpt id="p1">**</bpt>Expédier maintenant<ept id="p1">**</ept> depuis POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>The data entered by the shipping store can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les données entrées par le magasin d'expédition peuvent être enregistrées localement ou validées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>When saved locally, no updates are made to the transfer order document in HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsqu'elles sont enregistrées localement, aucune mise à jour n'est effectuée sur le document d'ordre de transfert au siège.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Saving should be done only if the user is not ready to post the shipment to HQ and needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Ship Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'enregistrement doit être fait que si l'utilisateur n'est pas prêt à valider l'expédition au siège et a juste besoin d'enregistrer temporairement les données <bpt id="p1">**</bpt>Expédier maintenant<ept id="p1">**</ept> entrées précédemment.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>After the store is ready to confirm shipment, the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option should be selected.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois le magasin est prêt à confirmer l'expédition, l'option <bpt id="p1">**</bpt>Valider<ept id="p1">**</ept> doit être sélectionnée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>This posts the shipment of the transfer order in HQ so that the receiving warehouse will now be able to receive against it.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette action confirme l'expédition de l'ordre de transfert au siège afin que l'entrepôt de réception puisse maintenant le recevoir.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>If the POS user is the receiving warehouse for a transfer order, they will be able to enter the <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> quantities from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si l'utilisateur POS est l'entrepôt de réception pour un ordre de transfert, il peut entrer des quantités <bpt id="p1">**</bpt>Recevoir maintenant<ept id="p1">**</ept> depuis POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The data entered by the receiving store can be saved locally or committed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les données entrées par le magasin de réception peuvent être enregistrées localement ou validées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>Saving should be done only if the user is not ready to post the receipt to HQ and needs a way to temporarily store the previously entered <bpt id="p1">**</bpt>Receive Now<ept id="p1">**</ept> data.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'enregistrement doit être fait que si l'utilisateur n'est pas prêt à valider la réception au siège et a besoin d'enregistrer temporairement les données <bpt id="p1">**</bpt>Recevoir maintenant<ept id="p1">**</ept> entrées précédemment.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>This saves the receive now data locally to the user's channel database.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cela enregistre les données Recevoir maintenant localement dans la base de données du canal de l'utilisateur.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>After the document is processed using the <bpt id="p1">**</bpt>Commit<ept id="p1">**</ept> option, the <bpt id="p2">**</bpt>Receive Now<ept id="p2">**</ept> data is sent to HQ and the transfer order receipt will be posted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois le document traité à l'aide de l'option <bpt id="p1">**</bpt>Valider<ept id="p1">**</ept>, les données <bpt id="p2">**</bpt>Recevoir maintenant<ept id="p2">**</ept> sont envoyées au siège et la réception d'un ordre de transfert est validée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>It's important to note that the receiving store will be restricted to only being able to commit receive quantities that are equal to or less than shipped quantities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il est important de noter que le magasin de réception est limité uniquement à valider les quantités de réception qui sont égales ou inférieures aux quantités expédiées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>An attempt to receive quantities on a transfer order that have not previously shipped will result in errors and the receipt will not be confirmed in HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Toute tentative de recevoir des quantités sur un ordre de transfert qui ne se sont pas déjà expédiées provoque des erreurs et la réception ne sera pas confirmée au siège.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Stock counts</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Inventaires</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Stock counts can be either scheduled or unscheduled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les inventaires peuvent être planifiés ou non planifiés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les inventaires planifiés sont engagés par le siège social, qui spécifie les articles à inventorier.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le siège social crée un document d'inventaire qui peut être reçu au magasin, où les quantités du stock réel et disponible sont entrées dans MPOS ou Cloud POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les inventaires non planifiés sont effectués dans un magasin et les quantités de stock disponible réelles sont mises à jour dans MPOS ou Cloud POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Contrairement aux inventaires planifiés, les inventaires non planifiés n'ont pas de liste prédéfinie d'articles.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>When a stock count of either type is completed, it is committed and sent to the head office.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsqu'un inventaire de l'un ou l'autre type est terminé, il est validé et envoyé au siège social.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>At the head office, the count is validated and posted as a separate step.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Au siège social, le nombre est contrôlé et validé lors d'une étape distincte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Inventory lookup</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Recherche de stock</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>The current product quantity on hand for multiple stores and warehouses can be viewed on the <bpt id="p1">**</bpt>Inventory lookup<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La quantité actuelle disponible de produits pour plusieurs magasins et entrepôts peut être affichée dans la page <bpt id="p1">**</bpt>Recherche de stock<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En plus de la quantité actuelle disponible, les futures quantités disponibles à la vente peuvent être affichées pour chaque magasin individuel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>To do so, select the store that you want to view the ATP for and then click <bpt id="p1">**</bpt>Show store availability<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour ce faire, sélectionnez le magasin dont vous souhaitez afficher les quantités disponibles à la vente, puis cliquez sur <bpt id="p1">**</bpt>Afficher la disponibilité du magasin<ept id="p1">**</ept>.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>