llllll-----
# Global Objects
## perkinelmer.ChemdrawWebManager
Singleton manager instance for managing CDD instances.
### attach(options) : void
Attaches a ChemDraw canvas to a DOM container specified by element object or the ID of the element.
###### Parameters
|Name|Type|Description|
|----|----|----|
|options|[AttachRequest](#attachrequest)|options to initialize ChemDraw|
###### Returns
void
###### Example
```javascript
function chemDrawAttached(cdd) {
  // Implement your own logic here.
  cdd.loadCDXML("CDXML content...");
}

perkinelmer.ChemdrawwebManager.attach({
  id: "cddContainer",
  callback: chemDrawAttached
})
```
# Classes
## perkinelmer.ChemdrawWeb
This declaration is used by ChemdrawWebManager and unit test.
### clear() : void
TODO
###### Parameters
None
###### Returns
void
### fitToContainer() : void
TODO
###### Parameters
None
###### Returns
void
### getCDXML() : string
TODO
###### Parameters
None
###### Returns
[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string)
### getVersion() : string
TODO
###### Parameters
None
###### Returns
[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string)
### loadCDXML(cdxml) : void
Loads the specified CDXML text to ChemDraw.
###### Parameters
|Name|Type|Description|
|----|----|----|
|cdxml|[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string)|the CDXML text|
###### Returns
void
###### Throws
err CDXML is invalid

### loadConfig(config) : void
TODO
###### Parameters
|Name|Type|Description|
|----|----|----|
|config|[JSON](#json)|TODO|
###### Returns
void
### setViewOnly(viewOnly) : void
TODO
###### Parameters
|Name|Type|Description|
|----|----|----|
|viewOnly|[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/boolean)|TODO|
###### Returns
void
### shrinkToFit() : void
TODO
###### Parameters
None
###### Returns
void
# JSON Structures
## AttachRequest
Stores the options data to initialize a ChemDraw canvas.
###### Properties
|Name|Type|Description|
|----|----|----|
|callback|[AttachCallback](#attachcallback)|__Optional__ |
|config|[Object](#object)|__Optional__ |
|configUrl|[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string)|__Optional__ |
|element|[HTMLElement](#htmlelement)|__Optional__ |
|id|[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string)|__Optional__ |
|license|[Object](#object)|__Optional__ |
|licenseUrl|[string](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string)|__Optional__ |
|preservePageInfo|[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/boolean)|__Optional__ |
|viewonly|[boolean](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/boolean)|__Optional__ |
# Callbacks
## AttachCallback
TODO
###### Parameters
|Name|Type|Description|
|----|----|----|
|cdd|[ChemdrawWeb](#chemdrawweb)|TODO|
