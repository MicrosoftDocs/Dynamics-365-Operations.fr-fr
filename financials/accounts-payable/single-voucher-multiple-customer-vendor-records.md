---
title: "N° de document unique avec plusieurs enregstrements client ou fournisseur"
description: "Cette rubrique fournit une vue d'ensemble de ce qui se produit lorsque vous validez un N° de document unique avec plusieurs enregistrements client ou fournisseur. Cette fonctionnalité sera arrêtée dans les futures versions de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Par conséquent, il n'est pas recommandé d'utiliser cette méthode de validation en raison de l'impact comptable qu'elle a sur le traitement des règlements."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 222534
ms.assetid: d4df11ce-4d36-4c66-8230-f5fc58e021bc
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 31040ff14b99a9b351268feb88698ac706befb55
ms.contentlocale: fr-fr
ms.lasthandoff: 06/13/2017

---

# <a name="single-voucher-with-multiple-customer-or-vendor-records"></a>N° de document unique avec plusieurs enregstrements client ou fournisseur

[!include[banner](../includes/banner.md)]


Cette rubrique fournit une vue d'ensemble de ce qui se produit lorsque vous validez un N° de document unique avec plusieurs enregistrements client ou fournisseur. Cette fonctionnalité sera arrêtée dans les futures versions de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Par conséquent, il n'est pas recommandé d'utiliser cette méthode de validation en raison de l'impact comptable qu'elle a sur le traitement des règlements. 

Certains exemples courants dans lesquels un N° de document est utilisé pour plusieurs clients ou fournisseurs incluent les transferts de solde entre clients, et les soldes de compensation entre clients et fournisseurs de la même organisation. 

Un N° de document contenant plusieurs clients ou fournisseurs peut être entré à l'aide d'une des méthodes suivantes :

-   Utilisation d'un journal dont l'option **Un seul N° de document** est sélectionnée afin que chaque ligne ajoutée au journal soit incluse dans le même N° de document.
-   Utilisation d'un N° de document multiligne, dans lequel il n'existe aucun compte général de contrepartie, avec plusieurs clients ou fournisseurs.
-   Saisie d'un N° de document avec le compte et le compte de contrepartie étant fournisseur/fournisseur, client/client, fournisseur/client, ou client/fournisseur.

Cette rubrique présente de quelle manière le règlement sera traité lorsqu'un N° de document avec plusieurs enregistrements client ou fournisseur est validé. En outre, cette rubrique fournit des solutions pour vous aider à comprendre comment éviter d'utiliser un N° de document avec plusieurs clients ou fournisseurs. Ainsi, il existe des exemples qui illustrent deux scénarios de règlement courants qui seront influencés par l'utilisation d'un N° de document avec plusieurs clients ou fournisseurs :

-   Comptabilité de l'escompte de règlement
-   Comptabilité de la réévaluation

## <a name="how-does-settlement-impact-single-voucher-usage"></a>Comment le règlement affecte l'utilisation d'un N° de document unique
Lors de la validation d'un N° de document contenant plusieurs enregistrements client ou fournisseur, un N° de document comptable unique qui contient plusieurs soldes de Comptabilité client et de Comptabilité fournisseur. Au cours du processus de règlement, les écritures comptables d'origine sont utilisées pour créer des écritures comptables pour l'escompte de règlement, les profits et les pertes non réalisés, les profits et les pertes réalisés, et l'exonération du compte collectif du document original. Par exemple, si un escompte de règlement est prélevé lors du règlement d'un paiement fournisseur dans une facture, la comptabilité d'escompte de règlement doit valider dans le compte général de la Comptabilité fournisseur à partir de la facture d'origine. Si la facture d'origine a été validée dans un N° de document contenant plusieurs enregistrements fournisseur, la comptabilité d'origine est résumée. Dans ce cas, du fait qu'il n'est pas possible d'accéder à l'écriture comptable détaillée de chaque transaction fournisseur dans le N° de document unique, il n'est pas possible de déterminer la façon dont l'utilisateur a prévu que l'escompte de règlement soit comptabilisé.

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-cash-discount-accounting"></a>Un N° de document avec plusieurs fournisseurs et l'impact sur la comptabilité d'escompte de règlement

