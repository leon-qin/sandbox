# Global Objects
## perkinelmer.ChemdrawwebManager
Singleton manager instance for managing CDD instances.
### attach(attachOptions) : void
Attaches a ChemDraw canvas to a DOM container specified by element object or the ID of the element.

###### Arguments
Name|Type|Description
----|----|----
attachOptions| [ChemDrawWebAttachOptions](#chemdrawwebattachoptions) (JSON object)|__required__.

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
### clear() : void
Attaches a ChemDraw canvas to a DOM container specified by element object or the ID of the element.

###### Arguments
Name|Type|Description
----|----|----
attachOptions| [ChemDrawWebAttachOptions](#chemdrawwebattachoptions) (JSON object)|__required__.

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

### loadCDXML(cdxml) : void
Attaches a ChemDraw canvas to a DOM container specified by element object or the ID of the element.

###### Arguments
Name|Type|Description
----|----|----
cdxml| [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)|__required__.

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

# JSON Structures
## ChemDrawWebAttachOptions
Name|Type|Description
----|----|----
id| [String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)|__required__.
callback| [chemdrawAttachedCallback](#chemdrawattachedcallbackcddvoid) (Function)

## ChemDrawWebConfig

# Callback Functions
## chemdrawAttachedCallback(cdd) : void
###### Arguments
Name|Type|Description
----|----|----
cdd|[ChemdrawWeb](#perkinelmerchemdrawweb)|the intance of attached ChemDraw

