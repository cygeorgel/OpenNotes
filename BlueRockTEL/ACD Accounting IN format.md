# ACD Accounting IN format

## AccountingEntryLineFormat

Defines: the columns expected by Acd.

```
<?php

namespace App\BlueRock\Accounts\Acd;

class AccountingEntryLineFormat
{
    protected $columns_count = 66;

    protected $document_columns_count = 5;

    protected $references = [
        0 => 'INT_TYP',           // length = 1  "1, 2 or 3"
        1 => 'INT_JL',            // length = 2  "Non utilisé"
        2 => 'INT_DAT',           // length = 6  "Date d'imputation"
        3 => 'INT_PIE',           // length = 5  "Numéro de pièce sur 5 caractères"
        4 => 'INT_LIB',           // length = 32 "Intitulé de l'écriture sur 32 caractères"
        5 => 'INT_CPT',           // length = 13 "Numéro de compte"
        6 => 'INT_DC',            // length = 1  "Code débit / crédit"
        7 => 'INT_MT',            // length = 12 "Montant de l'écriture exprimé en centimes"
        8 => 'INT_ECH',           // length = 6  "Date d'échéance"
        9 => 'INT_REG',           // length = 2  "Type de règlement"
        10 => 'INT_LET',          // length = 1
        11 => 'INT_ANO',          // length = 1
        12 => 'INT_ANC',          // length = 12
        13 => 'INT_INT',          // length = 30
        14 => 'INT_JAL',          // length = 4
        15 => 'INT_TJL',          // length = 1
        16 => 'INT_EIC',          // length = 10
        17 => 'INT_NLET',         // length = 2
        18 => 'INT_TRANS',        // length = 1
        19 => 'INT_DIV',          // length = 12
        20 => 'INT_DEVISE',       // length = 1
        21 => 'INT_ANCIEN',       // length = 4
        22 => 'INT_RAPDOR',       // length = 6
        23 => 'INT_LP1',          // length = 1
        24 => 'INT_EICCP',        // length = 6
        25 => 'INT_PIE2',         // length = 8
        26 => 'INT_ANA1',         // length = 5
        27 => 'INT_ANA2',         // length = 5
        28 => 'INT_ANA3',         // length = 5
        29 => 'INT_LIBANA',       // length = 64
        30 => 'INT_REF',          // length = 16
        31 => 'INT_TVA',          // length = 16
        32 => 'INT_CPT_TRF',      // length = 13
        33 => 'INT_REF32',        // length = 32
        34 => 'INT_DAAID',        // length = 10
        35 => 'INT_RESAZ',        // length = 32
        36 => 'INT_EXT',          // length = 1
        37 => 'INT_QTE',          // length = 12
        38 => 'INT_QTU',          // length = 1
        39 => 'INT_ECR_GED',      // length = 32
        40 => 'INT_LE_GED',       // length = 32
        41 => 'INT_LONG_ANA1',    // length = 20
        42 => 'INT_LONG_ANA2',    // length = 20
        43 => 'INT_LONG_ANA2',    // length = 20
        44 => 'INT_TAUX',         // length = 12
        45 => 'INT_PIE3',         // length = 16
        46 => 'INT_DATE_TVA',     // length = 8
        47 => 'INT_DATE_VAL',     // length = 8
        48 => 'INT_COL_VAL',      // length = 10
        49 => 'INT_DATE_SAI',     // length = 8
        50 => 'INT_COL_SAI',      // length = 10
        52 => 'INT_NUM_FEC',      // length = 12
        53 => 'INT_LIB2',         // length = 50
        54 => 'INT_UNI',          // length = 5
        55 => 'INT_ANAQTE',       // length = 12
        56 => 'INT_FACT',         // length = 20
        57 => 'INT_LET_CODE',     // length = 5
        58 => 'INT_LET_PARTIEL',  // length = 1
        59 => 'INT_INT_50',       // length = 50
        60 => 'INT_LIBRE_1',      // length = 20
        61 => 'INT_LIBRE_2',      // length = 20
        62 => 'INT_QTE2',         // length = 12
        63 => 'INT_UNI2',         // length = 5
        64 => 'INT_DATE_LET',     // length = 8
        65 => 'INT_LONG_MT',      // length = 14
    ];

    protected $line_format = [

        0 => [
            'element' => 'INT_TYP',
            'length' => 1,
            'format' => 'string',
        ],

        1 => [
            'element' => 'INT_JL',
            'length' => 2,
            'format' => 'numeric',
        ],

        2 => [
            'element' => 'INT_DAT',
            'length' => 6,
            'format' => 'numeric', // date Ymd
        ],

        3 => [
            'element' => 'INT_PIE',
            'length' => 5,
            'format' => 'string',
        ],

        4 => [
            'element' => 'INT_LIB',
            'length' => 32,
            'format' => 'string',
        ],

        5 => [
            'element' => 'INT_CPT',
            'length' => 13,
            'format' => 'string',
        ],

        /**
         * debit/credit:
         * 0 = positive debit
         * 1 = positive credit
         * 2 = negative debit
         * 3 = negative credit
         */
        6 => [
            'element' => 'INT_DC',
            'length' => 1,
            'format' => 'numeric',
        ],

        /**
         * amount in cents, no sign:
         */
        7 => [
            'element' => 'INT_MT',
            'length' => 12,
            'format' => 'numeric',
        ],

        8 => [
            'element' => 'INT_ECH',
            'length' => 6,
            'format' => 'numeric', // Ymd
        ],

        /**
        * "R" = Aucun
        * "B" = Carte bancaire
        * "C" = Lettre chèque
        * "O" = Ordre de virement (IBAN)
        * "T" = Lettre traite
        * "V" = Virement
        * "P" = Prélèvement
        * "L" = LCR magnétique
        * "E" = Espèce
        * "N" = Acompte
        * "X" = Bordereau
        */
        9 => [

            'element' => 'INT_REG',
            'length' => 2,
            'format' => 'string',
        ],

        /**
         * Not used
         */
        10 => [
            'element' => 'INT_LET',
            'length' => 1,
            'format' => 'numeric',
        ],

        /**
         * Analytics accounts
         */
        11 => [
            'element' => 'INT_ANO',
            'length' => 1,
            'format' => 'numeric',
        ],

        /**
        * Analytics accounts counterparty
         */
        12 => [
            'element' => 'INT_ANC',
            'length' => 12,
            'format' => 'string',
        ],

        /**
        * account label:
        */
        13 => [
            'element' => 'INT_INT',
            'length' => 30,
            'format' => 'string',
        ],

        /**
         * journal:
         */
        14 => [
            'element' => 'INT_JAL',
            'length' => 4,
            'format' => 'string',
        ],

        /**
         * journal type:
         * "0" pour les journaux de reports à nouveau
         * "1" pour les journaux d'achats
         * "2" pour les journaux de ventes
         * "3" pour les journaux de trésorerie
         * "4" pour les journaux d'opérations diverses
         * "5" pour les journaux situations
         */
        15 => [
            'element' => 'INT_TJL',
            'length' => 1,
            'format' => 'numeric', // documentation says string though?
        ],

        /**
         * not used:
         */
        16 => [
            'element' => 'INT_EIC',
            'length' => 10,
            'format' => 'numeric', // documentation says string though
        ],
        
        17 => [
            'element' => 'INT_NLET',
            'length' => 2,
            'format' => 'string',
        ],

        /**
        * not used:
        */
        18 => [
            'element' => 'INT_TRANS',
            'length' => 1,
            'format' => 'string',
        ],

        /**
         * misc account number:
         */
        19 => [
            'element' => 'INT_DIV',
            'length' => 12,
            'format' => 'string',
        ],

        /**
        * currency:
        */
        20 => [
            'element' => 'INT_DEVISE',
            'length' => 1,
            'format' => 'string',
        ],

        21 => [
            'element' => 'INT_ANCIEN',
            'length' => 4,
            'format' => 'numeric',
        ],

        /***
        * "Date du rapprochement au format AAAAMM"
         */
        22 => [
            'element' => 'INT_RAPDOR',
            'length' => 6,
            'format' => 'numeric', // Ym
        ],

        23 => [
            'element' => 'INT_LP1',
            'length' => 1,
            'format' => 'string',
        ],

        24 => [
            'element' => 'INT_EICCP',
            'length' => 6,
            'format' => 'string',
        ],

        25 => [
            'element' => 'INT_PIE2',
            'length' => 8,
            'format' => 'string',
        ],

        26 => [
            'element' => 'INT_ANA1',
            'length' => 5,
            'format' => 'string',
        ],

        27 => [
            'element' => 'INT_ANA2',
            'length' => 5,
            'format' => 'string',
        ],

        28 => [
            'element' => 'INT_ANA3',
            'length' => 5,
            'format' => 'string',
        ],

        29 => [
            'element' => 'INT_LIBANA',
            'length' => 64,
            'format' => 'string',
        ],

        30 => [
            'element' => 'INT_REF',
            'length' => 16,
            'format' => 'string',
        ],

        31 => [
            'element' => 'INT_TVA',
            'length' => 16,
            'format' => 'string',
        ],

        32 => [
            'element' => 'INT_CPT_TRF',
            'length' => 13,
            'format' => 'string',
        ],

        33 => [
            'element' => 'INT_REF32',
            'length' => 32,
            'format' => 'string',
        ],

        34 => [
            'element' => 'INT_DAAID',
            'length' => 10,
            'format' => 'numeric',
        ],

        35 => [
            'element' => 'INT_RESAZ',
            'length' => 32,
            'format' => 'string',
        ],

        36 => [
            'element' => 'INT_EXT',
            'length' => 1,
            'format' => 'string',
        ],

        37 => [
            'element' => 'INT_QTE',
            'length' => 12,
            'format' => 'numeric',
        ],

        38 => [
            'element' => 'INT_QTU',
            'length' => 1,
            'format' => 'string',
        ],

        39 => [
            'element' => 'INT_ECR_GED',
            'length' => 32,
            'format' => 'string',
        ],

        40 => [
            'element' => 'INT_LE_GED',
            'length' => 32,
            'format' => 'string',
        ],

        41 => [
            'element' => 'INT_LONG_ANA1',
            'length' => 20,
            'format' => 'string',
        ],

        42 => [
            'element' => 'INT_LONG_ANA2',
            'length' => 20,
            'format' => 'string',
        ],

        43 => [
            'element' => 'INT_LONG_ANA2',
            'length' => 20,
            'format' => 'string',
        ],

        44 => [
            'element' => 'INT_TAUX',
            'length' => 12,
            'format' => 'numeric',
        ],

        45 => [
            'element' => 'INT_PIE3',
            'length' => 16,
            'format' => 'string',
        ],

        46 => [
            'element' => 'INT_DATE_TVA',
            'length' => 8,
            'format' => 'numeric', // Ymd 
        ],

        47 => [
            'element' => 'INT_DATE_VAL',
            'length' => 8,
            'format' => 'numeric', //  Ymd
        ],

        48 => [
            'element' => 'INT_COL_VAL',
            'length' => 10,
            'format' => 'string',
        ],

        49 => [
            'element' => 'INT_DATE_SAI',
            'length' => 8,
            'format' => 'numeric', // Ymd
        ],

        50 => [
            'element' => 'INT_COL_SAI',
            'length' => 10,
            'format' => 'string',
        ],
        
        52 => [
            'element' => 'INT_NUM_FEC',
            'length' => 12,
            'format' => 'numeric',
        ],

        53 => [
            'element' => 'INT_LIB2',
            'length' => 50,
            'format' => 'string',
        ],

        54 => [
            'element' => 'INT_UNI',
            'length' => 5,
            'format' => 'string',
        ],

        55 => [
            'element' => 'INT_ANAQTE',
            'length' => 12,
            'format' => 'string',
        ],

        56 => [
            'element' => 'INT_FACT',
            'length' => 20,
            'format' => 'string',
        ],

        57 => [
            'element' => 'INT_LET_CODE',
            'length' => 5,
            'format' => 'string',
        ],

        58 => [
            'element' => 'INT_LET_PARTIEL',
            'length' => 1,
            'format' => 'string',
        ],

        59 => [
            'element' => 'INT_INT_50',
            'length' => 50,
            'format' => 'string',
        ],

        60 => [
            'element' => 'INT_LIBRE_1',
            'length' => 20,
            'format' => 'string',
        ],

        61 => [
            'element' => 'INT_LIBRE_2',
            'length' => 20,
            'format' => 'string',
        ],

        62 => [
            'element' => 'INT_QTE2',
            'length' => 12,
            'format' => 'numeric',
        ],

        63 => [
            'element' => 'INT_UNI2',
            'length' => 5,
            'format' => 'string',
        ],

        64 => [
            'element' => 'INT_DATE_LET',
            'length' => 8,
            'format' => 'numeric', // Ymd
        ],

        65 => [
            'element' => 'INT_LONG_MT',
            'length' => 14,
            'format' => 'numeric', 
        ],
    ];

    protected $document_references = [
        0 => 'ING_TYP',     // length = 1   "G"
        1 => 'ING_EL',      // length = 1   "Localisation de la référence électronique : E = Ecriture | L = Ligne écriture"
        2 => 'ING_ORIGINE', // length = 12  "Origine du fichier"
        3 => 'ING_PIECE',   // length = 255 "Nom + chemin du fichier ou uniquement le nom du fichier"
        4 => 'INT_ARBO_ID', // length = 19  "(Zone réservée)"
    ];

    protected $document_line_format = [

        0 => [
            'element' => 'ING_TYP',
            'length' => 1,
            'format' => 'string',
        ],

        1 => [
            'element' => 'ING_EL',
            'length' => 1,
            'format' => 'string',
        ],

        2 => [
            'element' => 'ING_ORIGINE',
            'length' => 12,
            'format' => 'string',
        ],

        3 => [
            'element' => 'ING_PIECE',
            'length' => 255,
            'format' => 'string',
        ],

        4 => [
            'element' => 'INT_ARBO_ID',
            'length' => 19,
            'format' => 'numeric',
        ],

    ];

    public function checkLineFormat(): void
    {
        $start_pos = 1;
        foreach ($this->line_format as $key => $data) {
            $element_start_pos =  $start_pos;
            print $data['element'] . ' ' . $element_start_pos . PHP_EOL;
            $start_pos += $data['length'];
        }
    }

    public function checkDocumentLineFormat(): void
    {
        $start_pos = 1;
        foreach ($this->document_line_format as $key => $data) {
            $element_start_pos =  $start_pos;
            print $data['element'] . ' ' . $element_start_pos . PHP_EOL;
            $start_pos += $data['length'];
        }
    }
}
```