Dans l'exemple suivant, plusieurs factures fournisseur sont enregistrées dans la comptabilité sur un N° de document unique sur la page **Journal des opérations diverses**. Ces factures sont distribuées entre plusieurs dimensions de compte.

|             |                  |              |                 |           |            |
|-------------|------------------|--------------|-----------------|-----------|------------|
| **Pièce justificative** | **Type de compte** | **Compte**  | **Description** | **Débit** | **Crédit** |
| GNJL001     | Fournisseur           | 1 001         | INV1            |           | 100,00     |
| GNJL001     | Fournisseur           | 1 001         | INV2            |           | 200,00     |
| GNJL001     | Fournisseur           | 1 001         | INV3            |           | 300,00     |
| GNJL001     | Comptabilité           | 606300-001-- | INV1            |   50,00   |            |
| GNJL001     | Comptabilité           | 606300-002-- | INV1            |   50,00   |            |
| GNJL001     | Comptabilité           | 606300-003-- | INV2            | 200,00    |            |
| GNJL001     | Comptabilité           | 606300-004-- | INV3            | 300,00    |            |

Après la validation, un N° de document est créé.

|             |              |                  |                                    |
|-------------|--------------|------------------|------------------------------------|
| **Pièce justificative** | **Compte**  | **Type de validation** | **Montant dans la devise de transaction** |
| GNJL001     | 606300-001-- | Journal comptable   | 50,00                              |
| GNJL001     | 606300-002-- | Journal comptable   | 50,00                              |
| GNJL001     | 606300-003-- | Journal comptable   | 200,00                             |
| GNJL001     | 606300-004-- | Journal comptable   | 300,00                             |
| GNJL001     | 200110-001-  | Solde fournisseur   | -100,00                            |
| GNJL001     | 200110-001-  | Solde fournisseur   | -200,00                            |
| GNJL001     | 200110-001-  | Solde fournisseur   | -300,00                            |

Notez que le N° de document contient trois entrées pour le type de validation du solde fournisseur dans le N° de document unique. Il n'est pas possible d'indiquer que le débit de 50,00 pour 606300-001 et le débit de 50,00 pour 606300-002 sont destinés à la contrepartie de l'écriture du solde fournisseur de 200110-001. Cela est dû au fait que l'utilisateur a entré les différents enregistrements fournisseur sur un N° de document unique.

Avec cet exemple, nous pouvons analyser l'impact de l'utilisation d'un N° de document sur la comptabilité de règlement en aval. Supposons que vous payiez 197,00 sur la facture de 200,00, avec un escompte de règlement de 3,00. Notez que la valeur du compte d'escompte de règlement est allouée à toutes les dimensions des comptes de dépenses du N° de document de facture. Cela est dû au fait qu'un N° de document a été utilisé pour valider la facture ci-dessus, sans indication sur la façon dont l'utilisateur a prévu que les distributions de dépense correspondent au solde fournisseur dans le N° de document unique.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Pièce justificative** | **Compte**  | **Type de validation**     | **Débit** | **Crédit** |
| APPAYM001   | 200110-001-  | Solde fournisseur       | 197.00    |            |
| APPAYM001   | 110110-001-  | Banque                 |           | 197.00     |
| 14000056    | 520200-001-- | Fournisseur - Escompte de règlement |           | 0.25       |
| 14000056    | 520200-002-- | Fournisseur - Escompte de règlement |           | 0.25       |
| 14000056    | 520200-003-- | Fournisseur - Escompte de règlement |           | 1,00       |
| 14000056    | 520200-004-- | Fournisseur - Escompte de règlement |           | 1.50       |
| 14000056    | 200110-001-  | Solde fournisseur       | 3,00      |            |

