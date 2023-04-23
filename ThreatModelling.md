# Threat Modelling using Microsoft Threat Modelling Tool

## Web Application Threat Modelling 

<p align= 'center'>
  
 ![image](https://user-images.githubusercontent.com/68326118/233858114-39c79c82-9fe4-4c20-bdb4-32da960f1ba4.png)

</p>

### Steps to create threat modelling model diagram
- we first connect human user to webserver with https and will have a data flow comeback from webserver to human user
- Now we connect web server to sql database with data flow request called as database request and we have the comeback called as database response
- Now we define element properties such as store credentials ( to verify username) , data encrypted , write access etc for all compnents in the diagram
- Before analyzing we should create some boundaries 
        i. Internet Boundary :
                - For human user who uses internet to access the web service
        ii. Generic Trust Boundary :
                - For webserver and sql database as they be in same cloud data center and they have same trust followed by components.

### To Indentify the threats in the model 

- Go to view and select analysis view we find list of STRIDE 

![image](https://user-images.githubusercontent.com/68326118/233850672-b55f98dd-e4b6-4aba-b3a5-1010f9ec4a98.png)

### MITIGATE
 
 Before mitigating we can generate the report of the each different strides 
 
 Ex: `file:///C:/Users/sirip/OneDrive/Documents/Report.htm`
 
 - we now check out the each threat properties and mitigate each of the STRIDE, here we update the following highlighted values like wise we do for all the other properties.
 
 ![image](https://user-images.githubusercontent.com/68326118/233851061-72fadeae-895b-49e2-be3a-d86b3afd9993.png)