## AccoutingEntryLine

Extends: AccountingEntryLineFormat.

Responsible for: creating a line.

```
<?php

namespace App\BlueRock\Accounts\Acd;

class AccountingEntryLine extends AccountingEntryLineFormat
{
    private $str_pad_rules = [
        'numeric' => [
            'pad_string' => '0',
            'pad_type' => STR_PAD_LEFT,
        ],
        'string' => [
            'pad_string' => ' ',
            'pad_type' => STR_PAD_RIGHT,
        ],
    ];

    /**
     * The element the string is padded with.
     *
     * @param $format
     * @return string
     */
    public function getStrPadString($format): string
    {
        return $this->str_pad_rules[$format]['pad_string'];
    }

    /**
     * The type the string is padded with. 
     *
     * @param $format
     * @return string
     */
    public function getStrPadType($format): string
    {
        return $this->str_pad_rules[$format]['pad_type'];
    }

    /** 
     * Regular line format:
     */

    /** 
     * default parameters for a regular line.
     */
    private $defaults = [
        0 => '2',
        9 => 'R',
    ];

    /**
     * The default value for the element on a regular new line.
     *
     * @param $key
     * @return mixed
     */
    public function getDefault($key)
    {
        if (array_key_exists($key, $this->defaults)) {
            return $this->defaults[$key];
        }
        return null;
    }

    /**
     * Intialise the regular line data with default values.
     *
     * @return array $data
     */
    public function initLineData(): array
    {
        $data = [];
        foreach (range(0, 65) as $column) {
            $data[$column] = $this->getDefault($column);
        }
        return $data;
    }

    /** 
     * Feed the line data with the data to be added, for both regular and document lines.
     *
     * @param array $line_data
     * @param array $data
     * @return array $line_data
     */
    public function feedLine($line_data, $data): array
    {
        foreach ($data as $key => $value) {
            $line_data[$key] = $value;
        }
        return $line_data;
    }

    /**
     * Actually create the regular line.
     *
     * @param array $feed
     * @return string
     */
    public function makeLine($feed): string
    {
        $line_format = $this->line_format;
        $init_line_data = $this->initLineData();

        $line_data = $this->feedLine($init_line_data, $feed);

        $line = '';

        foreach ($line_format as $key => $value) {
            $line .= str_pad($line_data[$key], $value['length'], $this->getStrPadString($value['format']), $this->getStrPadType($value['format']));
        }

        $line .= PHP_EOL;

        return $line;
    }

    /**
     * Document line:
     */

    private $document_defaults = [
        0 => 'G',
        1 => 'E',
    ];

    /**
     * The default value for the element on a new document line.
     *
     * @param $key
     * @return mixed
     */
    public function getDocumentDefault($key)
    {
        if (array_key_exists($key, $this->document_defaults)) {
            return $this->document_defaults[$key];
        }
        return null;
    }

    /**
     * Intialise the document line data with default values.
     *
     * @return array $data
     */
    public function initDocumentLineData(): array
    {
        $data = [];
        foreach (range(0, 4) as $column) {
            $data[$column] = $this->getDocumentDefault($column);
        }
        return $data;
    }

    /**
     * Actually create the document line.
     *
     * @param array $feed
     * @return string
     */
    public function makeDocumentLine($feed): string
    {
        $line_format = $this->document_line_format;
        $init_line_data = $this->initDocumentLineData();

        $line_data = $this->feedLine($init_line_data, $feed);

        $line = '';

        foreach ($line_format as $key => $value) {
            $line .= str_pad($line_data[$key], $value['length'], $this->getStrPadString($value['format']), $this->getStrPadType($value['format']));
        }

        $line .= PHP_EOL;

        return $line;
    }
}
```