Si l'utilisateur n'est pas satisfait de l'escompte de règlement allouée à toutes les répartitions de dépense de la facture d'origine, plutôt qu'un N° de document, plusieurs N° de documents doivent être utilisés pour enregistrer les factures. Voici un exemple de la procédure à utiliser pour entrer plusieurs N° de document dans la comptabilité, au lieu d'utiliser un N° de document, comme indiqué au début de cet exemple.

|             |                  |              |                 |           |            |                 |                    |
|-------------|------------------|--------------|-----------------|-----------|------------|-----------------|--------------------|
| **Pièce justificative** | **Type de compte** | **Compte**  | **Description** | **Débit** | **Crédit** | **Type de contrepartie** | **Compte de contrepartie** |
| GNJL001     | Fournisseur           | 1 001         | INV1            |           | 100,00     | Comptabilité          | &lt;vide&gt;      |
| GNJL001     | Comptabilité           | 606300-001-- | INV1            |   50,00   |            | Comptabilité          | &lt;vide&gt;      |
| GNJL001     | Comptabilité           | 606300-002-- | INV1            |   50,00   |            | Comptabilité          | &lt;vide&gt;      |
| GNJL002     | Fournisseur           | 1 001         | INV2            |           | 200,00     | Comptabilité          | 606300-003--       |
| GNJL003     | Fournisseur           | 1 001         | INV3            |           | 300,00     | Comptabilité          | 606300-004--       |

Désormais, lorsque INV2 est payée, l'écriture suivante est effectuée. Notez que les dimensions financières de l'escompte de règlement suivent les dimensions financières de la dépense associée.

|             |              |                      |           |            |
|-------------|--------------|----------------------|-----------|------------|
| **Pièce justificative** | **Compte**  | **Type de validation**     | **Débit** | **Crédit** |
| APPAYM001   | 200110-001-  | Solde fournisseur       | 197.00    |            |
| APPAYM001   | 110110-001-  | Banque                 |           | 197.00     |
| 14000056    | 520200-003-- | Fournisseur - Escompte de règlement |           | 3,00       |
| 14000056    | 200110-001-  | Solde fournisseur       | 3,00      |            |

### <a name="one-voucher-with-multiple-vendors-and-the-impact-on-realized-gainloss-accounting"></a>Un N° de document avec plusieurs fournisseurs et l'impact sur la comptabilité des gains/pertes réalisés

|             |                  |             |                 |           |            |                  |              |
|-------------|------------------|-------------|-----------------|-----------|------------|------------------|--------------|
| **Pièce justificative** | **Type de compte** | **Compte** | **Description** | **Débit** | **Crédit** | **Type de compte** | **Compte**  |
| GNJL001     | Fournisseur           | 1 001        | INV1            |           | 100,00     | Comptabilité           | 606300-001-- |
| GNJL001     | Fournisseur           | 1 001        | INV2            |           | 200,00     | Comptabilité           | 606300-002-- |

Dans l'exemple suivant, plusieurs factures fournisseur sont enregistrées dans la comptabilité sur un N° de document unique sur la page **Journal des opérations diverses**. Ces factures sont distribuées entre plusieurs dimensions de compte. Après la validation, un N° de document est créé.

|             |              |                  |                                          |                                         |
|-------------|--------------|------------------|------------------------------------------|-----------------------------------------|
| **Pièce justificative** | **Compte**  | **Type de validation** | **Montant dans la devise de transaction (EUR)** | **Montant en devise comptable (USD)** |
| GNJL001     | 606300-001-- | Journal comptable   | 100,00                                   | 114.00                                  |
| GNJL001     | 606300-002-- | Journal comptable   | 200,00                                   | 228.00                                  |
| GNJL001     | 200110-001-  | Solde fournisseur   | -100,00                                  | -114,00                                 |
| GNJL001     | 200110-001-  | Solde fournisseur   | -200,00                                  | -228,00                                 |

Notez que le N° de document contient deux entrées pour le type de validation du solde fournisseur dans le N° de document unique. Il n'existe aucune façon d'indiquer que le débit de 606300-001 est prévu pour compenser l'entrée du solde fournisseur de 100,00 dans 200110-001. Cela est dû au fait que l'utilisateur a entré les différents enregistrements fournisseur sur un N° de document unique. 

