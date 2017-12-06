# [Overzicht van Windows Management Framework (WMF)](README.md)

# [WMF 5.1](5.1/release-notes.md)
## [Nieuwe scenario's en onderdelen](5.1/scenarios-features.md)
### [Verbeteringen in Desired State Configuration (DSC)](5.1/DSC-improvements.md)
### [Verbeteringen in de PowerShell-console](5.1/console-improvements.md)
### [Verbeteringen in de PowerShell-engine](5.1/engine-improvements.md)
### [Verbeteringen in pakketbeheer](5.1/package-management-improvements.md)
### [Verbeteringen in JEA](5.1/jea-improvements.md)
### [Catalogus-cmdlets](5.1/catalog-cmdlets.md)
### [Fouten die zijn verholpen in WMF 5.1](5.1/bugfixes.md)
## [Installeren en configureren](5.1/install-configure.md)
## [Bekende problemen](5.1/known-issues.md)
## [Compatibiliteit](5.1/Compatibility.md)
## [Productcompatibiliteit](5.1/productincompat.md)

# [WMF 5.0](5.0/releasenotes.md)
## [Installatiedetails](5.0/requirements.md)
## [Bekende problemen en beperkingen](5.0/limitation_overview.md)
### [Bekende problemen voor Desired State Configuration (DSC)](5.0/limitation_dsc.md)
## [Productcompatibiliteitsstatus](5.0/productincompat.md)
## [Mogelijke scenario's met WMF 5.0]()
### [Just Enough Administration (JEA)](5.0/jea_overview.md)
#### [Een JEA-eindpunt maken en hier verbinding mee maken](5.0/jea_endpoint.md)
#### [Rapportage over JEA](5.0/jea_report.md)
### [Aangepaste typen maken met behulp van PowerShell-klassen](5.0/class_overview.md)
#### [Aangepaste typen definiëren](5.0/class_newtype.md)
#### [Basisklasse declareren](5.0/class_base.md)
#### [Geïmplementeerde interface declareren](5.0/class_interface.md)
#### [Klasseconstructor oproepbasis](5.0/class_baseconstructor.md)
#### [Klassemethode oproepbasis](5.0/class_basemethod.md)
### [Verbeteringen in foutopsporing voor PowerShell-scripts](5.0/debug_overview.md)
### [Verbeteringen in Desired State Configuration (DSC)](5.0/dsc_improvements.md)
#### [Configuraties]()
##### [Afhankelijkheden van meerdere knooppunten opgeven](5.0/dsc_waitfor.md)
##### [Versleutelde MOF's](5.0/dsc_encryptedmof.md)
##### [Help-ondersteuning voor DSC-configuratie](5.0/dsc_confighelp.md)
##### [Verbeteringen ontwerpen met behulp van PowerShell ISE](5.0/dsc_authoring.md)
##### [Mogelijkheid van identieke dubbele resources in een configuratie](5.0/dsc_identicalduplicate.md)
##### [Sleutelwoorden voor Import-DscResource bieden ondersteuning voor de parameter -ModuleVersion](5.0/dsc_importdscresource.md)
##### [WOW64-ondersteuning voor configuratiesleutelwoord](5.0/dsc_wow64.md)
#### [Resources]()
##### [DSC-resources op basis van een klasse](5.0/dsc_classbasedresource.md)
##### [Foutopsporing voor DSC-resourcescripts](5.0/dsc_resourcedebugging.md)
##### [Automatische RunAs-ondersteuning voor DSC-resources](5.0/dsc_runas.md)
##### [Ondersteuning voor zij aan zij versiebeheer voor DSC-resources](5.0/dsc_sxsresource.md)
##### [Nieuwe in-vak-resources](5.0/dsc_newresources.md)
#### [Local Configuration Manager]()
##### [Knooppunt met meerdere configuratiefragmenten configureren](5.0/dsc_partialconfig.md)
###### [Ondersteuning voor gemengde RefreshModes](5.0/dsc_partialconfig_mixedmode.md)
##### [DSC-engine met nieuw kenmerk configureren](5.0/dsc_metaconfiguration.md)
##### [Gedetailleerde informatie over LCM-status](5.0/dsc_lcmstate.md)
##### [Frequenties voor RefreshMode en ConfigurationMode hoeven geen veelvoud van elkaar te zijn](5.0/dsc_freqnomultiple.md)
##### [Aanvullende waarde voor eigenschap RefreshMode](5.0/dsc_refreshmode.md)
#### [Cmdlets]()
##### [Meer informatie over de configuratiestatus](5.0/dsc_getconfigurationstatus.md)
##### [De cmdlet Test-DscConfiguration ondersteunt verwijzingsconfiguraties](5.0/dsc_testconfiguration.md)
##### [Directe toegang tot DSC-resourcemethoden](5.0/dsc_directaccess.md)
##### [Configuratiedocument leveren zonder toe te passen](5.0/dsc_publishconfig.md)
##### [DSC-documenten verwijderen](5.0/dsc_removeconfigdoc.md)
##### [Uniforme en consistente status en statusweergave](5.0/dsc_statestatus.md)
##### [Cmdlet Set-DscLocalConfigurationManager biedt ondersteuning voor parameter -Force](5.0/dsc_setdsclcm.md)
#### [Pull-modus]()
##### [On-demand PULL van DSC-configuraties](5.0/dsc_updateconfig.md)
##### [Scheiding van knooppunt- en configuratie-id's](5.0/dsc_nodeid.md)
##### [Scheiding van de opslagplaatsen voor configuraties, resources en rapporten](5.0/dsc_repository.md)
##### [Configuratiestatus rapporteren naar centrale locatie](5.0/dsc_reporting.md)
### [PowerShell-gebruik controleren met behulp van transcriptie en logboekregistratie](5.0/audit_overview.md)
#### [Verbeterde transcriptiemogelijkheden](5.0/audit_transcript.md)
#### [Tracering en logboekregistratie voor scripts](5.0/audit_script.md)
#### [Cmdlets voor Cryptographic Message-syntaxis (CMS)](5.0/audit_cms.md)
### [Detecteren, installeren en inventariseren van software met PackageManagement](5.0/oneget_overview.md)
#### [PackageManagement-cmdlets](5.0/oneget_cmdlets.md)
### [Detecteren, installeren en inventariseren van PowerShell-modules met PowerShellGet](5.0/psget_module_overview.md)
#### [Een PowerShell-opslagplaats registreren](5.0/psget_psrepository.md)
#### [Side-by-Side-versie-ondersteuning op PowerShell 5.0 of hoger](5.0/psget_modulesxsinstall.md)
#### [Installatie van module-afhankelijkheden](5.0/psget_moduledependency.md)
#### [PowerShellGet-cmdlets voor modulebeheer](5.0/psget_modulecmdlets.md)
### [Detecteren, installeren en beheren van PwerShell-scripts met PowerShellGet](5.0/psget_script_overview.md)
#### [PowerShellGet-cmdlets voor scriptbeheer](5.0/psget_scriptcmdlets.md)
### [Nieuwe en bijgewerkte cmdlets op basis van feedback van de community](5.0/feedback_cmdlets.md)
#### [Symbolische koppelingen met Item-cmdlets](5.0/feedback_symbolic.md)
#### [Archief-cmdlets](5.0/feedback_archive.md)
#### [Klembord-cmdlets](5.0/feedback_clipboard.md)
#### [Convert-String](5.0/feedback_convertstring.md)
#### [Gestructureerd objecten buiten tekenreeks uitpakken en parseren](5.0/feedback_convertfromString.md)
#### [Format-Hex](5.0/feedback_formathex.md)
#### [Parameter NoNewLine](5.0/feedback_nonewline.md)
#### [New-TemporaryFile](5.0/feedback_tempfile.md)
#### [New-Guid](5.0/feedback_newguid.md)
#### [Get-ChildItem heeft parameter -Depth](5.0/feedback_getchilditem.md)
#### [Updates voor FileInfo-object](5.0/feedback_fileinfo.md)
#### [Module-ondersteuning voor declareren versiebereiken (1.*, enzovoort)](5.0/feedback_moduleversionranges.md)
### [Gegevensstroom](5.0/informationstream_overview.md)
### [PowerShell-cmdlets genereren op basis van OData-eindpunt](5.0/odata_overview.md)
### [Beheer van netwerkswitch met PowerShell](5.0/networkswitch_overview.md)
### [Registratie van software-inventaris (SIL)](5.0/sil_overview.md)