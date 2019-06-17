<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="omni-auto-charges.md" target-language="fr-FR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>omni-auto-charges.2f6e37.47829a6fcae37e03510929dc46b942455016df0b.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>47829a6fcae37e03510929dc46b942455016df0b</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\omni-auto-charges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Frais automatiques avancés omnicanaux</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes capabilities for managing additional order charges for Retail channel orders using advanced auto charges features.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique décrit les capacités pour gérer les frais supplémentaires des commandes du canal Retail via les fonctions de frais automatiques avancés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Omni-channel advanced auto charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Frais automatiques avancés omnicanaux</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides information on configuration and deployment of the advanced auto-charges feature which are available in Dynamics 365 for Retail version 10.0.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cette rubrique fournit des informations sur la configuration et le déploiement de la fonction de frais automatiques avancés disponible dans Dynamics 365 for Retail version 10.0.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>When the advanced auto-charges features are enabled, orders created in any supported Retail channel (point of sale (POS), call center, and online), can take advantage of the <bpt id="p1">[</bpt>auto-charges<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations defined in the ERP application for both header and line-level related charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque les fonctionnalités de frais automatiques avancés sont activées, les commandes créées dans tout canal de vente au détail pris en charge (point de vente (PDV), centre d'appels et en ligne) peuvent bénéficier des configurations <bpt id="p1">[</bpt>frais automatiques<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> définies dans l'application ERP pour les frais associés au niveau de l'en-tête et de la ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>In releases prior to Dynamics 365 for Retail version 10.0, <bpt id="p1">[</bpt>auto-charge<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> configurations are only accessible by orders created in e-Commerce and call center channels.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans les versions antérieures à la version 10.0 de Dynamics 365 for Retail, les configurations <bpt id="p1">[</bpt>frais automatiques<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery#define-charges-for-delivery-services)</ept> sont uniquement accessibles par les commandes créées dans des canaux de commerce électronique et des centres d'appels.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>In versions 10.0 and later, POS-created orders can leverage the auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans les versions 10.0 et ultérieures, les commandes créées en PDV peuvent valoriser les configurations de frais automatiques.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>That way, additional miscellaneous charges can systematically be added to sales transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ainsi, les différents frais supplémentaires peuvent systématiquement être ajoutés aux transactions de vente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>When using releases prior to version 10.0, a POS user is prompted to manually enter a shipping fee during the creation of a "ship all" or "ship selected" POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lors de l'utilisation de versions précédentes à la version 10.0, un utilisateur du PDV est invité à saisir manuellement des frais d'expédition pendant la création d'une transaction de PDV « Tout expédier » ou « Expédition sélectionnée ».</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>While the miscellaneous charges capabilities of the application are utilized in respect to how the charges are written to the order, no systematic calculation is provided – the calculation relies on the user's input to determine the value of the charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Même si les différentes fonctions de frais de l'application sont utilisées par rapport à la manière dont les frais sont rédigés dans la commande, aucun calcul systématique n'est fourni. Le calcul est basé sur la saisie de l'utilisateur pour déterminer la valeur des frais.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The charges can only be added as a single "shipping" related charges code and cannot easily be edited or changed in the POS after they are created.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les frais peuvent être ajoutés uniquement en tant que code de frais associés à l'expédition unique et ne peuvent pas être facilement modifiés ou mis à jour dans le PDV après leur création.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The use of manual prompts to add shipping charges is still available in versions 10.0 and later.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'utilisation des invites manuelles pour ajouter des frais d'expédition reste disponible dans les versions 10.0 et ultérieures.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>If an organization does not enable the <bpt id="p1">**</bpt>Advanced Auto-charges<ept id="p1">**</ept> parameter, the POS prompts for manual entry of charges will remain the same.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si une organisation n'active pas le paramètre <bpt id="p1">**</bpt>Frais automatiques avancés<ept id="p1">**</ept>, les invites du PDV pour la saisie manuelle des frais resteront les mêmes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>With the advanced auto-charges feature, POS users can have systematic calculations for any defined miscellaneous charges based on auto-charges setup tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avec la fonctionnalité des frais automatiques avancés, les utilisateurs peuvent avoir des calculs systématiques pour tous frais divers définis selon les tables de configuration des frais automatiques.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In addition, users will have the ability to add or edit an unlimited amount of additional charges and fees to any POS sales transaction at the header or line-level (for a cash and carry or customer order).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">En outre, les utilisateurs auront la capacité d'ajouter ou de mettre à jour un montant illimité des frais supplémentaires vers une transaction de vente en PDV au niveau de l'en-tête ou du niveau de ligne (pour un paiement au comptant ou une commande client).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Enabling advanced auto-charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Activation de frais automatiques avancés</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>On the <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept> page, go to the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab. On the <bpt id="p3">**</bpt>Charges<ept id="p3">**</ept> FastTab, set <bpt id="p4">**</bpt>Use advanced auto-charges<ept id="p4">**</ept> to <bpt id="p5">**</bpt>Yes<ept id="p5">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Sur la page <bpt id="p1">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Configuration du siège <ph id="ph2">\&gt;</ph> Paramètres <ph id="ph3">\&gt;</ph> Paramètres de la vente au détail<ept id="p1">**</ept>, accédez à l'onglet <bpt id="p2">**</bpt>Commandes client<ept id="p2">**</ept>. Dans l'organisateur <bpt id="p3">**</bpt>Frais<ept id="p3">**</ept>, définissez <bpt id="p4">**</bpt>Utiliser les frais automatiques avancés<ept id="p4">**</ept> sur <bpt id="p5">**</bpt>Oui<ept id="p5">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Advanced Auto-Charges Parameter</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramètre de frais automatiques avancés</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>When advanced auto-charges are enabled, users are no longer prompted to manually enter a shipping charge at the POS terminal when creating a ship-all or ship-selected customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque les frais automatiques avancés sont activés, les utilisateurs ne sont plus invités à saisir manuellement des frais d'expédition au terminal de PDV lors de la création d'une commande client de type « Expédier tout » ou « Expédition sélectionnée ».</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>POS order charges are systematically calculated and added to the POS transaction (if a corresponding auto-charges table that matches the criterion of the order being created are found).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les frais de commande au PDV sont systématiquement calculés et ajoutés à la transaction au PDV (si un tableau de frais automatiques correspondant qui répond aux critères de la commande créée est trouvé).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Users can also add or maintain header or line-level charges manually through newly added POS operations that can be added to the POS screen layouts.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les utilisateurs peuvent également ajouter ou conserver manuellement des frais au niveau de l'en-tête ou de la ligne manuellement via les opérations en PDV récemment ajoutées qui peuvent être ajoutées aux mises en page de l'écran de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>When advanced auto-charges are enabled, the existing <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> for <bpt id="p2">**</bpt>Shipping charges code<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> are no longer utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Lorsque les frais automatiques avancés sont activés, l'option existante <bpt id="p1">**</bpt>Paramètres de vente au détail<ept id="p1">**</ept> pour <bpt id="p2">**</bpt>Code frais d'expédition<ept id="p2">**</ept> et <bpt id="p3">**</bpt>Rembourser les frais d'expédition<ept id="p3">**</ept> ne sont plus utilisées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>These parameters are only applicable if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>No<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ces paramètres s'appliquent uniquement si le paramètre <bpt id="p1">**</bpt>Utiliser les frais automatiques avancés<ept id="p1">**</ept> est défini sur <bpt id="p2">**</bpt>Non<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Before you enable this feature, ensure that you have tested and trained your employees, as this will change the business process flow of how shipping or other charges are calculated and added to POS sales orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avant d'activer cette fonctionnalité, veillez à avoir testé et formé vos employés, puisque cela changera le flux du processus commercial de la manière dont les frais d'expédition ou autres frais sont calculés et ajoutés aux commandes client du PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Make sure that you understand the impact of the process flow to the creation of transactions from POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Veillez à comprendre l'impact du flux du processus sur la création des transactions depuis le PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>For call center and e-Commerce orders, the impact of enabling advanced auto-charges is minimal.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les commandes du centre d'appels et du commerce électronique, l'impact de l'activation des frais automatiques avancés est minime.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Call center and e-Commerce applications will continue to have the same behavior they have had historically related to the auto-charges tables to calculate additional order fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les applications du centre d'appels et du commerce électronique continueront à avoir le même comportement qu'elles ont eu historiquement par rapport aux tableaux de frais automatiques pour calculer les frais de commande supplémentaires.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>Call center channel users will continue to have the ability to manually edit any system calculated auto-charges at the header or line level, or manually add additional miscellaneous charges at the header or line level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les utilisateurs du canal de centre d'appels continueront à avoir la capacité de modifier manuellement tous les frais automatiques calculés par le système au niveau de l'en-tête ou de la ligne, ou d'ajouter manuellement divers frais au niveau de l'en-tête ou de la ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Additional POS operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Opérations de PDV supplémentaires</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>For advanced auto-charges to work properly in your POS application environment, new POS operations have been added.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour que les frais automatiques avancés fonctionnent correctement dans votre environnement d'application de PDV, de nouvelles opérations de PDV ont été ajoutées.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>These operations must be added to your <bpt id="p1">[</bpt>POS screen layouts<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> and deployed to the POS devices as you deploy advanced auto-charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ces opérations doivent être ajoutées à vos <bpt id="p1">[</bpt>Mises en page de l'écran du PDV<ept id="p1">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> et être déployées vers les périphériques de PDV à mesure que vous déployez les frais automatiques avancés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>If these operations are not added, users will not be able to manage or maintain miscellaneous charges on the POS transactions and will have no way of adjusting or changing the charges values that are systematically calculated based on auto-charges configurations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si ces opérations ne sont pas ajoutées, les utilisateurs ne seront pas en mesure de gérer ou de conserver des frais divers sur les transactions du PDV et n'auront pas la possibilité d'ajuster ou de modifier les valeurs des frais qui ne sont pas systématiquement calculés selon les configurations de frais automatiques.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>At minimum, it is suggested that you deploy the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation to your POS layout.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Au minimum, il est suggéré que vous déployiez l'opération <bpt id="p1">**</bpt>Gérer les frais<ept id="p1">**</ept> vers votre mise en page de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>The new operations are as follows.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Les nouvelles opérations sont les suivantes.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source><bpt id="p1">**</bpt>142 - Manage charges<ept id="p1">**</ept> – Use this operation to allow POS users to view and edit miscellaneous charges for the POS transaction that were either added manually or systematically through auto-charges calculations.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>142 - Gérer les frais<ept id="p1">**</ept> - Utilisez cette opération pour permettre aux utilisateurs du PDV d'afficher et de modifier différents frais pour la transaction du PDV ajoutée manuellement ou systématiquement via les calculs de frais automatiques.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source><bpt id="p1">**</bpt>141 - Add header charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a header-level miscellaneous charge to any POS sales transaction (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>141 - Ajouter des frais d'en-tête<ept id="p1">**</ept> - Utilisez cette opération pour donner à l'utilisateur la possibilité d'ajouter manuellement divers frais au niveau de l'en-tête à toute transaction de vente au PDV (et sélectionnez le code de frais à utiliser).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source><bpt id="p1">**</bpt>140 - Add line charges<ept id="p1">**</ept> – Use this operation to give the user the ability to manually add a line level miscellaneous charge to any POS sales transaction line (and select the charges code to be used).</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>140 - Ajouter des frais de ligne<ept id="p1">**</ept> - Utilisez cette opération pour donner à l'utilisateur la possibilité d'ajouter manuellement divers frais au niveau d'une ligne à toute transaction de vente au PDV (et sélectionnez le code de frais à utiliser).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source><bpt id="p1">**</bpt>143 - Recalculate charges<ept id="p1">**</ept> – Use this operation to perform a full re-calculation of the charges for the sales transaction.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>143 - Recalculer les frais<ept id="p1">**</ept> - Utilisez cette opération pour effectuer un recalcul complet des frais pour la transaction de vente.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Any previously user-overwritten auto-charges will be recalculated based on the current cart configuration.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Tous les frais automatiques précédemment remplacés par l'utilisateur seront recalculés selon la configuration actuelle du panier.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>As with all POS operations, security configurations can be made to require manager approval in order to execute the operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Comme avec toutes les opérations du PDV, les configurations de sécurité peuvent être faites pour exiger l'approbation du responsable afin d'exécuter l'opération.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>It is important to note that the above listed POS operations can also be added to the POS layout even if the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il est important d'observer que les opérations de PDV répertoriées ci-dessus peuvent être également ajoutées à la mise en page du PDV même si le paramètre <bpt id="p1">**</bpt>Utiliser les frais automatiques avancés<ept id="p1">**</ept> est désactivé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>In this scenario, organizations will still get added benefits of being able to view manually added charges and edit them using the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans ce scénario, les organisations bénéficient toujours d'avantages supplémentaires pour visualiser les frais ajoutés manuellement et les modifier avec l'opération <bpt id="p1">**</bpt>Gérer les frais<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>Users may also use the <bpt id="p1">**</bpt>Add header charges<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Add line charges<ept id="p2">**</ept> operations for POS transactions even when <bpt id="p3">**</bpt>Use advanced auto-charges<ept id="p3">**</ept> parameter is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les utilisateurs peuvent également utiliser les opérations <bpt id="p1">**</bpt>Ajouter des frais d'en-tête<ept id="p1">**</ept> et <bpt id="p2">**</bpt>Ajouter des frais de ligne<ept id="p2">**</ept> pour les transactions de PDV même lorsque le paramètre <bpt id="p3">**</bpt>Utiliser les frais automatiques avancés<ept id="p3">**</ept> est désactivé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>The <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation has less functionality if used when <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> is disabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'opération <bpt id="p1">**</bpt>Recalculer les frais<ept id="p1">**</ept> a une fonctionnalité moindre si elle est utilisée lorsque l'option <bpt id="p2">**</bpt>Utiliser les frais automatiques avancés<ept id="p2">**</ept> est désactivée.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>In this sceanrio, nothing would be recalculated and any charges manually added to the transaction would just reset to $0.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans ce scénario, rien n'a été recalculé et tous les frais ajoutés manuellement à la transaction sont réinitialisés sur 0,00 USD.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Use case examples</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Utiliser des exemples de scénario</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In this section, sample use cases are presented to help you understand the configuration and usage of auto-charges and miscellaneous charges within the context of Retail channel orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans cette section, des exemples de scénarios d'utilisation sont présentés pour vous aider à comprendre la configuration et l'utilisation des frais automatiques et divers frais dans le contexte de commandes du canal de vente au détail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>These examples illustrate the behavior of the application when the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter has been enabled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les exemples suivants illustrent le comportement de l'application lorsque le paramètre <bpt id="p1">**</bpt>Utiliser les frais automatiques avancés<ept id="p1">**</ept> a été activé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>Auto-charges header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple de frais d'en-tête Frais automatiques</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scénario d'utilisation</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>A retailer wants to automatically add charges for freight when transactions are created in any Retail channel that require a shipment of products to the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un détaillant souhaite ajouter automatiquement les frais pour le transport lorsque les transactions sont créées dans un canal de vente au détail qui exige une expédition des produits au client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>The retailer offers 2 methods of delivery: Ground and Air.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le détaillant propose 2 modes de livraison : terrestre et aérien.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>If a customer chooses Ground delivery and the order value is less than $100, the retailer wants to charge the customer a freight charge of $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si un client opte pour la livraison terrestre et si la valeur de la commande est inférieure à 100 USD, le détails souhaite imputer les frais de transport au client pour un montant de 10 USD.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>If the order is over $100 in value and the customer chooses ground shipping, the customer will not be charged any additional freight fees.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si la commande est supérieure à 100 USD et si le client opte pour l'expédition terrestre, le client ne sera pas imputé de frais de transport supplémentaires.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>If the customer chooses the Air method of delivery for all orders, regardless of their total value, will be charged a freight fee of $20.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le client opte pour la livraison aérienne de toutes les commandes, peu importe leur valeur totale, il sera facturé d'un montant de frais de transport de 20 USD.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrage et configuration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>This scenario requires the configuration of two auto-charges tables.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce scénario exige la configuration de deux tableaux de frais automatiques.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Go to <bpt id="p1">**</bpt>Accounts receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accédez à <bpt id="p1">**</bpt>Comptabilité client <ph id="ph1">\&gt;</ph> Paramétrage des frais <ph id="ph2">\&gt;</ph> Frais automatiques<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Configure two different header-level auto charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurez deux types de frais automatiques au niveau de l'en-tête.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>Configure one for the "Ground mode" of delivery and one for the "Air mode" of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurez des frais pour la livraison en « mode terrestre » et des frais pour la livraison en « mode aérien ».</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>For this scenario, configure them to be used for "All customers".</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour ce scénario, configurez-les pour une utilisation pour « Tous les clients ».</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source>For the ground delivery charges, in the lines section of the <bpt id="p1">**</bpt>Auto-charges<ept id="p1">**</ept> page, define a charge that will be applied for orders between $.01 and $100 as $10.00.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les frais de livraison terrestre, dans la section des lignes de la page <bpt id="p1">**</bpt>Frais automatiques<ept id="p1">**</ept>, définissez les frais qui seront appliqués pour les commandes entre 0,01 USD et 100 USD sur 10 USD.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Create another charges line to indicate orders over $100.01 will have no charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Créez une autre ligne de frais pour indiquer que les commandes supérieures à 100,01 USD n'auront pas de frais de livraison.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple de frais automatiques</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>For the air delivery charges, in the lines section of the auto-charges form, define a charge of $20.00 that will be applied to all orders (between a value of $.01 to $9,999,999).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les frais de livraison aérienne, dans la section des lignes du formulaire Frais automatiques, définissez les frais qui seront appliqués pour toutes les commandes (entre 0,01 USD et 9 999 999 USD) sur 20 USD.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>Send the changes to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envoyez les frais vers la base de données de canal/du serveur de vente au détail, de telle sorte que le PDV puisse les utiliser en exécutant la tâche <bpt id="p1">**</bpt>programme de distribution 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement des ventes pour ce scénario</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>After the configuration steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have the ground or air delivery methods set at the header level will utilize these charges and automatically apply them to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois les étapes de configuration ci-dessus validées et les modifications appliquées à la base de données du canal, toute commande client ou transaction de vente créée au PDV, centre d'appels ou via les canaux de commerce électroniques qui ont des modes de livraison terrestre ou aérien définis au niveau de l'en-tête utiliseront ces frais et les appliqueront automatiquement à la vente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>At this time the charges will apply to all sales transactions created within the legal entity that utilize these delivery modes, as there is no functionality to designate that an auto-charge configuration will only apply to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Actuellement, les frais s'appliqueront à toutes les transactions de vente créées dans l'entité juridique qui utilise ces modes de livraison puisqu'il n'y a pas de fonctionnalité pour définir qu'une configuration de frais automatiques ne s'appliquera qu'à un canal de vente spécifique.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>For POS and e-Commerce scenarios, because there is no clearly defined "header" on these orders, header-level charges will only apply if all sales lines on the transaction are set to ship with the exact same mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour les scénarios de PDV et de commerce électronique, car il n'y a pas d'« en-tête » clairement définie sur ces commandes, les frais au niveau de l'en-tête s'appliqueront uniquement si toutes les lignes de vente sur la transaction sont définies pour une expédition avec exactement le même mode de livraison.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>If there are "mixed-modes" of fulfillment on the transactions created by POS or e-Commerce, only line-level auto-charges will be considered and applied.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">S'il existe des « modes mixtes » d'exécution sur les transactions créées par le PDV ou le commerce électronique, seuls les frais automatiques au niveau de la ligne seront pris en compte et appliqués.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>In call center scenarios, the user has control over the setting of the delivery mode at the order header, therefore header-level charges will apply for these orders even if some of the sales lines have been configured to use a different mode of delivery.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Dans les scénarios du centre d'appels, l'utilisateur a le contrôle du paramètre du mode de livraison à l'en-tête de commande, par conséquent des frais au niveau de l'en-tête s'appliqueront pour ces commandes même si certaines des lignes de vente ont été configurées pour utiliser un autre mode de livraison.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Header-level charges for call center orders will always be based on the mode of delivery that is defined at the order header level of the sales order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les frais au niveau de l'en-tête pour les commandes de centre d'appels seront toujours basés sur le mode de livraison défini au niveau de l'en-tête de commande de la commande client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>Auto-charges line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple de frais de ligne Frais automatiques</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scénario d'utilisation</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>A retailer wants to add an additional charge to the customer for setup fees when the customer purchases a particular model of computer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un détaillant souhaite ajouter des frais supplémentaires au client pour configurer les frais lorsque le client achète un modèle d'ordinateur en particulier.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>This computer requires additional non-optional setup actions that the retailer will perform for the customer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cet ordinateur exige des actions de configuration non facultatives supplémentaires que le détaillant exécutera pour le client.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>The retailer has informed customers that there will be an additional fee for this setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le détaillant a informé les clients qu'il y aura des frais supplémentaires pour ce paramétrage.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>The retailer prefers to manage the charges related to this fee separately from the product sales price for financial reporting purposes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le détaillant préfère gérer les frais liés à ces frais séparément depuis le prix de vente du produit à des fins d'états financiers.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>A setup fee of $19.99 will be charged to the customer when this specific computer is purchased in any retail channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un forfait de configuration de 19,99 USD sera facturé au client lorsque cet ordinateur spécifique est acheté dans un canal de vente au détail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrage et configuration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>This scenario requires the configuration of one line-level auto charges table.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce scénario exige la configuration d'un tableau de frais automatiques au niveau d'une ligne.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>Go to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Auto charges<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Accédez à <bpt id="p1">**</bpt>Comptabilité client <ph id="ph1">\&gt;</ph> Paramétrage des frais <ph id="ph2">\&gt;</ph> Frais automatiques<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>Set the <bpt id="p1">**</bpt>Level<ept id="p1">**</ept> drop-down menu to <bpt id="p2">**</bpt>Line<ept id="p2">**</ept>, and create a new auto-charges record for all customers and for the specific product or product group where the setup fees will be charged.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Définissez le menu déroulant <bpt id="p1">**</bpt>Niveau<ept id="p1">**</ept> sur <bpt id="p2">**</bpt>Ligne<ept id="p2">**</ept>, puis créez un nouvel enregistrement de frais automatiques pour tous les clients et pour le produit ou le groupe de produits spécifique sur lequel les frais de paramétrage seront facturés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>Auto charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple de frais automatiques</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envoyez les frais vers la base de données de canal/du serveur de vente au détail, de telle sorte que le PDV puisse les utiliser en exécutant la tâche <bpt id="p1">**</bpt>programme de distribution 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Sales processing for this scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement des ventes pour ce scénario</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>After the configurations steps above are complete and the changes have been applied to the channel database, any customer order or sales transaction created in the POS, call center, or e-Commerce channels that have this item on the order will trigger a line-level charge to be systematically added to the order total.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois les étapes de configuration ci-dessus validées et les modifications appliquées à la base de données du canal, toute commande client ou transaction de vente créée au PDV, centre d'appels ou via les canaux de commerce électroniques qui ont cet article sur la commande déclencheront des frais au niveau de la ligne ajoutés systématiquement au total de la commande.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>At this time the charges will apply to any sales line that matches the configuration of the line-level auto charges within the legal entity, as there is no functionality to configure a line-level auto-charge to apply only to a specific selling channel.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Actuellement, les frais s'appliqueront à toute ligne de vente qui correspond à la configuration des frais automatiques au niveau de la ligne dans l'entité juridique, puisqu'il n'y a pas de fonctionnalité pour configurer des frais automatiques au niveau de la ligne à appliquer uniquement à un canal de vente en particulier.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>Manual header charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple de frais d'en-tête manuel</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>Use case scenario description</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Description du scénario d'utilisation</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>A retailer is making an exception to typical processes by offering to provide a special home delivery of products to a customers who order products in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un détaillant effectue une exception aux processus traditionnels en décidant de fournir une livraison des produits à domicile à un client dont les produits sont en magasin.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>The retailer and the customer have agreed that the customer will pay an additional $25 handling fee for this service.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le détaillant et le client ont convenu que le client paierait des frais de traitement supplémentaires de 25 USD pour ce service.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>The order-taker needs to add this additional fee to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le preneur de commande doit ajouter ces frais supplémentaires à la transaction.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>Because the fee is a blanket fee and not related to any single product on the order, a header charge will be utilized.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Parce que les frais sont un forfait global et ne sont pas associés à un produit unique de la commande, des frais d'en-tête seront utilisés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrage et configuration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Veillez à ce que le code de frais qui sera utilisé dans ce scénario a été correctement configuré en accédant à <bpt id="p1">**</bpt>Comptabilité client <ph id="ph1">\&gt;</ph> Paramétrage des frais <ph id="ph2">\&gt;</ph> Frais<ept id="p1">**</ept> pour définir un code de frais approprié pour le scénario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>Charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple de frais</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited">Si les frais doivent être considérés comme des frais associés « d'expédition » destinés aux remises et aux promotions pratiquées sur l'expédition, définissez <bpt id="p1">**</bpt>Frais d'expédition<ept id="p1">**</ept> du code de frais sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>If this charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si ces frais sont également autorisés pour être systématiquement remboursés pendant le traitement d'une transaction de retour dans l'application du PDV, définissez <bpt id="p1">**</bpt>Remboursable<ept id="p1">**</ept> sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'indicateur <bpt id="p1">**</bpt>Remboursable<ept id="p1">**</ept> est applicable uniquement lorsque le paramètre <bpt id="p2">**</bpt>Utiliser les frais automatiques avancés<ept id="p2">**</ept> est défini sur <bpt id="p3">**</bpt>Oui<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envoyez les frais vers la base de données de canal/du serveur de vente au détail, de telle sorte que le PDV puisse les utiliser en exécutant la tâche <bpt id="p1">**</bpt>programme de distribution 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>The <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 141).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'opération <bpt id="p1">**</bpt>Ajouter des frais d'en-tête<ept id="p1">**</ept> doit être configurée dans votre <bpt id="p2">[</bpt>Mise en page de l'écran du PDV<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> afin qu'un bouton qui est accessible à l'utilisateur du PDV puisse appeler cette opération (opération 141).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les modifications de mise en page de l'écran doivent être réparties sur le canal de vente au détail ainsi que via la fonction de planification de la distribution.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Sales processing of manual header charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement des ventes des frais d'en-tête manuel</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour exécuter le scénario dans l'application de PDV, l'utilisateur du PDV créera la transaction des ventes de manière habituelle, en ajoutant les produits et toute autre configuration à la vente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Prior to collecting payment, the user should execute the <bpt id="p1">**</bpt>Add header charge<ept id="p1">**</ept> operation, which will prompt the user to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avant de recueillir le paiement, l'utilisateur doit exécuter l'opération <bpt id="p1">**</bpt>Ajouter des frais d'en-tête<ept id="p1">**</ept>, ce qui invitera l'utilisateur à sélectionner un code de frais et à saisir la valeur des frais.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Once the user completes the process, the charge will be added to the sales order as a header-level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois que l'utilisateur exécute le processus, les frais sont ajoutés à la commande client en tant que frais d'en-tête.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>This process can be applied in the call center by using the existing <bpt id="p1">**</bpt>Charges<ept id="p1">**</ept> feature found on the <bpt id="p2">**</bpt>Sell<ept id="p2">**</ept> tab on the toolbar.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Ce processus peut être appliqué au centre d'appels à l'aide de la fonction <bpt id="p1">**</bpt>Frais<ept id="p1">**</ept> existante disponible dans l'onglet <bpt id="p2">**</bpt>Vendre<ept id="p2">**</ept> de la barre d'outils.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>On the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page, the user can add a new charges line to the order header.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Tenir les frais à jour<ept id="p1">**</ept>, l'utilisateur peut ajouter une nouvelle ligne de frais à l'en-tête de commande.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Manual line charges example</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exemple de frais de ligne manuel</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Use case scenario</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Scénario d'utilisation</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>A customer has requested that 2 of the 5 items on their sales order be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Un client a demandé que 2 des 5 éléments sur leur commande client soient mis dans un emballage cadeau.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>The retailer offers this optional service for a fee of $2.00 per item.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le détaillant propose ce service en option moyennant un forfait de 2 USD par article.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>The order-taker will need to add these fees to the specific items that need to be gift-wrapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le preneur d'ordre devra ajouter ces frais aux articles spécifiques qui doivent être mis dans un emballage cadeau.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>Setup and configuration</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Paramétrage et configuration</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>Ensure the charges code that will be used in this scenario has been properly configured by going to <bpt id="p1">**</bpt>Accounts Receivable <ph id="ph1">\&gt;</ph> Charges setup <ph id="ph2">\&gt;</ph> Charges<ept id="p1">**</ept> to define an appropriate charges code for the scenario.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Veillez à ce que le code de frais qui sera utilisé dans ce scénario a été correctement configuré en accédant à <bpt id="p1">**</bpt>Comptabilité client <ph id="ph1">\&gt;</ph> Paramétrage des frais <ph id="ph2">\&gt;</ph> Frais<ept id="p1">**</ept> pour définir un code de frais approprié pour le scénario.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>If the charge should be considered a "shipping" related charge for the purpose of shipping related discounts or promotions, set the <bpt id="p1">**</bpt>Shipping charge<ept id="p1">**</ept> on the charges code to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si les frais doivent être considérés comme des frais associés « d'expédition » destinés aux remises et aux promotions pratiquées sur l'expédition, définissez les <bpt id="p1">**</bpt>Frais d'expédition<ept id="p1">**</ept> du code de frais sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>If the charge is also allowed to be systematically refunded during the processing of a return transaction in the POS application, set <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si les frais sont également autorisés pour être systématiquement remboursés pendant le traitement d'une transaction de retour dans l'application du PDV, définissez <bpt id="p1">**</bpt>Remboursable<ept id="p1">**</ept> sur <bpt id="p2">**</bpt>Oui<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>The <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag is only applicable when the <bpt id="p2">**</bpt>Use advanced auto-charges<ept id="p2">**</ept> parameter is set to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'indicateur <bpt id="p1">**</bpt>Remboursable<ept id="p1">**</ept> est applicable uniquement lorsque le paramètre <bpt id="p2">**</bpt>Utiliser les frais automatiques avancés<ept id="p2">**</ept> est défini sur <bpt id="p3">**</bpt>Oui<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Send the charges to the Retail Server/Channel DB so that the POS can utilize them by running the <bpt id="p1">**</bpt>1040 distribution schedule<ept id="p1">**</ept> job.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Envoyez les frais vers la base de données de canal/du serveur de vente au détail, de telle sorte que le PDV puisse les utiliser en exécutant la tâche <bpt id="p1">**</bpt>programme de distribution 1040<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>The <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation must be configured in your <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a button that is accessible to the user from POS can call this operation (operation 140).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'opération <bpt id="p1">**</bpt>Ajouter des frais de ligne<ept id="p1">**</ept> doit être configurée dans votre <bpt id="p2">[</bpt>Mise en page de l'écran du PDV<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> afin qu'un bouton qui est accessible à l'utilisateur du PDV puisse appeler cette opération (opération 140).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>The screen layout changes must be distributed to the retail channel as well through the distribution schedule function.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les modifications de mise en page de l'écran doivent être réparties sur le canal de vente au détail ainsi que via la fonction de planification de la distribution.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>Sales processing of the manual line charge</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Traitement des ventes des frais de ligne manuelle</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>To execute the scenario in the POS application, the POS user will create the sales transaction as usual, adding the products and any other configurations to the sale.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour exécuter le scénario dans l'application de PDV, l'utilisateur du PDV créera la transaction des ventes de manière habituelle, en ajoutant les produits et toute autre configuration à la vente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>Prior to collecting payment, the user should select the specific line where the charge will apply from the POS item list display and execute the <bpt id="p1">**</bpt>Add line charge<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Avant de collecter le paiement, l'utilisateur doit sélectionner une ligne spécifique sur laquelle les frais s'appliqueront depuis la liste d'articles du PDV et exécuteront l'opération <bpt id="p1">**</bpt>Ajouter des frais de ligne<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>The user will be prompted to select a charges code and enter the charges value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'utilisateur sera invité à sélectionner un code de frais et à saisir la valeur des frais.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>Once the user completes the process, the charge will be linked to the line and added to the order total as a line level charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois que l'utilisateur exécute le processus, les frais seront associés à la ligne et ajoutés au total de la commande comme frais d'en-tête.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>The user can repeat the process to add additional line charges to other items lines on the transaction if needed.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'utilisateur peut répéter le processus pour ajouter des frais de ligne supplémentaires à d'autres lignes d'articles sur la transaction, le cas échéant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The same process can be applied in the call center by using the "maintain charges" feature found under the <bpt id="p1">**</bpt>Financials<ept id="p1">**</ept> drop-down menu in the <bpt id="p2">**</bpt>Sales order lines<ept id="p2">**</ept> section on the <bpt id="p3">**</bpt>Sales order<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le même processus peut être appliqué au centre d'appels à l'aide de la fonctionnalité « Tenir à jour les frais » sous le menu déroulant <bpt id="p1">**</bpt>Finances<ept id="p1">**</ept> dans la section <bpt id="p2">**</bpt>Lignes de commande client<ept id="p2">**</ept> sur la page <bpt id="p3">**</bpt>Commande client<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>This will open the <bpt id="p1">**</bpt>Maintain charges<ept id="p1">**</ept> page where the user can add a new line specific charge to the transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Cela ouvrira la page <bpt id="p1">**</bpt>Tenir les frais à jour<ept id="p1">**</ept> sur laquelle l'utilisateur peut ajouter une nouvelle ligne de frais spécifiques à la transaction.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Additional features</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fonctionnalités supplémentaires</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Editing charges on a POS sales transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Modifier les frais sur une transaction de vente au PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>The <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> operation (142) should be added to the <bpt id="p2">[</bpt>POS screen layout<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> so that a user can view and edit or override any system-calculated or manually-created header or line-level charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'opération <bpt id="p1">**</bpt>Gérer les frais<ept id="p1">**</ept> (142) doit être ajoutée à la <bpt id="p2">[</bpt>mise en page de l'écran du PDV<ept id="p2">](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts)</ept> afin qu'un utilisateur puisse afficher et modifier ou remplacer tous les frais de ligne ou d'en-tête créés manuellement ou calculés par le système.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>If the operation is not added, users will not be able to adjust the value of the charges on the POS transaction, nor will they be able to view the details of the charges such as the type of charges code tied to the charge.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si l'opération n'est pas ajoutée, les utilisateurs ne seront pas en mesure d'ajuster la valeur des frais sur la transaction du PDV, et ne pourront pas non plus afficher les détails des frais tels que le type de code de frais associé aux frais.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>On the <bpt id="p1">**</bpt>Manage charges<ept id="p1">**</ept> page in POS, the user can view both header and line-level charges details.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Sur la page <bpt id="p1">**</bpt>Gérer les frais<ept id="p1">**</ept> dans le PDV, l'utilisateur peut afficher les détails des frais au niveau de la ligne et de l'en-tête.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The user can use the <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> function available on this page to make changes to the amount charged to a specific charges line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'utilisateur peut utiliser la fonction <bpt id="p1">**</bpt>Modifier<ept id="p1">**</ept> disponible sur cette page pour apporter des modifications au montant imputé à une ligne spécifique de frais.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>Once a charges line is overwritten manually, it will not be systematically recalculated unless the user initiates the <bpt id="p1">**</bpt>Recalculate charges<ept id="p1">**</ept> operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Une fois qu'une ligne de frais est remplacée manuellement, elle ne sera pas systématiquement recalculée sauf si l'utilisateur initie l'opération <bpt id="p1">**</bpt>Recalculer les frais<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>If the <bpt id="p1">**</bpt>Charge override reason code<ept id="p1">**</ept> has been configured on the <bpt id="p2">**</bpt>Retail parameters<ept id="p2">**</ept> setup page, the user will be prompted to provide a reason code when charges have been modified in the POS application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le <bpt id="p1">**</bpt>Code du motif de remplacement des frais<ept id="p1">**</ept> a été configuré sur la page de configuration <bpt id="p2">**</bpt>Paramètres de vente au détail<ept id="p2">**</ept>, l'utilisateur est invité à fournir un code motif lorsque les frais ont été modifiés dans l'application du PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>If reason codes have been captured for overwritten charges, a new report is also available to review and audit these overrides.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si les codes de motif ont été capturés pour remplacer les frais, un nouveau rapport est également disponible pour passer en revue et auditer ces remplacements.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>The report can be found in <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge override history<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'état peut être trouvé dans <bpt id="p1">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Recherches et états <ph id="ph2">\&gt;</ph> Historique de remplacement des frais<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Refunding charges on a POS return transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Remboursement des frais dans le cadre d'une transaction de retour au PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>If the <bpt id="p1">**</bpt>Use advanced auto-charges<ept id="p1">**</ept> parameter is set to <bpt id="p2">**</bpt>Yes<ept id="p2">**</ept>, the existing retail parameter for <bpt id="p3">**</bpt>Refund shipping charges<ept id="p3">**</ept> is no longer applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si le paramètre <bpt id="p1">**</bpt>Utiliser<ept id="p1">**</ept> est défini sur <bpt id="p2">**</bpt>Activé<ept id="p2">**</ept>, le paramètre de détail existant pour <bpt id="p3">**</bpt>Rembourser les frais d'expédition<ept id="p3">**</ept> ne s'applique plus.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>To indicate which charges should be systematically refunded to a customer when using advanced auto-charges, ensure the related charges code has been configured as <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour indiquer quels frais doivent être systématiquement remboursés à un client lors de l'utilisation de frais automatiques avancés, veillez à ce que le code de frais associé a été configuré comme <bpt id="p1">**</bpt>Remboursable<ept id="p1">**</ept> sur la page de configuration <bpt id="p2">**</bpt>Code de frais<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>Make sure that the settings have been synchronized to your Retail channel databases through distribution schedule processing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Veillez à ce que les paramètres aient été synchronisés vers vos bases de données du canal de vente au détail via le traitement du programme de distribution.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Refunding charges on a return order transaction</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Remboursement des frais dans le cadre d'une transaction d'ordre de retour</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>Charges are not systematically refunded to <bpt id="p1">**</bpt>Return orders<ept id="p1">**</ept> created in Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les frais ne sont pas systématiquement remboursés aux <bpt id="p1">**</bpt>Ordres de retour<ept id="p1">**</ept> créés dans la vente au détail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>Users are required to select the <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> option when creating the <bpt id="p2">**</bpt>Return order<ept id="p2">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Les utilisateurs doivent sélectionner l'option <bpt id="p1">**</bpt>Copier les frais<ept id="p1">**</ept> en créant l'<bpt id="p2">**</bpt>Ordre de retour<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is not selected, charges from the original sales transaction will not be automatically refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si <bpt id="p1">**</bpt>Copier les frais<ept id="p1">**</ept> n'est pas sélectionné, les frais de la transaction de vente d'origine ne seront pas automatiquement remboursés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>If <bpt id="p1">**</bpt>Copy charges<ept id="p1">**</ept> is selected, all charges will be copied to the return order and the user can manually edit or remove any charges they do not want to have refunded.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si <bpt id="p1">**</bpt>Copier les frais<ept id="p1">**</ept> est sélectionné, tous les frais sont copiés dans l'ordre de retour et l'utilisateur peut modifier ou supprimer manuellement tous les frais pour lesquels il ne souhaite pas être remboursé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>The call center return order process currently does not acknowledge the <bpt id="p1">**</bpt>Refundable<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> setup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Le processus d'ordre de retour du centre d'appels ne reconnaît actuellement pas l'indicateur <bpt id="p1">**</bpt>Remboursable<ept id="p1">**</ept> sur la configuration <bpt id="p2">**</bpt>Code de frais<ept id="p2">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>Configuring POS receipts to show charges</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configuration des reçus du PDV pour afficher les frais</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>The following receipt elements have been added to the receipt line and footer to support the advanced auto-charges functionality.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Les éléments de reçu suivants ont été ajoutés à la ligne et au pied de page de reçu pour prendre en charge la fonctionnalité des frais automatiques avancés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source><bpt id="p1">**</bpt>Line Shipping Charges<ept id="p1">**</ept> – This line-level element can be used to recap specific charges codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Frais d'expédition de la ligne<ept id="p1">**</ept> - Cet élément au niveau de la ligne peut être utilisé pour résumer les codes de frais spécifiques appliqués à la ligne de vente.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>Only charges codes that have been flagged as <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> charges on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page will be displayed here.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Seuls les codes frais qui ont été marqués comme des frais d'<bpt id="p1">**</bpt>Expédition<ept id="p1">**</ept> sur la page <bpt id="p2">**</bpt>Code de frais<ept id="p2">**</ept> seront affichés ici.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source><bpt id="p1">**</bpt>Line Other Charges<ept id="p1">**</ept> – This line-level element can be used to recap any non-shipping specific charge codes that have been applied to the sales line.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Autres frais de la ligne<ept id="p1">**</ept> - Cet élément au niveau de la ligne peut être utilisé pour résumer les codes de frais spécifiques hors expédition appliqués à la ligne de vente.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>These are charges codes where the <bpt id="p1">**</bpt>Shipping<ept id="p1">**</ept> flag on the <bpt id="p2">**</bpt>Charges code<ept id="p2">**</ept> page has not been enabled.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Il s'agit de codes de frais où l'indicateur <bpt id="p1">**</bpt>Expédition<ept id="p1">**</ept> sur la page <bpt id="p2">**</bpt>Code de frais<ept id="p2">**</ept> n'a pas été activé.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source><bpt id="p1">**</bpt>Order Shipping Charges Details<ept id="p1">**</ept> – This footer-level element displays the descriptions of the charge codes applied to the order that have been flagged as <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept> charges on the <bpt id="p3">**</bpt>Charges code<ept id="p3">**</ept> setup page.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Détails des frais d'expédition de la commande<ept id="p1">**</ept> - Cet élément au niveau du pied de page affiche les descriptions des codes de frais appliquées à la commande et marqué comme frais d'<bpt id="p2">**</bpt>Expédition<ept id="p2">**</ept> sur la page de configuration <bpt id="p3">**</bpt>Code de frais<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source><bpt id="p1">**</bpt>Order Shipping Charges<ept id="p1">**</ept> – This footer-level element shows the dollar value of the shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Frais d'expédition de la commande<ept id="p1">**</ept> - Cet élément au niveau du pied de page indique la valeur en dollar des frais associés à l'expédition.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source><bpt id="p1">**</bpt>Order Other Charges Details<ept id="p1">**</ept> – This footer-level element displays the description of the charges codes applied to the order that have not been flagged as shipping-related charges.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Détails des autres frais de la commande<ept id="p1">**</ept> - Cet élément au niveau du pied de page affiche les descriptions des codes de frais appliquées à la commande et marqué comme frais d'expédition.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source><bpt id="p1">**</bpt>Order Other Charges<ept id="p1">**</ept> – This footer-level element displays the dollar value of the other charges that are not shipping-related.</source><target logoport:matchpercent="98" state="translated" state-qualifier="x-fuzzy-match-unedited"><bpt id="p1">**</bpt>Autres frais de la commande<ept id="p1">**</ept> - Cet élément au niveau du pied de page indique la valeur en dollar des autres frais associés, mais pas à l'expédition.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>It is recommended that the organization also add free text fields to the receipt footer, in order to define the areas where charges will be recapped.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nous recommandons à l'organisation d'ajouter également des champs de texte libre au pied de page de réception afin de définir les zones où les frais seront récapitulés.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>Preventing charges from being calculated until the POS order is completed</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Prévenir contre le calcul des frais avant la fin de la commande du PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Some organizations may prefer to wait until the user has finished adding all of the sales lines to the POS transaction before calculating charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Certaines organisations préfèreront attendre jusqu'à ce que l'utilisateur ait fini d'ajouter toutes les lignes de vente à la transaction du PDV avant de calculer les frais.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>To prevent calculation of charges as items are added to the POS transaction, turn on the <bpt id="p1">**</bpt>Manual charge calculation<ept id="p1">**</ept> parameter in the <bpt id="p2">**</bpt>Functionality profile<ept id="p2">**</ept> used by the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Pour empêcher le calcul des frais puisque les articles sont ajoutés à la transaction en PDV, activez le paramètre <bpt id="p1">**</bpt>Calcul manuel des frais<ept id="p1">**</ept> dans le <bpt id="p2">**</bpt>Profil de la fonctionnalité<ept id="p2">**</ept> utilisé par le magasin.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Enabling this parameter will require the POS user to use the <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation when they have completed adding the products to the POS transaction.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si vous activez ce paramètre, l'utilisateur du PDV pourra utiliser l'opération <bpt id="p1">**</bpt>Calculer les totaux<ept id="p1">**</ept> lorsqu'il aura terminé d'ajouter les produits à la transaction du PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>The <bpt id="p1">**</bpt>Calculate totals<ept id="p1">**</ept> operation will then trigger the calculation of any auto charges for the order header or lines as applicable.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'opération <bpt id="p1">**</bpt>Calculer les totaux<ept id="p1">**</ept> déclenchera ensuite le calcul de tous les frais automatiques de l'en-tête ou des lignes de la commande, le cas échéant.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Charges override reports</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">États de remplacement des frais</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>If users manually override the calculated charges or add a manual charge to the transaction, this data will available for auditing in the <bpt id="p1">**</bpt>Charge Override History<ept id="p1">**</ept> report.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Si les utilisateurs remplacent manuellement les frais calculés ou ajoutent des frais manuels à la transaction, ces données sont disponibles pour audit dans l'état <bpt id="p1">**</bpt>Historique de remplacement des frais<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>The report can be accessed from <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Inquiries and reports <ph id="ph2">\&gt;</ph> Charge Override History<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">L'état peut être accessible depuis <bpt id="p1">**</bpt>Vente au détail <ph id="ph1">\&gt;</ph> Recherches et états <ph id="ph2">\&gt;</ph> Historique de remplacement des frais<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>It is important to note that the data needed for this report is imported from the channel database into HQ through the "P" distribution schedule jobs.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Il est important d'observer que les données requises pour cet état sont importées depuis la base de données des canaux dans le siège social via les tâches de programme de distribution « P ».</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>Therefore, information about overrides just performed in the POS may not be immediately available on this report until this job has uploaded the store transaction data into HQ.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Par conséquent, les informations concernant les remplacements effectués dans le PDV peuvent ne pas être immédiatement disponibles sur cet état tant que cette tâche n'a pas chargé les données de transaction du magasin au siège.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>