Avec cet exemple, nous pouvons analyser l'impact de l'utilisation d'un N° de document sur la comptabilité de règlement en aval. Supposons que la devise comptable est USD et que les transactions ci-dessus ont été validées dans une devise de transaction d'EUR. Supposons que vous payiez l'intégralité de la facture de 200,00 EUR mais que vous rencontriez une perte réalisée suite à une différence de taux de change entre le moment où vous avez validé la facture et le paiement. Notez que la valeur du compte de perte réalisée est allouée à toutes les dimensions des comptes de dépenses du N° de document de facture. Dans ce cas, les dimensions 001 et 002 ont été affectées, même si la perception de l'utilisateur est peut-être que seul 002 appartient au compte de dépenses dans la facture en cours de réglement. Cela est dû au fait qu'un N° de document a été utilisé pour valider la facture ci-dessus, sans indication sur la façon dont l'utilisateur a prévu que les distributions de dépense correspondent au solde fournisseur dans le N° de document unique.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Pièce justificative** | **Compte** | **Type de validation**   | **Montant dans la devise de transaction (EUR)** | **Montant en devise comptable (USD)** |
| APPAYM001   | 200110-001- | Solde fournisseur     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Banque               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-001- | Perte de taux de change | 0,00                                     | 0.67                                    |
| 14000056    | 801300-002- | Perte de taux de change | 0,00                                     | 1.33                                    |
| 14000056    | 200110-001- | Solde fournisseur     |                                          | -2,00                                   |

Si l'utilisateur n'est pas satisfait de la perte de taux de change allouée à toutes les répartitions de dépense de la facture d'origine, plutôt qu'un N° de document, plusieurs N° de documents doivent être utilisés pour enregistrer les factures. Voici un exemple de la procédure à utiliser pour entrer plusieurs N° de document dans la comptabilité, au lieu d'utiliser un N° de document, comme indiqué au début de cet exemple.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Pièce justificative** | **Type de compte** | **Compte** | **Description** | **Débit** | **Crédit** | **Type de contrepartie** | **Compte de contrepartie** |
| GNJL002     | Fournisseur           | 1 001        | INV1            |           | 100,00     | Comptabilité          | 606300-001--       |
| GNJL003     | Fournisseur           | 1 001        | INV2            |           | 200,00     | Comptabilité          | 606300-002--       |

Désormais, lorsque INV2 est payée, l'écriture suivante est effectuée. Notez que les dimensions financières de la perte de taux de change suivent les dimensions financières de la dépense associée.

|             |             |                    |                                          |                                         |
|-------------|-------------|--------------------|------------------------------------------|-----------------------------------------|
| **Pièce justificative** | **Compte** | **Type de validation**   | **Montant dans la devise de transaction (EUR)** | **Montant en devise comptable (USD)** |
| APPAYM001   | 200110-001- | Solde fournisseur     | 200,00                                   | 230.00                                  |
| APPAYM001   | 110110-001- | Banque               | -200,00                                  | -230,00                                 |
| 14000056    | 801300-002- | Perte de taux de change | 0,00                                     | 2.00                                    |
| 14000056    | 200110-001- | Solde fournisseur     |                                          | -2,00                                   |

## <a name="one-voucher-for-balance-transfers-and-netting-scenarios"></a>Un N° de document pour les transferts de bilan et les scénarios de compensation
Deux scénarios utilisés couramment qui utilisent un N° de document contenant plusieurs clients ou fournisseurs incluent des transferts de solde à partir d'un client/fournisseur vers un autre client/fournisseur, et la compensation d'un client et d'un fournisseur de la même organisation. Les deux exemples suivants illustrent la méthode conseillée pour entrer ces scénarios dans Finance and Operations, comme alternative à leur entrée dans un N° de document. 

