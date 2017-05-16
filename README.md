# ChemDraw Direct API References

## Global Objects
### perkinelmer.ChemdrawwebManager
Singleton manager instance for managing CDD instances.

#### attach(attachOptions) : void
> _TODO: Change the type of AttachRequest to AttachOptions_

> _TODO: Change the parameter name to options_

Attaches a ChemDraw canvas to a DOM container specified by element object or the ID of the element.

##### Arguments
Name|Type|Description
----|----|----
attachOptions| [ChemDrawWebAttachOptions](#perkinelmer.ChemDrawWebAttachOptions) (JSON object)|__required__.

##### Returns
void

##### Example
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

## Classes
### perkinelmer.ChemdrawWeb

## JSON Structures
### perkinelmer.ChemDrawWebAttachOptions
### perkinelmer.ChemdrawWebConfig
