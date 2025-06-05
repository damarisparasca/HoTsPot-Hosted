Our intervention code is organized into two main components, the fodler "Intergrated_website" and the zipfile "WOWCOW":

## 1. `Intergrated_website`

This folders contains the full structure and logic of the "Value for Water" website, as well as the code for the machine learning models we used, it includes:

- HTML+CSS code for all website pages

- folder for Prediction model:
    - prediction model code (app.py)
    - prediction model data (nivm_dataset.csv)
    - required packages to run the model on streamlit (requirements.txt)


- folder for WaterCredits system simulator:
  - Two optimization models implemented using AMPL:
    - A Mathematical Program with Equilibrium Constraints (MPEC) model (kkt_equilibrium_model.mod).
    - A Quadratic Programming (QP) model (no_trading_kkt_equilibrium_model.mod).
  - A Python script to generate input data for the models(generate_dat.py).
  - A Streamlit-based interface that allows users to adjust model parameters, run simulations, view and compare results interactively(app.py).
  - Cost and Revenue data used in the model (total_cost_revenue_data.csv)
  - required packages to run the model on streamlit (requirements.txt)
  - folder "Cost and Revenue"
    - contains the cost and revenue prediciton model and predicted data. These data are used as input for the simulator, for more detailed information you can check the README file inside this folder

- evaluation model calculation for the Water Score  (evaluation_model.ipynb)

- javascript code for the Watercredits calculator (scriptnew.js)

- folders of images in the website

### How to Run

  #### To run the website: 
    - open homepage.html in any modern web browser:
    - You can also access our website directly from https://damarisparasca.github.io/HoTsPot-Hosted/index.html

  #### To run the prediction model only: 
    - Make sure you have Python 3 and Streamlit installed. Then go to the corresponding folder, run: **streamlit run app.py**
    - You can also access our prediction model directly from https://hotspot-intervention-wwpysabdsmce8rlswpnkv7.streamlit.app/?utm_medium=oembed

  #### To run the watercredit market simulator only: 
    - Make sure you have Python 3 and Streamlit installed. Then go to the corresponding folder, run: **streamlit run app.py**
    - You can also access our prediction model directly from https://mpecwatercredit.streamlit.app/


## 2. `WOWCOW.zip`

This ZIP contains the educational farming game WOWCOW, designed to illustrate WaterCredit machnism. It is adapted from the open-source game **Farmhand** by Jeremy Kahn, with modifications to include Watercredits and sustainable farming practices.

### How to Run

#### you can also access our game directly from https://flourishing-cucurucho-bf8da3.netlify.app/

#### to run locally

Requires:

- Node/NPM (npm version v1.18.26)
- Docker
- [nvm](https://github.com/nvm-sh/nvm) (or alternatively [asdf](https://asdf-vm.com))

In your shell, run this to ensure you're using the correct Node version and install all of the dependencies:

```sh
nvm i
npm ci --legacy-peer-deps
```

If `npm ci --legacy-peer-deps` errors out due to PhantomJS installation errors (this has been seen in some WSL/Linux environments), try `npm_config_tmp=/tmp npm ci` instead. [See this related comment](https://github.com/yarnpkg/yarn/issues/1016#issuecomment-283067214). Alternatively, try `npm ci --no-optional --legacy-peer-deps`.

To run the game locally with the API, Redis database, and peer pairing server, run:

```sh
npm run dev
```

To run the native app locally, run:

```sh
npm run dev:native
```

Note that you will need a Vercel account and be logged into locally for this to work (at least until [Vercel fixes this](https://github.com/vercel/vercel/discussions/4925)). Alternatively, if you just want to run the front end with no API or backend, you can run:

```sh
npm start
```

In this case, the local app will be using the Production API, database, and pairing server. However you boot, Farmhand will be accessible from http://localhost:3000/.


## Contact
For any questions about this code feel free to contact Yuyue at yuyue.xiao@student.uva.nl