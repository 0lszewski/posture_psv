# posture_psv

Passively discover Internet facing assets belonging to an organization. All that's needed to start are domain and organization names. Running notebook in a scheduled manner allows for easy tracking of company owned assets which can be used as a starting point of security posture management.

In the current version notebook uses TLS certificates search engine and Shodan integrations to assemble a list of assets containing:
- Common names parsed from certificates
- Matching identities
- Issuer names
- TTLs (to discover short-lived certificates often realted to dev enironments
- Whois information
- Discovered open ports
- TLS version and ciphersuites
- Certificate validity
- Discovered product/application name
- Discovered vulnerabilities
- Observed response banners
- Location country


## Prerequisites 

The notebook is split into sections so it is possible to execute only parts of it as for example gathering the TLS certificates infortmation and skipping parts using shodan inteagration.
![sections](https://user-images.githubusercontent.com/113899562/191201266-1135b774-9bd5-4faf-9ad7-6ce9a668563d.png)

I'm assuming that you are familiar with the basic usage of <a href="https://jupyter.org">Jupyter</a> notebooks and that you have Jupyter already running. If not there are great resources on YT that should get you started in no time.

The notebook requires you to install some extra Python modules:
```
pip3 install pandas
pip3 install matplotlib
pip3 install IPWhois
pip3 install shodan
pip3 install pycountry-convert
pip3 install geopy
pip3 install folium

```

## Running the notebook

1. Start by downloading the posture_psv.ipynb notebook from Git and opening it in your Jupyter installation.
2. Fill in the information required in the cells under <b>Complete your configuration here before proceeding:</b>

![setup](https://user-images.githubusercontent.com/113899562/191204890-21d032d6-b270-40e2-95c9-4ea3d2929912.png)

3. From there you can select the first cell in the notebook and either go to the 'Run' menu and select 'Run Selected cell and All Below' or manually continue through the notebook by pressing Shift+Enter to move cell by cell.

![run-all](https://user-images.githubusercontent.com/113899562/191205510-54f07cc7-f184-435d-87d7-1d86a91847f8.png)

4. After the notebook executes and there are no errors you can review the results. There will be also 2 CSV files saved in your Jupyter working folder containing all the results.
5. The notebook contains Searching section that lets you quickly find results of interest without switching to CSV yet.
![search-ports](https://user-images.githubusercontent.com/113899562/191210570-6f9ddb2c-6783-4b13-b762-fec0c2b910a8.png)

## Some Screenshots
