<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="catch-weight-processing.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>catch-weight-processing.d3ca7d.6e295456838ca0195a472518b5979dfdc7819f74.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>6e295456838ca0195a472518b5979dfdc7819f74</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>19859d8566a8c7840066b2c10c6b08b67f1b83f4</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/04/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\supply-chain\warehousing\catch-weight-processing.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement des produits en poids variable avec la gestion des entrepôts</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to use work templates and location directives to determine how and where work is done in the warehouse.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique décrit comment utiliser les modèles de travail et les instructions d'emplacement afin de déterminer de quelle manière et où effectuer le travail dans l'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement des produits en poids variable avec la gestion des entrepôts</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Feature exposure</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exposition de la fonctionnalité</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>To use warehouse management to process catch weight products, you must use a license configuration key to turn on the functionality.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour utiliser la gestion des entrepôts dans le cadre du traitement des produits en poids variable, vous devez utiliser une clé de configuration de licence pour activer la fonctionnalité.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>(Go to <bpt id="p1">**</bpt>System administration <ph id="ph1">\&gt;</ph> Setup <ph id="ph2">\&gt;</ph> License configuration<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Accédez à <bpt id="p1">**</bpt>Administration système <ph id="ph1">\&gt;</ph> Paramétrage <ph id="ph2">\&gt;</ph> Configuration des licences<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Then, on the <bpt id="p1">**</bpt>Configuration keys<ept id="p1">**</ept> tab, expand <bpt id="p2">**</bpt>Trade <ph id="ph1">\&gt;</ph> Warehouse and Transportation management<ept id="p2">**</ept>, and select the check box for <bpt id="p3">**</bpt>Catch weight for warehouse<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puis, dans l'onglet <bpt id="p1">**</bpt>Clés de configuration<ept id="p1">**</ept>, développez <bpt id="p2">**</bpt>Commerce <ph id="ph1">\&gt;</ph> Gestion des entrepôts et du transport<ept id="p2">**</ept>, puis cochez la case <bpt id="p3">**</bpt>Poids variable pour les entrepôts<ept id="p3">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Both the <bpt id="p1">**</bpt>Warehouse and Transportation management<ept id="p1">**</ept> license configuration key and the <bpt id="p2">**</bpt>Process distribution <ph id="ph1">\&gt;</ph> Catch weight<ept id="p2">**</ept> license configuration keys must also be turned on.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La clé de configuration de licence <bpt id="p1">**</bpt>Gestion des entrepôts et du transport<ept id="p1">**</ept> et les clés de configuration de licence <bpt id="p2">**</bpt>Traiter la distribution <ph id="ph1">\&gt;</ph> en poids variable<ept id="p2">**</ept> doivent être également activées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>After the license configuration key is turned on, when you create a released product, you can select <bpt id="p1">**</bpt>Catch weight<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois la clé de configuration de licence activée, lorsque vous créez un produit lancé, vous pouvez sélectionner <bpt id="p1">**</bpt>Poids variable<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>You can also associate the released product with a storage dimension group that the <bpt id="p1">**</bpt>Use warehouse management processes<ept id="p1">**</ept> parameter is selected for.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez également associer le produit lancé à un groupe de dimensions de stockage pour lequel le paramètre <bpt id="p1">**</bpt>Utiliser les processus de gestion des entrepôts<ept id="p1">**</ept> est sélectionné.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Before you can use the product in Warehouse management, you must do some basic product-specific setup for catch weight:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avant d'utiliser le produit dans la gestion des entrepôts, vous devez procéder à une certaine configuration de base propre aux produits concernant le poids variable :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Define the nominal weight conversion between the catch weight unit (box) and the inventory unit (kilogram <ph id="ph1">\[</ph>kg<ph id="ph2">\]</ph>) as part of a unit conversion definition.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Définissez la conversion du poids nominal entre l'unité de poids variable (boîte) et l'unité de stock (kilogramme <ph id="ph1">\[</ph>kg<ph id="ph2">\]</ph>) dans le cadre d'une définition de conversion unitaire.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Define the minimum and maximum weight tolerances as part of the catch weight unit setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Définissez les tolérances de poids minimale et maximale dans le cadre de la configuration de l'unité de poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Set up a unit sequence group where the catch weight unit is defined as the lowest stock keeping unit (SKU).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurez un groupe de séquences d'unités où l'unité de poids variable est définie comme l'unité de gestion de stock (UGS) la plus basse.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Set up a catch weight item handling policy.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurez une stratégie de gestion des articles en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>For more information, see <bpt id="p1">[</bpt>Setting up and maintaining catch weight items<ept id="p1">](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items)</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour plus d'informations, voir <bpt id="p1">[</bpt>Paramétrage et mise à jour des articles en poids variable<ept id="p1">](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items)</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Transaction adjustments</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ajustements des transactions</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Because the weight of inventory when it comes into a warehouse can differ from the weight when the inventory is issued out of the warehouse, the catch weight product processing must adjust the inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parce que le poids du stock, à son arrivée à l'entrepôt, peut varier du poids du stock à sa sortie de l'entrepôt, le traitement des produits en poids variable doit ajuster le stock.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source><bpt id="p1">**</bpt>Example 1<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Exemple 1 :<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>During a <bpt id="p1">**</bpt>Report as finished<ept id="p1">**</ept> production process, the inbound weight of a license plate that contains eight boxes of a catch weight product is captured as 80.1 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Au cours d'un processus de production <bpt id="p1">**</bpt>Déclaré terminé<ept id="p1">**</ept>, le poids entrant d'un contenant de huit boîtes d'un article en poids variable est saisi, soit 80,1 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>The license plate is then stored away in the finished goods area, and during the storage period, some weight is lost into the air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le contenant est ensuite stocké ailleurs dans la zone dédiée aux produits finis. Pendant la période de stockage, on constate l'évaporation d'un certain poids.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Later, as part of a sales order picking process, the weight of the same license plate is captured as 79.8 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ultérieurement, dans le cadre du processus de prélèvement des commandes client, le poids du même contenant saisi indique 79,8 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Therefore, in the system, you now have a weight difference as part of the physical dimension set.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par conséquent, le système affiche désormais une différence de poids concernant les dimensions physiques définies.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>In this case, the system automatically adjusts the difference by posting a transaction for the missing 0.3 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le système ajuste alors automatiquement la différence en validant une transaction pour les 300 grammes manquants.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source><bpt id="p1">**</bpt>Example 2<ept id="p1">**</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Exemple 2 :<ept id="p1">**</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In its definition, a product is set up to tolerate a minimum weight of 8 kg and a maximum weight of 12 kg for the <bpt id="p1">**</bpt>Box<ept id="p1">**</ept> catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans sa définition, un produit est paramétré pour tolérer un poids minimal de 8 kg et un poids maximal de 12 kg pour l'unité de poids variable <bpt id="p1">**</bpt>Boîte<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>You have two boxes of the product, and they have a registered weight of 16 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Deux boîtes de produits affichent un poids enregistré de 16 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>If a warehouse worker picks and weighs one of the boxes, and the weight is captured as 9 kg, the remaining box will weigh 7 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si un employé de l'entrepôt prélève et pèse une des boîtes, et si le poids saisi indique 9 kg, la boîte restante pèsera 7 kg.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>However, because 7 kg is below the minimum weight, the system does an automatic adjustment to increase the weight of the on-hand inventory by 1 kg.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Or, puisque 7 kg est une valeur inférieure au poids minimal, le système effectue un ajustement automatique pour augmenter de 1 kg le poids du stock disponible.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>To set up the accounts that these adjustments are posted to, go to <bpt id="p1">**</bpt>Cost management <ph id="ph1">\&gt;</ph> Ledger integration policies setup <ph id="ph2">\&gt;</ph> Posting<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour paramétrer les comptes dans lesquels ces ajustements sont validés, accédez à <bpt id="p1">**</bpt>Gestion des coûts <ph id="ph1">\&gt;</ph> Paramétrage des stratégies d'intégration de comptabilité <ph id="ph2">\&gt;</ph> Validation<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Then, on the <bpt id="p1">**</bpt>Inventory<ept id="p1">**</ept> tab, define the following accounts:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Puis, dans l'onglet <bpt id="p1">**</bpt>Stock<ept id="p1">**</ept>, définissez les comptes suivants :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Catch weight loss account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Compte des pertes en poids variable</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Catch weight profit account</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Comptes des profits en poids variable</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>Catch weight item handling policy</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Stratégie de gestion des articles en poids variable</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>The catch weight item handling policy defines two primary warehouse management flows for the items: when the weight of the items is captured, and how it's captured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La stratégie de traitement des articles en poids variable définit deux flux principaux de gestion des entrepôts pour les articles : le moment de la saisie du poids des articles et la manière dont il est saisi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>You can define when the weight is captured for sales and transfer order processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez définir le moment de la saisie du poids pour le traitement des ordres de transfert et des commandes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>The weight can be captured during either of the following processes:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le poids peut être saisi pendant un des processus suivants :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>Picking<ept id="p1">**</ept> – The weight is captured during the initial pick work lines of order work.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Prélèvement<ept id="p1">**</ept> – Le poids est saisi pendant les lignes de travail de prélèvement initiales des commandes client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Packing<ept id="p1">**</ept> – The weight is captured during manual packing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Emballage<ept id="p1">**</ept> – Le poids est saisi lors de l'emballage manuel.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>(You must send the items to a packing station.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Vous devez envoyer les articles à une station de conditionnement.)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>If the actual weight is captured at the packing station during the container packing processes, warehouse workers won't be prompted to capture the weight during picking work.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le poids réel est saisi à la station de conditionnement pendant les processus de conditionnement des conteneurs, les employés de l'entrepôt ne sont pas invités à saisir le poids pendant le travail de prélèvement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>Instead, the average weight of the physical inventory will be used as the weight of the picked inventory that goes to the packing area.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En lieu et place, le poids moyen du stock physique est utilisé comme le poids du stock prélevé déplacé vers la zone de conditionnement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>For internal warehouse management processes like counting and adjustment corrections it is possible to define if the weight should be captured or not.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les processus de gestion interne des entrepôts comme les corrections de comptage et d'ajustement, il est possible de définir si le poids doit être saisi ou non.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>If not captured the nominal weight will be used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">S'il n'est pas saisi, le poids nominal est utilisé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>You can also define how the weight is captured.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vous pouvez également définir la manière dont le poids est saisi.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>In one of the two main flows, catch weight tags are tracked and used to capture the weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans un des deux flux principaux, les balises en poids variable sont suivies et utilisées pour saisir le poids.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In the other flow, catch weight tags aren't tracked.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans l'autre flux, les balises en poids variable ne sont pas suivies.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source><bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> – The item uses catch weight tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Oui<ept id="p1">**</ept> – L'article utilise des balises en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Each tag number represents one catch weight unit (box), and a weight and other information are associated with the tag.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Chaque numéro de balise représente une unité de poids variable (boîte) et un poids et d'autres informations sont associés à la balise.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>For outbound processes, the weight that is associated with the tag is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les processus sortants, le poids associé à la balise est utilisé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source><bpt id="p1">**</bpt>No<ept id="p1">**</ept> – The item doesn't use catch weight tags.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Non<ept id="p1">**</ept> – L'article n'utilise pas de balises en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The inbound and outbound weighing processes are based on the actual weight that is captured during each process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les processus de pesée entrant et sortant sont basés sur le poids réel saisi pendant chaque processus.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The process of tracking catch weight tags can be used for items that won't change weight during the storage period.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le processus de suivi des balises en poids variable peut être utilisé pour les articles dont le poids ne variera pas pendant la période de stockage.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>The weight will be captured only during the inbound warehouse process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le poids est saisi uniquement pendant le processus d'entrepôt entrant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>During the outbound process, the catch weight tags will just be scanned, and the weights that are associated with the tags will be used for the outbound transactional processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors du processus sortant, les balises en poids variable sont simplement lues et les poids qui y sont associés sont utilisés pour le processus transactionnel sortant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>How to capture catch weight</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Comment saisir le poids variable ?</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>When catch weight tag tracking is used, a tag must always be created for every catch weigh unit that is received, and every tag must always be associated with a weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque le suivi des balises en poids variable est utilisé, une balise doit toujours être créée pour chaque unité en poids variable reçue et chaque balise doit toujours être associée à un poids.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>For example, <bpt id="p1">**</bpt>Box<ept id="p1">**</ept> is the catch weight unit, and you receive one pallet of eight boxes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par exemple, <bpt id="p1">**</bpt>Boîte<ept id="p1">**</ept> est l'unité en poids variable, et vous recevez une palette de huit boîte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>In this case, eight unique catch weight tags must be created, and a weight must be associated with each tag.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans ce cas, huit balises en poids variable unique doivent être créées, et un poids doit être associé à chaque balise.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Depending on the inbound catch weight tag, either the weight of all eight boxes can be captured, and the average weight can then be distributed to each box, or a unique weight can be captured for each box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Selon la balise en poids variable entrant, le poids des huit boîtes peut être saisi, et le poids moyen peut ensuite être réparti sur chaque boîte, ou un poids unique peut être saisi pour chaque boîte.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>When catch weight tag tracking isn't used, the weight can be captured for each dimension set (for example, for each license plate and tracking dimension).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le suivi des balises en poids variable n'est pas utilisé, le poids peut être saisi pour chaque dimension définie (par exemple, le contenant et la dimension de suivi).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>Alternatively, the weight can be captured based on an aggregated level, such as five license plates (pallets).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">À défaut, le poids peut être saisi à un niveau agrégé, comme cinq contenants (palettes).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>For the methods for capturing outbound weight, you can define whether the weighing is done for each catch weight unit (that is, per box), or whether the weight is captured based on the quantity that will be picked (for example, three boxes).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les méthodes de saisie du poids sortant, vous pouvez définir si la pesée est réalisée pour chaque unité en poids variable (à savoir, par boîte) ou si le poids est saisi selon la quantité prélevée (par exemple, trois boîtes).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Note that for the production line picking and internal movement processes, the average weight will be used if the <bpt id="p1">**</bpt>Not captured<ept id="p1">**</ept> option is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sachez que pour le processus de prélèvement de ligne de production et les processus de mouvement interne, le poids moyen est utilisé si l'option <bpt id="p1">**</bpt>Non capturé<ept id="p1">**</ept> est utilisée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>To restrict the warehouse management picking processes from capturing weights resulting in catch weight profit/loss adjustments, the Outbound weight variance method can be used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour empêcher les processus de prélèvement de la gestion des entrepôts de capturer des poids pouvant résulter en ajustements de résultat de poids variable, il est possible d'utiliser la méthode d'écart de poids sortant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Supported scenarios</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scénarios pris en charge</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Not all workflows support catch weight product processing with warehouse management.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les workflows ne prennent pas tous en charge le traitement des produits en poids variable avec la gestion des entrepôts.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>The following restrictions currently apply.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les restrictions suivantes s'appliquent actuellement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Configuring catch weight products for warehouse management processes</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configuration des produits en poids variable pour les processus de gestion des entrepôts</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For catch weight products, the storage dimension group for items can't be changed (so that warehouse management processes can be used for them).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les produits en poids variable, le groupe de dimensions de stockage pour les articles ne peut pas être changé (vous pouvez donc utiliser les processus de gestion des entrepôts).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Only formula processing is supported for catch weight products (not bill of materials).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Seul le traitement des formules est pris en charge pour les produits en poids variable (et pas la nomenclature).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Catch weight products can't be associated with a tracking dimension group by using the Owner dimension.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable ne peuvent pas être associés à un groupe de dimensions de suivi à l'aide de la dimension du propriétaire.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Catch weight products can't be used as services.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable ne peuvent pas être utilisés comme des services.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Catch weight products can be used as "stocked products" only as part the item model group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable peuvent être utilisés comme des « produits stockés » uniquement dans le cadre du groupe de modèles d'article.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Catch weight products can't be used together with the functionality for tracking "Active in sales process."</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité pour le suivi « Actif dans le processus de vente ».</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Catch weight products can't be used together with the functionality for capturing serial numbers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité pour la capture des numéros de série.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Therefore, products can't be transferred from a "blank" to a serial number as part of the picking/packing process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par conséquent, les produits ne peuvent pas être transférés depuis une valeur « vide » vers un numéro de série dans le cadre du processus de prélèvement/de conditionnement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>Catch weight products can't be used together with the functionality for registering serials before consumption.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable ne peuvent pas être utilisés ensemble avec la fonctionnalité d'enregistrement des numéros de série avant consommation.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>Catch weight products that are variant-enabled can't be used together with the functionality for converting variant units of measure.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable, dont la variable est active, ne peuvent pas être utilisés avec la fonctionnalité pour convertir les unités de mesure variables.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>Catch weight products can't be marked as a retail "product kit."</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable ne peuvent pas être marqués comme « kit de produits » de vente au détail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Catch weight products can be used only with a unit sequence group that has catch weight handling units, and that has the catch weight unit as the lowest sequence.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les produits en poids variable peuvent être utilisés uniquement avec un groupe de séquences d'unités ayant des unités de traitement en poids variable et dont l'unité en poids variable est la séquence la plus basse.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>For catch weight products, the inventory unit can be converted to the catch weight unit only if the conversion produces a nominal quantity that is more than 1.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les produits en poids variable, l'unité de stock peut être convertie en unité en poids variable uniquement si la conversion produit une quantité nominale supérieure à 1.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>The setup of bar codes for catch weight products doesn't support a variable weight setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La configuration des codes-barres pour les produits en poids variable ne prend pas en charge une configuration en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Order processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement des commandes</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>The creation of advance ship notice (ASN/packing structures) doesn't support weight information.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La création de l'avis préalable d'expédition (structures de conditionnement/APE) ne prend pas en charge les informations relatives au poids.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>The order quantity must be maintained based on the catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La quantité commandée doit être mise à jour selon l'unité en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Inbound warehouse processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement d'entrepôt entrant</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>Receiving license plates requires that weights be assigned during registration, because weight information isn't supported as part of the advance ship notice.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La réception de contenants exige que les poids soient attribués pendant l'enregistrement, car les informations relatives au poids ne sont pas prises en charge dans le cadre de l'avis préalable d'expédition.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>When catch weight tag processes are used, the tag number must be manually assigned per catch weight unit.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si des processus de balise en poids variable sont utilisés, le numéro de balise doit être manuellement attribué par unité en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Inventory and warehouse operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opérations en entrepôt et stocks</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Manual creation of quarantine orders isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La création manuelle des ordres de contrôle n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>Manual movement of inventory that is related to work isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le mouvement manuel des stocks associés au travail n'est pas pris en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>Consolidation of license plates isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">La consolidation des contenants n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>License plate loading to initialize warehouse stock isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Le chargement du contenant pour initialiser le stock de l'entrepôt n'est pas pris en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Batch balancing processes aren't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les processus d'équilibrage du lot ne sont pas pris en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Handling of negative physical inventory isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La gestion des stocks physiques négatifs n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Inventory marking can't be used for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le marquage du stock ne peut pas être utilisé pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Outbound warehouse processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement d'entrepôt sortant</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>The functionality for cluster picking isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La fonctionnalité pour le prélèvement de groupement n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>Pick and pack warehouse processing isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Le processus de prélèvement et de conditionnement en entrepôt n'est pas pris en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>For catch weight products, work that is defined in a work template can be run automatically.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Pour les produits en poids variable, le travail défini dans un modèle de travail peut être exécuté automatiquement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>The functionality for reversing work isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La fonctionnalité pour un travail de contrepassation n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>For catch weight products, manual packing station processing where work is created after containers are closed isn't supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les produits en poids variable, le traitement manuel de la station de conditionnement où le travail est créé une fois les conteneurs fermés n'est pas pris en charge.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The functionality for pcs-by-pcs scanning isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La fonctionnalité de lecture pièce par pièce n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Production processing</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement de production</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>For catch weight products, only batch orders for formula products are supported.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les produits en poids variable, seuls les lots de commandes pour les produits de formule sont pris en charge.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Kanban functionality isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">La fonctionnalité Kanban n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>For catch weight products, serial numbers can't be registered before consumption.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les produits en poids variable, les numéros de série ne peuvent pas être enregistrés avant consommation.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>The functionality for reversing license plates isn't supported for catch weight products.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">La fonctionnalité pour la contrepassation des contenants n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>For catch weight products, reporting as finished cannot be registered by serial number.</source><target logoport:matchpercent="94" state="translated" state-qualifier="fuzzy-match">Pour les produits en poids variable, la déclaration de fin ne peut être enregistrée par numéro de série.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Transportation management processing</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Traitement de la gestion du transport</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Load building workbench processing isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le processus d'atelier de création de chargement n'est pas pris en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>Transport request lines aren't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les lignes de demande de transport ne sont pas prises en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>Other restrictions and behaviors for catch weight product processing with warehouse management</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Autres restrictions et comportements pour le traitement des produits en poids variable avec la gestion des entrepôts</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>During picking processes where the user isn't prompted to identify tracking dimensions, the weight assignment is done based on the average weight.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors des processus de prélèvement, lorsque l'utilisateur n'est pas invité à identifier les dimensions de suivi, l'affectation du poids est effectuée selon la pondération moyenne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>This behavior occurs when, for example, a combination of tracking dimensions is used in the same location and, after a user processes picking, only one tracking dimension value is left in the location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce comportement survient lorsque, par exemple, une association des dimensions de suivi est utilisée dans le même emplacement et, une fois qu'un utilisateur procède au prélèvement, seule une valeur de dimension de suivi reste à l'emplacement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>When inventory is reserved for a catch weight product that is configured for warehouse management processes, the reservation is done based on the minimum weight that is defined, even if this quantity is the on-hand last handling quantity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le stock est réservé pour un produit en poids variable configuré pour les processus de gestion des entrepôts, la réservation se fait selon le poids minimum défini, même si cette quantité est la dernière quantité de traitement disponible.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>This behavior differs from the behavior for items that aren't configured for warehouse management processes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce comportement diffère du comportement pour les articles non configurés pour les processus de gestion des entrepôts.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>Processes that use the weight as part of capacity calculations (wave thresholds, work maximum breaks, container maximums, location load capacities, and so on) don't use the actual weight of the inventory.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les processus qui utilisent le poids dans le cadre des calculs de capacité (seuils de vague, pauses max. de travail, max. de conteneurs, capacités de chargement de l'emplacement, etc.) n'utilisent pas le poids réel du stock.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>Instead, the processes are based on the physical handling weight that is defined for the product.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En lieu et place, les processus sont basés sur le poids de traitement physique défini pour le produit.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>In general, Retail functionality isn't supported for catch weight products.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En général, la fonctionnalité Retail n'est pas prise en charge pour les produits en poids variable.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>Catch weight tags</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Balises en poids variable</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>Currently, the functionality for catch weight tags is supported only as part of the following scenarios:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Actuellement, la fonctionnalité pour les balises en poids variable est prise en charge uniquement dans le cadre d'un des scénarios suivants :</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>When processing purchase order warehouse app receiving.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors du traitement de la réception des commandes fournisseur dans l'application d'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>When processing load receiving via warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors du traitement de la réception du chargement via l'application d'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>For license plate receiving that is related to a purchase order load, weight assignment is requested during the receiving process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Concernant la réception des contenants associés à un chargement d'une commande fournisseur, l'affectation du poids est demandée pendant le processus de réception.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>By contrast, for transfer order receiving, the weight from the shipment data for the transfer order is used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En revanche, pour la réception de l'ordre de transfert, le poids des données d'expédition pour l'ordre de transfert est utilisé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>For transfer order item and line receiving that comes from a non-warehouse management process warehouse.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour la réception de la ligne et de l'article de l'ordre de transfert provenant d'un processus non lié à la de gestion des entrepôts.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The processing of sales return order receiving can record catch weight tags, but the processing won't be validated if the tags are the same tags that were originally shipped for a particular sales order line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le traitement de la réception des commandes de retour de vente peut enregistrer des balises en poids variable, mais le traitement n'est pas validé si les balises sont identiques à celles envoyées à l'origine pour une ligne de commande client particulière.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>When processing a inventory status changed by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors du traitement d'un statut de stock modifié à l'aide de l'application de l'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>When a warehouse transfer is done by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors du transfert en entrepôt à l'aide de l'application d'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>When processing adjustment in and out via the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors du traitement des ajustements entrants et sortants via l'application d'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>When picking work is processed for sales and transfer orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors du traitement de la tâche de prélèvement pour les commandes clients et les ordres de transfert.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>(Note that catch weight tags can't be recorded for production component picking.)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">(Sachez que les balises en poids variable ne peuvent pas être enregistrées pour le prélèvement des composants de production.)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>When picked quantities are reduced from load lines, regardless of whether containers are used.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois les quantités prélevées réduites des lignes de chargement, peu importe si des conteneurs sont utilisés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>When products are packed into containers at a packing station.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque les produits sont conditionnés en conteneurs dans une station de conditionnement.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>When containers are reopened.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque les conteneurs sont réouverts.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>When formula products are reported as finished by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque les produits de formule sont signalés comme finis à l'aide de l'application de l'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>When transport loads are processed by using the warehouse app.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque les charges de transport sont traitées à l'aide de l'application de l'entrepôt.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>A catch weight tag can either be created using a warehousing app process, manually created in the form, or creating using a data entity process.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une balise de poids variable peut être créée à l'aide d'un processus de l'application d'entreposage, être créée manuellement dans l'écran, ou être créée à l'aide d'un processus d'entité de données.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>If a catch weight tag gets associated with an inbound source document line, such as purchase order line, the tag will be registered.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si une balise de poids variable est associée à une ligne de document source entrant, comme une ligne de commande fournisseur, la balise est enregistrée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>If the line is used for outbound processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si la ligne est utilisée pour le traitement sortant,</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>The tag will be updated as shipped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">la balise est mise à jour comme expédiée.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>