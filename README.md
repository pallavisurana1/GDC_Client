# GDC_Client
How to use the GDC client to download the data from the GDC portal


# GDC_client_using
How to use the GDC client for downloading the files

## Prerequisites 
* **GDC_token**: Ask Ramana to provide the recent GDC token as the GDC token always expired after a certain time period.
* **Manifest_file**: Get the manifest file from [GDC portal](https://portal.gdc.cancer.gov/)

## Steps to follow
1. Get the GDC client from (GDC Data Transfer Tool)[https://gdc.cancer.gov/access-data/gdc-data-transfer-tool]. Use the following command to download the GDC client zip file
    ```
    wget https://gdc.cancer.gov/files/public/file/gdc-client_v1.6.1_Ubuntu_x64.zip
    ```
2. Once downloaded, you will need to unzip the file. You can use the unzip command:
    ```
    unzip gdc-client_XX.XX.XX.zip
    ```
3. Give permission to execute the GDC client
  ```
  * chmod +x <path_to_unzipped_gdc-client_file>/gdc-client
  * export PATH=$PATH:/path/to/gdc-client_directory
  ```
4. Now, check if you can run the GDC Data Transfer Tool from anywhere in your terminal by typing `gdc-client`.
5. Once installed `gdc-client` and you got your manifest file and gdc-token, you can download the data using the two following commands
   * First change the read and write permission of the `gdc-token`
     ```
     chmod 600 /path_to_gdc_token
     ```
   *  Then use the command to download files
    ```
    gdc-client download -m /home/pdutta/TCGA-GDC_data/Manifest_file/BRCA/SNV/maifest_file.txt -t /home/pdutta/TCGA-GDC_data/GDC_files/token.txt -d /home/pdutta/TCGA-GDC_data/Data/BRCA/SNV/
    ```
    Here,
    * `**-m /home/pdutta/TCGA-GDC_data/Manifest_file/BRCA/SNV/gdc_manifest.2023-07-05.txt**`: path to the manifest file
    * `-t /home/pdutta/TCGA-GDC_data/GDC_files/gdc-user-token.2023-06-29T15_22_52.765Z.txt` : path to the GDC token file
    *  `-d /home/pdutta/TCGA-GDC_data/Data/BRCA/SNV/` : path to the output folder where the data is stored