Un *transfert de solde* est un N° de document avec plusieurs clients, entrés afin de transférer le solde d'un client vers un autre client (identique pour les fournisseurs). Ce scénario peut survenir lorsque la responsabilité du règlement de la facture passe à un tiers, telle qu'une société enfant déplaçant la responsabilité à une société parente. 

Cet exemple suppose une vente au cours de laquelle le client peut bénéficier d'un escompte de règlement si le paiement est effectué sous 10 jours. Le client de cet exemple utilise une société d'assurance qui sera responsable du paiement de la facture. La compagnie d'assurance est paramétrée comme deuxième client dans le système. Le solde du client d'origine est transféré vers la compagnie d'assurance, qui paie la facture, en utilisant un escompte de règlement de 2 % pour le paiement au cours de la période de remise. 

Pour illustrer cela, supposons que la vente suivante est effectuée au client ACME. Les écritures comptables suivantes représentent la vente.

|                    |                  |           |            |
|--------------------|------------------|-----------|------------|
| **Compte général** | **Type de validation** | **Débit** | **Crédit** |
| 401100-002-023-    | Produit          |           | 100        |
| 130100-002-        | Client - Solde | 100       |            |

Ensuite, l'utilisateur transfère le solde dû d'ACME vers la compagnie d'assurance, dans un N° de document du journal des paiements de la Comptabilité fournisseur. Dans Finance and Operations, la compagnie d'assurance est paramétrée comme assurance du client.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Pièce justificative** | **Type de compte** | **Compte** | **Description** | **Débit** | **Crédit** | **Type de contrepartie** | **Compte de contrepartie** |
| ARPAYM001   | Client          | ACME        | Transfert        |           | 100,00     | Client         | Assurance          |

Notez que l'entrée ci-dessus est contenue dans un N° de document. Ce N° de document contient deux enregistrements client. Le N° de document suivant est créé lorsque l'écriture comptable ci-dessus est validée.

|             |             |                  |                                    |
|-------------|-------------|------------------|------------------------------------|
| **Pièce justificative** | **Compte** | **Type de validation** | **Montant dans la devise de transaction** |
| ARPAYM001   | 130100-002- | Client - Solde | 100,00                             |
| ARPAYM001   | 130100-002- | Client - Solde | -100,00                            |

Ensuite, supposez que vous recevez un paiement du client d'assurance pour 98,00 et que vous décidez de régler le paiement avec la facture créée par le transfert de solde. Cela entraîne la validation du N° de document suivant. Il peut y avoir une attente que le règlement utilise les dimensions financières de la facture d'origine, mais ce n'est pas possible car il n'y a pas de document de facture pour le client d'assurance. Notez que par défaut, les dimensions de répartition sur l'escompte de règlement proviennent de la transaction client créée lors du transfert, pas du compte de produit de la facture d'origine. La valeur par défaut est le résultat de l'utilisation d'un N° de document pour transférer les soldes.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Pièce justificative** | **Compte** | **Type de validation** | **Débit** | **Crédit** |
| ARPAYM002   | 110110-002- | Banque             | 98.00     |            |
| ARPAYM002   | 130100-002- | Client - Solde |           | 98.00      |

Dans le N° de document associé pour l'escompte de règlement, la valeur par défaut de la dimension financière provient de la transaction client créée lors du transfert, car le transfert comporte plusieurs clients.

|             |             |                        |           |            |
|-------------|-------------|------------------------|-----------|------------|
| **Pièce justificative** | **Compte** | **Type de validation**       | **Débit** | **Crédit** |
| ARP-00001   | 403300-002- | Client - Escompte de règlement | 2.00      |            |
| ARP-00001   | 130100-002- | Client - Solde       |           | 2.00       |

