---
    title: How to Set Up Electronic Document Sending and Receiving | Microsoft Docs
    description: As an alternative to emailing as file attachments, you can send and receive business documents electronically.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 10/01/2019
    ms.author: sgroespe

---
# Nastavení odesílání a přijímání elektronického dokladu
Jako alternativu k odesílání obchodních dokladů v přílohách e-mailů můžete obchodní dokumenty zasílat a přijímat elektronicky. Elektronickým dokladem se rozumí soubor vyhovující standardu představující obchodní doklad, jako například faktura od dodavatele, která může být obdržena a převedena na nákupní fakturu v [!INCLUDE[d365fin](includes/d365fin_md.md)]. Výměnu elektronických dokladů mezi dvěma obchodními partnery provádí externí poskytovatel služeb pro výměnu dokladů. Obecná verze [!INCLUDE[d365fin](includes/d365fin_md.md)] podporuje odesílání a přijímání elektronických faktur a dobropisů ve formátu PEPPOL, který je podporován největšími poskytovateli služeb pro výměnu dokladů. Hlavní poskytovatel služeb pro výměnu dokladů je předem nakonfigurován a připraven k nastavení ve vaší společnosti.

Z PDF nebo souborů s obrázky reprezentujících příchozí doklady můžeme nechat externí službu OCR (Optical Character Recognition - Optické rozpoznávání znaků) vytvořit elektronické doklady, které pak můžeme převést na došlé doklady v [!INCLUDE[d365fin](includes/d365fin_md.md)], stejně jako elektronické došlé doklady formátu PEPPOL. Pokud například od dodavatele obdržíte fakturu ve formátu PDF, můžete ji odeslat do služby OCR ze stránky  **Došlé doklady**. Po několika sekundách obdržíte soubor zpět jako elektronickou fakturu, kterou lze pro dodavatele převést na nákupní fakturu. Pokud soubor odešlete do služby OCR pomocí e-mailu, bude automaticky vytvořen nový záznam příchozího dokladu, v momentě, kdy obdržíte elektronický doklad zpět.

Formát elektronického dokumentu **PEPPOL** je předkonfigurován tak, aby vám umožnil odesílat elektronické faktury a dobropisy ve formátu PEPPOL. Nejprve je nutné nastavit různá hlavní data, například informace o společnosti, zákazníky, zboží a měrné jednotky.  Používají se k identifikaci obchodních partnerů a zboží, při převádění dat v polích v [!INCLUDE[d365fin](includes/d365fin_md.md)] na prvky v odchozích dokladech. Nakonec musíte vybrat formát na stránce **Formát elektronických dokumentů** pro každého zákazníka, kterému pošlete elektronické dokumenty PEPPOL. Více informací viz [Odeslání elektronických dokladů](sales-how-to-send-electronic-documents.md).

Definice výměny dat **PEPPOL – Faktura** a **PEPPOL – Dobropisy** jsou předkonfigurovány, aby vám umožnily příjímat elektroincké faktury a dobropisy ve formátu PEPPOL. Nejprve je nutné nastavit různá hlavní data, například informace o společnosti, dodavatele, zboží a měrné jednotky. Tyto položky slouží k identifikaci obchodních partnerů a zboží při převádění dat v prvcích příchozích dokumentů do polí v [!INCLUDE[d365fin](includes/d365fin_md.md)]. Nakonec musíte vybrat definici výměny dat na stránce **Došlé doklady** pro každý došlý elektronický doklad, který chcete převést na nákupní doklad v [INCLUDE[d365fin](includes/d365fin_md.md)].

Definice výměny dat **OCR – faktura** je předkonfigorována tak, aby umožňovala přijímat elektronické doklady, které jsou generovány službou OCR. Chcete-li například obdržet fakturu jako elektronický doklad OCR, nastavíte hlavní data a potom dokument zpracujete stejně, jako při příjmu elektronického dokumentu PEPPOL. Více informací viz [Použití funkce OCR k převedení souborů PDF a obrázkových souborů do elektronických dokumentů](across-how-use-ocr-pdf-images-files.md).

Předkonfigurované služby pro výměnu dokumentů a OCR musí být před odesláním nebo přijetím povoleny. Více informací viz [Nastavení služby směnných kurzů](across-how-to-set-up-a-document-exchange-service.md).

Téma obsahuje následující postupy:

* Nastavení společnosti pro odesílání a přijímání elektronických dokladů
* Nastavení účtování DPH pro odesílání a přijímání elektronických dokladů
* Nastavení zemí/oblastí pro odesílání a přijímání elektronických dokladů
* Nastavení položek pro odesílání a přijímání elektronických dokladů
* Nastavení měrných jednotek pro odesílání a přijímání elektronických dokladů
* Nastavení zákazníků pro odesílání elektronických dokladů
* Výběr formátu elektronického dokladu **PEPPOL** pro elektronické odesílání dokladů
* Nastavení dodavatelů pro příjem elektronických dokumentů
* Výběr definice výměny dat**PEPPOL – Faktura** pro příjem elektronických dokladů 
* Nastavení finančního účtu pro použití na nových řádcích nákupní faktury pro ne\existující a ne\identifikovatelné položky

### Nastavení společnosti pro odesílání a přijímání elektronických dokladů
1. V poli **Hledat**, zadejte **Informace o společnosti**, a pak zvolte související odkaz.
2. Na záložce s náhledem **Obecné** vyplňte pole, podle popisu v následující tabulce.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **GLN** | Identifikujte svou společnost. <br /><br /> Například, při odesílání elektronických faktur ve formátu PEPPOL se hodnota v tomto poli používá k naplnění prvku **EndPointID** v souboru pod uzlem **AccountingSupplierParty**. Číslo je založeno na standardu GS1, který je kompatibilní s ISO 6523. |
   | **DIČ** | Určete DIČ vaší společnosti. |
   | **Centrum odpovědnosti** | Pokud je vaše společnost nastavena s centrem odpovědnosti, ujistěte se, že je vyplněno pole** Kód země nebo ** oblasti. |

### Nastavení účtování DPH pro odesílání a přijímání elektronických dokladů
1. Do pole **Hledat**, zadejte **Nastavení účtování DPH** a poté vyberte související odkaz.
2. Pro každý řádek nastavení účtování DPH, který budete používat pro elektronické doklady, vyplňte pole popsané v následující tabulce.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **Kategorie daně** | Určuje kategorii DPH ve spojení<br /><br /> Například když posíláte elektronické faktury ve formátu PEPPOL, hodnota v tomto poli je použita k naplnění prvku **TaxApplied** v souboru pod uzlem **AccountingSupplierParty**. Číslo je založeno na standardu UNCL5305. |

### Nastavení zemí/oblastí pro odesílání a přijímání elektronických dokladů
1. V poli **Hledat**, zadejte **Země/oblasti**, a pak zvolte související odkaz.
2. Pro zemi, nebo oblast, každého subjektu se kterým budete vyměňovat elektronické dokumenty, vyplňte pole, jak je popsáno v následující tabulce.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **Schéma DPH** | Identify the national body that issues the VAT registration number for the country\/region in connection with electronic document sending.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **SchemeID** attribute for the **EndPointID** element under both the **AccountingSupplierParty** node and the **AccountingCustomerParty** in the file.<br /><br /> The **VAT Scheme** field is only used if the **GLN** field on the **Company Information** page is not filled. **Note:**  The value in the **Code** field on the **Countries\/Regions** page must comply with ISO 3166\-1:Alpha2. |

### Nastavení položek pro odesílání a přijímání elektronických dokladů
1. In the **Search** box, enter **Items**, and then choose the related link.
2. For each item that you buy or sell on electronic documents, fill the field as described in the following table.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **GTIN** | Identifies the item in connection with electronic document sending and receiving. For the PEPPOL format, the field is used as follows:<br /><br /> If the **StandardItemIdentification\/ID** element has the **SchemeID** attribute set to **GTIN**, then the element is mapped to the **GTIN** field on the item card. |

