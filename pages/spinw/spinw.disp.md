---
{title: spinw.disp method, link: spinw.disp, summary: prints information, keywords: sample,
  sidebar: sw_sidebar, permalink: spinw_disp, folder: spinw, mathjax: 'true'}

---
  
### Syntax
  
`{swdescr} = disp(obj)`
  
### Description
  
`{swdescr} = disp(obj)` generates text summary of a [spinw](spinw) object.
Calling it with output argument, it will generate a text version of the
internal data structure giving also the dimensions of the different
matrices.
  
### Examples
  
Here the internal data structure is generated:
 
```matlab
crystal = spinw
swFields = disp(crystal)
```
  
### Input Arguments
  
`obj`
: [spinw](spinw) object.
  
### Output Arguments
  
`swdescr`
: If output variable is given, the description of the `obj` object
  will be output into the `swdescr` variable, instead of being
  written onto the Command Window/file. Optional.
  
### See Also
  
[spinw](spinw)
 

{% include links.html %}
