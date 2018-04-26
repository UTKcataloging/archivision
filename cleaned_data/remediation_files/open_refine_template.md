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
<identifier type="Vendor ID">{{cells["VendorCatalogNum"].value}}</identifier>
<titleInfo><title>{{cells['PreferredTitle'].value}}</title></titleInfo>
<abstract>{{cells['ViewDescription'].value}}</abstract>
{{if(isBlank(cells['WorkDescription'].value), '', '<abstract>' + cells['WorkDescription'].value + '</abstract>')}}
<originInfo><publisher>Archivision, Inc.</publisher></originInfo>
<physicalDescription><form authority="aat" valueURI="http://vocab.getty.edu/aat/300046300">photographs</form><digitalOrigin>reformatted digital</digitalOrigin>
{{if(isBlank(cells['Dimensions'].value), '', '<extent>' + cells['Dimensions'].value + '</extent>')}}
</physicalDescription>
<name><namePart>Gilchrist, Scott</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/pht">Photographer</roleTerm></role></name>
{{if(isBlank(cells['CurrentLocation'].value), '', '<subject><geographic authority="geonames">' + cells['CurrentLocation'].value + '</geographic></subject>')}}
<relatedItem type="otherVersion"><titleInfo><title>{{cells['PreferredTitle'].value}}</title></titleInfo>
<identifier type="Work ID">{{cells["work_id"].value}}</identifier>
{{if(isBlank(cells['Artist1_SortName'].value), '', '<name' + if(isBlank(cells['Artist1_Corporate'].value), '', ' type="personal"') + if(isBlank(cells['Artist1_Vocab'].value), '', ' authority="' + cells['Artist1_Vocab'].value + '"') + if(isBlank(cells['Artist1_RefID'].value), '', ' valueURI="' + cells['Artist1_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist1_SortName'].value + '</namePart><displayForm>' + cells['Artist1_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist1_Lifetime'].value), '', '<namePart type="date">' + cells['Artist1_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist1_Nationality'].value), '', '<description>' + cells['Artist1_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role_URI'].value + '">' + cells['Artist1_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist2_SortName'].value), '', '<name' + if(isBlank(cells['Artist2_Corporate'].value), '', ' type="personal"') + if(isBlank(cells['Artist2_Vocab'].value), '', ' authority="' + cells['Artist2_Vocab'].value + '"') + if(isBlank(cells['Artist2_RefID'].value), '', ' valueURI="' + cells['Artist2_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist2_SortName'].value + '</namePart><displayForm>' + cells['Artist2_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist2_Lifetime'].value), '', '<namePart type="date">' + cells['Artist2_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist2_Nationality'].value), '', '<description>' + cells['Artist2_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role2_URI'].value + '">' + cells['Artist2_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist3_SortName'].value), '', '<name' + if(isBlank(cells['Artist3_Corporate'].value), '', ' type="personal"') + if(isBlank(cells['Artist3_Vocab'].value), '', ' authority="' + cells['Artist3_Vocab'].value + '"') + if(isBlank(cells['Artist3_RefID'].value), '', ' valueURI="' + cells['Artist3_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist3_SortName'].value + '</namePart><displayForm>' + cells['Artist3_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist3_Lifetime'].value), '', '<namePart type="date">' + cells['Artist3_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist3_Nationality'].value), '', '<description>' + cells['Artist3_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role3_URI'].value + '">' + cells['Artist3_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist4_SortName'].value), '', '<name' + if(isBlank(cells['Artist4_Corporate'].value), '', ' type="personal"') + if(isBlank(cells['Artist4_Vocab'].value), '', ' authority="' + cells['Artist4_Vocab'].value + '"') + if(isBlank(cells['Artist4_RefID'].value), '', ' valueURI="' + cells['Artist4_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist4_SortName'].value + '</namePart><displayForm>' + cells['Artist4_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist4_Lifetime'].value), '', '<namePart type="date">' + cells['Artist4_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist4_Nationality'].value), '', '<description>' + cells['Artist4_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role4_URI'].value + '">' + cells['Artist4_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['Artist5_SortName'].value), '', '<name' + if(isBlank(cells['Artist5_Corporate'].value), '', ' type="personal"') + if(isBlank(cells['Artist5_Vocab'].value), '', ' authority="' + cells['Artist5_Vocab'].value + '"') + if(isBlank(cells['Artist5_RefID'].value), '', ' valueURI="' + cells['Artist5_RefID'].value + '"') + '>' + '<namePart>' + cells['Artist5_SortName'].value + '</namePart><displayForm>' + cells['Artist5_DisplayName'].value + '</displayForm>' + if(isBlank(cells['Artist5_Lifetime'].value), '', '<namePart type="date">' + cells['Artist5_Lifetime'].value + '</namePart>') + if(isBlank(cells['Artist5_Nationality'].value), '', '<description>' + cells['Artist5_Nationality'].value + '</description>') + '<role><roleTerm type="text" authority="marcrelator" valueURI="' + cells['Role5_URI'].value + '">' + cells['Artist5_Role'].value + '</roleTerm></role>' + '</name>')}}
{{if(isBlank(cells['WorkDateDisplay'].value), '', '<originInfo><dateCreated>' + cells['WorkDateDisplay'].value + '</dateCreated></originInfo>')}}
<physicalDescription><form>{{cells['Classification'].value}}</form>
{{if(isBlank(cells['WorkType'].value), '', '<form authority="aat" valueURI="' + cells['WorkType_URI'].value + '">' + cells['WorkType'].value + '</form>')}}
</physicalDescription>
</relatedItem>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>Archivision</title></titleInfo></relatedItem>
<recordInfo><recordContentSource>Archivision, Inc.</recordContentSource><languageOfCataloging><languageTerm type="code" authority="iso639-2b">eng</languageTerm></languageOfCataloging></recordInfo>
<typeOfResource>still image</typeOfResource>
<accessCondition type="use and reproduction" xlink:href="http://rightsstatements.org/vocab/InC/1.0/">In Copyright</accessCondition>
<name><namePart>Gilchrist, Scott</namePart><role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/pht">Photographer</roleTerm></role></name>
</mods>

```

#### Suffix

```
</modsCollection>
```