### Nastavení měrných jednotek pro odesílání a přijímání elektronických dokladů
1. In the **Search** box, enter **Units of Measure**, and then choose the related link.
2. For each unit of measure that you will use for items on electronic documents, fill the field as described in the following table.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **International Standard Code** | Specify the unit of measure code expressed according to the UNECERec20 standard in connection with sending of electronic documents.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **unitCode** attribute of the **InvoicedQuantity** element under the **InvoiceLine** node. **Note:**  If the **Unit of Measure** field on the sales line is empty, the UNECERe20 standard value for “Piece” \(H87\) is inserted by default. For more information and a list of valid unit of measure codes, see [Recommendation No. 20 \- Units of Measure used in International Trade](https://www.unece.org/fileadmin/DAM/cefact/recommendations/rec20/rec20_rev3_Annex2e.pdf). |

### Nastavení zákazníků pro odesílání elektronických dokladů
1. In the **Search** box, enter **Customers**, and then choose the related link.
2. For each customer who you will send electronic documents to, fill the fields as described in the following table.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **GLN** | Identify the customer.<br /><br /> For example, when you send electronic invoices in the PEPPOL format, the value in this field is used to populate the **EndPointID** element under the **AccountingCustomerParty** node in the file. The number is based on the GS1 standard, which is compliant with ISO 6523.<br /><br /> If the **GLN** field is blank, the value in the **VAT Registration No.** field is used. |
   | **DIČ** | Specify the customer's VAT registration number. **Tip:**  Choose the DrillDown button to use the web service that verifies if the number exists in the country’s company register. |
   | **Centrum odpovědnosti** | If the customer is set up with a responsibility center, make sure that the **Country/Region Code** field is filled. |

   You can set up each customer with a preferred method of sending business documents, so that you do not have to select a sending option every time that you send a document to the customer. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

### To select the PEPPOL electronic document format for electronic document sending
1. In the **Search** box, enter **Document Sending Profiles**, and then choose the related link.
2. Open an existing document sending profile, or create a new one. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).
3. On the **Document Sending Profile** page, choose the **Electronic Format**, select the line for PEPPOL, and then choose **OK**.
4. In the **Electronic Document** field, select **Yes (Through Document Exchange Service)**.

   > [!NOTE]
   > [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically detects if the document is an invoice or a credit memo and applies the PEPPOL format accordingly.

5. To make this document sending profile apply to all customers, select the **Default** check box on the **General** FastTab. To make it apply to specific customers only, fill the **Document Sending Profile** field on the customer cards in question. For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).

   You can now send the electronic document containing the converted data. For more information, see [Send Electronic Documents](sales-how-to-send-electronic-documents.md).

### Nastavení dodavatelů pro příjem elektronických dokumentů
1. In the **Search** box, enter **Vendors**, and then choose the related link.
2. For each vendor that you will receive electronic documents from, fill the fields as described in the following table.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **GLN** | Identify the vendor.<br /><br /> For example, when you receive electronic invoices in the PEPPOL format, the value in this field is used to populate the **EndPointID** element under the **AccountingSupplierParty** node in the file. The number is based on the GS1 standard, which is compliant with ISO 6523.<br /><br /> If the **GLN** field is blank, the value in the **VAT Registration No.** field is used. |
   | **DIČ** | Specify the vendor’s VAT registration number. **Tip:**  Choose the DrillDown button to use the web service that verifies if the number exists in the country’s company register. |
   | **Centrum odpovědnosti** | If the vendor is set up with a responsibility center, make sure that the **Country/Region Code** field is filled. |

### To select the PEPPOL - Invoice data exchange definition for electronic document receiving
1. In the **Search** box, enter **Incoming Documents**, and then choose the related link.
2. On the line for the electronic document that you want to receive and convert, choose the **Data Exchange Type** field, and then select **PEPPOLINVOICE**.

   If the document to receive is a credit memo, select **PEPPOLCREDITMEMO**.

   You can now receive the electronic document by starting the data conversion process on the **Incoming Documents** page. For more information, see [Receive and Convert Electronic Documents](purchasing-how-to-receive-and-convert-electronic-documents.md).

### To set up the G/L account to use on new purchase invoice lines for non-identifiable items and non-items
1. In the **Search** box, enter **Purchases & Payables Setup**, and then choose the related link.
2. On the **Default Accounts** FastTab, fill the field as described in the following table.

   | Pole | Popis |
   |---------------------------------|---------------------------------------|  
   | **G/L Account for Non-Item Lines** | Specifies the G/L account that is automatically inserted on purchase lines that are created from electronic documents when the incoming document line does not contain an identifiable item. Any incoming document line that does not have a GTIN or the vendor’s item number will be converted to a purchase line of type **G/L Account**, and the **No.** field on the purchase line will contain the account that you select in the **G/L Account for Non-Item Lines** field.<br /><br /> If you leave the **G/L Account for Non-Item Lines** field blank, and the incoming document has lines without identifiable items, then the purchase document will not be created. An error message will instruct you to fill the **G/L Account for Non-Item Lines** field before you can complete the task. |

## Viz také
[Elektronická výměna dat](across-data-exchange.md)  
[Fakturace prodeje](sales-how-invoice-sales.md)  
[Záznam nákupu](purchasing-how-record-purchases.md)
