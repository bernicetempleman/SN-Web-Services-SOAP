# SNOW-Web-Services-SOAP
SOAP

- Deactivate business rule for rest if just did rest demo
- Rest uses endpoint and method
- Soap uses wsdl and transform map

## On receiver/ publisher/ create webservice// create inbound web service
- Web service-> inbound->create new
- Label: demo SOAP inci
- Target table: incident
- Check copy fields
- Check create transform

- Create
- Automap
- Save

## demo soap incident
- Wsdl -> give to consumer
- https://devxxxxx.service-now.com/u_demo_soap_inci.do?WSDL

### user- demo.soap
-give role: import_admin and soap*

## on source/
- outbound -> soap message
- Name: Demo soap incident
- Wsdl: https://devxxxxx.service-now.com/u_demo_soap_incident.do?WSDL
- Authentication: basic/ new

### Click link to generate xml sample soap

- Scroll down

- Only insert (delete others)
- Open insert

### Edit fields to send
- Save
- Test first with static values
- Auto generate variables/ add test values

## Authentication:

- Test
- Check Status and incident on receiver

## To Automate:
-  Create Business rule
- (get code from soap message function: preview script usage)
- s.setStringParameterNoEscape('insert.u_urgency', 'current.urgency');
-     s.setStringParameterNoEscape('insert.u_category', current.category);
-     s.setStringParameterNoEscape('insert.u_short_description', current.short_description);
-     s.setStringParameterNoEscape('insert.u_state', current.state);
-     s.setStringParameterNoEscape('insert.u_company', current.company);
-     var response = s.execute();
-     var responseBody = response.getBody();
-     var status = response.getStatusCode();