## AccountingEntry

Extends: AccountingEntryLine.

Responsible for: creating the entry.

An entry has a least two lines (debit and credit).

```
<?php

namespace App\BlueRock\Accounts\Acd;

use App\ChartOfAccount;
use App\Invoice;
use App\Sale;
use App\PurchaseInvoice;
use App\BlueRock\URLify\URLify;

class AccountingEntry extends AccountingEntryLine
{
    /**
     * @return array
     */
    public function taxAccounts(): array
    {
        return [
            'purchase' => ChartOfAccount::where('account_type', 'recoverable_tax')->first(),
            'sale' => ChartOfAccount::where('account_type', 'payable_tax')->first(),
        ];
    }

    /**
     * @param integer $purchase_invoice_id
     */
    public function purchaseInvoiceEntry($purchase_invoice_id): string
    {
        $purchase_invoice = PurchaseInvoice::find($purchase_invoice_id);

        $entry = "";

        $entry .= "1" . PHP_EOL;

        if ($purchase_invoice->amount_with_tax >= 0) {
            $direction = 1;
        } else {
            $direction = 0;
        }

        $amount_with_tax = abs($purchase_invoice->amount_with_tax);

        $credit_line_data = [
            0 => '2',
            2 => $purchase_invoice->invoice_date->format('ymd'),
            3 => substr($purchase_invoice->invoice_number, 0, 5),
            4 => substr($purchase_invoice->supplier->name, 0, 32),
            5 => $purchase_invoice->supplier->third_party_account,
            6 => $direction,
            7 => $amount_with_tax,
            13 => substr($purchase_invoice->supplier->name, 0, 30),
            14 => 'AC',
            20 => 'E',
            25 => substr($purchase_invoice->invoice_number, 0, 8),
            45 => substr($purchase_invoice->invoice_number, 0, 16),
            56 => substr($purchase_invoice->invoice_number, 0, 20),
        ];

        $entry .= $this->makeLine($credit_line_data);

        foreach ($purchase_invoice->purchaseDetails as $detail) {

            if ($detail->amount_with_tax >= 0) {
                $direction = 0;
            } else {
                $direction = 1;
            }

            $amount_without_tax = abs($detail->amount_without_tax);

            $debit_line_data = [
                0 => '2',
                2 => $purchase_invoice->invoice_date->format('ymd'),
                3 => substr($purchase_invoice->invoice_number, 0, 5),
                4 => substr($purchase_invoice->supplier->name, 0, 32),
                5 => 'G' . $detail->account_number, // G
                6 => $direction,
                7 => $amount_without_tax,
                13 => substr($detail->account->account_description, 0, 30),
                14 => 'AC',
                20 => 'E',
                25 => substr($purchase_invoice->invoice_number, 0, 8),
                45 => substr($purchase_invoice->invoice_number, 0, 16),
                56 => substr($purchase_invoice->invoice_number, 0, 20),
            ];

            $entry .= $this->makeLine($debit_line_data);
        }

        if ($purchase_invoice->tax) {

            if ($purchase_invoice->tax >= 0) {
                $direction = 0;
            } else {
                $direction = 1;
            }

            $purchase_invoice_tax = abs($purchase_invoice->tax);

            $tax_line_data = [
                0 => '2',
                2 => $purchase_invoice->invoice_date->format('ymd'),
                3 => substr($purchase_invoice->invoice_number, 0, 5),
                4 => substr($purchase_invoice->supplier->name, 0, 32),
                5 => 'G' . $this->taxAccounts()['purchase']->number,
                6 => $direction,
                7 => $purchase_invoice_tax,
                14 => 'AC',
                13 => substr($this->taxAccounts()['purchase']->account_description, 0, 30),
                20 => 'E',
                25 => substr($purchase_invoice->invoice_number, 0, 8),
                45 => substr($purchase_invoice->invoice_number, 0, 16),
                56 => substr($purchase_invoice->invoice_number, 0, 20),
            ];

            $entry .= $this->makeLine($tax_line_data);
        }

        $document_data = [
            '3' => $purchase_invoice->document,
        ];

        $entry .= $this->makeDocumentLine($document_data);

        $entry .= "3" . PHP_EOL;

        $purchase_invoice->exported = true;
        $purchase_invoice->save();

        return $entry;
    }


    /**
     * @param integer $invoice_id
     */
    public function saleInvoiceEntry($invoice_id): string
    {
        $invoice = Invoice::find($invoice_id);

        $entry = "";

        $entry .= "1" . PHP_EOL;

        if ($invoice->totalWithTax >= 0) {
            $direction = 0;
        } else {
            $direction = 1;
        }

        $invoice_total_with_tax = round($invoice->totalWithTax, 2) * 100;
        $invoice_total_with_tax = (integer) $invoice_total_with_tax;

        // bebore abs()!
        $tax_amount = $invoice_total_with_tax;

        $invoice_total_with_tax = abs($invoice_total_with_tax);

        $customer_name = strtoupper(substr(URLify::filter($invoice->customer->name), 0, 32));

        $debit_line_data = [
            0 => '2',
            2 => $invoice->date->format('ymd'),
            3 => substr($invoice->invoice_number, 0, 5),
            4 => $customer_name,
            5 => $invoice->customer->accountsReference,
            6 => $direction,
            7 => $invoice_total_with_tax,
            13 => substr($invoice->customer->name, 0, 30),
            14 => 'VT',
            20 => 'E',
            25 => substr($invoice->number, 0, 8),
            45 => substr($invoice->number, 0, 16),
            56 => substr($invoice->number, 0, 20),
        ];

        $entry .= $this->makeLine($debit_line_data);



        $revenue_accounts = Sale::where('invoice_id', $invoice_id)->selectRaw('distinct revenueAccount')->pluck('revenueAccount')->toArray();

        foreach ($revenue_accounts as $revenue_account) {

            $revenue_account_amount = $invoice->sales->where('revenueAccount', $revenue_account)->sum('lineWithoutTax');

            if ($revenue_account_amount >= 0) {
                $direction = 1;
            } else {
                $direction = 0;
            }

            $revenue_account_amount = round($revenue_account_amount, 2) * 100;
            $revenue_account_amount = (integer) $revenue_account_amount;

            // before abs()!
            // if ($revenue_account_amount >= 0) {
                $tax_amount -= $revenue_account_amount;
            // } else {
                // $tax_amount += $revenue_account_amount;
            // }

            $revenue_account_amount = abs($revenue_account_amount);

            $revenue_account_description = '';

            $chart_of_account = ChartOfAccount::where('number', $revenue_account)->first();

            if ($chart_of_account) {
                $revenue_account_description = $chart_of_account->account_description;
            }

        
            $credit_line_data = [
                0 => '2',
                2 => $invoice->date->format('ymd'),
                3 => substr($invoice->invoice_number, 0, 5),
                4 => $customer_name,
                5 => 'G' . $revenue_account,
                6 => $direction,
                7 => $revenue_account_amount,
                13 => substr($revenue_account_description, 0, 30),
                14 => 'VT',
                20 => 'E',
                25 => substr($invoice->number, 0, 8),
                45 => substr($invoice->number, 0, 16),
                56 => substr($invoice->number, 0, 20),
            ];

            $entry .= $this->makeLine($credit_line_data);
        }

        if ($tax_amount) {


            if ($tax_amount >= 0) {
                $direction = 1;
            } else {
                $direction = 0;
            }

            $tax_amount = abs ($tax_amount);

            $tax_line_data = [
                0 => '2',
                2 => $invoice->date->format('ymd'),
                3 => substr($invoice->invoice_number, 0, 5),
                4 => $customer_name,
                5 => 'G' . $this->taxAccounts()['sale']->number,
                6 => $direction,
                7 => $tax_amount,
                13 => substr($this->taxAccounts()['sale']->account_description, 0, 30),
                14 => 'VT',
                20 => 'E',
                25 => substr($invoice->number, 0, 8),
                45 => substr($invoice->number, 0, 16),
                56 => substr($invoice->number, 0, 20),
            ];

            $entry .= $this->makeLine($tax_line_data);
        }


        // $document_data = [
        //     '3' => $invoice->document,
        // ];
        //
        // $entry .= $this->makeDocumentLine($document_data);

        $entry .= "3" . PHP_EOL;

        $invoice->exported = true;
        $invoice->save();

        return $entry;

    }
}
```

