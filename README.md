# [![N|Solid](https://ngazngoblobpub.blob.core.windows.net/static/nexus-go-logo-black.png)](https://www.nexusgroup.com/) meets FORGEROCK

## Setup IDP in FORGEROCK OpenAM
1. Login to OpenAM
2. Select Realm
3. Click "Configure SAMLv2 Provider" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image1.png)
4. Click "Created Hosted Identity Provider" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image2.png)
5. Setup IDP
    1. Give the IDP a name
    2. Assign a Signing key to the IDP
    3. Add IDP to a new circle of trust
    4. Add the following attribute mappings
        * cn -> cn
        * mail -> mail    
    5. Click Continue ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image3.png)
    6. Click Finish ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image4.png)
6. Download IDP metadata with URL https://<IdP_FQDN>/openam/saml2/jsp/exportmetadata.jsp?entityid=<name of IDP>

## Setup IDP in Nexus GO
1. Login to Nexus GO Portal
2. Click Services ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image5.png)
3. Click "Signing" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image6.png)
4. Select your signing service ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image7.png)
5. Click "Edit SAML IDP configuration" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image8.png)
6. Set a display name 
7. Upload IDP metadata downloaded earlier
8. Click "NEXT" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image9.png)
9. Add the following attribute mappings
    * email -> mail
    * displayName -> cn
10. Click "NEXT" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image10.png)
11. Allow evenryone from this Idendity Provider as contributors
12. Click "NEXT" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image11.png)
13. Click "SUBMIT" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image12.png)
14. Download SP metadata ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image13.png)
15. Copy Login URL

## Import SP into FORGEROCK OpenAM
1. Login to OpenAM
2. Select Realm
3. Click "Applications" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image14.png)
4. Click "Federation" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image15.png)
5. Click "Entity Provider" ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image16.png)
6. Import the SP metadata downloaded earlier ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image17.png) ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image18.png)

## Login to Nexus GO signing portal
1. Use link copied earlier ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image19.png)
2. Use user credentials setup in FORGEROCK OpenAM ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image20.png)
3. Start using the Nexus GO signing portal ![screenshot](https://github.com/technologynexus/nexusgo-forgerock/raw/master/screenshots/image21.png)

## Further reading
* For more information about Nexus GO please visit [Nexus online documentation](https://doc.nexusgroup.com)
* For more information about FORGEROCK please visit [FORGEROCK Backstage](https://backstage.forgerock.com)


