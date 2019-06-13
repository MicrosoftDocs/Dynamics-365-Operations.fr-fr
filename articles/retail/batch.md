<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="batch.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>batch.e70006.4456fc3d5bc4547fa8211642b11ca6df455fa187.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4456fc3d5bc4547fa8211642b11ca6df455fa187</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\batch.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Improved handling of batch-tracked items</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Gestion améliorée des articles suivis par lots</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the improvements that have been made to the handling of batches for batch-tracked items during the Retail statement posting process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette rubrique décrit les améliorations qui ont été apportées à la gestion des lots pour les articles suivis par lots pendant le processus de validation des relevés de vente au détail.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Improved handling of batch-tracked items</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Gestion améliorée des articles suivis par lots</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dans le point de vente (PDV) Microsoft Dynamics 365 for Retail, les numéros de lot ne peuvent pas être capturés pour les articles suivis par lots au moment de la vente.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Toutefois, pour des configurations spécifiques, lorsque les ventes sont validées dans le siège par le biais des commandes client ou de la validation des relevés, le système Microsoft Dynamics s'attend à ce que des numéros de lot valides soient disponibles pour les articles suivis par lots et qu'ils soient utilisés pendant le processus de facturation.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Si des numéros de lot valides sont disponibles pour les produits, le processus de facturation des commandes client et le processus de facturation des commandes client par le biais de la validation des relevés les utilisent.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Sinon, le processus de facturation des commandes client ne peut pas être validé et l'utilisateur POS reçoit un message d'erreur.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Statement posting then goes into an error state.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La validation des relevés passe ensuite à l'état d'erreur.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>This error state occurs even when negative inventory has been turned on for the products.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cet état d'erreur se produit même si un stock négatif a été activé pour les produits.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Les améliorations qui ont été apportées dans Microsoft Dynamics for Retail version 10.0.4 et ultérieure garantissent qu'en cas d'activation d'un stock négatif pour les articles suivis par lots, la facturation des commandes client et la facturation des commandes client par le biais de la validation des relevés ne sont pas bloquées pour ces articles si le stock est égal à 0 (zéro) ou un numéro de lot n'est pas disponible.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">La nouvelle fonctionnalité utilise un ID de lot par défaut pour les lignes de vente lorsque les numéros de lot ne sont pas disponibles.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To define the default batch ID that is used for customer orders, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Order<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Pour définir l'ID de lot par défaut utilisé pour les commandes client, dans la page <bpt id="p1">**</bpt>Paramètres des ventes au détail<ept id="p1">**</ept>, sous l'onglet <bpt id="p2">**</bpt>Commandes client<ept id="p2">**</ept>, dans le raccourci <bpt id="p3">**</bpt>Commande<ept id="p3">**</ept>, définissez le champ <bpt id="p4">**</bpt>ID de lot par défaut<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>To define the default batch ID that is used for sales order invoicing through statement posting, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Posting<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Inventory update<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match">Pour définir l'ID de lot par défaut utilisé pour la facturation des commandes client par le biais de la validation des relevés, dans la page <bpt id="p1">**</bpt>Paramètres des ventes au détail<ept id="p1">**</ept>, sous l'onglet <bpt id="p2">**</bpt>Validation<ept id="p2">**</ept>, dans le raccourci <bpt id="p3">**</bpt>Mise à jour du stock<ept id="p3">**</ept>, définissez le champ <bpt id="p4">**</bpt>ID de lot par défaut<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Cette fonctionnalité est disponible uniquement lorsque l'entreposage avancé est activé pour l'entrepôt et les articles spécifiques.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Dans une version ultérieure, la fonctionnalité sera également prise en charge pour les scénarios où la gestion avancée des entrepôts n'est pas utilisée.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>