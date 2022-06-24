---
title: Approbations de factures par téléphone portable
description: Cet article est destinée à fournir une approche pratique pour concevoir des scénarios mobiles en prenant les approbations de facture de fournisseur pour mobile en tant que cas d’utilisation.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f635891e3d92fbd5978e10fe01eb67c0a28542c5
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946272"
---
# <a name="mobile-invoice-approvals"></a>Approbations de factures par téléphone portable

[!include [banner](../includes/banner.md)]

Les fonctionnalités mobiles permettent aux entreprises de créer des expériences mobiles. Pour les scénarios avancés, la plateforme permet également aux développeurs d’étendre les capacités comme ils le désirent. Le moyen le plus efficace d’apprendre quelques-uns des nouveaux concepts sur la fonction mobile est de passer en revue le processus de conception de quelques scénarios. Cet article est destinée à fournir une approche pratique pour concevoir des scénarios mobiles en prenant les approbations de facture de fournisseur pour mobile en tant que cas d’utilisation. Cet article doit vous aider à créer d’autres variations de scénarios et peut également être appliquée à d’autres scénarios non liés aux factures fournisseur.

## <a name="prerequisites"></a>Conditions préalables

| Logiciel requis                                                                                            | Description                       |
|---------------------------------------------------------------------------------------------------------|--------------------------------------------|
| Pré-lecture manuel mobile                                                                                |[Plateforme mobile](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 Finance                                                                              | Un environnement avec version 1611 et Platform update 3 (novembre 2016)                   |
| Installez le correctif KB 3204341.                                                                              | L’enregistreur de tâches peut enregistrer de manière erronée deux commandes Fermer pour les boîtes de dialogue déroulantes, incluses dans Platform Update 3 (mise à jour novembre 2016). |
| Installez le correctif KB 3207800.                                                                              | Ce correctif permet d’afficher les pièces jointes sur le client mobile, ce qui est inclus dans Platform Update 3 (mise à jour de novembre 2016).           |
| Installez le correctif KB 3208224.                                                                              | Le code d’application pour la demande d’approbation de facture fournisseur mobile est inclus dans la version 7.0.1 (mai 2016).                          |
| Périphérique Android ou iOS ou Windows doté de l’application mobile installée. | Recherche de l’application dans le magasin d’application adéquat.                            |

## <a name="introduction"></a>Introduction
Les approbations mobiles pour les factures fournisseur requièrent les trois correctifs mentionnés dans la section « Conditions préalables ». Ces correctifs ne présentent pas un espace de travail pour les approbations des factures. Pour savoir ce qu’est un espace de travail dans le contexte mobile, lisez le manuel mobile qui est mentionné dans la section « Conditions préalables ». L’espace de travail des approbations de facture doit être conçu. 

Chaque organisation orchestre et définit son processus métier pour les factures fournisseur différemment. Avant de concevoir une expérience mobile pour les approbations de facture fournisseur, vous devriez considérer les aspects suivants du processus métier. L’idée est d’utiliser ces points de données autant que possible pour optimiser l’expérience utilisateur sur le périphérique.

-   Quels champs de l’en-tête de la facture l’utilisateur souhaitera voir dans l’expérience mobile et dans quel ordre ?
-   Quels champs des lignes de la facture l’utilisateur souhaitera voir dans l’expérience mobile et dans quel ordre ?
-   Combien de lignes de facture y-a-t-il dans une facture ? Appliquez la règle 80-20 ici et effectuez une optimisation pour les 80 %%.
-   Les utilisateurs souhaiteront-ils voir les répartitions comptables (codage de facture) sur l’appareil mobile pendant les révisions ? Si la réponse à la question est Oui, tenez compte des questions suivantes :
    -   Combien de répartitions comptables (prix global, taxes, frais, fractionnements, etc.) y-a-t-il pour une ligne de facture ? Là aussi, appliquez la règle 80-20.
    -   Les factures ont-elles également les répartitions comptables dans l’en-tête de facture ? Dans ce cas, ces répartitions comptables doivent-elles être disponibles dans le périphérique ?

    > [!NOTE]
    > Cet article n’explique pas comment modifier les répartitions comptables, car cette fonctionnalité n’est actuellement pas prise en charge pour les scénarios mobiles.

-   Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?

La conception de l’expérience mobile pour les approbations des factures peut varier, selon les réponses à ces questions. Le but est d’optimiser l’expérience utilisateur pour le processus métier sur la fonction mobile dans une organisation. Dans le reste de cet article, nous regarderons deux variations de scénario basées sur les réponses aux questions précédentes. 

En général, lorsque vous travaillez avec le Concepteur mobile, veillez à « publier » les modifications pour empêcher la perte des mises à jour.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Conception d’un scénario simple d’approbation des factures pour Contoso
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut du scénario</th>
<th>Répondre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Quels champs de l’en-tête de la facture l’utilisateur souhaitera voir dans l’expérience mobile et dans quel ordre ?</td>
<td><ol>
<li>Nom du fournisseur</li>
<li>Total de la facture</li>
<li>Compte de facturation</li>
<li>Numéro de facture</li>
<li>Date de facture</li>
<li>Description de la facture</li>
<li>Date d’échéance</li>
<li>Devise de facturation</li>
</ol></td>
</tr>
<tr class="even">
<td>Quels champs des lignes de la facture l’utilisateur souhaitera voir dans l’expérience mobile et dans quel ordre ?</td>
<td><ol>
<li>Catégorie d’approvisionnement</li>
<li>Quantité</li>
<li>Prix unitaire</li>
<li>Montant net de ligne</li>
<li>Montant des honoraires</li>
</ol></td>
</tr>
<tr class="odd">
<td>Combien de lignes de facture y-a-t-il dans une facture ? Appliquez la règle 80-20 ici et effectuez une optimisation pour les 80 %%.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Les utilisateurs souhaiteront-ils voir les répartitions comptables (codage de facture) sur l’appareil mobile pendant les révisions ?</td>
<td>Oui</td>
</tr>
<tr class="odd">
<td>Combien de répartitions comptables (prix global, taxes, frais, etc.) y-a-t-il pour une ligne de facture ? Là aussi, appliquez la règle 80-20.</td>
<td>Prix global : 2 Taxe : 0 Frais : 0</td>
</tr>
<tr class="even">
<td>Les factures ont-elles également les répartitions comptables dans l’en-tête de facture ? Dans ce cas, ces répartitions comptables doivent-elles être disponibles dans le périphérique ?</td>
<td>Non utilisé</td>
</tr>
<tr class="odd">
<td>Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?</td>
<td>Oui</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Créer l’espace de travail

1.  Dans un navigateur, connectez-vous à l’application.
2.  Après vous être connecté, ajoutez **&mode=mobile** à l’URL comme indiqué dans l’exemple suivant, puis rafraîchissez la page : https://&lt;yoururl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  Cliquez sur le bouton **Paramètres** (engrenage) dans la partie supérieure droite de la page, puis cliquez sur **Application mobile**. Le Concepteur d’application mobile doit s’afficher, ainsi que l’Enregistreur de tâches.
4.  Cliquez sur **Ajouter** pour créer un espce de travail. Pour cet exemple, nommez l’espace de travail **Mes approbations**.
5.  Entrez une description.
6.  Sélectionnez une couleur d’espace de travail. La couleur de l’espace de travail est utilisée pour le style général des expériences mobiles de cet espace de travail.
7.  Sélectionnez une icône pour l’espace de travail.
8.  Cliquez sur **Terminé**
9.  Cliquez sur **Publier l’espace de travail** pour enregistrer les modifications.

### <a name="vendor-invoices-assigned-to-me"></a>Factures fournisseur qui me sont affectées

La première page mobile que vous devez configurer est la liste des factures affectées à l’utilisateur pour révision. Pour concevoir cette page mobile, utilisez la page **VendMobileInvoiceAssignedToMeListPage**. Avant de pouvoir exécuter cette procédure, assurez-vous qu’au moins une facture fournisseur vous est affectée à la révision, et que la ligne de facture a les deux répartitions. Ce paramétrage correspond aux exigences pour ce scénario.

1.  Dans l’URL, remplacez le nom de l’option de menu par **VendMobileInvoiceAssignedToMeListPage** pour ouvrir la version mobile de la page de liste **Factures fournisseur en attente qui me sont affectées** dans le module **Comptabilité fournisseur**. Selon le nombre de factures que vous avez dans votre système qui vous est affecté, cette page affiche les factures. Pour trouver une facture spécifique, vous pouvez utiliser le filtre à gauche. Toutefois, nous n’avons pas besoin d’une facture spécifique pour cet exemple. Nous demandons simplement une facture qui vous est attribuée, ce qui vous permettra de concevoir la page mobile. Les nouvelles pages disponibles doivent être désignées spécifiquement pour développer les scénarios mobiles pour la facture fournisseur. Par conséquent, vous devez utiliser ces pages. L’URL doit ressembler à l’adresse suivante, et une fois que vous l’avez entrée, la page affichée dans l’illustration doit apparaître : https://&lt;votreURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile 

    [![Page Factures fournisseur en attente qui me sont affectées.](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
    
2.  Cliquez sur le bouton **Paramètres** (engrenage) dans la partie supérieure droite de la page, puis cliquez sur **Application mobile**
3.  Sélectionnez l’espace de travail et cliquez sur **Modifier**
4.  Cliquez sur **Ajouter une page** pour créer la première page mobile.
5.  Entrez un nom, par exemple **Mes factures fournisseur**, et une description, par exemple **Factures fournisseur qui me sont affectées pour révision**.
6.  Cliquez sur **Terminé**.
7.  Dans le Concepteur mobile, sous l’onglet **Champs**, cliquez sur **Sélectionner des champs**. Les colonnes de la page de liste doivent ressembler à l’illustration suivante. 

    [![Colonnes figurant dans les factures fournisseur en attente qui me sont affectées.](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
    
8.  Ajoutez les colonnes voulues de la page de liste à afficher aux utilisateurs de la page mobile. L’ordre dans lequel vous ajoutez est l’ordre dans lequel les champs seront affichés à l’utilisateur final. La seule façon de modifier l’ordre des champs consiste à sélectionner tous les champs. Selon la configuration requise pour ce scénario, les huit champs suivants sont nécessaires. Cependant, certains utilisateurs pourraient considérer que huit champs constituent trop d’informations sur un périphérique mobile. Par conséquent, nous afficherons uniquement les champs principaux dans la vue de liste mobile. Les champs restants apparaîtront dans l’affichage détaillé que nous concevrons ultérieurement. Dans l’immédiat, nous ajouterons les champs suivants. Cliquez sur le signe plus (**+**) dans les colonnes à ajouter à la page mobile.
    - Nom du fournisseur
    - Total de la facture
    - Compte de facturation
    - Numéro de facture
    - Date de facture

    Une fois que les champs sont ajoutés, la page mobile doit ressembler à l’illustration suivante. 
    
    [![Page après l’ajout des champs.](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)

9.  Vous devez également ajouter les colonnes suivantes maintenant, de manière à ce que nous puissions activer les actions de workflow ultérieurement.
    - Afficher la tâche de fin
    - Afficher la tâche de délégation
    - Afficher la tâche de rappel
    - Afficher la tâche de rejet
    - Afficher la tâche d’exécution de la demande
    - Afficher la tâche de resoumission

10. Cliquez sur **Terminé** pour quitter le mode d’édition.
11. Cliquez sur **Précédent**, puis **Terminé** pour quitter l’espace de travail
12. Cliquez sur **Publier l’espace de travail** pour enregistrer votre travail.
13. Activez **Afficher le nombre total de factures sur la liste des factures fournisseur en attente** dans l’écran Paramètres Comptabilité fournisseur sous **Facture**. Notez que, uniquement en activant ce paramètre, les totaux de la facture sont calculés pour être affichés dans la page de liste des factures fournisseur en attente. Il s’agit d’une nouvelle fonctionnalité dans le cadre du correctif logiciel 3208224 de condition préalable.

### <a name="vendor-invoice-details"></a>Détails de la facture fournisseur

Pour déterminer la page Détails de facture pour la fonction mobile, utilisez la page **VendMobileInvoiceHeaderDetails**. Notez qu’en fonction du nombre de factures que vous avez dans votre système, cette page affiche l’ancienne facture (la facture qui a été créée préalablement). Pour trouver une facture spécifique, vous pouvez utiliser le filtre à gauche. Toutefois, nous n’avons pas besoin d’une facture spécifique pour cet exemple. Nous avons juste besoin de certaines données de factures afin que nous puissions concevoir la page mobile. 

[![Page Workflow.](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. Dans l’URL, remplacez le nom de l’option de menu par **VendMobileInvoiceHeaderDetails** pour ouvrir l’écran

2. Ouvrez le Concepteur mobile à partir du bouton **Paramètres** (engrenage)

3. Cliquez sur le bouton **Modifier** pour passer en mode d’édition dans l’espace de travail.

4. Sélectionnez la page **Mes factures fournisseur** créée précédemment, puis cliquez sur **Modifier**.

5. Sous l’onglet **Champs**, cliquez sur l’en-tête de colonne **Grille**.

6. Cliquez sur **Propriétés &gt; Ajouter une page**. **Remarque :** lorsque vous cliquez sur l’en-tête **Grille** et que vous ajoutez une page, la relation avec la page de détails est établie automatiquement.

7. Entrez un titre de page, tel que **Détails de la facture**, et une description, par exemple **Afficher les détails de l’en-tête et de la ligne**.

8. Cliquez sur **Sélectionner des champs**. Notez que l’ordre dans lequel vous ajoutez est l’ordre dans lequel les champs seront affichés à l’utilisateur final. La seule façon de modifier l’ordre des champs consiste à sélectionner tous les champs. 

9. Ajoutez les champs suivants à partir de l’en-tête selon la configuration requise pour ce scénario :
   - Nom du fournisseur
   - Total de la facture
   - Compte de facturation
   - Numéro de facture
   - Date de facture
   - Description de la facture
   - Date d’échéance
   - Devise de facturation

10. Ajoutez les champs suivants à partir de la grille de lignes dans la page :
    - Catégorie d’approvisionnement
    - Quantité
    - Prix unitaire
    - Montant net de ligne
    - Montant des honoraires

11. Une fois que l’ensemble des champs des deux étapes précédentes ont été ajoutés, cliquez sur **Terminé**. La page doit ressembler à l’illustration suivante.
    
    [![Illustration montrant des champs supplémentaires ajoutés.](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)

12. Cliquez sur **Terminé** pour quitter le mode d’édition.

13. Cliquez sur **Précédent**, puis **Terminé** pour quitter l’espace de travail

14. Cliquez sur **Publier l’espace de travail** pour enregistrer votre travail

### <a name="workflow-actions"></a>Actions de workflow

Pour ajouter des actions de workflow, utilisez la page **VendMobileInvoiceHeaderDetails**. Pour ouvrir cette page, remplacez le nom de l’option de menu dans l’URL, comme effectué précédemment. Ensuite, ouvrez le Concepteur mobile à partir du bouton **Paramètres** (engrenage). Procédez comme suit pour ajouter des actions de workflow dans la page de détails. Vous devez avoir des factures qui vous sont affectées dans l’état approprié pour vous permettre d’effectuer des actions de workflow en vue de les concevoir.

#### <a name="record-workflow-actions"></a>Enregistrer les actions de workflow
1.  Cliquez sur le bouton **Modifier** pour passer en mode d’édition dans l’espace de travail.
2.  Sélectionnez la page **Détails de la facture** créée précédemment, puis cliquez sur **Modifier**.
3.  Dans l’onglet **Actions**, cliquez sur **Ajouter une action**.
4.  Entrez un titre d’action, par exemple **Approuver**, et une description, par exemple **Approuver la facture**. Notez que le titre d’action que vous entrez ici devient le nom de l’action affiché pour l’utilisateur de l’application mobile.
5.  Cliquez sur **Terminé**.
6.  Cliquez sur **Sélectionner des champs**.
7.  Passez via le processus de workflow sur la page **VendMobileInvoiceHeaderDetails**, puis complétez l’action que vous avez souhaité enregistrer. Assurez-vous que vous entrez des commentaires de workflow lors de ce processus, afin qu’un champ de commentaires soit également inclus à l’expérience mobile.
8.  Une fois l’action de workflow exécutée, cliquez sur **Terminé** pour exécuter la tâche Sélectionner le champ.
9.  Cliquez sur **Terminé** pour quitter le mode d’édition.
10. Cliquez sur **Précédent**, puis **Terminé** pour quitter l’espace de travail
11. Cliquez sur **Publier l’espace de travail** pour enregistrer votre travail
12. Répétez les étapes précédentes pour enregistrer toutes les actions de workflow voulues. 

#### <a name="create-a-js-file"></a>Créez un fichier .js.
1. Ouvrez le Bloc-notes ou Microsoft Visual Studio, et collez le code suivant. Enregistrer le fichier au format .js. Ce code exécute ce qui suit :
    - Il masque les colonnes de workflow supplémentaires liées que nous avons ajoutées plus haut dans la page de liste mobile. Nous avons ajouté ces colonnes afin que l’application dispose de ces informations en contexte et puisse effectuer l’étape suivante.
    - Selon l’étape de workflow active, une logique permet d’afficher uniquement les actions.

    > [!NOTE]
    > Le nom des pages et d’autres contrôles dans le code doivent être identiques aux noms dans l’espace de travail.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }
    ```

2.  Téléchargez le fichier de code vers l’espace de travail en sélectionnant l’onglet **Logique**
3.  Cliquez sur **Terminé** pour quitter le mode d’édition.
4.  Cliquez sur **Précédent**, puis **Terminé** pour quitter l’espace de travail
5.  Cliquez sur **Publier l’espace de travail** pour enregistrer votre travail

### <a name="vendor-invoice-attachments"></a>Pièces jointes facture fournisseur

1. Cliquez sur le bouton **Paramètres** (engrenage) dans la partie supérieure droite de la page, puis cliquez sur **Application mobile**

2. Cliquez sur le bouton **Modifier** pour passer en mode d’édition dans l’espace de travail.

3. Sélectionnez la page <strong>Détails de la facture **créée précédemment, puis cliquez sur** Modifier</strong>.

4. Définissez l’option **Gestion des documents** sur **Oui** comme suit. **Remarque :** s’il n’existe aucune exigence d’afficher les pièces jointes sur le périphérique mobile, vous pouvez laisser cette option définie sur **Non**, qui est le paramètre par défaut.
   
   ![Gestion des documents.](./media/docmanagement-216x300.png)

5. Cliquez sur **Terminé** pour quitter le mode d’édition.

6. Cliquez sur **Précédent**, puis **Terminé** pour quitter l’espace de travail

7. Cliquez sur **Publier l’espace de travail** pour enregistrer votre travail

### <a name="vendor-invoice-line-distributions"></a>Répartitions des lignes de factures fournisseur

Les exigences pour ce scénario confirment qu’il n’y aura que des distributions au niveau ligne, et qu’une facture n’aura qu’une seule ligne. Comme ce scénario est unique, l’expérience utilisateur sur le périphérique mobile doit également être suffisamment simple pour que l’utilisateur ne descende pas de plusieurs niveaux pour afficher les répartitions. Les factures fournisseur incluent l’option pour afficher toutes les répartitions de l’en-tête de facture. Cette expérience est utile pour le scénario mobile. Par conséquent, nous emploierons la page **VendMobileInvoiceAllDistributionTree** pour concevoir cette partie du scénario mobile. 

> [!NOTE] 
> Connaître les besoins nous aide à définir les pages spécifiques à utiliser et comment optimiser exactement l’expérience de la mobilité pour l’utilisateur lorsque nous concevons le scénario. Dans le deuxième cas, nous utiliserons une page différente pour afficher les répartitions, car les exigences pour ce scénario diffèrent.

1.  Dans l’URL, remplacez le nom de l’option de menu, comme effectué précédemment. La page qui apparaît doit ressembler à l’illustration suivante.

    [![Page Toutes les répartitions.](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)

2.  Ouvrez le Concepteur mobile à partir du bouton **Paramètres** (engrenage)

3.  Cliquez sur le bouton **Modifier** pour passer en mode d’édition dans l’espace de travail. **Remarque :** deux nouvelles pages ont été créées automatiquement et s’affichent. Le système crée ces pages, si vous avez activé la gestion des documents dans la section précédente. Vous pouvez ignorer ces nouvelles pages.

4.  Cliquez sur **Ajouter une page**.

5.  Entrez un titre de page, tel que **Afficher la comptabilité** et une description, par exemple **Afficher la comptabilité pour la facture**.

6.  Cliquez sur **Terminé**.

7.  Sous l’onblet **Champs**, cliquez sur **Sélectionner des champs**, sélectionnez les champs suivants dans la page des répartitions, puis cliquez sur **Terminé** :
    1.  Montant
    2.  Devise
    3.  Compte général

    > [!NOTE] 
    > Nous n’avons pas sélectionné la colonne **Description** dans la grille des répartitions, car les conditions requises pour ce scénario ont confirmé que le prix global est le seul montant pour lequel il y aura des répartitions. Par conséquent, l’utilisateur ne demandera pas un autre champ pour déterminer le type de montant auquel la répartition est destinée. Toutefois, au prochain scénario, nous **utiliserons** ces informations, car les exigences pour ce scénario spécifient que d’autres types de montants disposent de répartitions (par exemple, taxe).

8.  Cliquez sur **Terminé** pour quitter le mode d’édition.

9.  Cliquez sur **Précédent**, puis **Terminé** pour quitter l’espace de travail

10. Cliquez sur **Publier l’espace de travail** pour enregistrer votre travail

#### <a name="adding-navigation-to-view-accounting-page"></a>Ajout de la navigation vers la page « Afficher la comptabilité »

La page **Afficher la comptabilité** n’est actuellement pas liée aux pages mobiles que nous avons conçues jusqu’à présent. Étant donné que l’utilisateur doit pouvoir naviguer vers la page **Afficher la comptabilité** à partir de la page **Détails de la facture** sur l’appareil mobile, nous devons fournir la navigation à partir de la page **Détails de la facture** vers la page **Afficher la comptabilité**. Nous établissons cette navigation à l’aide de la logique supplémentaire via Javascript.

1.  Ouvrez le fichier .js créé précédemment, et ajoutez les lignes qui sont en surbrillance dans le code suivant. Ce code permet d’effectuer deux choses :
    1.  Il permet de garantir que les utilisateurs ne peuvent pas accéder directement à la page **Afficher la comptabilité** à partir de l’espace de travail.
    2.  Il établit un contrôle de navigation à partir de la page **Détails de la facture** à la page **Afficher la comptabilité**.

    > [!NOTE] 
    > Le nom des pages et d’autres contrôles dans le code doivent être identiques aux noms dans l’espace de travail.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }
    ```
    
2.  Téléchargez le fichier de code vers l’espace de travail en sélectionnant l’onglet **Logique** pour remplacer le code précédent
3.  Cliquez sur **Terminé** pour quitter le mode d’édition.
4.  Cliquez sur **Précédent**, puis **Terminé** pour quitter l’espace de travail
5.  Cliquez sur **Publier l’espace de travail** pour enregistrer votre travail

### <a name="validation"></a>Validation

Dans votre périphérique mobile, ouvrez l’application, puis connectez-vous à votre instance. Vérifiez que vous vous connectez à la société par rapport à laquelle les factures fournisseur vous sont affectées pour la révision. Vous devriez pouvoir effectuer les actions suivantes :

-   Voir l’espace de travail **Mes approbations**.
-   Explorez l’espace de travail **Mes approbations** et consultez la page **Mes factures fournisseur**.
-   Explorez la page **Mes factures fournisseur** et consultez la liste des factures qui vous sont affectées.
-   Explorez l’une des factures, puis consultez les détails de la ligne d’en-tête et les détails de la ligne de facture.
-   Dans la page des détails, consultez le lien vers les pièces jointes, puis utilisez ce lien pour accéder à la liste des pièces jointes et afficher les pièces jointes.
-   Dans la page des détails, consultez le lien vers la page **Afficher la comptabilité**, puis utilisez ce lien pour accéder à la page des répartitions et afficher ces dernières.
-   Dans la page des détails, cliquez sur le menu **Actions** situé en bas de l’écran, et effectuez des actions de workflow qui s’appliquent à l’étape de workflow.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Conception d’un scénario complexe d’approbation des factures pour Fabrikam
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut du scénario</th>
<th>Répondre</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Quels champs de l’en-tête de la facture l’utilisateur souhaitera voir dans l’expérience mobile et dans quel ordre ?</td>
<td><ol>
<li>Nom du fournisseur</li>
<li>Montant de la facture</li>
<li>Compte de facturation</li>
<li>Numéro de facture</li>
<li>Date de facture</li>
<li>Description de la facture</li>
<li>Date d’échéance</li>
<li>Devise de facturation</li>
</ol></td>
</tr>
<tr class="even">
<td>Quels champs des lignes de la facture l’utilisateur souhaitera voir dans l’expérience mobile et dans quel ordre ?</td>
<td><ol>
<li>Catégorie d’approvisionnement</li>
<li>Quantité</li>
<li>Prix unitaire</li>
<li>Montant net de ligne</li>
<li>Montant des honoraires</li>
</ol></td>
</tr>
<tr class="odd">
<td>Combien de lignes de facture y-a-t-il dans une facture ? Appliquez la règle 80-20 ici et effectuez une optimisation pour les 80 %%.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Les utilisateurs souhaiteront-ils voir les répartitions comptables (codage de facture) sur l’appareil mobile pendant les révisions ?</td>
<td>Oui</td>
</tr>
<tr class="odd">
<td>Combien de répartitions comptables (prix global, taxes, frais, etc.) y-a-t-il pour une ligne de facture ? Là aussi, appliquez la règle 80-20.</td>
<td>Prix global : 2 Taxe : 2 Frais : 2</td>
</tr>
<tr class="even">
<td>Les factures ont-elles également les répartitions comptables dans l’en-tête de facture ? Dans ce cas, ces répartitions comptables doivent-elles être disponibles dans le périphérique ?</td>
<td>Non utilisé</td>
</tr>
<tr class="odd">
<td>Les utilisateurs souhaiteront-ils afficher les pièces jointes pour la facture sur le périphérique ?</td>
<td>Oui</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>Étapes suivantes

Les modifications suivantes peuvent être effectuées pour le scénario 1, selon les exigences du scénario 2. Vous pouvez utiliser cette section pour améliorer votre expérience d’application mobile.

1.  Étant donné que plus de lignes de facturation sont attendues dans le scénario 2, les modifications suivantes à la conception aideront à optimiser l’expérience utilisateur sur l’appareil mobile :
    1.  Au lieu des lignes de facture affichées dans la page de détails (comme dans le scénario 1), les utilisateurs peuvent choisir d’afficher des lignes sur une page mobile distincte.
    2.  Comme plusieurs lignes de facture sont prévues dans ce scénario, si la page **VendMobileInvoiceAllDistributionTree** est utilisée pour concevoir la page des répartitions pour la fonction mobile (comme dans le scénario 1), il peut être perturbant pour l’utilisateur de corréler des lignes aux répartitions. Utilisez par conséquent la page **VendMobileInvoiceLineDistributionTree** pour concevoir la page des répartitions.
    3.  Idéalement, les répartitions doivent être affichées dans le contexte d’une ligne de facture dans ce scénario. Par conséquent, veillez à ce que l’utilisateur puisse explorer une ligne pour afficher la page des répartitions. Utilisez la fonctionnalité de lien de page pour établir le suivi, tout comme vous l’avez fait pour les pages d’en-tête et de détails dans le scénario 1.

2.  Comme plusieurs types de montant sont prévus sur les répartitions dans le scénario 2 (taxes, frais, etc.), il est utile d’afficher la description du type de montant. (Nous avons omis ces informations dans le scénario 1).






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
