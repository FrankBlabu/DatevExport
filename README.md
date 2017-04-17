# DatevExport
Export DATEV tax file data from InBehandlung veterinary software backup files

# Purpose
[http://www.inbehandlung.de] is a popular veterinary software in Germany. Although already providing a lot of features, the DATEV export is missing. 

DATEV is an enchange format which enables the seamless passing of tax relevant data from an accountant software to your professional accountant or tax office. This script extracts the necessary data from InBehandlung backup files.

# Usage

* Ask InBehandlung to set up a backup for you. The backup will be done once a week and you will receive a link where you can download the latest backup data set.
* Download newest dataset. Be aware that the backup had to be done at a time where all your entires and changes to the database has already been made. You may have to wait for a week otherwise.
* Run script: 
```
datexexport.py -m <month> -y <year> -o <output file> [-c <crosscheck file>] <backup file>
```
* Example:
```
datevexport.py -m 03 -y 2017 -o datev-03-2017.csv -c crosscheck-03-2017.csv backup-16042017.tgz
```
* The file `datev-*.csv` will contain the DATEV data for import into the accountants software in CSV format.
* The file `crosscheck-*.csv`will contain data which can help you to balance your EC card invoices and manual bank account checking which the data present in the InBehandlung database. You can use it to verify that all payments have been correctly classified into EC card and cash on the one hand and that you have logged all bank account activities in InBehandlung.

# Legal stuff

* Please be aware this software is provided 'as is' **without warranty of any kind** as expressed in the license included. We are using it ourselves in our monthly tax workflow, but we cannot guarantee that it will work for you correctly.
* If you use it, you might have to adapt the account numbers at the beginning of the script after talking to your professional accountant. The numbers here will differ accorting to the tax software setup.