### AccountingFileContent

Extends: AccountingEntry.

Responsible for: creating the file content.

```
<?php

namespace App\BlueRock\Accounts\Acd;

use App\Invoice;
use App\PurchaseInvoice;

class AccountingFileContent extends AccountingEntry
{
    private string $type;
    private string $source;

    /**
    * @param string $start
    * @param string $source
    */
    public function __construct(string $type, string $source)
    {
        $this->type = $type;
        $this->source = $source;
    }

    private $classes = [
        'purchase_invoices' => PurchaseInvoice::class,
        'sale_invoices' => Invoice::class,
    ];

    /**
     * @param string $type
     * @return class-string 
     */
    private function getClass($type): string
    {
        return $this->classes[$type];
    }

    private $date_columns = [
        'purchase_invoices' => 'invoice_date',
        'sale_invoices' => 'date',
    ];

    /**
     * @param string $type
     * @return string
     */
    private function getDateColumn($type): string
    {
        return $this->date_columns[$type];
    }

    /**
     * @param string $type
     * @param string $source
     * @return array
     */
    public function getElementIds($type, $source): array
    {
        $class = $this->getClass($type);

        $column = $this->getDateColumn($type);

        $date = now()->startOfMonth();

        if ($class == 'App\PurchaseInvoice') {
            return $class::where('source', $source)
                ->where('exported', false)
                ->where($column, '<', $date)
                ->pluck('id')
                ->toArray();
        }
        

        return $class::where('exportable', true)
            ->where('exported', false)
            ->where($column, '<', $date)
            ->pluck('id')
            ->toArray();
    }

    /**
     * The actual content of the file
     *
     * @return string
     */
    public function content(): string
    {
        $type = $this->type;
        $source = $this->source;

        $element_ids = $this->getElementIds($type, $source);

        $content = "";

        foreach ($element_ids as $id) {

            if ($type == 'purchase_invoices') {
                $content .= $this->purchaseInvoiceEntry($id);
            }

            if ($type == 'sale_invoices') {
                $content .= $this->saleInvoiceEntry($id);
            }
        }

        return $content;
    }
}
```