### **Source Code Install on Windows** ###

For installing the source we have to install the dependencies manually.
 
- **Python 3.5** : Use [The official Python 3 installer](https://www.python.org/downloads/windows/). While installing check the checkbox for "add python.exe to Path". <br/>  Note: Please ensure that you are installing **Python 3.5** otherwise it will create problem in later stages. <br/> <br/>

- **PostgreSQL** : This will be our local database. Use [PostgreSQL for windows](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads). <br/>
After installation go to your environment variable and add PostgreSQL's **bin** directory to your **PATH**( default :C:\ProgramFiles\PostgreSQL\9.4\bin ).<br/> Now we have to create one postgres user: by default the only user is **postgres**. For creating a postgres user with a password go to your start **menu**-> **search pgAdmin III** -> **double-click the server**. After this select **Edit** ->**New Object**->**New Login Role**, give the username in the role name field(**odoo**), then open the definition tab and enter the password (**Odoo**), then click OK. <br/> <br/>
 

- **Fetch the sources** : It is always good to download the sorce from git repository. For community edition go to [github](https://github.com/odoo/odoo.git). <br/> 
  		* Install Git <br/>
        * After installing git go to your local system. Do right click and choose git bash here. One cmd window will pop up type **git clone https://github.com/odoo/odoo.git** <br/> <br/>
   

- **Install psycopg** : For installing go to [http://www.stickpeople.com/projects/python/win-psycopg/](http://www.stickpeople.com/projects/python/win-psycopg/). 
<br/> Note:Choose the one which is compatible with Python 3.5. <br/> <br/>
 
- **Python Dependencies** : Now that we have cloned the odoo source code go to the source code in your local system there we will be able to see one **requirements.txt** file. In this file all the dependencies are listed.<br/> For installing the dependencies type cmd in file path where you have cloned the odoo. Now one cmd window will open with address of your odoo path. type 
**pip.exe install -r requirements.txt** <br/>
ex: <br/>
    `C:\> cd \YourOdooPath` <br/>
    `C:\YourOdooPath>pip.exe install -r requirements.txt` <br/> Note : While the given command is running please make sure all the dependencies listed in the requirements.txt file are installing properly. If any error is coming while installing any particular dependencies please try to install it separately. 
 
	After all these if still some errors are coming try with <br/> **pip.exe install -r requirements.txt  --force --upgrade** <br/> <br/>

- **Install Less CSS via nodejs** : First install nodejs([install nodejs,](https://nodejs.org/en/download/)). <br/>After that go to cmd type **npm install -g Less**
   `C:\> npm install -g less` <br/>Note: After doing all the above steps please restart your laptop. <br/>Now all the setup has been done. <br/> <br/>

- **Running Odoo** : Go to your odoo source code. Open cmd on your odoo path and type below command <br/>
    `python odoo-bin -w odoo -r odoo --addons-path=addons  --db-filter=mydb$` <br/>Where **odoo**,**odoo** are the postgres login and password that we have created and **mydb** is the default db that serve on **localhost:8069**
