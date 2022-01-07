[comment]: # "Auto-generated SOAR connector documentation"
# Corelight

Publisher: Corelight  
Connector Version: 1\.0\.1  
Product Vendor: Corelight  
Product Name: Corelight  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.2\.7532  

This action supports investigative and generic actions to add configurations and update frameworks on Corelight

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Corelight asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**base\_url** |  required  | string | URL for Corelight
**verify\_server\_cert** |  optional  | boolean | Verify Server Certificate
**user** |  required  | string | User Name
**password** |  required  | password | Password

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using the supplied configuration  
[input framework](#action-input-framework) - Update input framework  
[intelligence update](#action-intelligence-update) - Update intel framework  
[get config](#action-get-config) - Get Corelight full configuration  
[list input](#action-list-input) - List the different input frameworks  
[list intelligence](#action-list-intelligence) - List the different input framework endpoints  
[backup box](#action-backup-box) - Create a JSON backup of the Corelight box  
[restore box](#action-restore-box) - Restore JSON config to the Corelight box  
[check results](#action-check-results) - Check the results for 202  

## action: 'test connectivity'
Validate the asset configuration for connectivity using the supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'input framework'
Update input framework

Type: **generic**  
Read only: **False**

Send data to the Corelight input framework\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**append** |  optional  | Is this an append to the input framework? Otherwise it will overwrite | boolean | 
**name** |  required  | Name of the list to upload/update | string | 
**fields** |  optional  | Tab\-seperated listed starts with \#fields separated by tabs | string | 
**input** |  required  | Information for the imput framework separated by tabs | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.append | boolean | 
action\_result\.parameter\.fields | string | 
action\_result\.parameter\.input | string | 
action\_result\.parameter\.name | string | 
action\_result\.data | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'intelligence update'
Update intel framework

Type: **generic**  
Read only: **False**

Send data to the Corelight intel framework\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ioc** |  required  | IP address or host name | string | 
**meta\_source** |  optional  | Source of the intel | string | 
**meta\_desc** |  optional  | Descrition of the intel | string | 
**meta\_url** |  optional  | URL of the intel | string | 
**is\_this\_a\_update** |  optional  | Is this an update? If not, it will overwrite the intel feed | boolean | 
**ipaddress** |  optional  | Is this an IP address? | boolean | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.ioc | string | 
action\_result\.parameter\.ipaddress | boolean | 
action\_result\.parameter\.is\_this\_a\_update | boolean | 
action\_result\.parameter\.meta\_desc | string | 
action\_result\.parameter\.meta\_source | string | 
action\_result\.parameter\.meta\_url | string | 
action\_result\.data | string | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get config'
Get Corelight full configuration

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.data\.\*\.authentication\.ldap\.enable | boolean | 
action\_result\.data\.\*\.bro\.analyzers\.smb\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.exclude | string | 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.filter | string | 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.mapping | string | 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.password | string | 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.prefix | string | 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.server | string |  `url` 
action\_result\.data\.\*\.bro\.export\.elasticsearch\.username | string |  `user name` 
action\_result\.data\.\*\.bro\.export\.files\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.files\.filter | string | 
action\_result\.data\.\*\.bro\.export\.files\.types\.archives | boolean | 
action\_result\.data\.\*\.bro\.export\.files\.types\.executables | boolean | 
action\_result\.data\.\*\.bro\.export\.files\.types\.flash | boolean | 
action\_result\.data\.\*\.bro\.export\.files\.types\.java | boolean | 
action\_result\.data\.\*\.bro\.export\.files\.types\.office\_documents | boolean | 
action\_result\.data\.\*\.bro\.export\.files\.types\.pdfs | boolean | 
action\_result\.data\.\*\.bro\.export\.json\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.json\.exclude | string | 
action\_result\.data\.\*\.bro\.export\.json\.filter | string | 
action\_result\.data\.\*\.bro\.export\.json\.server | string | 
action\_result\.data\.\*\.bro\.export\.kafka\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.logs\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.logs\.filter | string | 
action\_result\.data\.\*\.bro\.export\.logs\.format | string | 
action\_result\.data\.\*\.bro\.export\.logs\.interval | string | 
action\_result\.data\.\*\.bro\.export\.s3\.file\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.s3\.log\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.splunk\.enable | boolean | 
action\_result\.data\.\*\.bro\.export\.splunk\.exclude | string | 
action\_result\.data\.\*\.bro\.export\.splunk\.filter | string | 
action\_result\.data\.\*\.bro\.export\.splunk\.index | string | 
action\_result\.data\.\*\.bro\.export\.splunk\.servers | string | 
action\_result\.data\.\*\.bro\.export\.splunk\.servers\_enable | boolean | 
action\_result\.data\.\*\.bro\.export\.syslog\.enable | boolean | 
action\_result\.data\.\*\.bro\.input\.max\_total\_mb | numeric | 
action\_result\.data\.\*\.bro\.intel\.max\_indicators | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.bzar1\_epoch | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.bzar2\_epoch | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.bzar2\_limit | string | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.bzar3\_epoch | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.bzar3\_limit | string | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.file\_extract\_option | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.ignore\_orig\_h | string |  `ip` 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.bzar\.config\.ignore\_resp\_h | string |  `ip` 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.communityid\.config\.do\_base64 | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.communityid\.config\.seed | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.shunt\_burst\_conns | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.shunt\_ssl\_after\_negotiation | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.size\_threshold | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.speed\_threshold | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.corelight\_shunting\.loaded | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.config\.conn\.enable | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.config\.dns\.enable | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.config\.files\.enable | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.config\.http\.enable | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.config\.ssl\.enable | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.config\.stats\.enable | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.config\.weird\.enable | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.datared\.loaded | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.file\_sha256\.loaded | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.log\_add\_http\_post\_bodies\.config\.max\_body\_length | numeric | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.mac\_logging\.loaded | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.namecache\.config\.do\_mdns | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.namecache\.loaded | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.scan\_detection\.loaded | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.smtp\_links\.config\.max\_hostname\_repetitions | numeric |  `host name` 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.ssl\_expiring\_certs\.loaded | boolean | 
action\_result\.data\.\*\.bro\.pkgs\.corelight\.vlan\_logging\.loaded | boolean | 
action\_result\.data\.\*\.bro\.profiling\.sample\_rate | numeric | 
action\_result\.data\.\*\.bro\.site\.ignore\_bpf | string | 
action\_result\.data\.\*\.bro\.site\.local\_nets | string | 
action\_result\.data\.\*\.fleet\.enable | boolean | 
action\_result\.data\.\*\.metrics\.bro\.enable | boolean | 
action\_result\.data\.\*\.metrics\.bro\.interval | string | 
action\_result\.data\.\*\.metrics\.cloudwatch\.enable | boolean | 
action\_result\.data\.\*\.metrics\.graphite\.enable | boolean | 
action\_result\.data\.\*\.metrics\.syslog\.enable | boolean | 
action\_result\.data\.\*\.mode\.password\.strict | boolean | 
action\_result\.data\.\*\.network\.management\.ipv4\.dhcp\.enable | boolean | 
action\_result\.data\.\*\.network\.management\.ipv6\.auto\_dhcp\.enable | boolean | 
action\_result\.data\.\*\.network\.management\.ipv6\.enable | boolean | 
action\_result\.data\.\*\.network\.management\.ntp\.server | string | 
action\_result\.data\.\*\.network\.management\.proxy\.password | string | 
action\_result\.data\.\*\.network\.management\.proxy\.server | string | 
action\_result\.data\.\*\.network\.management\.proxy\.username | string |  `user name` 
action\_result\.data\.\*\.network\.management\.syslog\.server | string | 
action\_result\.data\.\*\.network\.monitor\.port0\.speed | string | 
action\_result\.data\.\*\.network\.monitor\.port1\.speed | string | 
action\_result\.data\.\*\.network\.monitor\.port2\.speed | string | 
action\_result\.data\.\*\.network\.monitor\.port3\.speed | string | 
action\_result\.data\.\*\.remote\.management | boolean | 
action\_result\.data\.\*\.remote\.share\.functional | boolean | 
action\_result\.data\.\*\.remote\.share\.health | boolean | 
action\_result\.data\.\*\.remote\.share\.performance | boolean | 
action\_result\.data\.\*\.security\.http\.enable | boolean | 
action\_result\.data\.\*\.security\.http\.networks | string | 
action\_result\.data\.\*\.security\.ssh\.enable | boolean | 
action\_result\.data\.\*\.security\.ssh\.networks | string | 
action\_result\.data\.\*\.security\.user\.admin\.password | string | 
action\_result\.data\.\*\.security\.user\.monitor\.password | string | 
action\_result\.data\.\*\.security\.user\.netconfig\.password | string | 
action\_result\.data\.\*\.system\.name | string | 
action\_result\.data\.\*\.system\.timezone | string | 
action\_result\.data\.\*\.updates\.all | boolean | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'list input'
List the different input frameworks

Type: **investigate**  
Read only: **True**

Get a list of the different input framework endpoints\.

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.data\.\*\.\*\.description | string | 
action\_result\.data\.\*\.\*\.entries | numeric | 
action\_result\.data\.\*\.\*\.name | string | 
action\_result\.data\.\*\.\*\.package | string | 
action\_result\.data\.\*\.\*\.size | numeric | 
action\_result\.data\.\*\.\*\.summary | string | 
action\_result\.data\.\*\.\*\.uploaded | boolean | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'list intelligence'
List the different input framework endpoints

Type: **investigate**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.data\.\*\.file\.content | string | 
action\_result\.data\.\*\.file\.name | string | 
action\_result\.data\.\*\.indicators | string | 
action\_result\.data\.\*\.last\-modified | numeric | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'backup box'
Create a JSON backup of the Corelight box

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**backup\_name** |  required  | Name of the backup | string | 
**bundle\_password** |  required  | Bundle password | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.backup\_name | string | 
action\_result\.parameter\.bundle\_password | string | 
action\_result\.data\.\*\.bro\.packages\.bundle | string | 
action\_result\.data\.\*\.bundle\-version | numeric | 
action\_result\.data\.\*\.keys\.exporter\.private | string | 
action\_result\.data\.\*\.keys\.exporter\.public | string | 
action\_result\.data\.\*\.keys\.host\.dsa\.private | string | 
action\_result\.data\.\*\.keys\.host\.dsa\.public | string | 
action\_result\.data\.\*\.keys\.host\.ecdsa\.private | string | 
action\_result\.data\.\*\.keys\.host\.ecdsa\.public | string | 
action\_result\.data\.\*\.keys\.host\.ed25519\.private | string | 
action\_result\.data\.\*\.keys\.host\.ed25519\.public | string | 
action\_result\.data\.\*\.keys\.host\.rsa\.private | string | 
action\_result\.data\.\*\.keys\.host\.rsa\.public | string | 
action\_result\.data\.\*\.name | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.bind\_dn | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.bind\_password | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.enable | boolean | 
action\_result\.data\.\*\.options\.authentication\.ldap\.encryption | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.group\_base\_dn | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.group\_read\_only | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.group\_read\_write | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.server | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.user\_base\_dn | string | 
action\_result\.data\.\*\.options\.authentication\.ldap\.user\_search\_template | string | 
action\_result\.data\.\*\.options\.bro\.analyzers\.smb\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.exclude | string | 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.filter | string | 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.mapping | string | 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.password | string | 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.prefix | string | 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.server | string |  `url` 
action\_result\.data\.\*\.options\.bro\.export\.elasticsearch\.username | string |  `user name` 
action\_result\.data\.\*\.options\.bro\.export\.files\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.files\.filter | string | 
action\_result\.data\.\*\.options\.bro\.export\.files\.types\.archives | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.files\.types\.executables | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.files\.types\.flash | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.files\.types\.java | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.files\.types\.office\_documents | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.files\.types\.pdfs | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.json\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.json\.exclude | string | 
action\_result\.data\.\*\.options\.bro\.export\.json\.filter | string | 
action\_result\.data\.\*\.options\.bro\.export\.json\.server | string | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.compression | string | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.exclude | string | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.filter | string | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.prefix | string | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.sasl\_password | string | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.sasl\_username | string |  `user name` 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.server | string | 
action\_result\.data\.\*\.options\.bro\.export\.kafka\.ssl\_enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.logs\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.logs\.exclude | string | 
action\_result\.data\.\*\.options\.bro\.export\.logs\.filter | string | 
action\_result\.data\.\*\.options\.bro\.export\.logs\.format | string | 
action\_result\.data\.\*\.options\.bro\.export\.logs\.interval | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.access\_key | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.file\.bucket | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.file\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.file\.prefix | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.log\.bucket | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.log\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.log\.exclude | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.log\.prefix | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.region | string | 
action\_result\.data\.\*\.options\.bro\.export\.s3\.secret\_access\_key | string | 
action\_result\.data\.\*\.options\.bro\.export\.sftp\.file\.path | string | 
action\_result\.data\.\*\.options\.bro\.export\.sftp\.file\.server | string | 
action\_result\.data\.\*\.options\.bro\.export\.sftp\.file\.user | string | 
action\_result\.data\.\*\.options\.bro\.export\.sftp\.log\.path | string | 
action\_result\.data\.\*\.options\.bro\.export\.sftp\.log\.server | string | 
action\_result\.data\.\*\.options\.bro\.export\.sftp\.log\.user | string | 
action\_result\.data\.\*\.options\.bro\.export\.splunk\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.splunk\.exclude | string | 
action\_result\.data\.\*\.options\.bro\.export\.splunk\.filter | string | 
action\_result\.data\.\*\.options\.bro\.export\.splunk\.index | string | 
action\_result\.data\.\*\.options\.bro\.export\.splunk\.servers | string | 
action\_result\.data\.\*\.options\.bro\.export\.splunk\.servers\_enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.syslog\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.export\.syslog\.exclude | string | 
action\_result\.data\.\*\.options\.bro\.export\.syslog\.facility | string | 
action\_result\.data\.\*\.options\.bro\.export\.syslog\.filter | string | 
action\_result\.data\.\*\.options\.bro\.export\.syslog\.format | string | 
action\_result\.data\.\*\.options\.bro\.export\.syslog\.server | string | 
action\_result\.data\.\*\.options\.bro\.export\.syslog\.severity | string | 
action\_result\.data\.\*\.options\.bro\.input\.max\_total\_mb | numeric | 
action\_result\.data\.\*\.options\.bro\.intel\.max\_indicators | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.bzar1\_epoch | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.bzar2\_epoch | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.bzar2\_limit | string | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.bzar3\_epoch | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.bzar3\_limit | string | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.file\_extract\_option | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.ignore\_orig\_h | string |  `ip` 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.bzar\.config\.ignore\_resp\_h | string |  `ip` 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.communityid\.config\.do\_base64 | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.communityid\.config\.seed | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.shunt\_burst\_conns | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.shunt\_ssl\_after\_negotiation | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.size\_threshold | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.corelight\_shunting\.config\.speed\_threshold | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.corelight\_shunting\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.config\.conn\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.config\.dns\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.config\.files\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.config\.http\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.config\.ssl\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.config\.stats\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.config\.weird\.enable | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.datared\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.file\_sha256\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.log\_add\_http\_post\_bodies\.config\.max\_body\_length | numeric | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.mac\_logging\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.namecache\.config\.do\_mdns | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.namecache\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.scan\_detection\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.smtp\_links\.config\.max\_hostname\_repetitions | numeric |  `host name` 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.ssl\_expiring\_certs\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.pkgs\.corelight\.vlan\_logging\.loaded | boolean | 
action\_result\.data\.\*\.options\.bro\.profiling\.sample\_rate | numeric | 
action\_result\.data\.\*\.options\.bro\.site\.ignore\_bpf | string | 
action\_result\.data\.\*\.options\.bro\.site\.local\_nets | string | 
action\_result\.data\.\*\.options\.fleet\.community\_string | string | 
action\_result\.data\.\*\.options\.fleet\.enable | boolean | 
action\_result\.data\.\*\.options\.fleet\.server | string | 
action\_result\.data\.\*\.options\.metrics\.bro\.enable | boolean | 
action\_result\.data\.\*\.options\.metrics\.bro\.interval | string | 
action\_result\.data\.\*\.options\.metrics\.cloudwatch\.aws\_access\_key\_id | string | 
action\_result\.data\.\*\.options\.metrics\.cloudwatch\.aws\_secret\_access\_key | string | 
action\_result\.data\.\*\.options\.metrics\.cloudwatch\.enable | boolean | 
action\_result\.data\.\*\.options\.metrics\.cloudwatch\.interval | string | 
action\_result\.data\.\*\.options\.metrics\.cloudwatch\.region | string | 
action\_result\.data\.\*\.options\.metrics\.graphite\.enable | boolean | 
action\_result\.data\.\*\.options\.metrics\.graphite\.interval | string | 
action\_result\.data\.\*\.options\.metrics\.graphite\.server | string | 
action\_result\.data\.\*\.options\.metrics\.syslog\.enable | boolean | 
action\_result\.data\.\*\.options\.metrics\.syslog\.interval | string | 
action\_result\.data\.\*\.options\.mode\.password\.strict | boolean | 
action\_result\.data\.\*\.options\.network\.management\.ipv4\.dhcp\.enable | boolean | 
action\_result\.data\.\*\.options\.network\.management\.ipv4\.dns\_search | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv4\.resolvers | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv4\.static\.address | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv4\.static\.gateway | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv4\.static\.subnet | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv6\.auto\_dhcp\.enable | boolean | 
action\_result\.data\.\*\.options\.network\.management\.ipv6\.dns\_search | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv6\.enable | boolean | 
action\_result\.data\.\*\.options\.network\.management\.ipv6\.resolvers | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv6\.static\.address | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv6\.static\.gateway | string | 
action\_result\.data\.\*\.options\.network\.management\.ipv6\.static\.prefix | string | 
action\_result\.data\.\*\.options\.network\.management\.ntp\.server | string | 
action\_result\.data\.\*\.options\.network\.management\.proxy\.password | string | 
action\_result\.data\.\*\.options\.network\.management\.proxy\.server | string | 
action\_result\.data\.\*\.options\.network\.management\.proxy\.username | string |  `user name` 
action\_result\.data\.\*\.options\.network\.management\.syslog\.server | string | 
action\_result\.data\.\*\.options\.network\.monitor\.port0\.speed | string | 
action\_result\.data\.\*\.options\.network\.monitor\.port1\.speed | string | 
action\_result\.data\.\*\.options\.network\.monitor\.port2\.speed | string | 
action\_result\.data\.\*\.options\.network\.monitor\.port3\.speed | string | 
action\_result\.data\.\*\.options\.remote\.management | boolean | 
action\_result\.data\.\*\.options\.remote\.share\.functional | boolean | 
action\_result\.data\.\*\.options\.remote\.share\.health | boolean | 
action\_result\.data\.\*\.options\.remote\.share\.performance | boolean | 
action\_result\.data\.\*\.options\.security\.http\.enable | boolean | 
action\_result\.data\.\*\.options\.security\.http\.networks | string | 
action\_result\.data\.\*\.options\.security\.ssh\.enable | boolean | 
action\_result\.data\.\*\.options\.security\.ssh\.networks | string | 
action\_result\.data\.\*\.options\.security\.user\.admin\.password | string | 
action\_result\.data\.\*\.options\.security\.user\.monitor\.password | string | 
action\_result\.data\.\*\.options\.security\.user\.netconfig\.password | string | 
action\_result\.data\.\*\.options\.system\.name | string | 
action\_result\.data\.\*\.options\.system\.timezone | string | 
action\_result\.data\.\*\.options\.updates\.all | boolean | 
action\_result\.data\.\*\.options\.updates\.no\_impact | boolean | 
action\_result\.data\.\*\.options\.updates\.reboot | boolean | 
action\_result\.data\.\*\.options\.updates\.service\_restart | boolean | 
action\_result\.data\.\*\.options\.updates\.visible\_change | boolean | 
action\_result\.data\.\*\.system\-info\.mac | string | 
action\_result\.data\.\*\.system\-info\.name | string | 
action\_result\.data\.\*\.system\-info\.time | string | 
action\_result\.data\.\*\.system\-info\.uid | string | 
action\_result\.data\.\*\.system\-info\.version | string | 
action\_result\.data\.\*\.vault\_id | string |  `sha1`  `vault id` 
action\_result\.summary\.name | string | 
action\_result\.summary\.vault\_id | string |  `sha1`  `vault id` 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'restore box'
Restore JSON config to the Corelight box

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vault\_id** |  required  | Vault ID of the file to be detonated | string |  `sha1`  `vault id` 
**bundle\_password** |  required  | Bundle password | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.bundle\_password | string | 
action\_result\.parameter\.vault\_id | string |  `sha1`  `vault id` 
action\_result\.data\.\*\.location | string |  `url` 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'check results'
Check the results for 202

Type: **generic**  
Read only: **True**

Check the results from restore and intel update\.

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**location** |  required  | The location for the 202 | string |  `url` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.status | string | 
action\_result\.parameter\.location | string |  `url` 
action\_result\.data\.\*\.message | string | 
action\_result\.data\.\*\.success | boolean | 
action\_result\.summary | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 