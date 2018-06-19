# [![N|Solid](https://ngazngoblobpub.blob.core.windows.net/static/nexus-go-logo-black.png)](https://www.nexusgroup.com/) meets FORGEROCK

## Setup IDP in FORGEROCK OpenAM
1. Login to OpenAM
2. Select Realm
3. Click "Configure SAMLv2 Provider" ![screenshot](image1.png)
4. Click "Created Hosted Identity Provider" ![screenshot](image2.png)
5. Setup IDP
    1. Give the IDP a name
    2. Assign a Signing key to the IDP
    3. Add IDP to a new circle of trust
    4. Add the following attribute mappings
        * cn -> cn
        * mail -> mail    
    5. Click Continue ![screenshot](image3.png)
    6. Click Finish ![screenshot](image4.png)
6. Download IDP metadata with URL https://<IdP_FQDN>/openam/saml2/jsp/exportmetadata.jsp?entityid=<name of IDP>

## Setup IDP in Nexus GO
1. Login to Nexus GO Portal
2. Click Services ![screenshot](image5.png)
3. Click "Signing" ![screenshot](image6.png)
4. Select your signing service ![screenshot](image7.png)
5. Click "Edit SAML IDP configuration" ![screenshot](image8.png)
6. Set a display name 
7. Upload IDP metadata downloaded earlier
8. Click "NEXT" ![screenshot](image9.png)
9. Add the following attribute mappings
    * email -> mail
    * displayName -> cn
10. Click "NEXT" ![screenshot](image10.png)
11. Allow evenryone from this Idendity Provider as contributors
12. Click "NEXT" ![screenshot](image11.png)
13. Click "SUBMIT" ![screenshot](image12.png)
14. Download SP metadata ![screenshot](image13.png)
15. Copy Login URL

## Import SP into FORGEROCK OpenAM
1. Login to OpenAM
2. Select Realm
3. Click "Applications" ![screenshot](image14.png)
4. Click "Federation" ![screenshot](image15.png)
5. Click "Entity Provider" ![screenshot](image16.png)
6. Import the SP metadata downloaded earlier ![screenshot](image17.png) ![screenshot](image18.png)

## Login to Nexus GO signing portal
1. Use link copied earlier ![screenshot](image19.png)
2. Use user credentials setup in FORGEROCK OpenAM ![screenshot](image20.png)
3. Start using the Nexus GO signing portal ![screenshot](image21.png)

## Further reading
* For more information about Nexus GO please visit [Nexus online documentation](https://doc.nexusgroup.com)
* For more information about FORGEROCK please visit [FORGEROCK Backstage](https://backstage.forgerock.com)


