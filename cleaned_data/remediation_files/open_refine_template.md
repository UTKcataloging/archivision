# Open Refine Template for Archivision

## Template

#### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```
####Body

```
<mods>
<identifier type="filename">{{cells["CatalogNum"].value}}</identifier>
<identifier type="Work ID">{{cells["work_id"].value}}</identifier>
<identifier type="Vendor ID">{{cells["VendorCatalogNum"].value}}</identifier>
{{if(isBlank(cells['RepositoryID'].value), '', '<identifier type="acquisition">' + cells['RepositoryID'].value + '</identifier>')}}
<titleInfo><title>{{cells['PreferredTitle'].value}}</title></titleInfo>
<abstract>{{cells['ViewDescription'].value}}</abstract>
{{if(isBlank(cells['WorkDescription'].value), '', '<abstract>' + cells['WorkDescription'].value + '</abstract>')}}
<originInfo><publisher>Archivision, Inc.</publisher>
{{if(isBlank(cells['date_note'].value), '', '<dateCreated>' + cells['date_note'].value + '</dateCreated>')}} 
{{if(isBlank(cells['date_edtf'].value), '', '<dateCreated encoding="edtf" keyDate="yes">' + cells['date_edtf'].value + '</dateCreated>')}} {{if(isBlank(cells['date_edtf_start'].value), '', '<dateCreated encoding="edtf" point="start" keyDate="yes"' + if(isBlank(cells['date_qualifier'].value), '', ' qualifier="' + cells['date_qualifier'].value + '"') + '>' + cells['date_edtf_start'].value + '</dateCreated><dateCreated encoding="edtf" point="end"' + if(isBlank(cells['date_qualifier'].value), '', ' qualifier="' + cells['date_qualifier'].value + '"') + '>' + cells['date_edtf_end'].value + '</dateCreated>')}}
{{if(isBlank(cells['dateOther_edtf'].value), '', '<dateOther encoding="edtf">' + cells['dateOther_edtf'].value + '</dateOther>')}}
{{if(isBlank(cells['dateOther_edtf_start'].value), '', '<dateOther  encoding="edtf" point="start">' + cells['dateOther_edtf_start'].value + '</dateOther><dateOther encoding="edtf" point="end">' + cells['dateOther_edtf_end'].value + '</dateOther>')}}
</originInfo>
<physicalDescription>
{{if(isBlank(cells['WorkType'].value), '', '<form authority="aat" valueURI="' + cells['WorkType_URI'].value + '">' + cells['WorkType'].value + '</form>')}}
{{if(isBlank(cells['MaterialDisplay'].value), '', '<form type="material">' + cells['MaterialDisplay'].value + '</form>')}}
{{if(isBlank(cells['Dimensions'].value), '', '<extent>' + cells['Dimensions'].value + '</extent>')}}
<digitalOrigin>reformatted digital</digitalOrigin></physicalDescription>
{{if(isBlank(cells['StylePeriod'].value), '', '<genre authority="aat" valueURI="' + cells['StylePeriod_aat_URI'].value + '">' + cells['StylePeriod'].value + '</genre>')}}
{{if(isBlank(cells['StylePeriod_LC'].value), '', '<genre authority="lcsh" valueURI="' + cells['StylePeriod_LC_URI'].value + '">' + cells['StylePeriod_LC'].value + '</genre>')}}
{{if(isBlank(cells['Artist1_Gender'].value), '', '<subject authority="lcsh" valueURI="' + cells['GenderSubject_URI'].value + '"><topic>' + cells['Artist1_Gender'].value + '</topic></subject>')}}
{{if(isBlank(cells['Artist2_Gender'].value), '', '<subject authority="lcsh" valueURI="' + cells['GenderSubject2_URI'].value + '"><topic>' + cells['Artist2_Gender'].value + '</topic></subject>')}}
{{if(isBlank(cells['CurrentLocation'].value), '', '<subject><geographic authority="geonames" valueURI="' + cells['Location_URI_Geo'].value + '">' + cells['CurrentLocation'].value + '</geographic><cartographics><coordinates>' + cells['Coordinates'].value + '</coordinates></cartographics></subject>')}}
{{if(isBlank(cells['Artist1_SortName'].value), '', '<name type="' + cells['Artist1_Corporate'].value + '"' + if(isBlank(cells['Artist1_Vocab'].value), '', ' authority="' + cells['Artist1_Vocab'].value + '"') + if(isBlank(cells['Artist1_RefID'].value), '', ' valueURI="' + cells['Artist1_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist1_SortName'].value + '</namePart><displayForm>' + cells['Artist1_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist1_Lifetime'].value), '', '<namePart type="date">' + cells['Artist1_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist1_Nationality'].value), '', '<description>' + cells['Artist1_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role_URI'].value + '">' + cells['Artist1_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist2_SortName'].value), '', '<name type="' + cells['Artist2_Corporate'].value + '"' + if(isBlank(cells['Artist2_Vocab'].value), '', ' authority="' + cells['Artist2_Vocab'].value + '"') + if(isBlank(cells['Artist2_RefID'].value), '', ' valueURI="' + cells['Artist2_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist2_SortName'].value + '</namePart><displayForm>' + cells['Artist2_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist2_Lifetime'].value), '', '<namePart type="date">' + cells['Artist2_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist2_Nationality'].value), '', '<description>' + cells['Artist2_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role2_URI'].value + '">' + cells['Artist2_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist3_SortName'].value), '', '<name type="' + if(isBlank(cells['Artist3_Corporate'].value), '', cells['Artist3_Corporate'].value + '"') + if(isBlank(cells['Artist3_Vocab'].value), '', ' authority="' + cells['Artist3_Vocab'].value + '"') + if(isBlank(cells['Artist3_RefID'].value), '', ' valueURI="' + cells['Artist3_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist3_SortName'].value + '</namePart><displayForm>' + cells['Artist3_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist3_Lifetime'].value), '', '<namePart type="date">' + cells['Artist3_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist3_Nationality'].value), '', '<description>' + cells['Artist3_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role3_URI'].value + '">' + cells['Artist3_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist4_SortName'].value), '', '<name' + if(isBlank(cells['Artist4_Corporate'].value), '', ' type="personal"') + if(isBlank(cells['Artist4_Vocab'].value), '', ' authority="' + cells['Artist4_Vocab'].value + '"') + if(isBlank(cells['Artist4_RefID'].value), '', ' valueURI="' + cells['Artist4_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist4_SortName'].value + '</namePart><displayForm>' + cells['Artist4_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist4_Lifetime'].value), '', '<namePart type="date">' + cells['Artist4_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist4_Nationality'].value), '', '<description>' + cells['Artist4_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role4_URI'].value + '">' + cells['Artist4_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist5_SortName'].value), '', '<name' + if(isBlank(cells['Artist5_Corporate'].value), '', ' type="personal"') + if(isBlank(cells['Artist5_Vocab'].value), '', ' authority="' + cells['Artist5_Vocab'].value + '"') + if(isBlank(cells['Artist5_RefID'].value), '', ' valueURI="' + cells['Artist5_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist5_SortName'].value + '</namePart><displayForm>' + cells['Artist5_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist5_Lifetime'].value), '', '<namePart type="date">' + cells['Artist5_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist5_Nationality'].value), '', '<description>' + cells['Artist5_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role5_URI'].value + '">' + cells['Artist5_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['MuseumName'].value), '', '<location><physicalLocation>' + cells['MuseumName'].value + '</physicalLocation></location>')}}
<relatedItem displayLabel="Project" type="host"><titleInfo><title>Archivision</title></titleInfo></relatedItem>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource><languageOfCataloging><languageTerm type="code" authority="iso639-2b">eng</languageTerm></languageOfCataloging></recordInfo>
<typeOfResource>still image</typeOfResource>
<accessCondition type="use and reproduction" xlink:href="http://rightsstatements.org/vocab/InC/1.0/">In Copyright</accessCondition>
<name><namePart>Gilchrist, Scott</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/cph">Copyright holder</roleTerm></role></name>
</mods>

```

#### Suffix

```
</modsCollection>
```