Si l'utilisateur n'est pas satisfait de la valeur par défaut des dimensions financières pour l'escompte de règlement, au lieu d'un N° de document, plusieurs N° de documents doivent être utilisés pour enregistrer le transfert de solde. Ce scénario doit être effectué lors de la création d'un avoir pour le client dont le solde est déplacé DE, et une note ou une facture de débit créée pour le client VERS lequel le solde est déplacé. L'exemple suivant montre comment plusieurs N° de documents peuvent être entrés dans le journal des paiements de la Comptabilité client pour transférer le solde, au lieu d'utiliser un N° de document, comme illustré précédemment dans cet exemple.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Pièce justificative** | **Type de compte** | **Compte** | **Description** | **Débit** | **Crédit** | **Type de contrepartie** | **Compte de contrepartie** |
| ARPAYM001   | Client          | ACME        |                 |           | 100,00     | Comptabilité          | 401100-002-023-    |
| ARPAYM002   | Client          | Assurance   |                 | 100,00    |            | Comptabilité          | 401100-002-023-    |

Cela signifie que lorsque le client d'assurance paie 98,00 avec le N° de document ARPAYM02, les dimensions financières correctes de l'écriture de compte général du N° de document ARPAYM002 seront utilisées.

|             |             |                  |           |            |
|-------------|-------------|------------------|-----------|------------|
| **Pièce justificative** | **Compte** | **Type de validation** | **Débit** | **Crédit** |
| ARPAYM003   | 110110-002- | Banque             | 98.00     |            |
| ARPAYM003   | 130100-002  | Client - Solde |           | 98.00      |

Sur le N° de document associé de l'escompte de règlement, les dimensions financières sont utilisées dans le compte de produit de compensation affiché sur le N° de document ARPAYM002.

|             |                 |                        |           |            |
|-------------|-----------------|------------------------|-----------|------------|
| **Pièce justificative** | **Compte**     | **Type de validation**       | **Débit** | **Crédit** |
| ARP-00001   | 403300-002-023- | Client - Escompte de règlement | 2.00      |            |
| ARP-00001   | 130100-002-     | Client - Solde       |           | 2.00       |

### 

## <a name="one-voucher-with-a-netting-for-multiple-customers-and-vendors"></a>Un N° de document avec un compensation de plusieurs clients et fournisseurs
La compensation peut être utile lorsqu'une organisation achète et vend à la même société. Plutôt que de règler les factures fournisseur et d'attendre de recevoir le paiement des factures client, les factures fournisseur et client sont compensées. La transaction de compensation est réglée par rapport aux soldes restants. 

Pour illustrer cela, supposons que le fournisseur 1001 et le client US-008 soient la même entité, de sorte que votre organisation veut compenser les soldes client et fournisseur avant de payer/recevoir le solde restant. Supposons que l'enregistrement client doit 75,00 EUR et l'enregistrement fournisseur a un solde dû de 100,00 EUR, ce qui signifie que vous préfèrez compenser les soldes et payer uniquement 25,00 EUR au fournisseur. Supposons également que la devise comptable est USD. Dans ce cas, une transaction de compensation est entrée sur un N° de document dans le journal des paiements de la Comptabilité fournisseur.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Pièce justificative** | **Type de compte** | **Compte** | **Description** | **Débit** | **Crédit** | **Type de contrepartie** | **Compte de contrepartie** |
| APPAYM001   | Fournisseur           | 1 001        | Compensation         |  75,00    |            | Client         | US-008             |

Pour éviter les problèmes indésirables de futures règlements pour cette transaction, au lieu d'utiliser un N° de document, plusieurs N° de documents doivent être entrés dans le journal pour enregistrer la transaction de compensation. Notez que les soldes client et fournisseurs sont compensés par un compte de compensation unique afin d'éviter l'utilisation d'un N° de document contenant plusieurs soldes client et fournisseur.

|             |                  |             |                 |           |            |                 |                    |
|-------------|------------------|-------------|-----------------|-----------|------------|-----------------|--------------------|
| **Pièce justificative** | **Type de compte** | **Compte** | **Description** | **Débit** | **Crédit** | **Type de contrepartie** | **Compte de contrepartie** |
| 001         | Client          | US-008      |                 |           |  75,00     | Comptabilité          | 999999---          |
| 002         | Fournisseur           | 1 001        |                 |  75,00    |            | Comptabilité          | 999999---          |

 




